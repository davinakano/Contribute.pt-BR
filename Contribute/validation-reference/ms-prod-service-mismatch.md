---
title: ms-prod-service-mismatch
description: Explicação e resolução para o problema de compilação ms-prod-service-mismatch de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4a3cf8bc5435972f0442ca1d41d4147e1ea00d78
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713167"
---
# <a name="ms-prod-service-mismatch"></a><span data-ttu-id="8d336-103">ms-prod-service-mismatch</span><span class="sxs-lookup"><span data-stu-id="8d336-103">ms-prod-service-mismatch</span></span>

<span data-ttu-id="8d336-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="8d336-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="8d336-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="8d336-105">Suggestion</span></span>

`Invalid attribute pair: ms.prod and ms.subservice. You can only pair ms.prod with ms.technology.`

`Invalid attribute pair: ms.service and ms.technology. You can only pair ms.service with ms.subservice.`

<span data-ttu-id="8d336-106">Use `ms.prod` para especificar os produtos locais e `ms.service` para serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8d336-106">Use `ms.prod` to specify on-premises products; `ms.service` for cloud services.</span></span> <span data-ttu-id="8d336-107">Para especificar informações mais detalhadas sobre `ms.prod`, opcionalmente, você pode especificar `ms.technology`.</span><span class="sxs-lookup"><span data-stu-id="8d336-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`.</span></span> <span data-ttu-id="8d336-108">Para especificar informações mais detalhadas sobre `ms.service`, você pode especificar `ms.subservice`.</span><span class="sxs-lookup"><span data-stu-id="8d336-108">To specify more detailed information about `ms.service`, you can specify `ms.subservice`.</span></span> <span data-ttu-id="8d336-109">Não é possível usar `ms.prod` com `ms.subservice` ou `ms.service` com `ms.technology`.</span><span class="sxs-lookup"><span data-stu-id="8d336-109">You can't use `ms.prod` with `ms.subservice` or `ms.service` with `ms.technology`.</span></span>

## <a name="resolution"></a><span data-ttu-id="8d336-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="8d336-110">Resolution</span></span>

<span data-ttu-id="8d336-111">Primeiro, verifique se você escolheu o atributo pai correto (`ms.prod` ou `ms.service`) para seu artigo.</span><span class="sxs-lookup"><span data-stu-id="8d336-111">First, verify that you have selected the correct parent attribute (`ms.prod` or `ms.service`) for your article.</span></span> <span data-ttu-id="8d336-112">Em seguida, adicione o campo filho apropriado com um valor pareado válido.</span><span class="sxs-lookup"><span data-stu-id="8d336-112">Then, add the appropriate child field with a valid paired value.</span></span> <span data-ttu-id="8d336-113">Remova os campos extras.</span><span class="sxs-lookup"><span data-stu-id="8d336-113">Remove any extra fields.</span></span>

<span data-ttu-id="8d336-114">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="8d336-114">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
