---
title: 'Início Rápido: definir e recuperar um segredo do Azure Key Vault | Microsoft Docs'
description: 'Início Rápido: definir e recuperar um segredo do Azure Key Vault'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages, keyvault-platforms
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8b758274203748bb6e04c03dec5de38fb77947b4
ms.sourcegitcommit: b0105f322f91bb4dbde47f6da35b3c12271d5b03
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43239573"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a>Início Rápido: definir e recuperar um segredo do Azure Key Vault

Este início rápido mostra como armazenar um segredo no Key Vault e como recuperá-lo usando um aplicativo Web. Para ver o valor do segredo, seria necessário executar isso no Azure. O início rápido usa Node.js e MSIs (identidades de serviço gerenciadas)

> [!div class="checklist"]
> * Crie um Key Vault.
> * Armazene um segredo no Key Vault.
> * Recupere um segredo do Key Vault.
> * Crie um aplicativo Web do Azure.
> * [Habilitar identidades de serviço gerenciadas](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).
> * Conceder as permissões necessárias para o aplicativo Web ler dados do Key Vault.

Antes de prosseguir, familiarize-se com os [conceitos básicos](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).

>[!NOTE]
Para entender por que o tutorial abaixo é a melhor prática, precisamos entender alguns conceitos. O Key Vault é um repositório central para armazenar segredos de forma programática. Mas, para fazer isso, os aplicativos/usuários precisam autenticar primeiro o Key Vault, ou seja, apresentar um segredo. Para seguir as melhores práticas de segurança, esse primeiro segredo também deve ser alterado periodicamente. Mas com a [Identidade de Serviço Gerenciada](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview), os aplicativos executados no Azure recebem uma identidade gerenciada automaticamente pelo Azure. Isso ajuda a resolver o **Problema de Introdução do Segredo**, no qual os usuários/aplicativos podem seguir as melhores práticas e não precisam se preocupar em alterar o primeiro segredo

## <a name="prerequisites"></a>Pré-requisitos

