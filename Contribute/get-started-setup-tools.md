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
# <a name="install-content-authoring-tools"></a>Instalar ferramentas de criação de conteúdo

Este artigo descreve as etapas para instalar de forma interativa ferramentas de cliente do git e Visual Studio Code.
> [!div class="checklist"]
> * Instalar o [Git para Windows](https://git-scm.com/download/win)
> * Instalar o [Visual Studio Code](https://code.visualstudio.com/)
> * Instalar o [Pacote de criação do Docs](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)

>[!IMPORTANT]
> Se você estiver fazendo apenas pequenas alterações em um artigo, *não* será necessário concluir as etapas nesse artigo e você poderá continuar diretamente para o [fluxo de trabalho de alterações rápidas](index.md#quick-edits-to-existing-documents).
>
> Incentivamos os principais colaboradores a concluírem estas etapas, que permitem usar o [Fluxo de trabalho de alterações importantes ou de execução longa](how-to-write-workflows-major.md). Mesmo que você tenha permissões de gravação no repositório principal, *é altamente recomendável (e pré-requisito para seguir esse guia) que você crie o fork e clone o repositório*, para que você tenha permissões de leitura/gravação para armazenar suas alterações propostas no fork.

## <a name="install-git-client-tools-on-windows"></a>Instalar as ferramentas de cliente do git no Windows

 Instale a versão mais recente das [ferramentas de cliente do Git da Software Freedom Conservancy](https://git-scm.com/download/). A instalação inclui o sistema de controle de versão do git e o git Bash, o aplicativo de linha de comando que você usa para interagir com o repositório git local.

Se você preferir uma GUI (Interface gráfica do usuário) em vez de uma CLI (Interface de linha de comando), consulte a [página GUI Clients (Clientes da GUI) disponível do Software Freedom Conservancy](https://git-scm.com/downloads/guis), o [GitHub Desktop do GitHub](https://desktop.github.com/) ou o [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) para conferir algumas opções populares.

Siga as instruções para o cliente escolhido para instalação e configuração.

No próximo artigo, você irá [Configurar um repositório git local](get-started-setup-local.md).

   Recursos adicionais do git estão disponíveis aqui: [Terminologia do git](https://help.github.com/articles/github-glossary) | [Noções básicas do git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Aprender sobre o git e GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)

## <a name="understand-markdown-editors"></a>Entender os editores de Markdown

Markdown é uma linguagem de marcação leve que é fácil de ler e de aprender. Por isso, ela se tornou rapidamente um padrão do setor. Para escrever artigos em Markdown, recomendamos que primeiro você baixe e instale um editor de Markdown.  O [Visual Studio Code](https://code.visualstudio.com/) é a ferramenta preferida para edição de Markdown na Microsoft. O [Atom](https://atom.io) é outra ferramenta popular para a edição de Markdown.

O texto de Markdown é salvo em arquivos com extensão .md.

Detalhes adicionais de como escrever com Markdown, incluindo as noções básicas de Markdown e os recursos compatíveis nas extensões de Markdown personalizadas do OPS serão abordados mais tarde em [Como usar Markdown](how-to-write-use-markdown.md).

## <a name="visual-studio-code"></a>Visual Studio Code

[Visual Studio Code](https://code.visualstudio.com/), também conhecido como o código do VS, é um editor leve que funciona no Windows, Linux e Mac. Ele inclui integração com o git e suporte a extensões.

Faça o download e instale o [Código do VS](https://code.visualstudio.com/). A home page do Código do VS deve detectar corretamente o seu sistema operacional.

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> Para iniciar o Código do VS e abrir a pasta atual, execute o comando `code .` na linha de comando ou shell do bash. Se a pasta atual é parte de um repositório do git local, a integração do GitHub aparece no Visual Studio Code automaticamente.

## <a name="docs-authoring-pack"></a>Pacote de Criação do Docs
Instale o Pacote de Criação do Docs para o Visual Studio Code. Este conjunto de extensões inclui a assistência básica de criação para ajudar ao gravar Markdown e uma funcionalidade de visualização que possibilita ver como o Markdown fica no estilo do site docs.microsoft.com.

   Visite esta [página do Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) e selecione **Instalar** ou pesquise por `docsmsft.docs-authoring-pack` na lista de extensões da janela do VS Code. 

   Acesse o Pacote de Criação do Docs pressionando Alt+M dentro do VS Code. A barra de ferramentas fica oculta por padrão, mas pode ser exibida. Edite as configurações do VS Code (Ctrl+vírgula) e adicione a configuração do usuário `"markdown.showToolbar": true` para mostrar a barra de ferramentas.

   Confira mais informações na página [Pacote de Criação do Docs](how-to-write-docs-auth-pack.md).


## <a name="next-steps"></a>Próximas etapas

Agora que você está pronto para [Configurar um repositório git local](get-started-setup-local.md).
