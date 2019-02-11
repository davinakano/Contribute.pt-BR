---
title: ms-component-deprecated
description: Explicação e resolução para o problema de compilação ms-component-deprecated de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4f89571e2d4c50439806fb26b9967a4b7588f4a9
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713144"
---
# <a name="ms-component-deprecated"></a>ms-component-deprecated

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
