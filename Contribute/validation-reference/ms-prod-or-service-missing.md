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
# <a name="ms-prod-or-service-missing"></a><span data-ttu-id="b77c3-103">ms-prod-or-service-missing</span><span class="sxs-lookup"><span data-stu-id="b77c3-103">ms-prod-or-service-missing</span></span>

<span data-ttu-id="b77c3-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="b77c3-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="b77c3-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="b77c3-105">Suggestion</span></span>

`Missing attribute: either ms.prod or ms.service is required. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a><span data-ttu-id="b77c3-106">Resolução</span><span class="sxs-lookup"><span data-stu-id="b77c3-106">Resolution</span></span>

<span data-ttu-id="b77c3-107">`ms.prod` ou `ms.service` é obrigatório e ambos não podem estar presentes: `ms.prod` é usado para produtos locais; `ms.service` é usado para serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b77c3-107">Either `ms.prod` or `ms.service` is required, and they can't both be present: `ms.prod` is used for on-premises products; `ms.service` is used for cloud services.</span></span> <span data-ttu-id="b77c3-108">Determine qual é o apropriado para seu artigo, verifique se o valor está correto e remova o outro campo.</span><span class="sxs-lookup"><span data-stu-id="b77c3-108">Determine which is appropriate for your article, verify that the value is correct, and remove the other field.</span></span>

<span data-ttu-id="b77c3-109">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="b77c3-109">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]