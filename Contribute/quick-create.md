---
title: 'Início Rápido: definir e recuperar um segredo do Azure Key Vault | Microsoft Docs'
description: 'Início Rápido: definir e recuperar um segredo do Azure Key Vault'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 27ebd3e348fc231d8b82e6c17f282bd9ca4afb9f
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308814"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a><span data-ttu-id="a0555-103">Início Rápido: definir e recuperar um segredo do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-103">Quickstart: Set and retrieve a secret from Azure Key Vault</span></span>

<span data-ttu-id="a0555-104">Este início rápido mostra como armazenar um segredo no Key Vault e como recuperá-lo usando um aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="a0555-104">This quickstart shows you how to store a secret in Key Vault and how to retrieve it using a Web app.</span></span> <span data-ttu-id="a0555-105">Para ver o valor do segredo, seria necessário executar isso no Azure.</span><span class="sxs-lookup"><span data-stu-id="a0555-105">To see the secret value you would have to run this on Azure.</span></span> <span data-ttu-id="a0555-106">O início rápido usa Node.js e MSIs (identidades de serviço gerenciadas)</span><span class="sxs-lookup"><span data-stu-id="a0555-106">The quickstart uses Node.js and Managed service identities (MSIs)</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a0555-107">Crie um Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a0555-107">Create a Key Vault.</span></span>
> * <span data-ttu-id="a0555-108">Armazene um segredo no Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a0555-108">Store a secret in Key Vault.</span></span>
> * <span data-ttu-id="a0555-109">Recupere um segredo do Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a0555-109">Retrieve a secret from Key Vault.</span></span>
> * <span data-ttu-id="a0555-110">Crie um aplicativo Web do Azure.</span><span class="sxs-lookup"><span data-stu-id="a0555-110">Create an Azure Web Application.</span></span>
> * <span data-ttu-id="a0555-111">[Habilitar identidades de serviço gerenciadas](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span><span class="sxs-lookup"><span data-stu-id="a0555-111">[Enable managed service identities](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span></span>
> * <span data-ttu-id="a0555-112">Conceder as permissões necessárias para o aplicativo Web ler dados do Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a0555-112">Grant the required permissions for the web application to read data from Key vault.</span></span>

<span data-ttu-id="a0555-113">Antes de prosseguir, familiarize-se com os [conceitos básicos](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span><span class="sxs-lookup"><span data-stu-id="a0555-113">Before you proceed make sure that you are familiar with the [basic concepts](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span></span>

> [!NOTE]
> <span data-ttu-id="a0555-114">Para entender por que o tutorial abaixo é a melhor prática, precisamos entender alguns conceitos.</span><span class="sxs-lookup"><span data-stu-id="a0555-114">To understand why the below tutorial is the best practice we need to understand a few concepts.</span></span> <span data-ttu-id="a0555-115">O Key Vault é um repositório central para armazenar segredos de forma programática.</span><span class="sxs-lookup"><span data-stu-id="a0555-115">Key Vault is a central repository to store secrets programmatically.</span></span> <span data-ttu-id="a0555-116">Mas, para fazer isso, os aplicativos/usuários precisam autenticar primeiro o Key Vault, ou seja, apresentar um segredo.</span><span class="sxs-lookup"><span data-stu-id="a0555-116">But to do so applications / users need to first authenticate to Key Vault i.e. present a secret.</span></span> <span data-ttu-id="a0555-117">Para seguir as melhores práticas de segurança, esse primeiro segredo também deve ser alterado periodicamente.</span><span class="sxs-lookup"><span data-stu-id="a0555-117">To follow security best practices this first secret needs to be rotated periodically as well.</span></span> <span data-ttu-id="a0555-118">Mas com a [Identidade de Serviço Gerenciada](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview), os aplicativos executados no Azure recebem uma identidade gerenciada automaticamente pelo Azure.</span><span class="sxs-lookup"><span data-stu-id="a0555-118">But with [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) applications that run in Azure are given an identity which is automatically managed by Azure.</span></span> <span data-ttu-id="a0555-119">Isso ajuda a resolver o **Problema de Introdução do Segredo**, no qual os usuários/aplicativos podem seguir as melhores práticas e não precisam se preocupar em alterar o primeiro segredo</span><span class="sxs-lookup"><span data-stu-id="a0555-119">This helps solve the **Secret Introduction Problem** where users / applications can follow best practices and not have to worry about rotating the first secret</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0555-120">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a0555-120">Prerequisites</span></span>

<span data-ttu-id="a0555-121">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="a0555-121">::: zone pivot="nodejs"</span></span>
* <span data-ttu-id="a0555-122">[Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="a0555-122">[Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"</span></span>
* <span data-ttu-id="a0555-123">[Visual Studio 2017 versão 15.7.3 ou posterior](https://www.microsoft.com/net/download/windows) com as seguintes cargas de trabalho:</span><span class="sxs-lookup"><span data-stu-id="a0555-123">[Visual Studio 2017 version 15.7.3 or later](https://www.microsoft.com/net/download/windows) with the following workloads:</span></span>
  * <span data-ttu-id="a0555-124">Desenvolvimento Web e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a0555-124">ASP.NET and web development</span></span>
  * <span data-ttu-id="a0555-125">Desenvolvimento multiplataforma com o .NET Core</span><span class="sxs-lookup"><span data-stu-id="a0555-125">.NET Core cross-platform development</span></span>
* <span data-ttu-id="a0555-126">[SDK do .NET Core 2.1 ou posterior](https://www.microsoft.com/net/download/windows) :::zone-end</span><span class="sxs-lookup"><span data-stu-id="a0555-126">[.NET Core 2.1 SDK or later](https://www.microsoft.com/net/download/windows) ::: zone-end</span></span>
* <span data-ttu-id="a0555-127">Git ([download](https://git-scm.com/downloads)).</span><span class="sxs-lookup"><span data-stu-id="a0555-127">Git ([download](https://git-scm.com/downloads)).</span></span>
* <span data-ttu-id="a0555-128">Uma assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="a0555-128">An Azure subscription.</span></span> <span data-ttu-id="a0555-129">Se você não tiver uma assinatura do Azure, crie uma [conta gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) antes de começar.</span><span class="sxs-lookup"><span data-stu-id="a0555-129">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>
* <span data-ttu-id="a0555-130">[CLI do Azure](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) versão 2.0.4 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="a0555-130">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 or later.</span></span> <span data-ttu-id="a0555-131">Disponível para Windows, Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="a0555-131">This is available for Windows, Mac, and Linux.</span></span>

## <a name="login-to-azure"></a><span data-ttu-id="a0555-132">Logon no Azure</span><span class="sxs-lookup"><span data-stu-id="a0555-132">Login to Azure</span></span>

<span data-ttu-id="a0555-133">Para fazer logon no Azure usando a CLI, você pode digitar:</span><span class="sxs-lookup"><span data-stu-id="a0555-133">To log in to Azure using the CLI, you can type:</span></span>

```azurecli
az login
```

## <a name="create-resource-group"></a><span data-ttu-id="a0555-134">Criar grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="a0555-134">Create resource group</span></span>

<span data-ttu-id="a0555-135">Crie um grupo de recursos com o comando [az group create](/cli/azure/group#az-group-create).</span><span class="sxs-lookup"><span data-stu-id="a0555-135">Create a resource group with the [az group create](/cli/azure/group#az-group-create) command.</span></span> <span data-ttu-id="a0555-136">Um grupo de recursos do Azure é um contêiner lógico no qual os recursos do Azure são implantados e gerenciados.</span><span class="sxs-lookup"><span data-stu-id="a0555-136">An Azure resource group is a logical container into which Azure resources are deployed and managed.</span></span>

<span data-ttu-id="a0555-137">Selecione um nome para o grupo de recursos e preencha o espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="a0555-137">Please select a Resource Group name and fill in the placeholder.</span></span>
<span data-ttu-id="a0555-138">O exemplo a seguir cria um grupo de recursos denominado *<YourResourceGroupName>* no local *eastus*.</span><span class="sxs-lookup"><span data-stu-id="a0555-138">The following example creates a resource group named *<YourResourceGroupName>* in the *eastus* location.</span></span>

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="a0555-139">O grupo de recursos que você acabou de criar é usado ao longo deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="a0555-139">The resource group you just created is used throughout this tutorial.</span></span>

## <a name="create-an-azure-key-vault"></a><span data-ttu-id="a0555-140">Criar um Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-140">Create an Azure Key Vault</span></span>

<span data-ttu-id="a0555-141">Em seguida, crie um Key Vault no grupo de recursos criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="a0555-141">Next you create a Key Vault using the resource group created in the previous step.</span></span> <span data-ttu-id="a0555-142">Embora “ContosoKeyVault” seja utilizado como o nome do Key Vault ao longo deste artigo, você deverá usar um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="a0555-142">Although “ContosoKeyVault” is used as the name for the Key Vault throughout this article, you have to use a unique name.</span></span> <span data-ttu-id="a0555-143">Forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="a0555-143">Provide the following information:</span></span>

* <span data-ttu-id="a0555-144">Nome do cofre: **selecione um nome para o Key Vault aqui**.</span><span class="sxs-lookup"><span data-stu-id="a0555-144">Vault name - **Select a Key Vault Name here**.</span></span>
* <span data-ttu-id="a0555-145">Nome do grupo de recursos: **selecione um nome para o grupo de recursos aqui**.</span><span class="sxs-lookup"><span data-stu-id="a0555-145">Resource group name - **Select a Resource Group Name here**.</span></span>
* <span data-ttu-id="a0555-146">O local: **Leste dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="a0555-146">The location - **East US**.</span></span>

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="a0555-147">Nesse ponto, sua conta do Azure é a única autorizada a executar qualquer operação nesse novo cofre.</span><span class="sxs-lookup"><span data-stu-id="a0555-147">At this point, your Azure account is the only one authorized to perform any operations on this new vault.</span></span>

## <a name="add-a-secret-to-key-vault"></a><span data-ttu-id="a0555-148">Adicionar um segredo ao Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-148">Add a secret to key vault</span></span>

<span data-ttu-id="a0555-149">Estamos adicionando um segredo para ajudar a ilustrar como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="a0555-149">We're adding a secret to help illustrate how this works.</span></span> <span data-ttu-id="a0555-150">Você pode estar armazenando uma cadeia de conexão SQL ou qualquer outra informação que precise manter com segurança, mas disponibilizar para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a0555-150">You could be storing a SQL connection string or any other information that you need to keep securely but make available to your application.</span></span> <span data-ttu-id="a0555-151">Neste tutorial, a senha será chamada **AppSecret** e armazenará o valor de **MySecret** nela.</span><span class="sxs-lookup"><span data-stu-id="a0555-151">In this tutorial, the password will be called **AppSecret** and will store the value of **MySecret** in it.</span></span>

<span data-ttu-id="a0555-152">Digite os comandos abaixo para criar um segredo no Key Vault chamado **AppSecret** que armazenará o valor **MySecret**:</span><span class="sxs-lookup"><span data-stu-id="a0555-152">Type the commands below to create a secret in Key Vault called **AppSecret** that will store the value **MySecret**:</span></span>

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

<span data-ttu-id="a0555-153">Para exibir o valor contido no segredo como texto sem formatação:</span><span class="sxs-lookup"><span data-stu-id="a0555-153">To view the value contained in the secret as plain text:</span></span>

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

<span data-ttu-id="a0555-154">Este comando mostra as informações secretas, incluindo o URI.</span><span class="sxs-lookup"><span data-stu-id="a0555-154">This command shows the secret information including the URI.</span></span> <span data-ttu-id="a0555-155">Após concluir essas etapas, você deverá ter um URI para um segredo em um Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a0555-155">After completing these steps, you should have a URI to a secret in an Azure Key Vault.</span></span> <span data-ttu-id="a0555-156">Anote essas informações.</span><span class="sxs-lookup"><span data-stu-id="a0555-156">Write this information down.</span></span> <span data-ttu-id="a0555-157">Ela serão necessárias em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="a0555-157">You need it in a later step.</span></span>

## <a name="clone-the-repo"></a><span data-ttu-id="a0555-158">Clonar o repositório</span><span class="sxs-lookup"><span data-stu-id="a0555-158">Clone the Repo</span></span>

<span data-ttu-id="a0555-159">Clone o repositório a fim de fazer uma cópia local para que você possa editar a fonte executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a0555-159">Clone the repo in order to make a local copy for you to edit the source by running the following command:</span></span>

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

<span data-ttu-id="a0555-160">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="a0555-160">::: zone pivot="nodejs"</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="a0555-161">Instalar dependências</span><span class="sxs-lookup"><span data-stu-id="a0555-161">Install dependencies</span></span>

<span data-ttu-id="a0555-162">Vamos instalar as dependências aqui.</span><span class="sxs-lookup"><span data-stu-id="a0555-162">Here we install the dependencies.</span></span> <span data-ttu-id="a0555-163">Execute os comandos a seguir cd key-vault-node-quickstart npm install</span><span class="sxs-lookup"><span data-stu-id="a0555-163">Run the following commands cd key-vault-node-quickstart npm install</span></span>

<span data-ttu-id="a0555-164">Este projeto usou dois módulos de nó:</span><span class="sxs-lookup"><span data-stu-id="a0555-164">This project used 2 node modules:</span></span>

* [<span data-ttu-id="a0555-165">ms-rest-azure</span><span class="sxs-lookup"><span data-stu-id="a0555-165">ms-rest-azure</span></span>](https://www.npmjs.com/package/ms-rest-azure) 
* [<span data-ttu-id="a0555-166">azure-keyvault</span><span class="sxs-lookup"><span data-stu-id="a0555-166">azure-keyvault</span></span>](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="a0555-167">Publicar o aplicativo Web no Azure</span><span class="sxs-lookup"><span data-stu-id="a0555-167">Publish the web application to Azure</span></span>

<span data-ttu-id="a0555-168">Abaixo estão as etapas que precisamos realizar</span><span class="sxs-lookup"><span data-stu-id="a0555-168">Below are the few steps we need to do</span></span>

* <span data-ttu-id="a0555-169">A 1ª etapa é criar um Plano do [Serviço de Aplicativo do Azure](https://azure.microsoft.com/services/app-service/).</span><span class="sxs-lookup"><span data-stu-id="a0555-169">The 1st step is to create a [Azure App Service](https://azure.microsoft.com/services/app-service/) Plan.</span></span> <span data-ttu-id="a0555-170">Você pode armazenar vários aplicativos Web nesse plano.</span><span class="sxs-lookup"><span data-stu-id="a0555-170">You can store multiple web apps in this plan.</span></span>

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* <span data-ttu-id="a0555-171">Em seguida, criamos um aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="a0555-171">Next we create a web app.</span></span> <span data-ttu-id="a0555-172">No exemplo a seguir, substitua <nome_do_aplicativo> por um nome de aplicativo exclusivo globalmente (os caracteres válidos são a-z, 0-9 e -).</span><span class="sxs-lookup"><span data-stu-id="a0555-172">In the following example, replace <app_name> with a globally unique app name (valid characters are a-z, 0-9, and -).</span></span> <span data-ttu-id="a0555-173">O tempo de execução é definido como NODE|6.9.</span><span class="sxs-lookup"><span data-stu-id="a0555-173">The runtime is set to NODE|6.9.</span></span> <span data-ttu-id="a0555-174">Para ver todos os tempos de execução com suporte, execute az webapp list-runtimes</span><span class="sxs-lookup"><span data-stu-id="a0555-174">To see all supported runtimes, run az webapp list-runtimes</span></span>

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    <span data-ttu-id="a0555-175">Quando o aplicativo Web for criado, a CLI do Azure mostrará um resultado semelhante ao seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="a0555-175">When the web app has been created, the Azure CLI shows output similar to the following example:</span></span>

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
    <span data-ttu-id="a0555-176">Navegue até o aplicativo Web criado recentemente e verá um aplicativo Web funcionando.</span><span class="sxs-lookup"><span data-stu-id="a0555-176">Browse to your newly created web app and you should see a functioning web app.</span></span> <span data-ttu-id="a0555-177">Substitua <nome_do_aplicativo> por um nome exclusivo do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a0555-177">Replace <app_name> with a unique app name.</span></span>

    ```text
    http://<app name>.azurewebsites.net
    ```
    <span data-ttu-id="a0555-178">O comando acima também cria um aplicativo habilitado para Git que permite a implantação no Azure do git local.</span><span class="sxs-lookup"><span data-stu-id="a0555-178">The above command also creates a Git-enabled app which allows you to deploy to azure from your local git.</span></span> 
    <span data-ttu-id="a0555-179">O git local está configurado com a URL 'https://<username>@<nome_do_aplicativo>.scm.azurewebsites.net/<nome_do_aplicativo>.git'</span><span class="sxs-lookup"><span data-stu-id="a0555-179">Local git is configured with url of 'https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git'</span></span>

* <span data-ttu-id="a0555-180">Criar um usuário de implantação após a conclusão do comando anterior; você pode adicionar um Azure remoto ao repositório Git local.</span><span class="sxs-lookup"><span data-stu-id="a0555-180">Create a deployment user After the previous command is completed you can add add an Azure remote to your local Git repository.</span></span> <span data-ttu-id="a0555-181">Substitua <url> pela URL do Git remoto que você obteve de Habilitar o Git para seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a0555-181">Replace <url> with the URL of the Git remote that you got from Enable Git for your app.</span></span>

    ```bash
    git remote add azure <url>
    ```
    
<span data-ttu-id="a0555-182">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="a0555-182">::: zone-end</span></span>

<span data-ttu-id="a0555-183">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="a0555-183">::: zone pivot="dotnet"</span></span>
## <a name="open-and-edit-the-solution"></a><span data-ttu-id="a0555-184">Abrir e editar a solução</span><span class="sxs-lookup"><span data-stu-id="a0555-184">Open and edit the solution</span></span>

<span data-ttu-id="a0555-185">Edite o arquivo program.cs para executar o exemplo com o nome específico de seu cofre de chaves:</span><span class="sxs-lookup"><span data-stu-id="a0555-185">Edit the program.cs file to run the sample with your specific key vault name:</span></span>

1. <span data-ttu-id="a0555-186">Navegue até a pasta key-vault-dotnet-core-quickstart.</span><span class="sxs-lookup"><span data-stu-id="a0555-186">Browse to the folder key-vault-dotnet-core-quickstart.</span></span>
2. <span data-ttu-id="a0555-187">Abra o arquivo key-vault-dotnet-core-quickstart.sln no Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a0555-187">Open the key-vault-dotnet-core-quickstart.sln file in Visual Studio 2017.</span></span>
3. <span data-ttu-id="a0555-188">Abra o arquivo Program.cs e atualize o espaço reservado *YourKeyVaultName* com o nome do cofre de chaves criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a0555-188">Open the Program.cs file and update the placeholder *YourKeyVaultName* with the name of your key vault that you created earlier.</span></span>

<span data-ttu-id="a0555-189">A solução usa as bibliotecas NuGet [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) e [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).</span><span class="sxs-lookup"><span data-stu-id="a0555-189">This solution uses [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) and [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet libraries.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="a0555-190">Executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="a0555-190">Run the app</span></span>

<span data-ttu-id="a0555-191">No menu principal do Visual Studio 2017, selecione **Depurar** > **Iniciar** sem depuração.</span><span class="sxs-lookup"><span data-stu-id="a0555-191">From the main menu of Visual Studio 2017, select **Debug** > **Start** without debugging.</span></span> <span data-ttu-id="a0555-192">Quando o navegador aparecer, acesse a página **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="a0555-192">When the browser appears, go to the **About** page.</span></span> <span data-ttu-id="a0555-193">O valor para **AppSecret** é exibido.</span><span class="sxs-lookup"><span data-stu-id="a0555-193">The value for **AppSecret** is displayed.</span></span>

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="a0555-194">Publicar o aplicativo Web no Azure</span><span class="sxs-lookup"><span data-stu-id="a0555-194">Publish the web application to Azure</span></span>

<span data-ttu-id="a0555-195">Publique esse aplicativo do Azure para vê-lo ao vivo como um aplicativo Web e verifique se você pode buscar o valor do segredo:</span><span class="sxs-lookup"><span data-stu-id="a0555-195">Publish this app to Azure to see it live as a web app, and to see that you can fetch the secret value:</span></span>

1. <span data-ttu-id="a0555-196">No Visual Studio, selecione o projeto **key-vault-dotnet-core-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="a0555-196">In Visual Studio, select the **key-vault-dotnet-core-quickstart** project.</span></span>
2. <span data-ttu-id="a0555-197">Selecione **Publicar** > **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="a0555-197">Select **Publish** > **Start**.</span></span>
3. <span data-ttu-id="a0555-198">Crie um novo **Serviço de Aplicativo** e selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="a0555-198">Create a new **App Service**, and then select **Publish**.</span></span>
4. <span data-ttu-id="a0555-199">Altere o nome do aplicativo para **keyvaultdotnetcorequickstart**.</span><span class="sxs-lookup"><span data-stu-id="a0555-199">Change the app name to **keyvaultdotnetcorequickstart**.</span></span>
5. <span data-ttu-id="a0555-200">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a0555-200">Select **Create**.</span></span>

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]
<span data-ttu-id="a0555-201">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="a0555-201">::: zone-end</span></span>

## <a name="enable-managed-service-identities"></a><span data-ttu-id="a0555-202">Habilitar identidades de serviço gerenciadas</span><span class="sxs-lookup"><span data-stu-id="a0555-202">Enable managed service identities</span></span>

<span data-ttu-id="a0555-203">O Azure Key Vault fornece uma maneira de armazenar com segurança as credenciais e outras chaves e segredos, mas seu código precisa autenticar no Azure Key Vault para recuperá-los.</span><span class="sxs-lookup"><span data-stu-id="a0555-203">Azure Key Vault provides a way to securely store credentials and other keys and secrets, but your code needs to authenticate to Azure Key Vault to retrieve them.</span></span> <span data-ttu-id="a0555-204">A Identidade de Serviço Gerenciada facilita fornecendo aos serviços do Azure uma identidade gerenciada automaticamente no Azure AD (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="a0555-204">Managed Service Identity makes this easier by giving Azure services an automatically managed identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a0555-205">Você pode usar essa identidade para autenticar em qualquer serviço que dá suporte à autenticação do Azure AD, incluindo o Key Vault, sem ter que todas as credenciais no seu código.</span><span class="sxs-lookup"><span data-stu-id="a0555-205">You can use this identity to authenticate to any service that supports Azure AD authentication, including Key Vault, without having any credentials in your code.</span></span>

1. <span data-ttu-id="a0555-206">Volte para a CLI do Azure.</span><span class="sxs-lookup"><span data-stu-id="a0555-206">Return to the Azure CLI.</span></span>
2. <span data-ttu-id="a0555-207">Execute o comando assign-identity para criar a identidade para esse aplicativo:</span><span class="sxs-lookup"><span data-stu-id="a0555-207">Run the assign-identity command to create the identity for this application:</span></span>

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
><span data-ttu-id="a0555-208">O comando nesse procedimento é o equivalente de ir para o portal e alternar **Identidade de serviço gerenciada** para **On** nas propriedades do aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="a0555-208">The command in this procedure is the equivalent of going to the portal and switching **Managed service identity** to **On** in the web application properties.</span></span>

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a><span data-ttu-id="a0555-209">Atribuir permissões ao aplicativo para ler segredos do Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-209">Assign permissions to your application to read secrets from Key Vault</span></span>

<span data-ttu-id="a0555-210">Anote a saída quando você publicar o aplicativo no Azure.</span><span class="sxs-lookup"><span data-stu-id="a0555-210">Make a note of the output when you publish the application to Azure.</span></span> <span data-ttu-id="a0555-211">Ela deve ter o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="a0555-211">It should be of the format:</span></span>

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

<span data-ttu-id="a0555-212">Em seguida, execute o comando usando o nome do seu Key Vault e o valor do **PrincipalId**:</span><span class="sxs-lookup"><span data-stu-id="a0555-212">Then, run this command by using the name of your key vault and the value of **PrincipalId**:</span></span>

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

<span data-ttu-id="a0555-213">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="a0555-213">::: zone pivot="nodejs"</span></span>
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a><span data-ttu-id="a0555-214">Implantar o aplicativo Node no Azure e recuperar o valor do segredo</span><span class="sxs-lookup"><span data-stu-id="a0555-214">Deploy the Node App to Azure and retrieve the secret value</span></span>

<span data-ttu-id="a0555-215">Agora está tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="a0555-215">Now that everything is set.</span></span> <span data-ttu-id="a0555-216">Execute o seguinte comando para implantar o aplicativo no Azure</span><span class="sxs-lookup"><span data-stu-id="a0555-216">Run the following command to deploy the app to Azure</span></span>

```bash
git push azure master
```

<span data-ttu-id="a0555-217">Depois de fazer isso, quando você navegar por https://<nome_do_aplicativo>.azurewebsites.net, verá o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="a0555-217">After this when you browse https://<app_name>.azurewebsites.net you can see the secret value.</span></span>
<span data-ttu-id="a0555-218">Substitua o nome <YourKeyVaultName> pelo nome do cofre</span><span class="sxs-lookup"><span data-stu-id="a0555-218">Make sure that you replaced the name <YourKeyVaultName> with your vault name</span></span>

<span data-ttu-id="a0555-219">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="a0555-219">::: zone-end</span></span>

<span data-ttu-id="a0555-220">::: zone pivot="dotnet" Agora que você executou o aplicativo, deverá ver o valor do segredo recuperado.</span><span class="sxs-lookup"><span data-stu-id="a0555-220">::: zone pivot="dotnet" Now when you run the application, you should see your secret value retrieved.</span></span>
<span data-ttu-id="a0555-221">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="a0555-221">::: zone-end</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0555-222">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a0555-222">Next steps</span></span>

<span data-ttu-id="a0555-223">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="a0555-223">::: zone pivot="nodejs"</span></span>
* [<span data-ttu-id="a0555-224">Home page do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-224">Azure Key Vault Home Page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="a0555-225">Documentação do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-225">Azure Key Vault Documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="a0555-226">SDK do Azure para Node</span><span class="sxs-lookup"><span data-stu-id="a0555-226">Azure SDK For Node</span></span>](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* <span data-ttu-id="a0555-227">[Referência da API REST do Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="a0555-227">[Azure REST API Reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>

<span data-ttu-id="a0555-228">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="a0555-228">::: zone pivot="dotnet"</span></span>
* [<span data-ttu-id="a0555-229">Home page do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-229">Azure Key Vault home page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="a0555-230">Documentação do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a0555-230">Azure Key Vault documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="a0555-231">SDK do Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="a0555-231">Azure SDK For .NET</span></span>](https://github.com/Azure/azure-sdk-for-net)
* <span data-ttu-id="a0555-232">[Referência da API REST do Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="a0555-232">[Azure REST API reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>
