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
# <a name="ms-component-deprecated"></a><span data-ttu-id="10839-103">ms-component-deprecated</span><span class="sxs-lookup"><span data-stu-id="10839-103">ms-component-deprecated</span></span>

<span data-ttu-id="10839-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="10839-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="10839-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="10839-105">Suggestion</span></span>

`Deprecated attribute: ms.component. Use ms.subservice instead.`

<span data-ttu-id="10839-106">Use `ms.service` para especificar serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="10839-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="10839-107">Para especificar informações mais detalhadas sobre `ms.service`, você pode especificar `ms.subservice` opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="10839-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="10839-108">Não use `ms.component`. Ele foi preterido para este conteúdo.</span><span class="sxs-lookup"><span data-stu-id="10839-108">Don't use `ms.component`; it's deprecated for this content.</span></span>

## <a name="resolution"></a><span data-ttu-id="10839-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="10839-109">Resolution</span></span>

<span data-ttu-id="10839-110">Confirme se seu valor `ms.service` está correto para o artigo.</span><span class="sxs-lookup"><span data-stu-id="10839-110">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="10839-111">Em seguida, escolha um valor `ms.subservice` válido.</span><span class="sxs-lookup"><span data-stu-id="10839-111">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="10839-112">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="10839-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
