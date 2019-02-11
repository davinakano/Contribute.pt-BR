---
title: ms-prod-or-service-missing
description: Explicação e resolução para o problema de compilação ms-prod-or-service-missing de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/20/2018
ms.prod: non-product-specific
ms.openlocfilehash: f4d5bc7537ec851ce7ac1de3be2208fd74cbe37f
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713535"
---
# <a name="ms-prod-or-service-missing"></a>ms-prod-or-service-missing

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Missing attribute: either ms.prod or ms.service is required. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a>Resolução

`ms.prod` ou `ms.service` é obrigatório e ambos não podem estar presentes: `ms.prod` é usado para produtos locais; `ms.service` é usado para serviços de nuvem. Determine qual é o apropriado para seu artigo, verifique se o valor está correto e remova o outro campo.

Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]