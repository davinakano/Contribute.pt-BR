---
title: Como contribuir com o docs.microsoft.com
description: Este artigo descreve diferentes maneiras como você pode contribuir com conteúdo para o docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 01/17/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: bc6f9c314eda5f0d950da049374a7a157f16782a
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-contribute-to-docsmicrosoftcom"></a>Como contribuir com o docs.microsoft.com

Há várias maneiras de participar da melhoria do conteúdo que compõe o [docs.microsoft.com](https://docs.microsoft.com):

- É possível [registrar problemas](#create-issues) para recomendar novos artigos ou melhorar os artigos existentes.
- É possível [editar rapidamente](#quick-edits) artigos para fazer pequenas alterações no editor online do GitHub.
- É possível [analisar os rascunhos dos novos artigos](#review-new-articles) para garantir qualidade e exatidão técnica.
- É possível [criar novos artigos](#create-new-articles) para tópicos quando você quer ajudar a impulsionar a história do conteúdo.
- É possível [atualizar](#update-samples) ou [criar](#create-samples) amostras para melhorar os exemplos de código que reforçam conceitos importantes.

Neste artigo, você conhecerá as diferentes maneiras de colaborar, verá como realizar cada uma dessas tarefas e encontrará ponteiros para obter mais informações sobre cada uma dessas tarefas.

Nossos repositórios públicos são hospedados no [GitHub](https://wwww.GitHub.com).  Você precisará criar uma conta no GitHub para participar dos nossos repositórios de documentação.

Você também precisará de um editor de texto para carregar os documentos. Recomendamos o [Visual Studio Code](https://www.visualstudio.com/code). Você deve ter uma compreensão básica da sintaxe do [Markdown](https://daringfireball.net/projects/markdown/syntax).

Se você estiver adicionando ou modificando exemplos, será preciso um ambiente de desenvolvimento. Recomendamos o [Visual Studio](https://www.visualstudio.com) em PC e Mac ou o [Visual Studio Code](https://www.visualstudio.com/code) em todas as plataformas.

## <a name="create-issues"></a>Registrar problemas

Se você encontrar omissões ou imprecisões em um artigo, registre um problema em relação a este artigo. A maneira mais fácil de encontrar o local correto é clicar no botão "Edit" no seu navegador, o que o levará para o artigo de origem no repositório público correto do GitHub. A partir daí, você pode recuperar a URL da fonte do artigo da sua barra de endereços. Clique em "Create issue" (Registrar problema) para gerar um novo tópico no artigo.

> [!NOTE]
> Se você encontrar problemas que pode corrigir com pequenas edições, como erros de digitação ou questões gramaticais, você pode economizar o seu e o nosso tempo [enviando a correção](#quick-edits) usando o navegador para editar a fonte.

A maioria dos nossos repositórios públicos contém modelos para novos problemas, os quais vão instruir você sobre como fornecer as informações necessárias para a correção do problema.

Você também pode contribuir com novos problemas quando não encontrar as informações de que precisa. O processo é o mesmo: criar um novo problema em um dos repositórios públicos de documentos. Diga o que você estava procurando, o que queria fazer e por que os artigos não ajudaram da maneira esperada.

## <a name="review-new-articles"></a>Examinar novos artigos

Se você estiver trabalhando em um software novo, possivelmente CTP ou beta, é possível que estejamos desenvolvendo os documentos enquanto você explora a tecnologia. Você pode encontrar os documentos em processo em nossos repositórios públicos. Se você tiver comentários, ajude-nos a torná-los melhores antes de os lançarmos.

Novos artigos são revisados em público, usando o processo de [Fluxo do GitHub](https://guides.github.com/introduction/flow/). Confira qualquer um dos nossos repositórios de documentos e verifique as solicitações de pull (PRs) abertas. Revisões e comentários sobre qualquer solicitação de pull aberta são bem-vindos. Isso nos ajuda a publicar o melhor conteúdo em nossa primeira versão, em vez de aguardar comentários após o lançamento.

Estamos procurando maneiras de melhorar a precisão técnica, clareza das descrições e precisão gramatical.

## <a name="quick-edits"></a>Edições rápidas

As edições rápidas são uma maneira de fazer pequenas correções usando o editor baseado no navegador. Se você encontrar pequenos erros ortográficos ou gramaticais, ou APIs nomeadas incorretamente, pule a etapa de registro de um problema fazendo a edição e o envio de uma PR.

Neste artigo, clique no botão "Edit" (Editar), geralmente na parte superior direita da página, faça as edições e clique em "Submit PR" (Enviar PR) na parte inferior da página. Vamos examinar a PR e mesclá-la enquanto fazemos nossa revisão diária de PR.

## <a name="create-new-articles"></a>Criar novos artigos

Se houver conceitos em que você tenha interesse e deseje explicar a outras pessoas, crie os artigos e envie uma PR.

A criação de novos artigos exige tempo, e agradecemos o seu tempo e as suas contribuições. Queremos estar envolvidos no processo desde o início para garantir que as nossas diretrizes e estilo sejam seguidos desde o princípio. Recomendamos as seguintes etapas:

1. [Registre um problema](#create-issues) descrevendo o que está faltando e como resolver.
1. Comente sobre o problema, dizendo que gostaria de trabalhar nele e sugerindo uma estrutura e um resumo para o artigo.
1. Responderemos com sugestões. Elas podem incluir links para artigos relacionados, sugestões de amostras ou como o artigo será organizado.
1. Depois que concordarmos com a estrutura, crie um fork do repositório e comece a trabalhar.
1. No começo do processo, abra uma PR, com "[WIP]" no início do título.
1. Um dos principais colaboradores fará os comentários iniciais.
1. Continue escrevendo, @-mention a pessoa que revisou o primeiro rascunho quando estiver pronto para receber mais comentários.
1. Remova o texto "[WIP]" quando estiver pronto para a revisão final.
1. Responder aos comentários
1. Os principais colaboradores mesclarão a PR.

Há alguns pontos que valem a pena expandir em ambas as listas. Em geral, seguimos o processo do [Fluxo do GitHub](https://guides.github.com/introduction/flow/) para revisar o conteúdo o quanto antes. Dessa forma, podemos concordar sobre onde um artigo deve ficar no sumário, qual é a vantagem que o leitor obterá do novo artigo e o escopo de qualquer exemplo que você criar. Podemos fazer as correções de curso necessárias antecipadamente, antes que você invista muito tempo de escrita.

## <a name="update-samples"></a>Atualizar exemplos

Alguns exemplos podem ter sido escritos originalmente várias versões atrás, usando práticas que não são mais recomendadas. Talvez você possa querer ajudar a atualizar esses exemplos. Ou você pode observar que uma simples alteração do nome da variável poderia aumentar a clareza de uma explicação.

Os códigos de exemplo exibidos com cada artigo fazem parte dos programas que são criados e testados com frequência em nosso sistema de CI.

Para fazer pequenas atualizações, encontre a fonte no repositório apropriado, faça a alteração de código no navegador e envie uma PR. Nosso sistema de CI criará as alterações e mesclaremos a PR após a conclusão.

Para alterações em larga escala, faça o fork do repositório e realize as alterações no seu ambiente de desenvolvimento favorito. Adicione alguns testes para garantir que as alterações estejam funcionando como desejado. Envie uma PR e nós a revisaremos.

Com todas as alterações de código, siga as convenções de código existentes para o código de exemplo que você está modificando. Nossos padrões de código de repositórios de exemplo refletirão os das equipes de produtos correspondentes. Verifique cada repositório para obter orientações específicas.

> [!NOTE]
> Nós mesmos estamos trabalhando para seguir essas orientações. Alguns dos exemplos são anteriores aos nossos padrões atuais e não foram atualizados ainda. Estamos trabalhando para fazer com que todos que executam códigos de exemplo sejam exibidos em trabalhando, testado, exemplos.

## <a name="create-samples"></a>Criar exemplos

Você também pode criar novos exemplos que demonstrem conceitos ou cenários. Todos os exemplos devem ser acompanhados por um artigo que explique as principais informações do exemplo.

Se o seu novo exemplo complementar um artigo existente, adicione uma referência ao exemplo nesse artigo. Se não, trabalhe conosco para [escrever o artigo](#create-new-articles) que acompanhará o exemplo.

Em todos os casos, o nosso código de exemplo segue as convenções de codificação usadas pelas equipes de produtos relacionadas. Uma exceção é que temos maiores chances de usar variáveis digitadas explicitamente no lugar de digitadas implicitamente (declarado com `var`) para dar maior clareza quando essas declarações estão inclusas no artigo.

Siga o processo de exemplo descrito no início da seção para [novos artigos](#create-new-articles) para que possamos examinar o código no início do processo de desenvolvimento.
