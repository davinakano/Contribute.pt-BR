---
title: ms-date-too-late
description: Explicação e resolução para o problema de compilação ms-date-too-late de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 863b13e55c2aaa2057920e3bd77ec75ab5945277
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713098"
---
# <a name="ms-date-too-late"></a>ms-date-too-late

**Em breve!**

## <a name="warning"></a>Aviso

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

O atributo `ms.date` é usado para indicar "atualização", ou seja, quando o artigo foi revisado pela última vez para verificação da relevância, precisão, capturas de tela corretas e links operacionais. Portanto, não pode estar no futuro! São permitidos cinco dias para contabilizar o tempo de liberação, como quando o conteúdo é congelado para o controle de qualidade durante a preparação para um evento importante.

## <a name="resolution"></a>Resolução

Especifique um `ms.date` que não ultrapasse cinco dias a partir de hoje, no formato MM/DD/AAAA.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
