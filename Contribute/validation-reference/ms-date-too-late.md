---
title: ms-date-too-late
description: Explicação e resolução para o problema de build do Docs ms-date-too-late
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: b38392e9f297e4ee4147ca7fc65f938b5cd53403
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431474"
---
# <a name="ms-date-too-late"></a><span data-ttu-id="d832a-103">ms-date-too-late</span><span class="sxs-lookup"><span data-stu-id="d832a-103">ms-date-too-late</span></span>

<span data-ttu-id="d832a-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="d832a-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="d832a-105">Aviso</span><span class="sxs-lookup"><span data-stu-id="d832a-105">Warning</span></span>

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

<span data-ttu-id="d832a-106">O atributo `ms.date` é usado para indicar "atualização", ou seja, quando o artigo foi revisado pela última vez para verificação da relevância, precisão, capturas de tela corretas e links operacionais.</span><span class="sxs-lookup"><span data-stu-id="d832a-106">The `ms.date` attribute is used to indicate "freshness" - that is, when the article was last reviewed for relevance, accuracy, correct screen shots, and working links.</span></span> <span data-ttu-id="d832a-107">Portanto, não pode estar no futuro!</span><span class="sxs-lookup"><span data-stu-id="d832a-107">Therefore, it can't be in the future!</span></span> <span data-ttu-id="d832a-108">São permitidos cinco dias para contabilizar o tempo de liberação, como quando o conteúdo é congelado para o controle de qualidade durante a preparação para um evento importante.</span><span class="sxs-lookup"><span data-stu-id="d832a-108">Five days are allowed to account for release time, such as when content is frozen for QA in preparation for a major event.</span></span>

## <a name="resolution"></a><span data-ttu-id="d832a-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="d832a-109">Resolution</span></span>

<span data-ttu-id="d832a-110">Especifique uma `ms.date` que não ultrapasse cinco dias a partir de hoje, no formato MM/DD/AAAA:</span><span class="sxs-lookup"><span data-stu-id="d832a-110">Specify an `ms.date` no more than five days from today, in format MM/DD/YYYY:</span></span>

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
