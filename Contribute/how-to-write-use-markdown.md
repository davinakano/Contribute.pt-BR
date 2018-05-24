---
title: Como usar o Markdown para escrever Docs
description: Este artigo descreve as noções básicas e informações de referência para a linguagem Markdown usada para escrever artigos do docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 07/13/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 041398361aef90c44bdf3a0dad4aaa2d40a38289
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="fd1a6-103">Como usar o Markdown para escrever Docs</span><span class="sxs-lookup"><span data-stu-id="fd1a6-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="fd1a6-104">Os artigos do docs.microsoft.com são escritos em uma linguagem de marcação leve chamada [Markdown](https://daringfireball.net/projects/markdown/), que é fácil de ler e fácil de aprender.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-104">Docs.microsoft.com articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="fd1a6-105">Por isso, tornou-se rapidamente um padrão do setor.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="fd1a6-106">Como o conteúdo do Docs é armazenado no GitHub, ele pode usar um superconjunto de Markdown chamado [GFM (GitHub Flavored Markdown)](https://help.github.com/categories/writing-on-github/), que fornece mais funcionalidades para necessidades de formatação comuns.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-106">Because Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="fd1a6-107">Além disso, o OPS (Open Publishing Services) implementa o Analisador de Markdown Markdig.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="fd1a6-108">O Markdig é altamente compatível com o GFM (GitHub Flavored Markdown), agregando funcionalidades para habilitar recursos específicos do Docs.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-108">Markdig is highly compatible with GitHub Flavored Markdown (GFM), adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="fd1a6-109">O Markdig é um processador de Markdown extensível, em conformidade com CommonMark potente e rápido para .NET.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="fd1a6-110">Melhor suporte da comunidade</span><span class="sxs-lookup"><span data-stu-id="fd1a6-110">Better community support</span></span>
* <span data-ttu-id="fd1a6-111">Melhor suporte de padrões</span><span class="sxs-lookup"><span data-stu-id="fd1a6-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="fd1a6-112">Noções básicas de markdown</span><span class="sxs-lookup"><span data-stu-id="fd1a6-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="fd1a6-113">Títulos</span><span class="sxs-lookup"><span data-stu-id="fd1a6-113">Headings</span></span>

<span data-ttu-id="fd1a6-114">Para criar um título, use uma marca de hash (#), da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="fd1a6-115">Texto em negrito e em itálico</span><span class="sxs-lookup"><span data-stu-id="fd1a6-115">Bold and italic text</span></span>

<span data-ttu-id="fd1a6-116">Para formatar o texto como **negrito**, coloque dois asteriscos de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-116">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
    This text is **bold**.
```

<span data-ttu-id="fd1a6-117">Para formatar o texto como *itálico*, coloque um único asterisco de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-117">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
    This text is *italic*.
```

<span data-ttu-id="fd1a6-118">Para formatar o texto como ***negrito e itálico***, coloque três asteriscos de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-118">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="fd1a6-119">Listas</span><span class="sxs-lookup"><span data-stu-id="fd1a6-119">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="fd1a6-120">Lista não ordenada</span><span class="sxs-lookup"><span data-stu-id="fd1a6-120">Unordered list</span></span>

<span data-ttu-id="fd1a6-121">Para formatar uma lista não ordenada/com marcador, use asteriscos ou traços.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-121">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="fd1a6-122">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-122">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="fd1a6-123">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-123">will be rendered as:</span></span>

- <span data-ttu-id="fd1a6-124">Item de lista 1</span><span class="sxs-lookup"><span data-stu-id="fd1a6-124">List item 1</span></span>
- <span data-ttu-id="fd1a6-125">Item de lista 2</span><span class="sxs-lookup"><span data-stu-id="fd1a6-125">List item 2</span></span>
- <span data-ttu-id="fd1a6-126">Item de lista 3</span><span class="sxs-lookup"><span data-stu-id="fd1a6-126">List item 3</span></span>

<span data-ttu-id="fd1a6-127">Para aninhar uma lista em outra lista, recue os itens de lista filha.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-127">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="fd1a6-128">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-128">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="fd1a6-129">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-129">will be rendered as:</span></span>

- <span data-ttu-id="fd1a6-130">Item de lista 1</span><span class="sxs-lookup"><span data-stu-id="fd1a6-130">List item 1</span></span>
  - <span data-ttu-id="fd1a6-131">Item de lista A</span><span class="sxs-lookup"><span data-stu-id="fd1a6-131">List item A</span></span>
  - <span data-ttu-id="fd1a6-132">Item de lista B</span><span class="sxs-lookup"><span data-stu-id="fd1a6-132">List item B</span></span>
- <span data-ttu-id="fd1a6-133">Item de lista 2</span><span class="sxs-lookup"><span data-stu-id="fd1a6-133">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="fd1a6-134">Lista ordenada</span><span class="sxs-lookup"><span data-stu-id="fd1a6-134">Ordered list</span></span>

<span data-ttu-id="fd1a6-135">Para formatar uma lista ordenada/gradual, use números correspondentes.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-135">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="fd1a6-136">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-136">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="fd1a6-137">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-137">will be rendered as:</span></span>

1. <span data-ttu-id="fd1a6-138">Primeira instrução</span><span class="sxs-lookup"><span data-stu-id="fd1a6-138">First instruction</span></span>
2. <span data-ttu-id="fd1a6-139">Segunda instrução</span><span class="sxs-lookup"><span data-stu-id="fd1a6-139">Second instruction</span></span>
3. <span data-ttu-id="fd1a6-140">Terceira instrução</span><span class="sxs-lookup"><span data-stu-id="fd1a6-140">Third instruction</span></span>

<span data-ttu-id="fd1a6-141">Para aninhar uma lista em outra lista, recue os itens de lista filha.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-141">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="fd1a6-142">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-142">For example, the following Markdown:</span></span>

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="fd1a6-143">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-143">will be rendered as:</span></span>

1. <span data-ttu-id="fd1a6-144">Primeira instrução</span><span class="sxs-lookup"><span data-stu-id="fd1a6-144">First instruction</span></span>
    1. <span data-ttu-id="fd1a6-145">Subinstrução</span><span class="sxs-lookup"><span data-stu-id="fd1a6-145">Sub-instruction</span></span>
    2. <span data-ttu-id="fd1a6-146">Subinstrução</span><span class="sxs-lookup"><span data-stu-id="fd1a6-146">Sub-instruction</span></span>
2. <span data-ttu-id="fd1a6-147">Segunda instrução</span><span class="sxs-lookup"><span data-stu-id="fd1a6-147">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="fd1a6-148">Tabelas</span><span class="sxs-lookup"><span data-stu-id="fd1a6-148">Tables</span></span>

<span data-ttu-id="fd1a6-149">As tabelas não fazem parte da especificação principal do Markdown, mas são compatíveis com o GFM.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-149">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="fd1a6-150">Você pode criar tabelas usando os caracteres barra vertical (|) e hífen (-).</span><span class="sxs-lookup"><span data-stu-id="fd1a6-150">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="fd1a6-151">Os hifens criam o cabeçalho de cada coluna e as barras verticais separam cada coluna.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-151">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="fd1a6-152">Inclua uma linha em branco antes da sua tabela para que a renderização ocorra corretamente.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-152">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="fd1a6-153">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-153">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="fd1a6-154">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-154">will be rendered as:</span></span>

| <span data-ttu-id="fd1a6-155">Diversão</span><span class="sxs-lookup"><span data-stu-id="fd1a6-155">Fun</span></span>                  | <span data-ttu-id="fd1a6-156">Com</span><span class="sxs-lookup"><span data-stu-id="fd1a6-156">With</span></span>                 | <span data-ttu-id="fd1a6-157">Tabelas</span><span class="sxs-lookup"><span data-stu-id="fd1a6-157">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="fd1a6-158">coluna alinhada à esquerda</span><span class="sxs-lookup"><span data-stu-id="fd1a6-158">left-aligned column</span></span>  | <span data-ttu-id="fd1a6-159">coluna alinhada à direita</span><span class="sxs-lookup"><span data-stu-id="fd1a6-159">right-aligned column</span></span> | <span data-ttu-id="fd1a6-160">coluna centralizada</span><span class="sxs-lookup"><span data-stu-id="fd1a6-160">centered column</span></span> |
| <span data-ttu-id="fd1a6-161">$100</span><span class="sxs-lookup"><span data-stu-id="fd1a6-161">$100</span></span>                 | <span data-ttu-id="fd1a6-162">$100</span><span class="sxs-lookup"><span data-stu-id="fd1a6-162">$100</span></span>                 | <span data-ttu-id="fd1a6-163">$100</span><span class="sxs-lookup"><span data-stu-id="fd1a6-163">$100</span></span>            |
| <span data-ttu-id="fd1a6-164">$10</span><span class="sxs-lookup"><span data-stu-id="fd1a6-164">$10</span></span>                  | <span data-ttu-id="fd1a6-165">$10</span><span class="sxs-lookup"><span data-stu-id="fd1a6-165">$10</span></span>                  | <span data-ttu-id="fd1a6-166">$10</span><span class="sxs-lookup"><span data-stu-id="fd1a6-166">$10</span></span>             |
| <span data-ttu-id="fd1a6-167">$1</span><span class="sxs-lookup"><span data-stu-id="fd1a6-167">$1</span></span>                   | <span data-ttu-id="fd1a6-168">$1</span><span class="sxs-lookup"><span data-stu-id="fd1a6-168">$1</span></span>                   | <span data-ttu-id="fd1a6-169">$1</span><span class="sxs-lookup"><span data-stu-id="fd1a6-169">$1</span></span>              |

<span data-ttu-id="fd1a6-170">Para saber mais sobre como criar tabelas, consulte:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-170">For more information on creating tables, see:</span></span>

- <span data-ttu-id="fd1a6-171">O [recurso de encapsulamento da tabela](#table-wrapping) do Markdig, que pode ajudar com a formatação de tabelas grandes</span><span class="sxs-lookup"><span data-stu-id="fd1a6-171">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables</span></span>
- <span data-ttu-id="fd1a6-172">[Organizar informações com tabelas](https://help.github.com/articles/organizing-information-with-tables/) do GitHub</span><span class="sxs-lookup"><span data-stu-id="fd1a6-172">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)</span></span>
- <span data-ttu-id="fd1a6-173">O aplicativo Web [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="fd1a6-173">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app</span></span>
- [<span data-ttu-id="fd1a6-174">Markdown Cheatsheet de Adam Pritchard</span><span class="sxs-lookup"><span data-stu-id="fd1a6-174">Adam Pritchard's Markdown Cheatsheet</span></span>](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)
- [<span data-ttu-id="fd1a6-175">Markdown Extra de Michel Fortin</span><span class="sxs-lookup"><span data-stu-id="fd1a6-175">Michel Fortin's Markdown Extra</span></span>](https://michelf.ca/projects/php-markdown/extra/#table)
- [<span data-ttu-id="fd1a6-176">Converta tabelas HTML para Markdown</span><span class="sxs-lookup"><span data-stu-id="fd1a6-176">Convert HTML tables to Markdown</span></span>](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a><span data-ttu-id="fd1a6-177">Links</span><span class="sxs-lookup"><span data-stu-id="fd1a6-177">Links</span></span>

<span data-ttu-id="fd1a6-178">A sintaxe do Markdown para um link embutido é composta pela parte `[link text]`, que é o texto que receberá o hiperlink, seguida pela parte `(file-name.md)`, que é a URL ou o nome do arquivo de destino do link:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-178">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="fd1a6-179">Para saber mais sobre vinculação, confira:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-179">For more information on linking, see:</span></span>

- <span data-ttu-id="fd1a6-180">O [guia de sintaxe do Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obter detalhes sobre o suporte à vinculação de base do Markdown.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-180">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="fd1a6-181">A seção [Links](how-to-write-links.md) deste guia para obter detalhes sobre a sintaxe de vinculação adicional que o Markdig fornece.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-181">The [Links](how-to-write-links.md) section of this guide for details on additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="fd1a6-182">Trechos de código</span><span class="sxs-lookup"><span data-stu-id="fd1a6-182">Code snippets</span></span>

<span data-ttu-id="fd1a6-183">O Markdown é compatível com o posicionamento de trechos de código, seja embutido em uma sentença, seja como um bloco "isolado" e separado entre as sentenças.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-183">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="fd1a6-184">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-184">For details, see:</span></span>

- [<span data-ttu-id="fd1a6-185">Suporte nativo do Markdown para blocos de código</span><span class="sxs-lookup"><span data-stu-id="fd1a6-185">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="fd1a6-186">Suporte do GFM para isolamento de código e destaque de sintaxe</span><span class="sxs-lookup"><span data-stu-id="fd1a6-186">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="fd1a6-187">Os blocos de código isolados representam uma maneira fácil de habilitar o destaque de sintaxe para seus trechos de código.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-187">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="fd1a6-188">O formato geral dos blocos de código isolados é:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-188">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="fd1a6-189">O alias após os três caracteres de acento grave (\`) iniciais define o destaque de sintaxe a ser usado.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-189">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="fd1a6-190">Veja a seguir uma lista de linguagens de programação normalmente usadas no conteúdo do Docs e no rótulo correspondente:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-190">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="fd1a6-191">Essas linguagens têm o suporte de nome amigável e a maioria tem realce de linguagem.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-191">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="fd1a6-192">Nome</span><span class="sxs-lookup"><span data-stu-id="fd1a6-192">Name</span></span>|<span data-ttu-id="fd1a6-193">Rótulo de Markdown</span><span class="sxs-lookup"><span data-stu-id="fd1a6-193">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="fd1a6-194">Console do .NET</span><span class="sxs-lookup"><span data-stu-id="fd1a6-194">.NET Console</span></span>|<span data-ttu-id="fd1a6-195">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="fd1a6-195">dotnetcli</span></span>|
|<span data-ttu-id="fd1a6-196">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="fd1a6-196">ASP.NET (C#)</span></span>|<span data-ttu-id="fd1a6-197">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="fd1a6-197">aspx-csharp</span></span>|
|<span data-ttu-id="fd1a6-198">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="fd1a6-198">ASP.NET (VB)</span></span>|<span data-ttu-id="fd1a6-199">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="fd1a6-199">aspx-vb</span></span>|
|<span data-ttu-id="fd1a6-200">AzCopy</span><span class="sxs-lookup"><span data-stu-id="fd1a6-200">AzCopy</span></span>|<span data-ttu-id="fd1a6-201">azcopy</span><span class="sxs-lookup"><span data-stu-id="fd1a6-201">azcopy</span></span>|
|<span data-ttu-id="fd1a6-202">CLI do Azure</span><span class="sxs-lookup"><span data-stu-id="fd1a6-202">Azure CLI</span></span>|<span data-ttu-id="fd1a6-203">azurecli</span><span class="sxs-lookup"><span data-stu-id="fd1a6-203">azurecli</span></span>|
|<span data-ttu-id="fd1a6-204">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd1a6-204">Azure PowerShell</span></span>|<span data-ttu-id="fd1a6-205">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="fd1a6-205">azurepowershell</span></span>|
|<span data-ttu-id="fd1a6-206">C++</span><span class="sxs-lookup"><span data-stu-id="fd1a6-206">C++</span></span>|<span data-ttu-id="fd1a6-207">cpp</span><span class="sxs-lookup"><span data-stu-id="fd1a6-207">cpp</span></span>|
|<span data-ttu-id="fd1a6-208">C++/CX</span><span class="sxs-lookup"><span data-stu-id="fd1a6-208">C++/CX</span></span>|<span data-ttu-id="fd1a6-209">cppcx</span><span class="sxs-lookup"><span data-stu-id="fd1a6-209">cppcx</span></span>|
|<span data-ttu-id="fd1a6-210">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="fd1a6-210">C++/WinRT</span></span>|<span data-ttu-id="fd1a6-211">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="fd1a6-211">cppwinrt</span></span>|
|<span data-ttu-id="fd1a6-212">C#</span><span class="sxs-lookup"><span data-stu-id="fd1a6-212">C#</span></span>|<span data-ttu-id="fd1a6-213">csharp</span><span class="sxs-lookup"><span data-stu-id="fd1a6-213">csharp</span></span>|
|<span data-ttu-id="fd1a6-214">CSHTML</span><span class="sxs-lookup"><span data-stu-id="fd1a6-214">CSHTML</span></span>|<span data-ttu-id="fd1a6-215">cshtml</span><span class="sxs-lookup"><span data-stu-id="fd1a6-215">cshtml</span></span>|
|<span data-ttu-id="fd1a6-216">DAX</span><span class="sxs-lookup"><span data-stu-id="fd1a6-216">DAX</span></span>|<span data-ttu-id="fd1a6-217">dax</span><span class="sxs-lookup"><span data-stu-id="fd1a6-217">dax</span></span>|
|<span data-ttu-id="fd1a6-218">F#</span><span class="sxs-lookup"><span data-stu-id="fd1a6-218">F#</span></span>|<span data-ttu-id="fd1a6-219">fsharp</span><span class="sxs-lookup"><span data-stu-id="fd1a6-219">fsharp</span></span>|
|<span data-ttu-id="fd1a6-220">Go</span><span class="sxs-lookup"><span data-stu-id="fd1a6-220">Go</span></span>|<span data-ttu-id="fd1a6-221">go</span><span class="sxs-lookup"><span data-stu-id="fd1a6-221">go</span></span>|
|<span data-ttu-id="fd1a6-222">HTML</span><span class="sxs-lookup"><span data-stu-id="fd1a6-222">HTML</span></span>|<span data-ttu-id="fd1a6-223">html</span><span class="sxs-lookup"><span data-stu-id="fd1a6-223">html</span></span>|
|<span data-ttu-id="fd1a6-224">HTTP</span><span class="sxs-lookup"><span data-stu-id="fd1a6-224">HTTP</span></span>|<span data-ttu-id="fd1a6-225">http</span><span class="sxs-lookup"><span data-stu-id="fd1a6-225">http</span></span>|
|<span data-ttu-id="fd1a6-226">Java</span><span class="sxs-lookup"><span data-stu-id="fd1a6-226">Java</span></span>|<span data-ttu-id="fd1a6-227">java</span><span class="sxs-lookup"><span data-stu-id="fd1a6-227">java</span></span>|
|<span data-ttu-id="fd1a6-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="fd1a6-228">JavaScript</span></span>|<span data-ttu-id="fd1a6-229">javascript</span><span class="sxs-lookup"><span data-stu-id="fd1a6-229">javascript</span></span>|
|<span data-ttu-id="fd1a6-230">JSON</span><span class="sxs-lookup"><span data-stu-id="fd1a6-230">JSON</span></span>|<span data-ttu-id="fd1a6-231">json</span><span class="sxs-lookup"><span data-stu-id="fd1a6-231">json</span></span>|
|<span data-ttu-id="fd1a6-232">Markdown</span><span class="sxs-lookup"><span data-stu-id="fd1a6-232">Markdown</span></span>|<span data-ttu-id="fd1a6-233">md</span><span class="sxs-lookup"><span data-stu-id="fd1a6-233">md</span></span>|
|<span data-ttu-id="fd1a6-234">NodeJS</span><span class="sxs-lookup"><span data-stu-id="fd1a6-234">NodeJS</span></span>|<span data-ttu-id="fd1a6-235">nodejs</span><span class="sxs-lookup"><span data-stu-id="fd1a6-235">nodejs</span></span>|
|<span data-ttu-id="fd1a6-236">Objective-C</span><span class="sxs-lookup"><span data-stu-id="fd1a6-236">Objective-C</span></span>|<span data-ttu-id="fd1a6-237">objc</span><span class="sxs-lookup"><span data-stu-id="fd1a6-237">objc</span></span>|
|<span data-ttu-id="fd1a6-238">OData</span><span class="sxs-lookup"><span data-stu-id="fd1a6-238">OData</span></span>|<span data-ttu-id="fd1a6-239">odata</span><span class="sxs-lookup"><span data-stu-id="fd1a6-239">odata</span></span>|
|<span data-ttu-id="fd1a6-240">PHP</span><span class="sxs-lookup"><span data-stu-id="fd1a6-240">PHP</span></span>|<span data-ttu-id="fd1a6-241">php</span><span class="sxs-lookup"><span data-stu-id="fd1a6-241">php</span></span>|
|<span data-ttu-id="fd1a6-242">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="fd1a6-242">Power Apps Formula</span></span>|<span data-ttu-id="fd1a6-243">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="fd1a6-243">powerappsfl</span></span>|
|<span data-ttu-id="fd1a6-244">PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd1a6-244">PowerShell</span></span>|<span data-ttu-id="fd1a6-245">powershell</span><span class="sxs-lookup"><span data-stu-id="fd1a6-245">powershell</span></span>|
|<span data-ttu-id="fd1a6-246">Python</span><span class="sxs-lookup"><span data-stu-id="fd1a6-246">Python</span></span>|<span data-ttu-id="fd1a6-247">python</span><span class="sxs-lookup"><span data-stu-id="fd1a6-247">python</span></span>|
|<span data-ttu-id="fd1a6-248">Q#</span><span class="sxs-lookup"><span data-stu-id="fd1a6-248">Q#</span></span>|<span data-ttu-id="fd1a6-249">qsharp</span><span class="sxs-lookup"><span data-stu-id="fd1a6-249">qsharp</span></span>|
|<span data-ttu-id="fd1a6-250">Ruby</span><span class="sxs-lookup"><span data-stu-id="fd1a6-250">Ruby</span></span>|<span data-ttu-id="fd1a6-251">ruby</span><span class="sxs-lookup"><span data-stu-id="fd1a6-251">ruby</span></span>|
|<span data-ttu-id="fd1a6-252">SQL</span><span class="sxs-lookup"><span data-stu-id="fd1a6-252">SQL</span></span>|<span data-ttu-id="fd1a6-253">sql</span><span class="sxs-lookup"><span data-stu-id="fd1a6-253">sql</span></span>|
|<span data-ttu-id="fd1a6-254">Swift</span><span class="sxs-lookup"><span data-stu-id="fd1a6-254">Swift</span></span>|<span data-ttu-id="fd1a6-255">swift</span><span class="sxs-lookup"><span data-stu-id="fd1a6-255">swift</span></span>|
|<span data-ttu-id="fd1a6-256">TypeScript</span><span class="sxs-lookup"><span data-stu-id="fd1a6-256">TypeScript</span></span>|<span data-ttu-id="fd1a6-257">typescript</span><span class="sxs-lookup"><span data-stu-id="fd1a6-257">typescript</span></span>|
|<span data-ttu-id="fd1a6-258">VB</span><span class="sxs-lookup"><span data-stu-id="fd1a6-258">VB</span></span>|<span data-ttu-id="fd1a6-259">vb</span><span class="sxs-lookup"><span data-stu-id="fd1a6-259">vb</span></span>|
|<span data-ttu-id="fd1a6-260">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="fd1a6-260">VSTS CLI</span></span>|<span data-ttu-id="fd1a6-261">vstscli</span><span class="sxs-lookup"><span data-stu-id="fd1a6-261">vstscli</span></span>|
|<span data-ttu-id="fd1a6-262">XAML</span><span class="sxs-lookup"><span data-stu-id="fd1a6-262">XAML</span></span>|<span data-ttu-id="fd1a6-263">xaml</span><span class="sxs-lookup"><span data-stu-id="fd1a6-263">xaml</span></span>|
|<span data-ttu-id="fd1a6-264">XML</span><span class="sxs-lookup"><span data-stu-id="fd1a6-264">XML</span></span>|<span data-ttu-id="fd1a6-265">xml</span><span class="sxs-lookup"><span data-stu-id="fd1a6-265">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="fd1a6-266">Exemplo: C\#</span><span class="sxs-lookup"><span data-stu-id="fd1a6-266">Example: C\#</span></span>

<span data-ttu-id="fd1a6-267">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="fd1a6-267">__Markdown__</span></span>

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

<span data-ttu-id="fd1a6-268">__Renderização__</span><span class="sxs-lookup"><span data-stu-id="fd1a6-268">__Render__</span></span>

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a><span data-ttu-id="fd1a6-269">Exemplo: SQL</span><span class="sxs-lookup"><span data-stu-id="fd1a6-269">Example: SQL</span></span>

<span data-ttu-id="fd1a6-270">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="fd1a6-270">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="fd1a6-271">__Renderização__</span><span class="sxs-lookup"><span data-stu-id="fd1a6-271">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="fd1a6-272">Extensões de Markdown personalizada do OPS</span><span class="sxs-lookup"><span data-stu-id="fd1a6-272">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="fd1a6-273">O OPS (Open Publishing Services) implementa um Analisador de Markdown Markdig, que é altamente compatível com o GFM (GitHub Flavored Markdown).</span><span class="sxs-lookup"><span data-stu-id="fd1a6-273">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="fd1a6-274">O Markdig adiciona algumas funcionalidades por meio de extensões de Markdown.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-274">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="fd1a6-275">Portanto, alguns artigos selecionados no Guia de Criação do OPS completo foram incluídos neste guia para referência.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-275">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="fd1a6-276">(Por exemplo, veja "extensões de Markdown e Markdig" e "Trechos de código" no sumário.)</span><span class="sxs-lookup"><span data-stu-id="fd1a6-276">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="fd1a6-277">Os artigos do Docs usam o GFM para a maior parte da formatação do artigo, como parágrafos, links, listas e cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-277">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="fd1a6-278">Para uma formatação mais avançada, os artigos podem usar recursos do Markdig, como:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-278">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="fd1a6-279">Blocos de nota</span><span class="sxs-lookup"><span data-stu-id="fd1a6-279">Note blocks</span></span>
- <span data-ttu-id="fd1a6-280">Inclusões</span><span class="sxs-lookup"><span data-stu-id="fd1a6-280">Includes</span></span>
- <span data-ttu-id="fd1a6-281">Seletores</span><span class="sxs-lookup"><span data-stu-id="fd1a6-281">Selectors</span></span>
- <span data-ttu-id="fd1a6-282">Vídeos incorporados</span><span class="sxs-lookup"><span data-stu-id="fd1a6-282">Embedded videos</span></span>
- <span data-ttu-id="fd1a6-283">Trechos/amostras de código</span><span class="sxs-lookup"><span data-stu-id="fd1a6-283">Code snippets/samples</span></span>

<span data-ttu-id="fd1a6-284">Para obter a lista completa, veja "extensões de Markdown e Markdig" e "Trechos de código" no sumário.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-284">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="fd1a6-285">Blocos de nota</span><span class="sxs-lookup"><span data-stu-id="fd1a6-285">Note blocks</span></span>

<span data-ttu-id="fd1a6-286">Você pode escolher entre quatro tipos de blocos de notas para chamar atenção para um conteúdo específico:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-286">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="fd1a6-287">OBSERVAÇÃO</span><span class="sxs-lookup"><span data-stu-id="fd1a6-287">NOTE</span></span>
- <span data-ttu-id="fd1a6-288">AVISO</span><span class="sxs-lookup"><span data-stu-id="fd1a6-288">WARNING</span></span>
- <span data-ttu-id="fd1a6-289">DICA</span><span class="sxs-lookup"><span data-stu-id="fd1a6-289">TIP</span></span>
- <span data-ttu-id="fd1a6-290">IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="fd1a6-290">IMPORTANT</span></span>

<span data-ttu-id="fd1a6-291">Em geral, os blocos de notas devem ser usados com moderação porque eles podem atrapalhar.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-291">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="fd1a6-292">Embora eles também deem suporte para blocos de código, imagens, listas e links, tente manter seus blocos de nota simples e diretos.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-292">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="fd1a6-293">Inclusões</span><span class="sxs-lookup"><span data-stu-id="fd1a6-293">Includes</span></span>

<span data-ttu-id="fd1a6-294">Quando você tiver um texto ou arquivos de imagem reutilizáveis que precisem ser incluídos nos arquivos do artigo, use uma referência ao arquivo de "inclusão" por meio do recurso de inclusão de arquivo do Markdig.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-294">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="fd1a6-295">Esse recurso instrui o OPS a incluir o arquivo no arquivo do artigo no tempo de build, para que ele faça parte do artigo publicado.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-295">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="fd1a6-296">Três tipos de inclusões estão disponíveis para ajudá-lo a reutilizar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-296">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="fd1a6-297">Embutido: reutilize um trecho de texto comum embutido dentro de outra frase.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-297">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="fd1a6-298">Bloco: reutilize um arquivo Markdown inteiro como um bloco aninhado dentro de uma seção de um artigo.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-298">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="fd1a6-299">Imagem: é como a inclusão de imagem padrão é implementada no Docs.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-299">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="fd1a6-300">A inclusão de um embutido ou de um bloco é apenas um arquivo Markdown (.md) simples.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-300">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="fd1a6-301">Ele pode conter qualquer Markdown válido.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-301">It can contain any valid Markdown.</span></span> <span data-ttu-id="fd1a6-302">Todos os arquivos Markdown de inclusão devem ser colocados em um [subdiretório `/includes` comum](git-github-fundamentals.md#includes-subdirectory), na raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-302">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="fd1a6-303">Quando o artigo é publicado, o arquivo incluído fica perfeitamente integrado.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-303">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="fd1a6-304">Aqui estão os requisitos e as considerações para inclusões:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-304">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="fd1a6-305">Use inclusões sempre que precisar que o mesmo texto apareça em vários artigos.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-305">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="fd1a6-306">Use inclusões em bloco para quantidades consideráveis de conteúdo, como um ou dois parágrafos, um procedimento compartilhado ou uma seção compartilhada.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-306">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="fd1a6-307">Não use-os para nada menor do que uma sentença.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-307">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="fd1a6-308">As inclusões não serão renderizadas no modo de exibição renderizado do GitHub do seu artigo, pois elas dependem de extensões do Markdig.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-308">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="fd1a6-309">Elas serão renderizadas somente após a publicação.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-309">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="fd1a6-310">Verifique se todo o texto em uma inclusão está escrito em sentenças ou frases completas que não dependem do texto anterior ou seguinte no artigo que faz referência à inclusão.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-310">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="fd1a6-311">Se você ignorar essa orientação, criará uma cadeia de caracteres não traduzível no artigo que quebrará a experiência localizada.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-311">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="fd1a6-312">Não incorpore inclusões dentro de outras inclusões.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-312">Don't embed includes within other includes.</span></span> <span data-ttu-id="fd1a6-313">Não há suporte para isso.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-313">They are not supported.</span></span>
- <span data-ttu-id="fd1a6-314">Coloque os arquivos de mídia em uma pasta de mídia específica para o subdiretório de inclusão, por exemplo, a pasta `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-314">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="fd1a6-315">O diretório de mídia não deve conter imagens em sua raiz.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-315">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="fd1a6-316">Se a inclusão não tiver imagens, não será necessário ter um diretório de mídia correspondente.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-316">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="fd1a6-317">Assim como ocorre com os artigos regulares, não compartilhe a mídia entre arquivos de inclusão.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-317">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="fd1a6-318">Use um arquivo separado com um nome exclusivo para cada inclusão e artigo.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-318">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="fd1a6-319">Armazene o arquivo de mídia na pasta de mídia associada à inclusão.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-319">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="fd1a6-320">Não use uma inclusão como único conteúdo de um artigo.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-320">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="fd1a6-321">As inclusões servem como complemento ao conteúdo do restante do artigo.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-321">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="fd1a6-322">Seletores</span><span class="sxs-lookup"><span data-stu-id="fd1a6-322">Selectors</span></span>

<span data-ttu-id="fd1a6-323">Use seletores em artigos técnicos ao criar vários tipos do mesmo artigo, a fim de solucionar diferenças de implementação entre tecnologias e plataformas.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-323">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="fd1a6-324">Normalmente, isso é mais aplicável ao nosso conteúdo de plataforma móvel para desenvolvedores.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-324">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="fd1a6-325">No momento, há dois tipos diferentes de seletores no Markdig, um seletor único e um seletor múltiplo.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-325">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="fd1a6-326">Como o mesmo Markdown seletor vai para cada artigo na seleção, recomendamos posicionar o seletor do artigo em uma inclusão.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-326">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="fd1a6-327">Em seguida, você poderá referenciar essa inclusão em todos os artigos que usarem o mesmo seletor.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-327">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="fd1a6-328">Trechos de código</span><span class="sxs-lookup"><span data-stu-id="fd1a6-328">Code snippets</span></span>

<span data-ttu-id="fd1a6-329">O Markdig também é compatível com a inclusão avançada de código em um artigo por meio de sua extensão de trecho de código.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-329">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="fd1a6-330">Ela fornece renderização avançada que aproveita os recursos do GFM, como seleção de linguagem de programação e coloração de sintaxe, além de recursos incríveis como:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-330">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="fd1a6-331">Inclusão de amostras/trechos de código centralizados de um repositório externo.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-331">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="fd1a6-332">Interface do usuário com guias para mostrar várias versões de amostras de código em linguagens diferentes.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-332">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="fd1a6-333">Armadilhas e solução de problemas</span><span class="sxs-lookup"><span data-stu-id="fd1a6-333">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="fd1a6-334">Texto Alt</span><span class="sxs-lookup"><span data-stu-id="fd1a6-334">Alt text</span></span>

<span data-ttu-id="fd1a6-335">Textos Alt que contenham caracteres sublinhado não serão renderizados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-335">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="fd1a6-336">Por exemplo, em vez de usar isto:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-336">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="fd1a6-337">Insira um escape para os sublinhados desta forma:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-337">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="fd1a6-338">Apóstrofes e aspas</span><span class="sxs-lookup"><span data-stu-id="fd1a6-338">Apostrophes and quotation marks</span></span>

<span data-ttu-id="fd1a6-339">Se você copiar do Word para um editor de Markdown, o texto poderá conter apóstrofes ou aspas "inteligentes" (inglesas).</span><span class="sxs-lookup"><span data-stu-id="fd1a6-339">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="fd1a6-340">Eles precisam ser codificados ou alterados para apóstrofos ou aspas simples.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-340">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="fd1a6-341">Caso contrário, quando o arquivo for publicado poderão ocorrer erros como: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="fd1a6-341">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="fd1a6-342">Estas são as codificações para as versões "inteligentes" dessas marcas de pontuação:</span><span class="sxs-lookup"><span data-stu-id="fd1a6-342">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="fd1a6-343">Aspas à esquerda (de abertura): `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="fd1a6-343">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="fd1a6-344">Aspas à direita (de fechamento): `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="fd1a6-344">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="fd1a6-345">Aspas simples à direita (de fechamento) ou apóstrofe: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="fd1a6-345">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="fd1a6-346">Aspas simples à esquerda (de abertura) (raramente usadas): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="fd1a6-346">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="fd1a6-347">Colchetes angulares</span><span class="sxs-lookup"><span data-stu-id="fd1a6-347">Angle brackets</span></span>

<span data-ttu-id="fd1a6-348">Se você usar colchetes angulares no texto (não no código) no arquivo, por exemplo, para indicar um espaço reservado, será necessário codificar manualmente os colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-348">If you use angle brackets in text (not code) in your file--for example, to denote a placeholder--you need to manually encode the angle brackets.</span></span> <span data-ttu-id="fd1a6-349">Caso contrário, o Markdown entenderá que eles são uma marca HTML.</span><span class="sxs-lookup"><span data-stu-id="fd1a6-349">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="fd1a6-350">Por exemplo, codifique `<script name>` como `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="fd1a6-350">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="fd1a6-351">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fd1a6-351">See also</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="fd1a6-352">Recursos do Markdown</span><span class="sxs-lookup"><span data-stu-id="fd1a6-352">Markdown resources</span></span>

- [<span data-ttu-id="fd1a6-353">Introdução a Markdown</span><span class="sxs-lookup"><span data-stu-id="fd1a6-353">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="fd1a6-354">Roteiro de Markdown do Docs</span><span class="sxs-lookup"><span data-stu-id="fd1a6-354">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="fd1a6-355">Noções básicas de Markdown do GitHub</span><span class="sxs-lookup"><span data-stu-id="fd1a6-355">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
