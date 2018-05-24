---
title: Visão geral do guia do colaborador do Microsoft Docs
description: O guia descreve como é possível contribuir com a documentação da Microsoft do site docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 04/17/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1cda40c890e5b30e6e1e10f3bcee0278f8004653
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2018
---
# <a name="microsoft-docs-contributor-guide-overview"></a>Visão geral do guia do colaborador do Microsoft Docs

Bem-vindo ao Guia do Colaborador do [docs.microsoft.com](https://docs.microsoft.com) (Docs)!

Diversos de nossos conjuntos de documentação são de software livre, hospedados no GitHub. Mais e mais equipes estão adotando este modelo, a todo momento. Até mesmo conjuntos de documentos que não são totalmente de software livre têm repositórios voltados para o público em que você é convidado a realizar solicitações de pull. Ele simplifica e aprimora a comunicação entre os engenheiros de produto, as equipes de conteúdo e nossos clientes. Trabalhar com software livre tem diversas vantagens:

- O planejamento de repositórios em software livre permite obter comentários sobre quais documentos são mais necessários.
- A análise de repositórios em software livre permite publicar o conteúdo mais útil em nossa primeira versão.
- A atualização de repositórios em software livre facilita o aprimoramento contínuo do conteúdo.

A experiência do usuário em [docs.microsoft.com](https://docs.microsoft.com) integra fluxos de trabalho do [GitHub](https://github.com) diretamente para tornar o uso ainda mais fácil. Comece [editando o documento que você está exibindo](#quick-edits-to-existing-documents). Ou então, ajude [analisando novos tópicos](#review-open-prs) ou [crie registros de problemas de qualidade](#create-quality-issues).

> [!IMPORTANT]
> Todos os repositórios que publicam no docs.microsoft.com adotaram o [Código de Conduta de Software Livre da Microsoft](https://opensource.microsoft.com/codeofconduct/) ou o [Código de Conduta de .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obter mais informações, consulte as [Perguntas frequentes do código de conduta](https://opensource.microsoft.com/codeofconduct/faq/). Ou entre em contato com [opencode@microsoft.com](mailto:opencode@microsoft.com) ou [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) com perguntas ou comentários.<br>
>
> As correções secundárias ou esclarecimentos para a documentação e exemplos de código em repositório públicos são cobertos pelos [Termos de Uso de docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). As alterações novas ou significativas geram um comentário na solicitação de pull, pedindo o envio de um CLA (Contrato de Licença de Contribuição) online, caso você não seja um funcionário da Microsoft. Você deve preencher o formulário online antes que possamos examinar ou aceitar sua solicitação de pull.

## <a name="quick-edits-to-existing-documents"></a>Edições rápidas a documentos existentes

As edições rápidas simplificam o processo de relatar e corrigir pequenos erros e omissões em documentos. Apesar de todos os esforços, pequenos erros gramaticais e ortográficos aparecem em nossos documentos publicados. Embora você possa criar registros de problemas para relatar erros, é mais rápido e mais fácil criar uma PR (solicitação de pull) para corrigir o problema propriamente dito. Praticamente todos os artigos exibem um botão de edição, conforme mostrado na figura a seguir. Clicar no botão **Editar** leva você ao arquivo de origem no GitHub.

![Localização do link de edição](./media/index/edit-article.png)

Em seguida, clique no ícone de lápis mostrado na figura a seguir para editar o artigo.

> [!NOTE]
> Se o ícone de lápis está esmaecido, você precisa fazer logon na sua conta do GitHub ou criar uma conta. Faça suas alterações no editor da Web. Você pode clicar na guia **Visualizar alterações** para verificar a formatação de sua alteração.

![Localização do ícone de lápis](./media/index/editicon.png)

Após ter feito suas alterações, role até a parte inferior da página. Insira um título e uma descrição para sua solicitação de pull e clique em **Propor alteração de arquivo** conforme mostrado na figura a seguir:

![propondo a sua alteração](./media/index/submit-pull-request.png)

É isso! Membros de equipes de conteúdo examinarão e mesclarão sua solicitação de pull. Você poderá obter alguns comentários solicitando alterações caso você tenha feito alterações mais significativas.

A interface do usuário de edição do GitHub responde às suas permissões no repositório. As imagens anteriores são precisas para colaboradores que não têm permissões de gravação para o repositório de destino. O GitHub cria automaticamente um fork para o repositório de destino em sua conta. Se você tem acesso de gravação para o repositório de destino, o GitHub cria nele um novo branch. O nome do branch tem o formato **\<GitHubId\>-patch-n** usando sua ID do GitHub e um identificador numérico para o branch do patch.

Usamos solicitações de pull para todas as alterações, até mesmo para colaboradores que têm acesso de gravação. A maioria dos repositórios têm o branch `master` protegido, de modo que as atualizações precisam ser emitidas como solicitações de pull.

A experiência de edição no navegador é a melhor para alterações secundárias ou esporádicas. Se você fizer colaborações grandes ou usar recursos avançados do Git (como gerenciamento de branch, resolução avançada de conflitos de mesclagem), precisará [criar um fork do repositório e trabalhar localmente](how-to-write-workflows-major.md).

## <a name="review-open-prs"></a>Examinar as solicitações de pull em aberto

Você pode ler novos tópicos antes de eles serem publicados, verificando as solicitações de pull em aberto atualmente. As revisões seguem o processo do [fluxo do GitHub](https://guides.github.com/introduction/flow/). Você pode ver as atualizações propostas ou novos artigos em repositórios públicos. Revise-os e adicione seus comentários. Confira qualquer um dos nossos repositórios de documentos e verifique as PRs (solicitações de pull) em aberto para áreas que lhe interessam. Os comentários da comunidade sobre atualizações propostas ajudam toda a comunidade.

## <a name="create-quality-issues"></a>Criar registros de problemas de qualidade

Nossos documentos são um trabalho contínuo em andamento. Bons registros de problemas nos ajudam a concentrar nossos esforços nas maiores prioridades para a comunidade. Quanto mais detalhes você fornecer, mais útil será o registro do problema. Diga-nos quais informações você buscou. Diga-nos quais termos de pesquisa você usou. Se você não souber como começar, diga-nos como você deseja explorar tecnologia com a qual não está familiarizado.

Os registros de problemas iniciam a conversa sobre o que é necessário. A equipe de conteúdo responderá a esses registros de problemas com ideias sobre o que podemos adicionar e pedirá suas opiniões. Quando criarmos um rascunho, pediremos a você que [revise a solicitação de pull](#review-open-prs).

## <a name="get-more-involved"></a>Aumente seu nível de envolvimento

Outros tópicos ajudam você a começar a contribuir de modo produtivo com o Microsoft Docs. Eles explicam o trabalho com repositórios do GitHub, ferramentas de Markdown e extensões usadas na plataforma do Microsoft Docs.
