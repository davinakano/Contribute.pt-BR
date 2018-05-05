---
title: Fluxo de trabalho de colaboração do GitHub para alterações secundárias ou infrequentes
description: Este artigo mostra como usar o fluxo de trabalho "secundário" do colaborador para fazer contribuições nos artigos do docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 10/06/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 8bde44d502e1942b0870df9dd546a97705c2bb4f
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="github-contribution-workflow-for-minor-or-infrequent-changes"></a>Fluxo de trabalho de colaboração do GitHub para alterações secundárias ou infrequentes

> [!IMPORTANT]
> Todos os repositórios que publicam no docs.microsoft.com adotaram o [Código de Conduta de Software Livre da Microsoft](https://opensource.microsoft.com/codeofconduct/) ou o [Código de Conduta de .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obter mais informações, consulte as [Perguntas frequentes do código de conduta](https://opensource.microsoft.com/codeofconduct/faq/). Ou entre em contato com [opencode@microsoft.com](mailto:opencode@microsoft.com) ou [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) com perguntas ou comentários.<br>
>
> As correções secundárias ou esclarecimentos para a documentação e exemplos de código em repositório públicos são cobertos pelos [Termos de Uso de docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). As alterações novas ou significativas gerarão um comentário na solicitação de pull, pedindo o envio de um CLA (Contrato de Licença de Contribuição) online, caso você não seja um funcionário da Microsoft. Precisamos que você preencha o formulário online antes de aceitarmos sua solicitação de pull.

## <a name="overview"></a>Visão geral

Este fluxo de trabalho é adequado para fazer alterações secundárias ou pouco frequentes, usando o editor de Markdown na Web do GitHub. O editor do GitHub é limitado em relação ao que pode ser feito, pois a interface do usuário não dá suporte a todas as operações e cenários de criação do Git. Se você precisar fazer colaborações grandes ou se precisar de suporte para recursos avançados do Git (como gerenciamento de branch, resolução avançada de conflitos de mesclagem), veja o [fluxo de trabalho de alterações importantes ou de execução longa](full-workflow.md).

## <a name="procedure-for-using-the-github-editor-to-propose-your-changes"></a>Procedimento para usar o editor do GitHub para propor alterações

1. Navegue até o repositório do GitHub correspondente ao artigo e até o arquivo de Markdown. Você pode usar um dos seguintes métodos:

   - Localize o artigo procurando nos arquivos de Markdown do repositório do GitHub relacionado.
   - Acesse o artigo no [docs.microsoft.com](https://docs.microsoft.com/) e selecione o link **Editar** no canto superior direito da página.

     ![Localização do link de edição](./media/light-workflow/contributetogit.png)

2. Selecione o ícone de lápis **Editar este arquivo** para entrar no modo de edição:

    ![Localização do ícone de lápis](./media/light-workflow/editicon.png)

3. Faça alterações usando Markdown na guia **Editar arquivo** e visualize suas alterações na guia **Visualizar alterações**. Usar o editor é muito simples, mas se você precisar de assistência, confira os seguintes guias:

   - [Como usar Markdown](how-to-write-use-markdown.md)
   - [Criação de arquivos no GitHub](https://github.com/blog/1327-creating-files-on-github)
   - [Carregar arquivos em seus repositórios](https://github.com/blog/2105-upload-files-to-your-repositories)

4. Role até a parte inferior da página, onde um destes procedimentos é exibido:

   - **Propor alteração no arquivo**: aparece quando você tem acesso somente leitura ao repositório, como [editar arquivos no repositório de outro usuário](https://help.github.com/articles/editing-files-in-another-user-s-repository/). Nesse caso, o GitHub criará um branch de "patch" em seu fork do repositório (e criará automaticamente um fork, se ele não existir). Depois de selecionar **Propor alterações no arquivo**, uma página **Comparando alterações** será exibida para que você possa verificar suas alterações. Depois, selecione o botão **Criar solicitação de pull** para enviar suas alterações para a fila de solicitações de pull e prossiga para a [próxima seção](#pull-request-processing).

   - **Confirmar alterações**: aparece quando você tem permissões de gravação para um repositório, como [editar arquivos em seu próprio repositório](https://help.github.com/articles/editing-files-in-your-repository/). Nesse caso, o GitHub fornece duas opções para salvar suas alterações:

     - **Confirmar diretamente no `<branch-name>` branch**, em que `<branch-name>` é o nome do branch no qual você estava quando selecionou o botão **Editar**. Isso aplica suas alterações diretamente no branch, em vez de usar uma solicitação de pull. Agora você terminou!

     - **Criar um novo branch para essa confirmação e iniciar uma solicitação de pull**, que solicita um nome padrão para criar um novo branch. Depois de selecionar **Propor alterações no arquivo**, uma página **Comparando alterações** será exibida para que você possa verificar suas alterações. Depois, selecione o botão **Criar solicitação de pull** para enviar suas alterações para a fila de solicitações de pull e prossiga para a [próxima seção](#pull-request-processing).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Próximas etapas

- Continue nos artigos “Noções básicas de escrita” para saber mais sobre tópicos como Markdown, Sintaxe de extensões de Markdown e muito mais.
