---
title: ms-date-too-late
description: Explicação e resolução para o problema de build do Docs ms-date-too-late
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: b38392e9f297e4ee4147ca7fc65f938b5cd53403
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431474"
---
# <a name="ms-date-too-late"></a>ms-date-too-late

**Em breve!**

## <a name="warning"></a>Aviso

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

O atributo `ms.date` é usado para indicar "atualização", ou seja, quando o artigo foi revisado pela última vez para verificação da relevância, precisão, capturas de tela corretas e links operacionais. Portanto, não pode estar no futuro! São permitidos cinco dias para contabilizar o tempo de liberação, como quando o conteúdo é congelado para o controle de qualidade durante a preparação para um evento importante.

## <a name="resolution"></a>Resolução

Especifique uma `ms.date` que não ultrapasse cinco dias a partir de hoje, no formato MM/DD/AAAA:

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
