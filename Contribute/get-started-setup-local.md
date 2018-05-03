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
ms.openlocfilehash: d9c7211641fb05aaca8a76e10c7216ff61a5d23c
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2018
---
# <a name="set-up-git-repository-locally-for-documentation"></a><span data-ttu-id="f63bd-103">Configurar o repositório do git localmente para documentação</span><span class="sxs-lookup"><span data-stu-id="f63bd-103">Set up Git repository locally for documentation</span></span>

<span data-ttu-id="f63bd-104">Este artigo descreve as etapas para configurar um repositório do git na sua máquina local, com a intenção de contribuir para a documentação da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f63bd-104">This article describes the steps to set up a git repository on your local machine, with the intent to contribute to Microsoft documentation.</span></span> <span data-ttu-id="f63bd-105">Colaboradores podem usar um repositório clonado localmente para adicionar novos artigos, fazer edições importantes em artigos existentes ou alterar a arte.</span><span class="sxs-lookup"><span data-stu-id="f63bd-105">Contributors may use a locally cloned repository to add new articles, do major edits on existing articles, or change artwork.</span></span>

<span data-ttu-id="f63bd-106">Execute essas atividades de configuração única para começar a contribuir:</span><span class="sxs-lookup"><span data-stu-id="f63bd-106">You run these one-time setup activities to get started contributing:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f63bd-107">Determine o repositório apropriado</span><span class="sxs-lookup"><span data-stu-id="f63bd-107">Determine the appropriate repository</span></span>
> * <span data-ttu-id="f63bd-108">Crie um fork do repositório para sua conta do GitHub</span><span class="sxs-lookup"><span data-stu-id="f63bd-108">Fork the repository to your GitHub account</span></span>
> * <span data-ttu-id="f63bd-109">Escolha uma pasta local para os arquivos clonados</span><span class="sxs-lookup"><span data-stu-id="f63bd-109">Choose a local folder for the cloned files</span></span>
> * <span data-ttu-id="f63bd-110">Clone o repositório em seu computador local</span><span class="sxs-lookup"><span data-stu-id="f63bd-110">Clone the repository to your local machine</span></span>
> * <span data-ttu-id="f63bd-111">Configure o valor remoto upstream</span><span class="sxs-lookup"><span data-stu-id="f63bd-111">Configure the upstream remote value</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f63bd-112">Se você estiver fazendo apenas pequenas alterações em um artigo, *não* é necessário concluir as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f63bd-112">If you're making only minor changes to an article, you *do not* need to complete the steps in this article.</span></span> <span data-ttu-id="f63bd-113">Você pode continuar diretamente no [fluxo de trabalho de alterações secundárias/pouco frequentes](light-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f63bd-113">You can continue directly to the [minor/infrequent changes workflow](light-workflow.md).</span></span>
>

## <a name="overview"></a><span data-ttu-id="f63bd-114">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f63bd-114">Overview</span></span>

<span data-ttu-id="f63bd-115">Para contribuir com o site de documentação da Microsoft, você pode criar e editar arquivos de markdown localmente, clonando o repositório de documentação correspondente.</span><span class="sxs-lookup"><span data-stu-id="f63bd-115">To contribute to Microsoft's documentation site, you can make and edit Markdown files locally by cloning the corresponding documentation repository.</span></span> <span data-ttu-id="f63bd-116">A Microsoft requer a criação de um fork do repositório apropriado na sua própria conta do GitHub, para que você tenha permissões de leitura/gravação para armazenar as alterações propostas.</span><span class="sxs-lookup"><span data-stu-id="f63bd-116">Microsoft requires you to fork the appropriate repository into your own github account, so that you have read/write permissions there to store your proposed changes.</span></span> <span data-ttu-id="f63bd-117">Em seguida, use solicitações de pull para mesclar as alterações no repositório compartilhado central de somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f63bd-117">Then you use pull requests to merge changes into the read-only central shared repository.</span></span>

