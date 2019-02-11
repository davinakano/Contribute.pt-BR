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
# <a name="ms-prod-and-technology-invalid"></a><span data-ttu-id="28827-103">ms-prod-and-technology-invalid</span><span class="sxs-lookup"><span data-stu-id="28827-103">ms-prod-and-technology-invalid</span></span>

<span data-ttu-id="28827-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="28827-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="28827-105">Aviso</span><span class="sxs-lookup"><span data-stu-id="28827-105">Warning</span></span>

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

<span data-ttu-id="28827-106">Use `ms.prod` para especificar os produtos locais.</span><span class="sxs-lookup"><span data-stu-id="28827-106">Use `ms.prod` to specify on-premises products.</span></span> <span data-ttu-id="28827-107">Para especificar informações mais detalhadas sobre `ms.prod`, opcionalmente, você pode especificar `ms.technology`.</span><span class="sxs-lookup"><span data-stu-id="28827-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`.</span></span> <span data-ttu-id="28827-108">Os valores de `ms.prod` e `ms.technology` devem ser um par válido.</span><span class="sxs-lookup"><span data-stu-id="28827-108">The values for `ms.prod` and `ms.technology` must be a valid pair.</span></span> <span data-ttu-id="28827-109">Seu valor `ms.prod` é inválido ou seu valor `ms.technology` não é um par válido com seu `ms.prod`.</span><span class="sxs-lookup"><span data-stu-id="28827-109">Either your `ms.prod` value is invalid, or your `ms.technology` value is not a valid pair with your `ms.prod`.</span></span>

## <a name="resolution"></a><span data-ttu-id="28827-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="28827-110">Resolution</span></span>

<span data-ttu-id="28827-111">Confirme se seu valor `ms.prod` está correto para o artigo.</span><span class="sxs-lookup"><span data-stu-id="28827-111">Confirm that your `ms.prod` value is correct for your article.</span></span> <span data-ttu-id="28827-112">Em seguida, escolha um valor `ms.technology` válido.</span><span class="sxs-lookup"><span data-stu-id="28827-112">Then choose a valid `ms.technology` value.</span></span>

<span data-ttu-id="28827-113">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="28827-113">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!-- Can we link to whitelist externally? -->

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
