---
title: Processo de revisão das solicitações de pull de documentos do .NET
description: Os documentos do .NET não têm ganchos de mesclagem de PR habilitados. Este artigo descreve o processo de PR para esses repositórios
ms.date: 01/-4/2019
ms.openlocfilehash: d8f35e328beffcbd5bac9f0f7313d8127fbeffb0
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713558"
---
# <a name="pull-request-review-process-for-the-net-docs-repositories"></a>Processo de revisão das solicitações de pull para repositórios de documentos do .NET

Muitos repositórios não têm ganchos de mesclagem de PR habilitados, que mesclam automaticamente os PRs secundários. Este artigo descreve o processo de revisão de PR para esses repositórios. O processo de revisão de PR foi criado com estas metas:

1. Publicar conteúdo de alta qualidade da equipe, membros da equipe de produto e membros da comunidade.
1. Fornecer comentários oportunos e práticos para autores de maneira consistente.
1. Facilitar a discussão entre autores e revisores.

Os processos continuam a evoluir conforme as equipes inovam e a plataforma amadurece.

## <a name="reviewers"></a>Revisores

Um dos membros da equipe de conteúdo examina cada PR. Os membros da equipe de conteúdo podem solicitar uma revisão de membros específicos da equipe de produto para verificar a exatidão técnica. A equipe de conteúdo usa recursos de propriedade de código do GitHub para solicitar automaticamente revisões de membros da equipe de conteúdo. Como parte desse processo, um revisor pode marcar outros membros da equipe para revisar PRs internos. Os membros da equipe veem as revisões solicitadas de membros da equipe e membros da comunidade na mesma fila.

Membros da comunidade podem revisar PRs e fazer comentários. No entanto, pelo menos um membro da equipe de conteúdo principal deve aprovar qualquer PR antes da mesclagem.

## <a name="review-process"></a>Plano de revisão

As revisões seguem um dos três caminhos com base no PR:

- **PRs pequenos** - PRs pequenos são uma única correção de bug: erros de ortografia, links desfeitos, pequenas alterações de código ou alterações semelhantes.
- **Grandes contribuições** - as grandes contribuições são edições significativas em um artigo existente, em novos artigos ou edições em vários artigos.
- **Trabalho em andamento** - os autores podem solicitar uma revisão em andamento abrindo um PR com a marca "[WIP]" no título. A marca "WIP" significa "Trabalho em andamento". 

O processamento usado pelo bot de CLA (Contrato de Licença do Colaborador) é uma boa diretriz para a distinção entre contribuições "pequenas" e "grandes". PRs que não exigem a assinatura do CLA provavelmente são "pequenos". PRs que exigem CLA provavelmente são "grandes".

### <a name="small-prs"></a>PRs pequenos

As alterações em PRs pequenos são revisadas para fins de precisão e verificadas usando o build do site de revisão. Como são pequenos, esses PRs não disparam uma revisão do artigo inteiro. 

Os revisores podem notar outras pequenas alterações que melhorariam um artigo. Se essas alterações também forem pequenas, sugira-as em comentários. Se as alterações sugeridas dispararem uma revisão maior, abra um problema e resolva-o mais tarde. 

### <a name="larger-changes"></a>Alterações maiores

PRs maiores passam por uma revisão mais completa. Tudo isto é verificado:

- O código de exemplo deve estar incluído no PR, na origem e como um arquivo zip para download.
- O código de exemplo é compilado e executado corretamente.
- O artigo descreve claramente as metas para o leitor, e essas metas são cumpridas.
- O artigo atende às [diretrizes de estilo e gramática](dotnet-style-guide.md) e segue nossos [princípios de voz e tom](dotnet-voice-tone.md).
- Todos os links devem ser resolvidos corretamente.

Os membros da equipe de conteúdo revisarão o PR e enviarão a revisão com comentários. Se somente pequenas alterações forem solicitadas, os membros da equipe "aprovam" o PR com os comentários. O autor pode resolver os comentários e mesclar o PR. A maioria das revisões solicita alterações e, quando essas alterações são feitas, o revisor faz outra revisão.

Se as edições exigirem uma revisão técnica, o revisor da equipe de conteúdo solicitará uma revisão do membro da equipe de produto apropriado.

### <a name="review-wip-pull-requests"></a>Solicitações de pull de "WIP" de revisão

Talvez os novos autores queiram receber feedback antecipado no processo. Eles podem abrir um PR e adicionar o rótulo "[WIP]" ao título. Em um comentário, podem solicitar uma revisão antecipada.

Esse tipo de revisão não é tão minucioso quanto a revisão completa de PR. A equipe de conteúdo fará comentários, mas não irá "aprovar" ou "solicitar alterações" usando o recurso de revisão do GitHub. Essas revisões antecipadas enfocam a estrutura do artigo: a estrutura de tópicos, o conteúdo geral e os exemplos. Elas não incluem uma verificação completa de gramática e links corretos.

## <a name="respond-to-reviews"></a>Responder às revisões

O autor atualiza o PR para responder aos comentários, marcando cada comentário abordado com a reação "+1" para indicar que ele foi resolvido. Se o autor não concordar com o comentário ou abordar o comentário em um local diferente, ele adicionará um comentário explicando sua alteração.

O autor faz uma menção com @-mentions ao revisor original em um comentário para solicitar uma nova revisão. 

## <a name="response-time-expectations"></a>Tempos de resposta esperados

Geralmente, os membros da equipe de conteúdo revisam PRs novo em dois dias úteis. Se a revisão demorar mais do que isso, um dos membros da equipe adicionará um comentário para confirmar a PR e definir as expectativas.

Depois que uma revisão for enviada, os autores devem tentar responder aos comentários em uma semana ou menos. Os voluntários podem não conseguir atender a essas expectativas devido a outros compromissos. Nesses casos, os membros da equipe perguntarão se o autor da comunidade atualizará o PR. Caso contrário, o membro da equipe atualizará e mesclará o PR para ele.
