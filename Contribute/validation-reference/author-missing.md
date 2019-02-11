---
title: author-missing
description: Explicação e resolução para o problema de compilação author-missing de Docs.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: cba9788c113101fc93bffa674702b2bed95afbcb
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713029"
---
# <a name="author-missing"></a>author-missing

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Missing attribute: author. Add a valid GitHub ID.`

O atributo `author` identifica o autor do artigo pela ID do GitHub. 

## <a name="resolution"></a>Resolução

Adicione a ID do GitHub do autor ao cabeçalho YML:

```markdown
---
author: meganbradley
ms.author: mbradley
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]