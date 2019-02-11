---
title: ms-prod-and-service
description: Explicação e resolução para o problema de compilação ms-prod-and-service de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 42e6f063c8b3d97386b2655b49a19a3e103d6b3b
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713190"
---
# <a name="ms-prod-and-service"></a><span data-ttu-id="16d54-103">ms-prod-and-service</span><span class="sxs-lookup"><span data-stu-id="16d54-103">ms-prod-and-service</span></span>

<span data-ttu-id="16d54-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="16d54-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="16d54-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="16d54-105">Suggestion</span></span>

`Both ms.prod and ms.service can't be specified. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a><span data-ttu-id="16d54-106">Resolução</span><span class="sxs-lookup"><span data-stu-id="16d54-106">Resolution</span></span>

<span data-ttu-id="16d54-107">`ms.prod` ou `ms.service` é obrigatório e ambos não podem estar presentes: `ms.prod` é usado para produtos locais; `ms.service` é usado para serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="16d54-107">Either `ms.prod` or `ms.service` is required, and they can't both be present: `ms.prod` is used for on-premises products; `ms.service` is used for cloud services.</span></span> <span data-ttu-id="16d54-108">Determine qual é o apropriado para seu artigo, verifique se o valor está correto e remova o outro campo.</span><span class="sxs-lookup"><span data-stu-id="16d54-108">Determine which is appropriate for your article, verify that the value is correct, and remove the other field.</span></span>

<span data-ttu-id="16d54-109">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="16d54-109">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
