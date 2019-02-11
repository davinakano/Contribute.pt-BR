---
title: ms-service-and-subservice-invalid
description: Explicação e resolução para o problema de compilação ms-service-and-subservice-invalid de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 6a2efc5cee04d7721e7a8fe1602ca24dc09ca7fd
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713121"
---
# <a name="ms-service-and-subservice-invalid"></a>ms-service-and-subservice-invalid

**Em breve!**

## <a name="warning"></a>Aviso

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

Use `ms.service` para especificar serviço de nuvem. Para especificar informações mais detalhadas sobre `ms.service`, você pode especificar `ms.subservice` opcionalmente. Os valores de `ms.service` e `ms.subservice` devem ser um par válido. Seu valor `ms.service` é inválido ou seu valor `ms.subservice` não é um par válido com seu `ms.service`.

## <a name="resolution"></a>Resolução

Confirme se seu valor `ms.service` está correto para o artigo. Em seguida, escolha um valor `ms.subservice` válido.

Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
