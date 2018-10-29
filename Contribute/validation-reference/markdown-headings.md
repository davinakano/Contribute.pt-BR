---
title: Cabeçalhos do Markdown
description: Descreve os requisitos para cabeçalhos do Markdown.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 05/03/2017
ms.openlocfilehash: 18beb815fdf7caad3e8e675e8d79853d8a5688f2
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084414"
---
# <a name="markdown-headings"></a>Cabeçalhos do Markdown

Estes requisitos de validação se aplicam aos cabeçalhos de arquivos markdown OPS.

## <a name="h1"></a>H1

`H1` se refere ao primeiro cabeçalho em um arquivo markdown. Quando publicado no docs.microsoft.com, o H1 é exibido na parte superior da página com uma fonte grande.

O H1 é criado ao iniciar uma linha com uma barra única (`#`) seguida por um espaço e pelo texto do cabeçalho. Por exemplo, o H1 deste artigo é:

```md
# Markdown headings
```

As seguintes regras se aplicam aos cabeçalhos H1:

- Um H1 precisa estar presente no arquivo.
- Só pode haver um H1.
- O H1 precisa ter conteúdo.

  ```markdown
  # 
  This is not allowed.
  ```
- É necessário um espaço entre o `#` e o conteúdo do H1. Um H1 sem espaço não renderiza como cabeçalho na página publicada.

  ```markdown
  #This looks bad on the site.
  ```
- O H1 precisa ser o primeiro conteúdo no arquivo após o cabeçalho de metadados YML. Não deve haver conteúdo, como texto ou imagens, entre o fim do cabeçalho YML e o H1.

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- O elemento HTML para cabeçalhos de primeiro nível, `<h1>`, não deve ser usado. Use a sintaxe de markdown (`# `).
- O H1 não deve ter mais de 100 caracteres. Esta é uma diretriz de estilo.

## <a name="h2---h6"></a>H2 – H6

H2 (`## `) a H6 (`###### `) são permitidos no OPS. Use os cabeçalhos de markdown, e não o HTML (`<h2>` - `<h6>`), para criar cabeçalhos.
