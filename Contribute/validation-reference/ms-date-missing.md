---
title: ms-date-missing
description: Explicação e resolução para o problema de build do Docs ms-date-missing
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: d7697c8449e451879c137d9d6cdf42327e597be6
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431451"
---
# <a name="ms-date-missing"></a>ms-date-missing

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Missing attribute: ms.date. A freshness date is required for this content. Add a date in format MM/DD/YYYY.`

Essa data é usada para indicar "atualização", ou seja, quando o artigo foi revisado pela última vez para verificação da relevância, precisão, capturas de tela corretas e links operacionais. Essa data não é igual à última data em que o artigo foi *publicado* e será exibida na página se `ms.date` não for explicitamente especificada.

## <a name="resolution"></a>Resolução

Confirme se o artigo está atualizado e sem conteúdo corrompido e adicione uma data válida no formato MM/DD/AAAA:

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
