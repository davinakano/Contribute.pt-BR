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
# <a name="multiple-values"></a>multiple-values

**Em breve!**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Sugestão

`Single-valued attribute {attribute} has multiple values. Remove additional values.`

Você especificou mais de um valor para um atributo que só permite um valor.

`Single-valued attribute {attribute} is in multi-valued array format. Change to scalar format.`

Os atributos que não podem ter mais de um valor devem ser especificados no formato YML de valor único (escalar).

## <a name="resolution"></a>Resolução

Essa Sugestão aparecerá sempre que uma matriz de vários valores for usada para um atributo de valor único, seja com vários valores ou com um valor único na matriz.

O YML é compatível com os seguintes formatos de matriz para atributos de vários valores, como `ms.custom`:

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

Tais formatos não são válidos para atributos de valores únicos, como `author`.

Caso tenha especificado vários valores, analise os valores especificados e determine qual está certo. Remova os demais valores e especifique o valor único na mesma linha como o atributo sem colchetes, da seguinte maneira:

```yml
---
author: meganbradley
---
```

Se tiver uma matriz de valor único, altere-a para o formato escalar acima.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
