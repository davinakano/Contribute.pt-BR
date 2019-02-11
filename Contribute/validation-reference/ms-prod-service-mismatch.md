---
title: ms-prod-service-mismatch
description: Explicação e resolução para o problema de compilação ms-prod-service-mismatch de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4a3cf8bc5435972f0442ca1d41d4147e1ea00d78
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713167"
---
# <a name="ms-prod-service-mismatch"></a>ms-prod-service-mismatch

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Invalid attribute pair: ms.prod and ms.subservice. You can only pair ms.prod with ms.technology.`

`Invalid attribute pair: ms.service and ms.technology. You can only pair ms.service with ms.subservice.`

Use `ms.prod` para especificar os produtos locais e `ms.service` para serviços de nuvem. Para especificar informações mais detalhadas sobre `ms.prod`, opcionalmente, você pode especificar `ms.technology`. Para especificar informações mais detalhadas sobre `ms.service`, você pode especificar `ms.subservice`. Não é possível usar `ms.prod` com `ms.subservice` ou `ms.service` com `ms.technology`.

## <a name="resolution"></a>Resolução

Primeiro, verifique se você escolheu o atributo pai correto (`ms.prod` ou `ms.service`) para seu artigo. Em seguida, adicione o campo filho apropriado com um valor pareado válido. Remova os campos extras.

Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
