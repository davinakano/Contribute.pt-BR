---
title: author-missing
description: Explicação e resolução para o problema de compilação author-missing de Docs.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 89725dcfbd4ec266071c45a003748021b480bbc2
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431520"
---
# <a name="author-missing"></a><span data-ttu-id="b59d4-103">author-missing</span><span class="sxs-lookup"><span data-stu-id="b59d4-103">author-missing</span></span>

<span data-ttu-id="b59d4-104">**Em breve!**</span><span class="sxs-lookup"><span data-stu-id="b59d4-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="b59d4-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="b59d4-105">Suggestion</span></span>

`Missing attribute: author. Add a valid GitHub ID.`

<span data-ttu-id="b59d4-106">O atributo `author` identifica o autor do artigo pela ID do GitHub.</span><span class="sxs-lookup"><span data-stu-id="b59d4-106">The `author` attribute identifies the author of the article by GitHub ID.</span></span> 

## <a name="resolution"></a><span data-ttu-id="b59d4-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="b59d4-107">Resolution</span></span>

<span data-ttu-id="b59d4-108">Adicione a ID do GitHub do autor ao cabeçalho YML:</span><span class="sxs-lookup"><span data-stu-id="b59d4-108">Add the author's GitHub ID to the YML header:</span></span>

```yml
---
author: meganbradley
ms.author: mbradley
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]