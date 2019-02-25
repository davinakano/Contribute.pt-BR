---
title: ms-date-missing
description: Explicação e resolução para o problema de build do Docs ms-date-missing
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: d7697c8449e451879c137d9d6cdf42327e597be6
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431451"
---
# <a name="ms-date-missing"></a><span data-ttu-id="28377-103">ms-date-missing</span><span class="sxs-lookup"><span data-stu-id="28377-103">ms-date-missing</span></span>

<span data-ttu-id="28377-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="28377-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="28377-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="28377-105">Suggestion</span></span>

`Missing attribute: ms.date. A freshness date is required for this content. Add a date in format MM/DD/YYYY.`

<span data-ttu-id="28377-106">Essa data é usada para indicar "atualização", ou seja, quando o artigo foi revisado pela última vez para verificação da relevância, precisão, capturas de tela corretas e links operacionais.</span><span class="sxs-lookup"><span data-stu-id="28377-106">This date is used to indicate "freshness" - that is, when the article was last reviewed for relevance, accuracy, correct screen shots, and working links.</span></span> <span data-ttu-id="28377-107">Essa data não é igual à última data em que o artigo foi *publicado* e será exibida na página se `ms.date` não for explicitamente especificada.</span><span class="sxs-lookup"><span data-stu-id="28377-107">This is not the same as the last date the article was *published*, which will show on the page if `ms.date` is not explicitly specified.</span></span>

## <a name="resolution"></a><span data-ttu-id="28377-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="28377-108">Resolution</span></span>

<span data-ttu-id="28377-109">Confirme se o artigo está atualizado e sem conteúdo corrompido e adicione uma data válida no formato MM/DD/AAAA:</span><span class="sxs-lookup"><span data-stu-id="28377-109">Confirm that the article is up-to-date with no broken content, then add a valid date in the format MM/DD/YYYY:</span></span>

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
