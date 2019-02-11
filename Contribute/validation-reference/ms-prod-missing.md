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
# <a name="ms-prod-missing"></a><span data-ttu-id="a2959-103">ms-prod-missing</span><span class="sxs-lookup"><span data-stu-id="a2959-103">ms-prod-missing</span></span>

<span data-ttu-id="a2959-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="a2959-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="a2959-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="a2959-105">Suggestion</span></span>

`Missing attribute: ms.prod. If you specify ms.technology, you must also specify ms.prod.`

<span data-ttu-id="a2959-106">Use `ms.prod` para especificar os produtos locais.</span><span class="sxs-lookup"><span data-stu-id="a2959-106">Use `ms.prod` to specify on-premises products.</span></span> <span data-ttu-id="a2959-107">Para especificar informações mais detalhadas sobre `ms.prod`, opcionalmente, você pode especificar `ms.technology`, mas, se você especificar `ms.technology`, também deverá especificar `ms.prod`.</span><span class="sxs-lookup"><span data-stu-id="a2959-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`, but if you specify `ms.technology`, you must also specify `ms.prod`.</span></span> <span data-ttu-id="a2959-108">Os valores de `ms.prod` e `ms.technology` devem ser um par válido.</span><span class="sxs-lookup"><span data-stu-id="a2959-108">The values for `ms.prod` and `ms.technology` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="a2959-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="a2959-109">Resolution</span></span>

<span data-ttu-id="a2959-110">Confirme se o valor `ms.technology` especificado está correto para o artigo.</span><span class="sxs-lookup"><span data-stu-id="a2959-110">Confirm that the `ms.technology` value you've specified is correct for your article.</span></span> <span data-ttu-id="a2959-111">Em seguida, adicione o valor `ms.prod` apropriado que é um pai válido para o `ms.technology`.</span><span class="sxs-lookup"><span data-stu-id="a2959-111">Then add the appropriate `ms.prod` value that is a valid parent for the `ms.technology`.</span></span>

<span data-ttu-id="a2959-112">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="a2959-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
