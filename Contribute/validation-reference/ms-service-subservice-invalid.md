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
# <a name="ms-service-and-subservice-invalid"></a><span data-ttu-id="4d5b2-103">ms-service-and-subservice-invalid</span><span class="sxs-lookup"><span data-stu-id="4d5b2-103">ms-service-and-subservice-invalid</span></span>

<span data-ttu-id="4d5b2-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="4d5b2-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="4d5b2-105">Aviso</span><span class="sxs-lookup"><span data-stu-id="4d5b2-105">Warning</span></span>

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

<span data-ttu-id="4d5b2-106">Use `ms.service` para especificar serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4d5b2-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="4d5b2-107">Para especificar informações mais detalhadas sobre `ms.service`, você pode especificar `ms.subservice` opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="4d5b2-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="4d5b2-108">Os valores de `ms.service` e `ms.subservice` devem ser um par válido.</span><span class="sxs-lookup"><span data-stu-id="4d5b2-108">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span> <span data-ttu-id="4d5b2-109">Seu valor `ms.service` é inválido ou seu valor `ms.subservice` não é um par válido com seu `ms.service`.</span><span class="sxs-lookup"><span data-stu-id="4d5b2-109">Either your `ms.service` value is invalid, or your `ms.subservice` value is not a valid pair with your `ms.service`.</span></span>

## <a name="resolution"></a><span data-ttu-id="4d5b2-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="4d5b2-110">Resolution</span></span>

<span data-ttu-id="4d5b2-111">Confirme se seu valor `ms.service` está correto para o artigo.</span><span class="sxs-lookup"><span data-stu-id="4d5b2-111">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="4d5b2-112">Em seguida, escolha um valor `ms.subservice` válido.</span><span class="sxs-lookup"><span data-stu-id="4d5b2-112">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="4d5b2-113">Os valores válidos podem ser encontrados [neste site interno da Microsoft](https://docsmetadatatool.azurewebsites.net/whitelists).</span><span class="sxs-lookup"><span data-stu-id="4d5b2-113">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
