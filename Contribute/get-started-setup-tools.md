---
title: Instalar ferramentas de criação de conteúdo
description: Este artigo ajuda a baixar e instalar as ferramentas cliente necessárias para o Git e para editar arquivos de markdown.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1011c3fc829202a3df134ddc80eb05b8959b7bf6
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2018
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="2530c-103">Instalar ferramentas de criação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="2530c-103">Install content authoring tools</span></span>

<span data-ttu-id="2530c-104">Este artigo descreve as etapas para instalar de forma interativa ferramentas de cliente do git e Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2530c-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2530c-105">Instalar o [Git para Windows](https://git-scm.com/download/win)</span><span class="sxs-lookup"><span data-stu-id="2530c-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="2530c-106">Instalar o [Visual Studio Code](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="2530c-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>
> * <span data-ttu-id="2530c-107">Instalar o [Pacote de criação do Docs](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span><span class="sxs-lookup"><span data-stu-id="2530c-107">Install [Docs Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="2530c-108">Se você estiver fazendo apenas pequenas alterações em um artigo, *não* será necessário concluir as etapas nesse artigo e você poderá continuar diretamente para o [fluxo de trabalho de alterações rápidas](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="2530c-108">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>
> <span data-ttu-id="2530c-109">Incentivamos os principais colaboradores a concluírem estas etapas, que permitem usar o [Fluxo de trabalho de alterações importantes ou de execução longa](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="2530c-109">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](how-to-write-workflows-major.md).</span></span> <span data-ttu-id="2530c-110">Mesmo que você tenha permissões de gravação no repositório principal, *é altamente recomendável (e pré-requisito para seguir esse guia) que você crie o fork e clone o repositório*, para que você tenha permissões de leitura/gravação para armazenar suas alterações propostas no fork.</span><span class="sxs-lookup"><span data-stu-id="2530c-110">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="2530c-111">Instalar as ferramentas de cliente do git no Windows</span><span class="sxs-lookup"><span data-stu-id="2530c-111">Install Git client tools on Windows</span></span>

 <span data-ttu-id="2530c-112">Instale a versão mais recente das [ferramentas de cliente do Git da Software Freedom Conservancy](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="2530c-112">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="2530c-113">A instalação inclui o sistema de controle de versão do git e o git Bash, o aplicativo de linha de comando que você usa para interagir com o repositório git local.</span><span class="sxs-lookup"><span data-stu-id="2530c-113">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="2530c-114">Se você preferir uma GUI (Interface gráfica do usuário) em vez de uma CLI (Interface de linha de comando), consulte a [página GUI Clients (Clientes da GUI) disponível do Software Freedom Conservancy](https://git-scm.com/downloads/guis), o [GitHub Desktop do GitHub](https://desktop.github.com/) ou o [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) para conferir algumas opções populares.</span><span class="sxs-lookup"><span data-stu-id="2530c-114">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="2530c-115">Siga as instruções para o cliente escolhido para instalação e configuração.</span><span class="sxs-lookup"><span data-stu-id="2530c-115">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="2530c-116">No próximo artigo, você irá [Configurar um repositório git local](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="2530c-116">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="2530c-117">Recursos adicionais do git estão disponíveis aqui: [Terminologia do git](https://help.github.com/articles/github-glossary) | [Noções básicas do git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Aprender sobre o git e GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span><span class="sxs-lookup"><span data-stu-id="2530c-117">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="2530c-118">Entender os editores de Markdown</span><span class="sxs-lookup"><span data-stu-id="2530c-118">Understand Markdown editors</span></span>

<span data-ttu-id="2530c-119">Markdown é uma linguagem de marcação leve que é fácil de ler e de aprender.</span><span class="sxs-lookup"><span data-stu-id="2530c-119">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="2530c-120">Por isso, ela se tornou rapidamente um padrão do setor.</span><span class="sxs-lookup"><span data-stu-id="2530c-120">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="2530c-121">Para escrever artigos em Markdown, recomendamos que primeiro você baixe e instale um editor de Markdown.</span><span class="sxs-lookup"><span data-stu-id="2530c-121">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="2530c-122">O [Visual Studio Code](https://code.visualstudio.com/) é a ferramenta preferida para edição de Markdown na Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2530c-122">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="2530c-123">O [Atom](https://atom.io) é outra ferramenta popular para a edição de Markdown.</span><span class="sxs-lookup"><span data-stu-id="2530c-123">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="2530c-124">O texto de Markdown é salvo em arquivos com extensão .md.</span><span class="sxs-lookup"><span data-stu-id="2530c-124">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="2530c-125">Detalhes adicionais de como escrever com Markdown, incluindo as noções básicas de Markdown e os recursos compatíveis nas extensões de Markdown personalizadas do OPS serão abordados mais tarde em [Como usar Markdown](how-to-write-use-markdown.md).</span><span class="sxs-lookup"><span data-stu-id="2530c-125">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="2530c-126">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2530c-126">Visual Studio Code</span></span>

<span data-ttu-id="2530c-127">[Visual Studio Code](https://code.visualstudio.com/), também conhecido como o código do VS, é um editor leve que funciona no Windows, Linux e Mac.</span><span class="sxs-lookup"><span data-stu-id="2530c-127">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="2530c-128">Ele inclui integração com o git e suporte a extensões.</span><span class="sxs-lookup"><span data-stu-id="2530c-128">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="2530c-129">Faça o download e instale o [Código do VS](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="2530c-129">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="2530c-130">A home page do Código do VS deve detectar corretamente o seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2530c-130">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="2530c-131">Windows</span><span class="sxs-lookup"><span data-stu-id="2530c-131">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="2530c-132">Mac</span><span class="sxs-lookup"><span data-stu-id="2530c-132">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="2530c-133">Linux</span><span class="sxs-lookup"><span data-stu-id="2530c-133">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="2530c-134">Para iniciar o Código do VS e abrir a pasta atual, execute o comando `code .` na linha de comando ou shell do bash.</span><span class="sxs-lookup"><span data-stu-id="2530c-134">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="2530c-135">Se a pasta atual é parte de um repositório do git local, a integração do GitHub aparece no Visual Studio Code automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2530c-135">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="docs-authoring-pack"></a><span data-ttu-id="2530c-136">Pacote de Criação do Docs</span><span class="sxs-lookup"><span data-stu-id="2530c-136">Docs Authoring Pack</span></span>
<span data-ttu-id="2530c-137">Instale o Pacote de Criação do Docs para o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2530c-137">Install the Docs Authoring Pack for Visual Studio Code.</span></span> <span data-ttu-id="2530c-138">Este conjunto de extensões inclui a assistência básica de criação para ajudar ao gravar Markdown e uma funcionalidade de visualização que possibilita ver como o Markdown fica no estilo do site docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2530c-138">This set of extensions includes basic authoring assistance for help when writing Markdown, and a preview feature, so that you can see what the Markdown looks like in the style of the docs.microsoft.com site.</span></span>

   <span data-ttu-id="2530c-139">Visite esta [página do Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) e selecione **Instalar** ou pesquise por `docsmsft.docs-authoring-pack` na lista de extensões da janela do VS Code.</span><span class="sxs-lookup"><span data-stu-id="2530c-139">Visit this [marketplace page](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) and select **Install**, or search for `docsmsft.docs-authoring-pack` in your extensions list in the VS Code window.</span></span> 

   <span data-ttu-id="2530c-140">Acesse o Pacote de Criação do Docs pressionando Alt+M dentro do VS Code.</span><span class="sxs-lookup"><span data-stu-id="2530c-140">The Docs Authoring Pack is accessible by pressing Alt+M inside of VS Code.</span></span> <span data-ttu-id="2530c-141">A barra de ferramentas fica oculta por padrão, mas pode ser exibida.</span><span class="sxs-lookup"><span data-stu-id="2530c-141">The toolbar is hidden by default but can be shown.</span></span> <span data-ttu-id="2530c-142">Edite as configurações do VS Code (Ctrl+vírgula) e adicione a configuração do usuário `"markdown.showToolbar": true` para mostrar a barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="2530c-142">Edit the VS Code settings (Control+comma) and adding user setting `"markdown.showToolbar": true` to show the toolbar.</span></span>

   <span data-ttu-id="2530c-143">Confira mais informações na página [Pacote de Criação do Docs](how-to-write-docs-auth-pack.md).</span><span class="sxs-lookup"><span data-stu-id="2530c-143">For more information, see the [Docs Authoring Pack](how-to-write-docs-auth-pack.md) page.</span></span>


## <a name="next-steps"></a><span data-ttu-id="2530c-144">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2530c-144">Next steps</span></span>

<span data-ttu-id="2530c-145">Agora que você está pronto para [Configurar um repositório git local](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="2530c-145">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
