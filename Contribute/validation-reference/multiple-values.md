---
title: multiple-values
description: Explicação e resolução para o problema de build do Docs multiple-values
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/19/2019
ms.prod: non-product-specific
ms.openlocfilehash: 8cee25b07e5bd1e019f8d270888eff73292d8e7c
ms.sourcegitcommit: ae71ca811c143deb6214147c7eea8704444a6093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56465106"
---
# <a name="multiple-values"></a><span data-ttu-id="0cd1f-103">multiple-values</span><span class="sxs-lookup"><span data-stu-id="0cd1f-103">multiple-values</span></span>

<span data-ttu-id="0cd1f-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="0cd1f-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="0cd1f-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="0cd1f-105">Suggestion</span></span>

`Single-valued attribute {attribute} has multiple values. Remove additional values.`

<span data-ttu-id="0cd1f-106">Você especificou mais de um valor para um atributo que só permite um valor.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-106">You specified more than one value for an attribute that is ony allowed one value.</span></span>

`Single-valued attribute {attribute} is in multi-valued array format. Change to scalar format.`

<span data-ttu-id="0cd1f-107">Os atributos que não podem ter mais de um valor devem ser especificados no formato YML de valor único (escalar).</span><span class="sxs-lookup"><span data-stu-id="0cd1f-107">Attributes that aren't allowed to have more than one value must be specified in the single-valued (scalar) YML format.</span></span>

## <a name="resolution"></a><span data-ttu-id="0cd1f-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="0cd1f-108">Resolution</span></span>

<span data-ttu-id="0cd1f-109">Essa Sugestão aparecerá sempre que uma matriz de vários valores for usada para um atributo de valor único, seja com vários valores ou com um valor único na matriz.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-109">You get this Suggestion any time a multi-valued array is used for a single-valued attribute, either with multiple values or a single value in the array.</span></span>

<span data-ttu-id="0cd1f-110">O YML é compatível com os seguintes formatos de matriz para atributos de vários valores, como `ms.custom`:</span><span class="sxs-lookup"><span data-stu-id="0cd1f-110">YML supports the following array formats for multi-valued attributes, such as `ms.custom`:</span></span>

```yml
---
# comma-separated bracketed list:
ms.custom: [WIP, generated-via-CI]

# each value on its own line:
ms.custom:
  - WIP
  - generated-via-CI
---
```

<span data-ttu-id="0cd1f-111">Tais formatos não são válidos para atributos de valores únicos, como `author`.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-111">These formats aren't valid for single-valued attributes, such as `author`.</span></span>

<span data-ttu-id="0cd1f-112">Caso tenha especificado vários valores, analise os valores especificados e determine qual está certo.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-112">If you specified multiple values, review the specified values and determine which is correct.</span></span> <span data-ttu-id="0cd1f-113">Remova os demais valores e especifique o valor único na mesma linha como o atributo sem colchetes, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0cd1f-113">Remove other values and specify the single value on the same line as the attribute with no brackets, as follows:</span></span>

```yml
---
author: meganbradley
---
```

<span data-ttu-id="0cd1f-114">Se tiver uma matriz de valor único, altere-a para o formato escalar acima.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-114">If you have a single-valued array, change it to the scalar format above.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
