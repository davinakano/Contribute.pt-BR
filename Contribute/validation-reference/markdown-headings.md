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
# <a name="markdown-headings"></a><span data-ttu-id="7a446-103">Cabeçalhos do Markdown</span><span class="sxs-lookup"><span data-stu-id="7a446-103">Markdown headings</span></span>

<span data-ttu-id="7a446-104">Estes requisitos de validação se aplicam aos cabeçalhos de arquivos markdown OPS.</span><span class="sxs-lookup"><span data-stu-id="7a446-104">The following validation requirements apply to headings in OPS Markdown files.</span></span>

## <a name="h1"></a><span data-ttu-id="7a446-105">H1</span><span class="sxs-lookup"><span data-stu-id="7a446-105">H1</span></span>

<span data-ttu-id="7a446-106">`H1` se refere ao primeiro cabeçalho em um arquivo markdown.</span><span class="sxs-lookup"><span data-stu-id="7a446-106">`H1` refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="7a446-107">Quando publicado no docs.microsoft.com, o H1 é exibido na parte superior da página com uma fonte grande.</span><span class="sxs-lookup"><span data-stu-id="7a446-107">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span>

<span data-ttu-id="7a446-108">O H1 é criado ao iniciar uma linha com uma barra única (`#`) seguida por um espaço e pelo texto do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="7a446-108">An H1 is created by beginning a line with a single hash (`#`) followed by a space, then the heading text.</span></span> <span data-ttu-id="7a446-109">Por exemplo, o H1 deste artigo é:</span><span class="sxs-lookup"><span data-stu-id="7a446-109">For example, the H1 of this article is:</span></span>

```md
# Markdown headings
```

<span data-ttu-id="7a446-110">As seguintes regras se aplicam aos cabeçalhos H1:</span><span class="sxs-lookup"><span data-stu-id="7a446-110">The following rules apply to H1 headings:</span></span>

- <span data-ttu-id="7a446-111">Um H1 precisa estar presente no arquivo.</span><span class="sxs-lookup"><span data-stu-id="7a446-111">An H1 must be present in the file.</span></span>
- <span data-ttu-id="7a446-112">Só pode haver um H1.</span><span class="sxs-lookup"><span data-stu-id="7a446-112">There can only be one H1.</span></span>
- <span data-ttu-id="7a446-113">O H1 precisa ter conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7a446-113">The H1 must have content.</span></span>

  ```markdown
  # 
  This is not allowed.
  ```
- <span data-ttu-id="7a446-114">É necessário um espaço entre o `#` e o conteúdo do H1.</span><span class="sxs-lookup"><span data-stu-id="7a446-114">There must be a space between the `#` and the H1 content.</span></span> <span data-ttu-id="7a446-115">Um H1 sem espaço não renderiza como cabeçalho na página publicada.</span><span class="sxs-lookup"><span data-stu-id="7a446-115">An H1 with no space doesn't render as a heading on the published page.</span></span>

  ```markdown
  #This looks bad on the site.
  ```
- <span data-ttu-id="7a446-116">O H1 precisa ser o primeiro conteúdo no arquivo após o cabeçalho de metadados YML.</span><span class="sxs-lookup"><span data-stu-id="7a446-116">The H1 must be the first content in the file after the YML metadata header.</span></span> <span data-ttu-id="7a446-117">Não deve haver conteúdo, como texto ou imagens, entre o fim do cabeçalho YML e o H1.</span><span class="sxs-lookup"><span data-stu-id="7a446-117">No content, such as text or images, is allowed between the end of the YML header and the H1.</span></span>

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- <span data-ttu-id="7a446-118">O elemento HTML para cabeçalhos de primeiro nível, `<h1>`, não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="7a446-118">The HTML element for first-level headings, `<h1>`, should not be used.</span></span> <span data-ttu-id="7a446-119">Use a sintaxe de markdown (`# `).</span><span class="sxs-lookup"><span data-stu-id="7a446-119">Use the Markdown syntax (`# `).</span></span>
- <span data-ttu-id="7a446-120">O H1 não deve ter mais de 100 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a446-120">The H1 should be no more than 100 characters long.</span></span> <span data-ttu-id="7a446-121">Esta é uma diretriz de estilo.</span><span class="sxs-lookup"><span data-stu-id="7a446-121">This is a style guideline.</span></span>

## <a name="h2---h6"></a><span data-ttu-id="7a446-122">H2 – H6</span><span class="sxs-lookup"><span data-stu-id="7a446-122">H2 - H6</span></span>

<span data-ttu-id="7a446-123">H2 (`## `) a H6 (`###### `) são permitidos no OPS.</span><span class="sxs-lookup"><span data-stu-id="7a446-123">H2 (`## `) through H6 (`###### `) are allowed in OPS.</span></span> <span data-ttu-id="7a446-124">Use os cabeçalhos de markdown, e não o HTML (`<h2>` - `<h6>`), para criar cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="7a446-124">Use the Markdown headers, not the HTML (`<h2>` - `<h6>`), to create headings.</span></span>
