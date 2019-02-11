---
title: ms-prod-missing
description: Explicação e resolução para o problema de compilação ms-prod-missing de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: ee29396a20345f6884a5bbc94aa25f48dafaff52
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713213"
---
# <a name="ms-prod-missing"></a>ms-prod-missing

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Missing attribute: ms.prod. If you specify ms.technology, you must also specify ms.prod.`

Use `ms.prod` para especificar os produtos locais. Para especificar informações mais detalhadas sobre `ms.prod`, opcionalmente, você pode especificar `ms.technology`, mas, se você especificar `ms.technology`, também deverá especificar `ms.prod`. Os valores de `ms.prod` e `ms.technology` devem ser um par válido.

## <a name="resolution"></a>Resolução

Confirme se o valor `ms.technology` especificado está correto para o artigo. Em seguida, adicione o valor `ms.prod` apropriado que é um pai válido para o `ms.technology`.

Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
