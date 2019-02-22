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
# <a name="author-missing"></a>author-missing

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Missing attribute: author. Add a valid GitHub ID.`

O atributo `author` identifica o autor do artigo pela ID do GitHub. 

## <a name="resolution"></a>Resolução

Adicione a ID do GitHub do autor ao cabeçalho YML:

```yml
---
author: meganbradley
ms.author: mbradley
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]