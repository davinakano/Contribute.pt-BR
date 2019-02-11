---
title: ms-date-too-late
description: Explicação e resolução para o problema de compilação ms-date-too-late de Docs
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 863b13e55c2aaa2057920e3bd77ec75ab5945277
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713098"
---
# <a name="ms-date-too-late"></a><span data-ttu-id="a3b3c-103">ms-date-too-late</span><span class="sxs-lookup"><span data-stu-id="a3b3c-103">ms-date-too-late</span></span>

<span data-ttu-id="a3b3c-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="a3b3c-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="a3b3c-105">Aviso</span><span class="sxs-lookup"><span data-stu-id="a3b3c-105">Warning</span></span>

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

<span data-ttu-id="a3b3c-106">O atributo `ms.date` é usado para indicar "atualização", ou seja, quando o artigo foi revisado pela última vez para verificação da relevância, precisão, capturas de tela corretas e links operacionais.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-106">The `ms.date` attribute is used to indicate "freshness" - that is, when the article was last reviewed for relevance, accuracy, correct screen shots, and working links.</span></span> <span data-ttu-id="a3b3c-107">Portanto, não pode estar no futuro!</span><span class="sxs-lookup"><span data-stu-id="a3b3c-107">Therefore, it can't be in the future!</span></span> <span data-ttu-id="a3b3c-108">São permitidos cinco dias para contabilizar o tempo de liberação, como quando o conteúdo é congelado para o controle de qualidade durante a preparação para um evento importante.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-108">Five days are allowed to account for release time, such as when content is frozen for QA in preparation for a major event.</span></span>

## <a name="resolution"></a><span data-ttu-id="a3b3c-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="a3b3c-109">Resolution</span></span>

<span data-ttu-id="a3b3c-110">Especifique um `ms.date` que não ultrapasse cinco dias a partir de hoje, no formato MM/DD/AAAA.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-110">Specify an `ms.date` no more than five days from today, in format MM/DD/YYYY.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