![Triangulo do GitHub](./media/git-and-github-initial-setup.png)

<span data-ttu-id="f63bd-119">Se você é novo no GitHub, assista ao vídeo a seguir para obter uma visão geral conceitual do processo de criação de fork e de clonagem:</span><span class="sxs-lookup"><span data-stu-id="f63bd-119">If you're new to GitHub, watch the following video for a conceptual overview of the forking and cloning process:</span></span>

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a><span data-ttu-id="f63bd-120">Determinar o repositório</span><span class="sxs-lookup"><span data-stu-id="f63bd-120">Determine the repository</span></span>

<span data-ttu-id="f63bd-121">A documentação hospedada em [docs.microsoft.com](https://docs.microsoft.com) reside em vários repositórios diferentes em [github.com](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="f63bd-121">Documentation hosted at [docs.microsoft.com](https://docs.microsoft.com) resides in several different repositories at [github.com](https://www.github.com).</span></span>

1. <span data-ttu-id="f63bd-122">Caso não tenha certeza quanto a qual repositório deseja usar, visite o artigo no docs.microsoft.com usando seu navegador Web.</span><span class="sxs-lookup"><span data-stu-id="f63bd-122">If you are unsure of which repository to use, then visit the article on docs.microsoft.com using your web browser.</span></span> <span data-ttu-id="f63bd-123">Selecione o link **Editar** (ícone de lápis) no canto superior direito do artigo.</span><span class="sxs-lookup"><span data-stu-id="f63bd-123">Select the **Edit** link (pencil icon) on the upper right of the article.</span></span>

   ![Clique em Editar para determinar o local do arquivo e do repositório.](media/edit-article.png)

2. <span data-ttu-id="f63bd-125">Esse link direciona para o local do github.com para o arquivo de markdown correspondente no repositório apropriado.</span><span class="sxs-lookup"><span data-stu-id="f63bd-125">That link takes you to github.com location for the corresponding Markdown file in the appropriate repository.</span></span> <span data-ttu-id="f63bd-126">Observe a URL para visualizar o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="f63bd-126">Note the URL to view the repository name.</span></span>

   ![Observe a URL para determinar o local do repositório.](media/public-repo.png)

   <span data-ttu-id="f63bd-128">Por exemplo, esses repositórios populares estão disponíveis para contribuições públicas:</span><span class="sxs-lookup"><span data-stu-id="f63bd-128">For example, these popular repositories are available for public contributions:</span></span>
   - <span data-ttu-id="f63bd-129">Documentação do Azure [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span><span class="sxs-lookup"><span data-stu-id="f63bd-129">Azure documentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span></span>
   - <span data-ttu-id="f63bd-130">Documentação do SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span><span class="sxs-lookup"><span data-stu-id="f63bd-130">SQL Server documentation [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span></span>
   - <span data-ttu-id="f63bd-131">Documentação do Visual Studio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span><span class="sxs-lookup"><span data-stu-id="f63bd-131">Visual Studio documentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span></span>
   - <span data-ttu-id="f63bd-132">Documentação do .NET [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span><span class="sxs-lookup"><span data-stu-id="f63bd-132">.NET Documentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span></span>
   - <span data-ttu-id="f63bd-133">Documentação do SDK do .Net do Azure [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span><span class="sxs-lookup"><span data-stu-id="f63bd-133">Azure .Net SDK documentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span></span>

## <a name="fork-the-repository"></a><span data-ttu-id="f63bd-134">Criar um fork do repositório</span><span class="sxs-lookup"><span data-stu-id="f63bd-134">Fork the repository</span></span>
<span data-ttu-id="f63bd-135">Usando o repositório adequado, crie um fork do repositório em sua própria conta do GitHub usando o site do GitHub.</span><span class="sxs-lookup"><span data-stu-id="f63bd-135">Using the appropriate repository, create a fork of the repository into your own GitHub account by using the GitHub website.</span></span>

<span data-ttu-id="f63bd-136">É necessário um fork pessoal, já que todos os principais repositórios de documentação oferecem acesso somente leitura, o que significa que você não pode fazer alterações diretamente no conteúdo dos repositórios.</span><span class="sxs-lookup"><span data-stu-id="f63bd-136">A personal fork is required since all main documentation repositories provide read-only access, which means you cannot make changes directly on content in the repositories.</span></span> <span data-ttu-id="f63bd-137">Para fazer alterações, é necessário enviar uma [solicitação de pull](git-github-fundamentals.md#pull-requests) do seu fork para o repositório principal.</span><span class="sxs-lookup"><span data-stu-id="f63bd-137">To make changes, you must submit a [pull request](git-github-fundamentals.md#pull-requests) from your fork into the main repository.</span></span> <span data-ttu-id="f63bd-138">Para facilitar esse processo, primeiro você precisa da sua própria cópia do repositório, na qual você terá acesso de gravação.</span><span class="sxs-lookup"><span data-stu-id="f63bd-138">To facilitate this process, you first need your own copy of the repository, in which you have write access.</span></span> <span data-ttu-id="f63bd-139">Um *fork* do GitHub atende a esse objetivo.</span><span class="sxs-lookup"><span data-stu-id="f63bd-139">A GitHub *fork* serves that purpose.</span></span>

1. <span data-ttu-id="f63bd-140">Acesse a página do GitHub do repositório principal e clique no botão **Fork** no lado superior direito.</span><span class="sxs-lookup"><span data-stu-id="f63bd-140">Go to the main repository's GitHub page and click the **Fork** button on the upper right.</span></span>

   ![Exemplo de perfil do GitHub](./media/contribute-get-started-setup-local/fork.png)

2. <span data-ttu-id="f63bd-142">Caso seja solicitado, selecione o seu bloco da conta do GitHub como o destino no qual o fork deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="f63bd-142">If you are prompted, select your GitHub account tile as the destination where the fork should be created.</span></span> <span data-ttu-id="f63bd-143">Essa solicitação cria uma cópia do repositório dentro de sua conta do GitHub, conhecido como um fork.</span><span class="sxs-lookup"><span data-stu-id="f63bd-143">This prompt creates a copy of the repository within your GitHub account, known as a fork.</span></span>

## <a name="choose-a-local-folder"></a><span data-ttu-id="f63bd-144">Escolher uma pasta local</span><span class="sxs-lookup"><span data-stu-id="f63bd-144">Choose a local folder</span></span>
<span data-ttu-id="f63bd-145">Crie uma pasta local para conter uma cópia do repositório localmente.</span><span class="sxs-lookup"><span data-stu-id="f63bd-145">Make a local folder to hold a copy of the repository locally.</span></span> <span data-ttu-id="f63bd-146">Alguns repositórios podem ser grandes; até 5 GB para azure-docs, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="f63bd-146">Some of the repositories can be large; up to 5 GB for azure-docs for example.</span></span> <span data-ttu-id="f63bd-147">Escolha um local com espaço em disco disponível.</span><span class="sxs-lookup"><span data-stu-id="f63bd-147">Choose a location with available disk space.</span></span>

1. <span data-ttu-id="f63bd-148">Escolha um nome para a pasta. Ele deve ser fácil de lembrar e de digitar.</span><span class="sxs-lookup"><span data-stu-id="f63bd-148">Choose a folder name should be easy for you to remember and type.</span></span> <span data-ttu-id="f63bd-149">Por exemplo, considere uma pasta raiz `C:\docs\` ou crie uma pasta no seu diretório de perfil do usuário `~/Documents/docs/`</span><span class="sxs-lookup"><span data-stu-id="f63bd-149">For example, consider a root folder `C:\docs\` or make a folder in your user profile directory `~/Documents/docs/`</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f63bd-150">Evite escolher um caminho de pasta local que esteja aninhado dentro de outro local de pasta de repositório do git.</span><span class="sxs-lookup"><span data-stu-id="f63bd-150">Avoid choosing a local folder path that is nested inside of another git repository folder location.</span></span> <span data-ttu-id="f63bd-151">Embora seja aceitável armazenar as pastas clonadas do git adjacentes umas às outras, aninhar pastas do git umas dentro das outras causa erros no acompanhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="f63bd-151">While it is acceptable to store the git cloned folders adjacent to each other, nesting git folders inside one another causes errors for the file tracking.</span></span>

2. <span data-ttu-id="f63bd-152">Iniciar o Git Bash</span><span class="sxs-lookup"><span data-stu-id="f63bd-152">Launch Git Bash</span></span>

   ![Iniciar o Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   <span data-ttu-id="f63bd-154">O local padrão no qual o Git Bash inicia é normalmente o diretório inicial (~) ou `/c/users/<Windows-user-account>/` no sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="f63bd-154">The default location that Git Bash starts in is typically the home directory (~) or `/c/users/<Windows-user-account>/` on Windows OS.</span></span>

   <span data-ttu-id="f63bd-155">Para determinar o diretório atual, digite `pwd` no prompt $.</span><span class="sxs-lookup"><span data-stu-id="f63bd-155">To determine the current directory, type `pwd` at the $ prompt.</span></span> 

3. <span data-ttu-id="f63bd-156">Altere o diretório (cd) para a pasta criada para hospedar o repositório localmente.</span><span class="sxs-lookup"><span data-stu-id="f63bd-156">Change directory (cd) into the folder that you created for hosting the repository locally.</span></span> <span data-ttu-id="f63bd-157">Observe que o Git Bash usa a convenção do Linux de barras inclinadas para frente, em vez de barras invertidas para caminhos de pasta.</span><span class="sxs-lookup"><span data-stu-id="f63bd-157">Note that Git Bash uses Linux convention of forward-slashes instead of back-slashes for folder paths.</span></span>

   <span data-ttu-id="f63bd-158">Por exemplo, `cd /c/docs/ ` ou `cd ~/Documents/docs/`</span><span class="sxs-lookup"><span data-stu-id="f63bd-158">For example, `cd /c/docs/ ` or `cd ~/Documents/docs/`</span></span>

## <a name="create-a-local-clone"></a><span data-ttu-id="f63bd-159">Criar um clone local</span><span class="sxs-lookup"><span data-stu-id="f63bd-159">Create a local clone</span></span>

<span data-ttu-id="f63bd-160">Usando o Git Bash, prepare-se para executar o comando **clone** para extrair uma cópia de um repositório (seu fork) para seu dispositivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="f63bd-160">Using Git Bash, prepare to run the **clone** command to pull a copy of a repository (your fork) down to your device on the current directory.</span></span> 

### <a name="authenticate-by-using-git-credential-manager"></a><span data-ttu-id="f63bd-161">Autenticar usando o Git Credential Manager</span><span class="sxs-lookup"><span data-stu-id="f63bd-161">Authenticate by using Git Credential Manager</span></span>
<span data-ttu-id="f63bd-162">Se você tiver instalado a versão mais recente do Git para Windows e aceitado a instalação padrão, o Git Credential Manager estará habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f63bd-162">If you installed the latest version of Git for Windows and accepted the default installation, Git Credential Manager is enabled by default.</span></span> <span data-ttu-id="f63bd-163">O Git Credential Manager facilita muito a autenticação porque você não precisa lembrar do token de acesso pessoal ao restabelecer as conexões autenticadas e remotas com o GitHub.</span><span class="sxs-lookup"><span data-stu-id="f63bd-163">Git Credential Manager makes authentication much easier, because you don't need to recall your personal access token when re-establishing authenticated connections and remotes with GitHub.</span></span>

1. <span data-ttu-id="f63bd-164">Execute o comando **clone** fornecendo o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="f63bd-164">Run the **clone** command, by providing the repository name.</span></span> <span data-ttu-id="f63bd-165">A clonagem baixa (clone) o repositório com fork em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="f63bd-165">Cloning downloads (clone) the forked repository on your local computer.</span></span> 

    > [!Tip]
    > <span data-ttu-id="f63bd-166">Você pode obter a URL do GitHub do fork para o comando de clonagem no botão **Clonar ou baixar** na interface do usuário do GitHub:</span><span class="sxs-lookup"><span data-stu-id="f63bd-166">You can get your fork's GitHub URL for the clone command from the **Clone or download** button in the GitHub UI:</span></span>
    >
    > ![Clonar ou baixar](./media/contribute-get-started-setup-local/clone-or-download.png)

    <span data-ttu-id="f63bd-168">Lembre-se de especificar o caminho até o *seu fork* durante o processo de clonagem e não até o repositório principal do qual você criou o fork.</span><span class="sxs-lookup"><span data-stu-id="f63bd-168">Be sure to specify the path to *your fork* during the cloning process, not the main repository from which you created the fork.</span></span> <span data-ttu-id="f63bd-169">Caso contrário, não é possível contribuir com as alterações.</span><span class="sxs-lookup"><span data-stu-id="f63bd-169">Otherwise, you cannot contribute changes.</span></span> <span data-ttu-id="f63bd-170">Seu fork é referenciado por meio da sua conta de usuário pessoal do GitHub, como `github.com/<github-username>/<repo>`.</span><span class="sxs-lookup"><span data-stu-id="f63bd-170">Your fork is referenced through your personal GitHub user account, such as `github.com/<github-username>/<repo>`.</span></span>

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    <span data-ttu-id="f63bd-171">Seu comando clone deve ter aparência semelhante à deste exemplo:</span><span class="sxs-lookup"><span data-stu-id="f63bd-171">Your clone command should look similar to this example:</span></span>

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. <span data-ttu-id="f63bd-172">Quando solicitado, insira suas credenciais do GitHub.</span><span class="sxs-lookup"><span data-stu-id="f63bd-172">When you're prompted, enter your GitHub credentials.</span></span>

    ![Logon no GitHub](./media/contribute-get-started-setup-local/github-login.png)

3. <span data-ttu-id="f63bd-174">Quando solicitado, insira o código de autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="f63bd-174">When you're prompted, enter your two-factor authentication code.</span></span>

    ![Autenticação de dois fatores do GitHub](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > <span data-ttu-id="f63bd-176">Suas credenciais serão salvas e usadas para autenticar as próximas solicitações do GitHub.</span><span class="sxs-lookup"><span data-stu-id="f63bd-176">Your credentials will be saved and used to authenticate future GitHub requests.</span></span> <span data-ttu-id="f63bd-177">É necessário somente fazer essa autenticação uma vez por computador.</span><span class="sxs-lookup"><span data-stu-id="f63bd-177">You only need to do this authentication once per computer.</span></span> 

4. <span data-ttu-id="f63bd-178">O comando clone executa e baixa uma cópia dos arquivos de repositório do seu fork para uma nova pasta no disco local.</span><span class="sxs-lookup"><span data-stu-id="f63bd-178">The clone command runs and downloads a copy of the repository files from your fork into a new folder on the local disk.</span></span> <span data-ttu-id="f63bd-179">Uma nova pasta é criada dentro da pasta atual.</span><span class="sxs-lookup"><span data-stu-id="f63bd-179">A new folder is made within the current folder.</span></span> <span data-ttu-id="f63bd-180">Isso pode levar alguns minutos dependendo do tamanho do repositório.</span><span class="sxs-lookup"><span data-stu-id="f63bd-180">It may take a few minutes, depending on the repository size.</span></span> <span data-ttu-id="f63bd-181">É possível explorar a pasta para ver a estrutura após sua conclusão.</span><span class="sxs-lookup"><span data-stu-id="f63bd-181">You can explore the folder to see the structure once it is finished.</span></span>

## <a name="configure-remote-upstream"></a><span data-ttu-id="f63bd-182">Configurar upstream remoto</span><span class="sxs-lookup"><span data-stu-id="f63bd-182">Configure remote upstream</span></span>
<span data-ttu-id="f63bd-183">Após clonar o repositório, configure uma conexão remota somente leitura com o repositório principal nomeado **upstream**.</span><span class="sxs-lookup"><span data-stu-id="f63bd-183">After cloning the repository, set up a read-only remote connection to the main repository named **upstream**.</span></span> <span data-ttu-id="f63bd-184">Use a URL upstream para manter seu repositório local em sincroniza com as últimas alterações feitas pelos outros.</span><span class="sxs-lookup"><span data-stu-id="f63bd-184">You use the upstream URL to keep your local repository in sync with the latest changes made by others.</span></span> <span data-ttu-id="f63bd-185">O comando **git remote** é usado para definir o valor de configuração.</span><span class="sxs-lookup"><span data-stu-id="f63bd-185">The **git remote** command is used to set the configuration value.</span></span> <span data-ttu-id="f63bd-186">Use o comando **fetch** para atualizar as informações sobre o branch do repositório upstream.</span><span class="sxs-lookup"><span data-stu-id="f63bd-186">You use the **fetch** command to refresh the branch info from the upstream repository.</span></span>

1. <span data-ttu-id="f63bd-187">Se você estiver usando o **Git Credential Manager**, use os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="f63bd-187">If you're using **Git Credential Manager**, use the following commands.</span></span> <span data-ttu-id="f63bd-188">Substitua os espaços reservados \<repositório\> e \<organização\>.</span><span class="sxs-lookup"><span data-stu-id="f63bd-188">Replace the \<repo\> and \<organization\> placeholders.</span></span>
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. <span data-ttu-id="f63bd-189">Exiba os valores configurados e confirme que as URLs estão corretas.</span><span class="sxs-lookup"><span data-stu-id="f63bd-189">View the configured values and confirm the URLs are correct.</span></span> <span data-ttu-id="f63bd-190">Certifique-se de que as URLs de **origem** apontam para seu fork pessoal.</span><span class="sxs-lookup"><span data-stu-id="f63bd-190">Ensure the **origin** URLs point to your personal fork.</span></span> <span data-ttu-id="f63bd-191">Certifique-se de que as URLs **upstream** apontam para o repositório principal, como o MicrosoftDocs ou Azure.</span><span class="sxs-lookup"><span data-stu-id="f63bd-191">Ensure the **upstream** URLs point to the main repository, such as MicrosoftDocs or Azure.</span></span> 
   ```bash
   git remote -v 
   ```

   <span data-ttu-id="f63bd-192">É mostrado um exemplo de saída remota.</span><span class="sxs-lookup"><span data-stu-id="f63bd-192">Example remote output is shown.</span></span> <span data-ttu-id="f63bd-193">Uma conta do git fictícia nomeada MyGitAccount é configurada com um token de acesso pessoal para acessar o repositório azure-docs:</span><span class="sxs-lookup"><span data-stu-id="f63bd-193">A fictitious git account named MyGitAccount is configured with a personal access token to access the repo azure-docs:</span></span>
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. <span data-ttu-id="f63bd-194">Se você comete um erro, é possível remover o valor remoto.</span><span class="sxs-lookup"><span data-stu-id="f63bd-194">If you made a mistake, you can remove the remote value.</span></span> <span data-ttu-id="f63bd-195">Para remover o valor upstream, execute o comando `git remote remove upstream`.</span><span class="sxs-lookup"><span data-stu-id="f63bd-195">To remove the upstream value, run the command `git remote remove upstream`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f63bd-196">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f63bd-196">Next steps</span></span>
- <span data-ttu-id="f63bd-197">Para saber mais sobre como adicionar e atualizar conteúdo, prossiga para o [fluxo de trabalho de contribuição do GitHub](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="f63bd-197">To learn more about adding and updating content, continue to the [GitHub contribution workflow](how-to-write-workflows-major.md).</span></span>