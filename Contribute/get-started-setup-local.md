---
title: Configurar o repositório Git localmente
description: Este artigo oferece orientação para criar seu repositório Git local e para contribuir com a documentação, incluindo o processo de fork e de clonagem.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 01/18/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: f702d0d29ee7dc9c69cb26b79bf6283d91b6b6bc
ms.sourcegitcommit: 3ec397fab57ea582edb03a59609f62d886410ee8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="set-up-git-repository-locally-for-documentation"></a>Configurar o repositório do git localmente para documentação

Este artigo descreve as etapas para configurar um repositório do git na sua máquina local, com a intenção de contribuir para a documentação da Microsoft. Colaboradores podem usar um repositório clonado localmente para adicionar novos artigos, fazer edições importantes em artigos existentes ou alterar a arte.

Execute essas atividades de configuração única para começar a contribuir:
> [!div class="checklist"]
> * Determine o repositório apropriado
> * Crie um fork do repositório para sua conta do GitHub
> * Escolha uma pasta local para os arquivos clonados
> * Clone o repositório em seu computador local
> * Configure o valor remoto upstream

> [!IMPORTANT]
> Se você estiver fazendo apenas pequenas alterações em um artigo, *não* é necessário concluir as etapas neste artigo. Você pode continuar diretamente no [fluxo de trabalho de alterações rápidas](index.md#quick-edits-to-existing-documents).
>

## <a name="overview"></a>Visão geral

Para contribuir com o site de documentação da Microsoft, você pode criar e editar arquivos de markdown localmente, clonando o repositório de documentação correspondente. A Microsoft requer a criação de um fork do repositório apropriado na sua própria conta do GitHub, para que você tenha permissões de leitura/gravação para armazenar as alterações propostas. Em seguida, use solicitações de pull para mesclar as alterações no repositório compartilhado central de somente leitura.

![Triangulo do GitHub](./media/git-and-github-initial-setup.png)

Se você é novo no GitHub, assista ao vídeo a seguir para obter uma visão geral conceitual do processo de criação de fork e de clonagem:

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a>Determinar o repositório

A documentação hospedada em [docs.microsoft.com](https://docs.microsoft.com) reside em vários repositórios diferentes em [github.com](https://www.github.com).

1. Caso não tenha certeza quanto a qual repositório deseja usar, visite o artigo no docs.microsoft.com usando seu navegador Web. Selecione o link **Editar** (ícone de lápis) no canto superior direito do artigo.

   ![Clique em Editar para determinar o local do arquivo e do repositório.](media/index/edit-article.png)

2. Esse link direciona para o local do github.com para o arquivo de markdown correspondente no repositório apropriado. Observe a URL para visualizar o nome do repositório.

   ![Observe a URL para determinar o local do repositório.](media/public-repo.png)

   Por exemplo, esses repositórios populares estão disponíveis para contribuições públicas:
   - Documentação do Azure [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)
   - Documentação do SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)
   - Documentação do Visual Studio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)
   - Documentação do .NET [https://github.com/dotnet/docs](https://github.com/dotnet/docs)
   - Documentação do SDK do .Net do Azure [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)

## <a name="fork-the-repository"></a>Criar um fork do repositório
Usando o repositório adequado, crie um fork do repositório em sua própria conta do GitHub usando o site do GitHub.

É necessário um fork pessoal, já que todos os principais repositórios de documentação oferecem acesso somente leitura, o que significa que você não pode fazer alterações diretamente no conteúdo dos repositórios. Para fazer alterações, é necessário enviar uma [solicitação de pull](git-github-fundamentals.md#pull-requests) do seu fork para o repositório principal. Para facilitar esse processo, primeiro você precisa da sua própria cópia do repositório, na qual você terá acesso de gravação. Um *fork* do GitHub atende a esse objetivo.

1. Acesse a página do GitHub do repositório principal e clique no botão **Fork** no lado superior direito.

   ![Exemplo de perfil do GitHub](./media/contribute-get-started-setup-local/fork.png)

2. Caso seja solicitado, selecione o seu bloco da conta do GitHub como o destino no qual o fork deve ser criado. Essa solicitação cria uma cópia do repositório dentro de sua conta do GitHub, conhecido como um fork.

## <a name="choose-a-local-folder"></a>Escolher uma pasta local
Crie uma pasta local para conter uma cópia do repositório localmente. Alguns repositórios podem ser grandes; até 5 GB para azure-docs, por exemplo. Escolha um local com espaço em disco disponível.

1. Escolha um nome para a pasta. Ele deve ser fácil de lembrar e de digitar. Por exemplo, considere uma pasta raiz `C:\docs\` ou crie uma pasta no seu diretório de perfil do usuário `~/Documents/docs/`

   > [!IMPORTANT]
   > Evite escolher um caminho de pasta local que esteja aninhado dentro de outro local de pasta de repositório do git. Embora seja aceitável armazenar as pastas clonadas do git adjacentes umas às outras, aninhar pastas do git umas dentro das outras causa erros no acompanhamento de arquivos.

2. Iniciar o Git Bash

   ![Iniciar o Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   O local padrão no qual o Git Bash inicia é normalmente o diretório inicial (~) ou `/c/users/<Windows-user-account>/` no sistema operacional Windows.

   Para determinar o diretório atual, digite `pwd` no prompt $. 

3. Altere o diretório (cd) para a pasta criada para hospedar o repositório localmente. Observe que o Git Bash usa a convenção do Linux de barras inclinadas para frente, em vez de barras invertidas para caminhos de pasta.

   Por exemplo, `cd /c/docs/ ` ou `cd ~/Documents/docs/`

## <a name="create-a-local-clone"></a>Criar um clone local

Usando o Git Bash, prepare-se para executar o comando **clone** para extrair uma cópia de um repositório (seu fork) para seu dispositivo no diretório atual. 

### <a name="authenticate-by-using-git-credential-manager"></a>Autenticar usando o Git Credential Manager
Se você tiver instalado a versão mais recente do Git para Windows e aceitado a instalação padrão, o Git Credential Manager estará habilitado por padrão. O Git Credential Manager facilita muito a autenticação porque você não precisa lembrar do token de acesso pessoal ao restabelecer as conexões autenticadas e remotas com o GitHub.

1. Execute o comando **clone** fornecendo o nome do repositório. A clonagem baixa (clone) o repositório com fork em seu computador local. 

    > [!Tip]
    > Você pode obter a URL do GitHub do fork para o comando de clonagem no botão **Clonar ou baixar** na interface do usuário do GitHub:
    >
    > ![Clonar ou baixar](./media/contribute-get-started-setup-local/clone-or-download.png)

    Lembre-se de especificar o caminho até o *seu fork* durante o processo de clonagem e não até o repositório principal do qual você criou o fork. Caso contrário, não é possível contribuir com as alterações. Seu fork é referenciado por meio da sua conta de usuário pessoal do GitHub, como `github.com/<github-username>/<repo>`.

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    Seu comando clone deve ter aparência semelhante à deste exemplo:

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. Quando solicitado, insira suas credenciais do GitHub.

    ![Logon no GitHub](./media/contribute-get-started-setup-local/github-login.png)

3. Quando solicitado, insira o código de autenticação de dois fatores.

    ![Autenticação de dois fatores do GitHub](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > Suas credenciais serão salvas e usadas para autenticar as próximas solicitações do GitHub. É necessário somente fazer essa autenticação uma vez por computador. 

4. O comando clone executa e baixa uma cópia dos arquivos de repositório do seu fork para uma nova pasta no disco local. Uma nova pasta é criada dentro da pasta atual. Isso pode levar alguns minutos dependendo do tamanho do repositório. É possível explorar a pasta para ver a estrutura após sua conclusão.

## <a name="configure-remote-upstream"></a>Configurar upstream remoto
Após clonar o repositório, configure uma conexão remota somente leitura com o repositório principal nomeado **upstream**. Use a URL upstream para manter seu repositório local em sincroniza com as últimas alterações feitas pelos outros. O comando **git remote** é usado para definir o valor de configuração. Use o comando **fetch** para atualizar as informações sobre o branch do repositório upstream.

1. Se você estiver usando o **Git Credential Manager**, use os seguintes comandos. Substitua os espaços reservados \<repositório\> e \<organização\>.
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. Exiba os valores configurados e confirme que as URLs estão corretas. Certifique-se de que as URLs de **origem** apontam para seu fork pessoal. Certifique-se de que as URLs **upstream** apontam para o repositório principal, como o MicrosoftDocs ou Azure. 
   ```bash
   git remote -v 
   ```

   É mostrado um exemplo de saída remota. Uma conta do git fictícia nomeada MyGitAccount é configurada com um token de acesso pessoal para acessar o repositório azure-docs:
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. Se você comete um erro, é possível remover o valor remoto. Para remover o valor upstream, execute o comando `git remote remove upstream`.

## <a name="next-steps"></a>Próximas etapas
- Para saber mais sobre como adicionar e atualizar conteúdo, prossiga para o [fluxo de trabalho de contribuição do GitHub](how-to-write-workflows-major.md).