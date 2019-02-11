---
title: ms-service-missing
description: Explicação e resolução para o problema de compilação ms-service-missing de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: 2bc425726f82840565978072b2efdf13a1284ec0
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713075"
---
# <a name="ms-service-missing"></a>ms-service-missing

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Missing attribute: ms.service. If you specify ms.subservice, you must also specify ms.service.`

Use `ms.service` para especificar serviço de nuvem. Para especificar informações mais detalhadas sobre `ms.service`, você poderá especificar `ms.subservice` opcionalmente, mas se especificar `ms.subservice`, também deverá especificar `ms.service`. Os valores de `ms.service` e `ms.subservice` devem ser um par válido.

## <a name="resolution"></a>Resolução

Confirme se o valor `ms.subservice` especificado está correto para o artigo. Em seguida, adicione o valor `ms.service` apropriado que é um pai válido para o `ms.subservice`.

Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