::: zone pivot="nodejs"
* [Node JS](https://nodejs.org/en/) ::: zone-end

::: zone pivot="dotnet, windows"
* [Visual Studio 2017 versão 15.7.3 ou posterior](https://www.microsoft.com/net/download/windows) com as seguintes cargas de trabalho:
  * Desenvolvimento Web e ASP.NET
  * Desenvolvimento multiplataforma com o .NET Core
* [SDK do .NET Core 2.1 ou posterior](https://www.microsoft.com/net/download/windows) :::zone-end

::: zone pivot="dotnet, mac"
* Confira as [Novidades do Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/).
:::zone-end

* Git ([download](https://git-scm.com/downloads)).
* Uma assinatura do Azure. Se você não tiver uma assinatura do Azure, crie uma [conta gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) antes de começar.
* [CLI do Azure](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) versão 2.0.4 ou posterior. Disponível para Windows, Mac e Linux.

## <a name="login-to-azure"></a>Logon no Azure

Para fazer logon no Azure usando a CLI, você pode digitar:

```azurecli
az login
```

## <a name="create-resource-group"></a>Criar grupo de recursos

Crie um grupo de recursos com o comando [az group create](/cli/azure/group#az-group-create). Um grupo de recursos do Azure é um contêiner lógico no qual os recursos do Azure são implantados e gerenciados.

Selecione um nome para o grupo de recursos e preencha o espaço reservado.
O exemplo a seguir cria um grupo de recursos denominado *<YourResourceGroupName>* no local *eastus*.

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

O grupo de recursos que você acabou de criar é usado ao longo deste tutorial.

## <a name="create-an-azure-key-vault"></a>Criar um Azure Key Vault

Em seguida, crie um Key Vault no grupo de recursos criado na etapa anterior. Embora “ContosoKeyVault” seja utilizado como o nome do Key Vault ao longo deste artigo, você deverá usar um nome exclusivo. Forneça as seguintes informações:

* Nome do cofre: **selecione um nome para o Key Vault aqui**.
* Nome do grupo de recursos: **selecione um nome para o grupo de recursos aqui**.
* O local: **Leste dos EUA**.

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

Nesse ponto, sua conta do Azure é a única autorizada a executar qualquer operação nesse novo cofre.

## <a name="add-a-secret-to-key-vault"></a>Adicionar um segredo ao Key Vault

Estamos adicionando um segredo para ajudar a ilustrar como isso funciona. Você pode estar armazenando uma cadeia de conexão SQL ou qualquer outra informação que precise manter com segurança, mas disponibilizar para o aplicativo. Neste tutorial, a senha será chamada **AppSecret** e armazenará o valor de **MySecret** nela.

Digite os comandos abaixo para criar um segredo no Key Vault chamado **AppSecret** que armazenará o valor **MySecret**:

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

Para exibir o valor contido no segredo como texto sem formatação:

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

Este comando mostra as informações secretas, incluindo o URI. Após concluir essas etapas, você deverá ter um URI para um segredo em um Azure Key Vault. Anote essas informações. Ela serão necessárias em uma etapa posterior.

## <a name="clone-the-repo"></a>Clonar o repositório

Clone o repositório a fim de fazer uma cópia local para que você possa editar a fonte executando o seguinte comando:

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a>Instalar dependências

Vamos instalar as dependências aqui. Execute os comandos a seguir cd key-vault-node-quickstart npm install

Este projeto usou dois módulos de nó:

* [ms-rest-azure](https://www.npmjs.com/package/ms-rest-azure) 
* [azure-keyvault](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a>Publicar o aplicativo Web no Azure

Abaixo estão as etapas que precisamos realizar

* A 1ª etapa é criar um Plano do [Serviço de Aplicativo do Azure](https://azure.microsoft.com/services/app-service/). Você pode armazenar vários aplicativos Web nesse plano.

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* Em seguida, criamos um aplicativo Web. No exemplo a seguir, substitua <nome_do_aplicativo> por um nome de aplicativo exclusivo globalmente (os caracteres válidos são a-z, 0-9 e -). O tempo de execução é definido como NODE|6.9. Para ver todos os tempos de execução com suporte, execute az webapp list-runtimes

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    Quando o aplicativo Web for criado, a CLI do Azure mostrará um resultado semelhante ao seguinte exemplo:

    ```json
    {
      "availabilityState": "Normal",
      "clientAffinityEnabled": true,
      "clientCertEnabled": false,
      "cloningInfo": null,
      "containerSize": 0,
      "dailyMemoryTimeQuota": 0,
      "defaultHostName": "<app_name>.azurewebsites.net",
      "enabled": true,
      "deploymentLocalGitUrl": "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git"
      < JSON data removed for brevity. >
    }
    ```
    Navegue até o aplicativo Web criado recentemente e verá um aplicativo Web funcionando. Substitua <nome_do_aplicativo> por um nome exclusivo do aplicativo.

    ```text
    http://<app name>.azurewebsites.net
    ```
    O comando acima também cria um aplicativo habilitado para Git que permite a implantação no Azure do git local. 
    O git local está configurado com a URL 'https://<username>@<nome_do_aplicativo>.scm.azurewebsites.net/<nome_do_aplicativo>.git'

* Criar um usuário de implantação após a conclusão do comando anterior; você pode adicionar um Azure remoto ao repositório Git local. Substitua <url> pela URL do Git remoto que você obteve de Habilitar o Git para seu aplicativo.

    ```bash
    git remote add azure <url>
    ```
::: zone-end

::: zone pivot="dotnet"

## <a name="open-and-edit-the-solution"></a>Abrir e editar a solução

Edite o arquivo program.cs para executar o exemplo com o nome específico de seu cofre de chaves:

1. Navegue até a pasta key-vault-dotnet-core-quickstart.
2. Abra o arquivo key-vault-dotnet-core-quickstart.sln no Visual Studio 2017.
3. Abra o arquivo Program.cs e atualize o espaço reservado *YourKeyVaultName* com o nome do cofre de chaves criado anteriormente.

A solução usa as bibliotecas NuGet [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) e [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).

## <a name="run-the-app"></a>Executar o aplicativo

No menu principal do Visual Studio 2017, selecione **Depurar** > **Iniciar** sem depuração. Quando o navegador aparecer, acesse a página **Sobre**. O valor para **AppSecret** é exibido.

## <a name="publish-the-web-application-to-azure"></a>Publicar o aplicativo Web no Azure

Publique esse aplicativo do Azure para vê-lo ao vivo como um aplicativo Web e verifique se você pode buscar o valor do segredo:

1. No Visual Studio, selecione o projeto **key-vault-dotnet-core-quickstart**.
2. Selecione **Publicar** > **Iniciar**.
3. Crie um novo **Serviço de Aplicativo** e selecione **Publicar**.
4. Altere o nome do aplicativo para **keyvaultdotnetcorequickstart**.
5. Selecione **Criar**.

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]

::: zone-end

## <a name="enable-managed-service-identities"></a>Habilitar identidades de serviço gerenciadas

O Azure Key Vault fornece uma maneira de armazenar com segurança as credenciais e outras chaves e segredos, mas seu código precisa autenticar no Azure Key Vault para recuperá-los. A Identidade de Serviço Gerenciada facilita fornecendo aos serviços do Azure uma identidade gerenciada automaticamente no Azure AD (Azure Active Directory). Você pode usar essa identidade para autenticar em qualquer serviço que dá suporte à autenticação do Azure AD, incluindo o Key Vault, sem ter que todas as credenciais no seu código.

1. Volte para a CLI do Azure.
2. Execute o comando assign-identity para criar a identidade para esse aplicativo:

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
>O comando nesse procedimento é o equivalente de ir para o portal e alternar **Identidade de serviço gerenciada** para **On** nas propriedades do aplicativo Web.

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a>Atribuir permissões ao aplicativo para ler segredos do Key Vault

Anote a saída quando você publicar o aplicativo no Azure. Ela deve ter o seguinte formato:

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

Em seguida, execute o comando usando o nome do seu Key Vault e o valor do **PrincipalId**:

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a>Implantar o aplicativo Node no Azure e recuperar o valor do segredo

Agora está tudo pronto. Execute o seguinte comando para implantar o aplicativo no Azure

```bash
git push azure master
```

Depois de fazer isso, quando você navegar por https://<nome_do_aplicativo>.azurewebsites.net, verá o valor do segredo.
Substitua o nome <YourKeyVaultName> pelo nome do cofre ::: zone-end

::: zone pivot="dotnet" Agora que você executou o aplicativo, deverá ver o valor do segredo recuperado.
::: zone-end

## <a name="next-steps"></a>Próximas etapas

::: zone pivot="nodejs"
* [Home page do Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Documentação do Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [SDK do Azure para Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* [Referência da API REST do Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end

::: zone pivot="dotnet"
* [Home page do Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Documentação do Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [SDK do Azure para .NET](https://github.com/Azure/azure-sdk-for-net)
* [Referência da API REST do Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end