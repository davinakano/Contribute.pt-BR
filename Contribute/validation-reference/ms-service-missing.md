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
# <a name="ms-service-missing"></a><span data-ttu-id="f6d94-103">ms-service-missing</span><span class="sxs-lookup"><span data-stu-id="f6d94-103">ms-service-missing</span></span>

<span data-ttu-id="f6d94-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="f6d94-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="f6d94-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="f6d94-105">Suggestion</span></span>

`Missing attribute: ms.service. If you specify ms.subservice, you must also specify ms.service.`

<span data-ttu-id="f6d94-106">Use `ms.service` para especificar serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="f6d94-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="f6d94-107">Para especificar informações mais detalhadas sobre `ms.service`, você poderá especificar `ms.subservice` opcionalmente, mas se especificar `ms.subservice`, também deverá especificar `ms.service`.</span><span class="sxs-lookup"><span data-stu-id="f6d94-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`, but if you specify `ms.subservice`, you must also specify `ms.service`.</span></span> <span data-ttu-id="f6d94-108">Os valores de `ms.service` e `ms.subservice` devem ser um par válido.</span><span class="sxs-lookup"><span data-stu-id="f6d94-108">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="f6d94-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="f6d94-109">Resolution</span></span>

<span data-ttu-id="f6d94-110">Confirme se o valor `ms.subservice` especificado está correto para o artigo.</span><span class="sxs-lookup"><span data-stu-id="f6d94-110">Confirm that the `ms.subservice` value you've specified is correct for your article.</span></span> <span data-ttu-id="f6d94-111">Em seguida, adicione o valor `ms.service` apropriado que é um pai válido para o `ms.subservice`.</span><span class="sxs-lookup"><span data-stu-id="f6d94-111">Then add the appropriate `ms.service` value that is a valid parent for the `ms.subservice`.</span></span>

<span data-ttu-id="f6d94-112">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="f6d94-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
