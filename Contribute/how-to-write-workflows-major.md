---
title: Fluxo de trabalho de contribuição do GitHub para alterações importantes ou de execução longa
description: Este artigo mostra como usar o fluxo de trabalho "principal" do colaborador para fazer contribuições nos artigos do docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 08/30/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: e26b62923eed22d5b2005b1d84dc4ae240d262b1
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469545"
---
# <a name="github-contribution-workflow-for-major-or-long-running-changes"></a>Fluxo de trabalho de contribuição do GitHub para alterações importantes ou de execução longa

> [!IMPORTANT]
> Todos os repositórios que publicam no docs.microsoft.com adotaram o [Código de Conduta de Software Livre da Microsoft](https://opensource.microsoft.com/codeofconduct/) ou o [Código de Conduta de .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obter mais informações, consulte as [Perguntas frequentes do código de conduta](https://opensource.microsoft.com/codeofconduct/faq/). Ou entre em contato com [opencode@microsoft.com](mailto:opencode@microsoft.com) ou [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) com perguntas ou comentários.<br>
>
> As correções secundárias ou esclarecimentos para a documentação e exemplos de código em repositório públicos são cobertos pelos [Termos de Uso de docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). As alterações novas ou significativas gerarão um comentário na solicitação de pull, pedindo o envio de um CLA (Contrato de Licença de Contribuição) online, caso você não seja um funcionário da Microsoft. Será necessário completar o formulário online antes de sua solicitação de pull poder ser mesclada.

## <a name="overview"></a>Visão geral

Este fluxo de trabalho é adequado para um colaborador que precise fazer uma alteração importante ou que será um colaborador frequente de um repositório. Os colaboradores frequentes normalmente têm alterações constantes (execução longa), que passam por vários ciclos de build/validação/preparo ou que abrangem vários dias, antes da aprovação e da mesclagem da solicitação de pull.

Entre os exemplos desses tipos de colaborações estão:

[!INCLUDE[contribute-major-changes-change-definition](includes/contribute-how-to-write-workflows-major-change-definition.md)]

### <a name="terminology"></a>Terminologia

Antes de começar, vamos revisar alguns dos termos do Git/GitHub e monikers usados neste fluxo de trabalho. Não se preocupe em compreendê-los agora. Apenas saiba que você vai aprender sobre eles e poderá consultar esta seção novamente quando precisar verificar uma definição.

| Nome | Descrição |
|-----------|-------------|
|fork|Normalmente usado como um substantivo ao referir-se a uma cópia de um repositório principal do GitHub. Na prática, um fork é só outro repositório. Mas é especial, no fato de que o GitHub mantém uma conexão com o repositório principal/pai. Às vezes, é usado como verbo, como em "Primeiro você deve criar o fork do repositório".|
|remote|Uma conexão nomeada com um repositório remoto, como o remoto de "origin" ou "upstream". O Git se refere a eles como remotos porque eles são usados para referenciar um repositório hospedado em outro computador. Nesse fluxo de trabalho, um remote é sempre um repositório do GitHub.|
|origin|O nome atribuído à conexão entre o repositório local e o repositório do qual ele foi clonado. Neste fluxo de trabalho, origin representa a conexão com seu fork. Às vezes, é usado como um moniker para o próprio repositório de origem, como em “Lembre-se de enviar suas alterações por push para a origem”.|
|upstream|Assim como o remote origin, upstream é uma conexão nomeada com outro repositório. Neste fluxo de trabalho, upstream representa a conexão entre seu repositório local e o repositório principal, a partir do qual seu fork foi criado. Às vezes, é usado como um moniker para o próprio repositório upstream, como em “Lembre-se de enviar suas alterações por push do upstream”.|

## <a name="workflow"></a>Fluxo de trabalho

>[!IMPORTANT]
> Conclua as etapas na seção [Instalação](get-started-setup-github.md), caso ainda não tenha feito isso. Esta seção aborda a configuração da conta do GitHub, a instalação do Git Bash e de um editor de Markdown, a criação de uma bifurcação e a configuração do repositório local. Se você não estiver familiarizado com os conceitos do Git e do GitHub, como repositório ou branch, primeiro examine as [Noções básicas do Git/GitHub](git-github-fundamentals.md).

Neste fluxo de trabalho, as alterações fluem em um ciclo repetitivo. Começando no repositório local de seu dispositivo, elas fluem de volta para seu fork do GitHub, para o repositório principal do GitHub, e de volta para o local novamente à medida que você incorporar alterações de outros colaboradores.

### <a name="use-github-flow"></a>Use o fluxo do GitHub

Lembre-se do que viu em [Noções básicas do Git e do GitHub](git-github-fundamentals.md#git), que um repositório do Git contém um branch mestre, além de outros branches em progresso que não foram integrados ao mestre. Sempre que você introduz um conjunto de alterações relacionadas logicamente, uma prática recomendada é criar um *branch de trabalho* para gerenciar as alterações no fluxo de trabalho. Chamamos de branch de trabalho, pois é um espaço de trabalho para iterar/refinar as alterações, até que elas possam ser reintegradas ao branch mestre.

O isolamento de alterações relacionadas em um branch específico permite que você controle e introduza essas alterações de forma independente, direcionando-as a um período de lançamento específico no ciclo de publicação. Na realidade, dependendo do tipo de trabalho que você faz, é possível que você acabe criando vários branches de trabalho no repositório. Não é incomum trabalhar em vários branches simultaneamente, cada um representando um projeto diferente.

>[!TIP]
>Fazer suas alterações no branch mestre *não* é uma prática recomendada. Imagine que você use o branch mestre para introduzir um conjunto de alterações para um lançamento de recurso com prazo. Você termina as alterações e está esperando para lançá-las. Enquanto isso, você recebe uma solicitação urgente para corrigir algo. Você faz a alteração em um arquivo no branch mestre e, em seguida, publica a alteração. Neste exemplo, você publica acidentalmente tanto a correção *quanto* as alterações que você estava esperando para lançar em uma data específica.

Agora, vamos criar um novo branch de trabalho em seu repositório local, a fim de capturar suas alterações propostas. Cada cliente git é diferente, por isso, confira a Ajuda do seu cliente preferido. Confira uma visão geral do processo no Guia do GitHub em [Fluxo do GitHub](https://guides.github.com/introduction/flow/).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Próximas etapas

É isso! Você fez uma colaboração ao conteúdo do docs.microsoft.com!

- Para saber mais sobre tópicos como Markdown e Sintaxe de extensões de Markdown, continue na seção “Noções básicas de escrita”.
