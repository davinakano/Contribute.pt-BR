---
title: ms-prod-and-technology-invalid
description: Explicação e resolução para o problema de compilação ms-prod-and-technology-invalid de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 92e8b17c3b5c96d544d12d394534a494ada3b901
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713259"
---
# <a name="ms-prod-and-technology-invalid"></a>ms-prod-and-technology-invalid

**Em breve!**

## <a name="warning"></a>Aviso

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

Use `ms.prod` para especificar os produtos locais. Para especificar informações mais detalhadas sobre `ms.prod`, opcionalmente, você pode especificar `ms.technology`. Os valores de `ms.prod` e `ms.technology` devem ser um par válido. Seu valor `ms.prod` é inválido ou seu valor `ms.technology` não é um par válido com seu `ms.prod`.

## <a name="resolution"></a>Resolução

Confirme se seu valor `ms.prod` está correto para o artigo. Em seguida, escolha um valor `ms.technology` válido.

Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).

<!-- Can we link to whitelist externally? -->

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
