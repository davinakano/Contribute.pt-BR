---
title: deprecated-attribute
description: Explicação e resolução para o problema de build do Docs deprecated-attribute
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4f9ddc611d401bc7003e1b7d378517d5e374da87
ms.sourcegitcommit: a2c8317ccf8b56371773c84f4960a44787ce8666
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56322666"
---
# <a name="deprecated-attribute"></a>deprecated-attribute

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Deprecated attribute: ms.component. Use ms.subservice instead.`

Use `ms.service` para especificar serviço de nuvem. Para especificar informações mais detalhadas sobre `ms.service`, você pode especificar `ms.subservice` opcionalmente. Não use `ms.component`. Ele foi preterido para este conteúdo.

## <a name="resolution"></a>Resolução

Confirme se seu valor `ms.service` está correto para o artigo. Em seguida, escolha um valor `ms.subservice` válido.

Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
