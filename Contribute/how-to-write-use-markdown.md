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
ms.openlocfilehash: 96d00abc052c3b23ca62201dccdbe590a927e72d
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="f9de0-103">Como usar o Markdown para escrever Docs</span><span class="sxs-lookup"><span data-stu-id="f9de0-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="f9de0-104">Os artigos do docs.microsoft.com são escritos em uma linguagem de marcação leve chamada [Markdown](https://daringfireball.net/projects/markdown/), que é fácil de ler e fácil de aprender.</span><span class="sxs-lookup"><span data-stu-id="f9de0-104">Docs.microsoft.com articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="f9de0-105">Por isso, tornou-se rapidamente um padrão do setor.</span><span class="sxs-lookup"><span data-stu-id="f9de0-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="f9de0-106">Como o conteúdo do Docs é armazenado no GitHub, ele pode usar um superconjunto de Markdown chamado [GFM (GitHub Flavored Markdown)](https://help.github.com/categories/writing-on-github/), que fornece mais funcionalidades para necessidades de formatação comuns.</span><span class="sxs-lookup"><span data-stu-id="f9de0-106">Because Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="f9de0-107">Além disso, o OPS (Open Publishing Services) implementa o DFM (DocFX Flavored Markdown).</span><span class="sxs-lookup"><span data-stu-id="f9de0-107">Additionally, Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="f9de0-108">O DFM é altamente compatível com o GFM (GitHub Flavored Markdown), agregando funcionalidades para habilitar recursos específicos do Docs.</span><span class="sxs-lookup"><span data-stu-id="f9de0-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), adding functionality to enable Docs-specific features.</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="f9de0-109">Noções básicas de markdown</span><span class="sxs-lookup"><span data-stu-id="f9de0-109">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="f9de0-110">Títulos</span><span class="sxs-lookup"><span data-stu-id="f9de0-110">Headings</span></span>

<span data-ttu-id="f9de0-111">Para criar um título, use uma marca de hash (#), da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f9de0-111">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="f9de0-112">Texto em negrito e em itálico</span><span class="sxs-lookup"><span data-stu-id="f9de0-112">Bold and italic text</span></span>

<span data-ttu-id="f9de0-113">Para formatar o texto como **negrito**, coloque dois asteriscos de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="f9de0-113">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
    This text is **bold**.
```

<span data-ttu-id="f9de0-114">Para formatar o texto como *itálico*, coloque um único asterisco de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="f9de0-114">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
    This text is *italic*.
```

<span data-ttu-id="f9de0-115">Para formatar o texto como ***negrito e itálico***, coloque três asteriscos de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="f9de0-115">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="f9de0-116">Listas</span><span class="sxs-lookup"><span data-stu-id="f9de0-116">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="f9de0-117">Lista não ordenada</span><span class="sxs-lookup"><span data-stu-id="f9de0-117">Unordered list</span></span>

<span data-ttu-id="f9de0-118">Para formatar uma lista não ordenada/com marcador, use asteriscos ou traços.</span><span class="sxs-lookup"><span data-stu-id="f9de0-118">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="f9de0-119">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="f9de0-119">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="f9de0-120">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="f9de0-120">will be rendered as:</span></span>

- <span data-ttu-id="f9de0-121">Item de lista 1</span><span class="sxs-lookup"><span data-stu-id="f9de0-121">List item 1</span></span>
- <span data-ttu-id="f9de0-122">Item de lista 2</span><span class="sxs-lookup"><span data-stu-id="f9de0-122">List item 2</span></span>
- <span data-ttu-id="f9de0-123">Item de lista 3</span><span class="sxs-lookup"><span data-stu-id="f9de0-123">List item 3</span></span>

<span data-ttu-id="f9de0-124">Para aninhar uma lista em outra lista, recue os itens de lista filha.</span><span class="sxs-lookup"><span data-stu-id="f9de0-124">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="f9de0-125">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="f9de0-125">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="f9de0-126">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="f9de0-126">will be rendered as:</span></span>

- <span data-ttu-id="f9de0-127">Item de lista 1</span><span class="sxs-lookup"><span data-stu-id="f9de0-127">List item 1</span></span>
  - <span data-ttu-id="f9de0-128">Item de lista A</span><span class="sxs-lookup"><span data-stu-id="f9de0-128">List item A</span></span>
  - <span data-ttu-id="f9de0-129">Item de lista B</span><span class="sxs-lookup"><span data-stu-id="f9de0-129">List item B</span></span>
- <span data-ttu-id="f9de0-130">Item de lista 2</span><span class="sxs-lookup"><span data-stu-id="f9de0-130">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="f9de0-131">Lista ordenada</span><span class="sxs-lookup"><span data-stu-id="f9de0-131">Ordered list</span></span>

<span data-ttu-id="f9de0-132">Para formatar uma lista ordenada/gradual, use números correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f9de0-132">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="f9de0-133">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="f9de0-133">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="f9de0-134">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="f9de0-134">will be rendered as:</span></span>

1. <span data-ttu-id="f9de0-135">Primeira instrução</span><span class="sxs-lookup"><span data-stu-id="f9de0-135">First instruction</span></span>
2. <span data-ttu-id="f9de0-136">Segunda instrução</span><span class="sxs-lookup"><span data-stu-id="f9de0-136">Second instruction</span></span>
3. <span data-ttu-id="f9de0-137">Terceira instrução</span><span class="sxs-lookup"><span data-stu-id="f9de0-137">Third instruction</span></span>

<span data-ttu-id="f9de0-138">Para aninhar uma lista em outra lista, recue os itens de lista filha.</span><span class="sxs-lookup"><span data-stu-id="f9de0-138">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="f9de0-139">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="f9de0-139">For example, the following Markdown:</span></span>

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="f9de0-140">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="f9de0-140">will be rendered as:</span></span>

1. <span data-ttu-id="f9de0-141">Primeira instrução</span><span class="sxs-lookup"><span data-stu-id="f9de0-141">First instruction</span></span>
    1. <span data-ttu-id="f9de0-142">Subinstrução</span><span class="sxs-lookup"><span data-stu-id="f9de0-142">Sub-instruction</span></span>
    2. <span data-ttu-id="f9de0-143">Subinstrução</span><span class="sxs-lookup"><span data-stu-id="f9de0-143">Sub-instruction</span></span>
2. <span data-ttu-id="f9de0-144">Segunda instrução</span><span class="sxs-lookup"><span data-stu-id="f9de0-144">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="f9de0-145">Tabelas</span><span class="sxs-lookup"><span data-stu-id="f9de0-145">Tables</span></span>

<span data-ttu-id="f9de0-146">As tabelas não fazem parte da especificação principal do Markdown, mas são compatíveis com o GFM.</span><span class="sxs-lookup"><span data-stu-id="f9de0-146">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="f9de0-147">Você pode criar tabelas usando os caracteres barra vertical (|) e hífen (-).</span><span class="sxs-lookup"><span data-stu-id="f9de0-147">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="f9de0-148">Os hifens criam o cabeçalho de cada coluna e as barras verticais separam cada coluna.</span><span class="sxs-lookup"><span data-stu-id="f9de0-148">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="f9de0-149">Inclua uma linha em branco antes da sua tabela para que a renderização ocorra corretamente.</span><span class="sxs-lookup"><span data-stu-id="f9de0-149">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="f9de0-150">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="f9de0-150">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="f9de0-151">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="f9de0-151">will be rendered as:</span></span>

| <span data-ttu-id="f9de0-152">Diversão</span><span class="sxs-lookup"><span data-stu-id="f9de0-152">Fun</span></span>                  | <span data-ttu-id="f9de0-153">Com</span><span class="sxs-lookup"><span data-stu-id="f9de0-153">With</span></span>                 | <span data-ttu-id="f9de0-154">Tabelas</span><span class="sxs-lookup"><span data-stu-id="f9de0-154">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="f9de0-155">coluna alinhada à esquerda</span><span class="sxs-lookup"><span data-stu-id="f9de0-155">left-aligned column</span></span>  | <span data-ttu-id="f9de0-156">coluna alinhada à direita</span><span class="sxs-lookup"><span data-stu-id="f9de0-156">right-aligned column</span></span> | <span data-ttu-id="f9de0-157">coluna centralizada</span><span class="sxs-lookup"><span data-stu-id="f9de0-157">centered column</span></span> |
| <span data-ttu-id="f9de0-158">$100</span><span class="sxs-lookup"><span data-stu-id="f9de0-158">$100</span></span>                 | <span data-ttu-id="f9de0-159">$100</span><span class="sxs-lookup"><span data-stu-id="f9de0-159">$100</span></span>                 | <span data-ttu-id="f9de0-160">$100</span><span class="sxs-lookup"><span data-stu-id="f9de0-160">$100</span></span>            |
| <span data-ttu-id="f9de0-161">$10</span><span class="sxs-lookup"><span data-stu-id="f9de0-161">$10</span></span>                  | <span data-ttu-id="f9de0-162">$10</span><span class="sxs-lookup"><span data-stu-id="f9de0-162">$10</span></span>                  | <span data-ttu-id="f9de0-163">$10</span><span class="sxs-lookup"><span data-stu-id="f9de0-163">$10</span></span>             |
| <span data-ttu-id="f9de0-164">$1</span><span class="sxs-lookup"><span data-stu-id="f9de0-164">$1</span></span>                   | <span data-ttu-id="f9de0-165">$1</span><span class="sxs-lookup"><span data-stu-id="f9de0-165">$1</span></span>                   | <span data-ttu-id="f9de0-166">$1</span><span class="sxs-lookup"><span data-stu-id="f9de0-166">$1</span></span>              |

<span data-ttu-id="f9de0-167">Para saber mais sobre como criar tabelas, consulte:</span><span class="sxs-lookup"><span data-stu-id="f9de0-167">For more information on creating tables, see:</span></span>

- <span data-ttu-id="f9de0-168">O [recurso de disposição da tabela](#table-wrapping) do DFM, que pode ajudar com a formatação de tabelas grandes</span><span class="sxs-lookup"><span data-stu-id="f9de0-168">The DFM [table wrapping feature](#table-wrapping), which can help with formatting of wide tables</span></span>
- <span data-ttu-id="f9de0-169">[Organizar informações com tabelas](https://help.github.com/articles/organizing-information-with-tables/) do GitHub</span><span class="sxs-lookup"><span data-stu-id="f9de0-169">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)</span></span>
- <span data-ttu-id="f9de0-170">O aplicativo Web [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="f9de0-170">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app</span></span>
- [<span data-ttu-id="f9de0-171">Markdown Cheatsheet de Adam Pritchard</span><span class="sxs-lookup"><span data-stu-id="f9de0-171">Adam Pritchard's Markdown Cheatsheet</span></span>](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)
- [<span data-ttu-id="f9de0-172">Markdown Extra de Michel Fortin</span><span class="sxs-lookup"><span data-stu-id="f9de0-172">Michel Fortin's Markdown Extra</span></span>](https://michelf.ca/projects/php-markdown/extra/#table)
- [<span data-ttu-id="f9de0-173">Converta tabelas HTML para Markdown</span><span class="sxs-lookup"><span data-stu-id="f9de0-173">Convert HTML tables to Markdown</span></span>](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a><span data-ttu-id="f9de0-174">Links</span><span class="sxs-lookup"><span data-stu-id="f9de0-174">Links</span></span>

<span data-ttu-id="f9de0-175">A sintaxe do Markdown para um link embutido é composta pela parte `[link text]`, que é o texto que receberá o hiperlink, seguida pela parte `(file-name.md)`, que é a URL ou o nome do arquivo de destino do link:</span><span class="sxs-lookup"><span data-stu-id="f9de0-175">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="f9de0-176">Para saber mais sobre vinculação, confira:</span><span class="sxs-lookup"><span data-stu-id="f9de0-176">For more information on linking, see:</span></span>

- <span data-ttu-id="f9de0-177">O [guia de sintaxe do Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obter detalhes sobre o suporte à vinculação de base do Markdown.</span><span class="sxs-lookup"><span data-stu-id="f9de0-177">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="f9de0-178">A seção [Links](how-to-write-links.md) deste guia para obter detalhes sobre a sintaxe de vinculação adicional que o DFM fornece.</span><span class="sxs-lookup"><span data-stu-id="f9de0-178">The [Links](how-to-write-links.md) section of this guide for details on additional linking syntax that DFM provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="f9de0-179">Trechos de código</span><span class="sxs-lookup"><span data-stu-id="f9de0-179">Code snippets</span></span>

<span data-ttu-id="f9de0-180">O Markdown é compatível com o posicionamento de trechos de código, seja embutido em uma sentença, seja como um bloco "isolado" e separado entre as sentenças.</span><span class="sxs-lookup"><span data-stu-id="f9de0-180">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="f9de0-181">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="f9de0-181">For details, see:</span></span>

- [<span data-ttu-id="f9de0-182">Suporte nativo do Markdown para blocos de código</span><span class="sxs-lookup"><span data-stu-id="f9de0-182">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="f9de0-183">Suporte do GFM para isolamento de código e destaque de sintaxe</span><span class="sxs-lookup"><span data-stu-id="f9de0-183">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="f9de0-184">Os blocos de código isolados representam uma maneira fácil de habilitar o destaque de sintaxe para seus trechos de código.</span><span class="sxs-lookup"><span data-stu-id="f9de0-184">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="f9de0-185">O formato geral dos blocos de código isolados é:</span><span class="sxs-lookup"><span data-stu-id="f9de0-185">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="f9de0-186">O alias após os três caracteres de acento grave (\`) iniciais define o destaque de sintaxe a ser usado.</span><span class="sxs-lookup"><span data-stu-id="f9de0-186">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="f9de0-187">Veja a seguir uma lista de linguagens de programação normalmente usadas no conteúdo do Docs e no rótulo correspondente:</span><span class="sxs-lookup"><span data-stu-id="f9de0-187">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="f9de0-188">Essas linguagens têm o suporte de nome amigável e a maioria tem realce de linguagem.</span><span class="sxs-lookup"><span data-stu-id="f9de0-188">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="f9de0-189">Nome</span><span class="sxs-lookup"><span data-stu-id="f9de0-189">Name</span></span>|<span data-ttu-id="f9de0-190">Rótulo de Markdown</span><span class="sxs-lookup"><span data-stu-id="f9de0-190">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="f9de0-191">Console do .NET</span><span class="sxs-lookup"><span data-stu-id="f9de0-191">.NET Console</span></span>|<span data-ttu-id="f9de0-192">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="f9de0-192">dotnetcli</span></span>|
|<span data-ttu-id="f9de0-193">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="f9de0-193">ASP.NET (C#)</span></span>|<span data-ttu-id="f9de0-194">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="f9de0-194">aspx-csharp</span></span>|
|<span data-ttu-id="f9de0-195">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="f9de0-195">ASP.NET (VB)</span></span>|<span data-ttu-id="f9de0-196">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="f9de0-196">aspx-vb</span></span>|
|<span data-ttu-id="f9de0-197">AzCopy</span><span class="sxs-lookup"><span data-stu-id="f9de0-197">AzCopy</span></span>|<span data-ttu-id="f9de0-198">azcopy</span><span class="sxs-lookup"><span data-stu-id="f9de0-198">azcopy</span></span>|
|<span data-ttu-id="f9de0-199">CLI do Azure</span><span class="sxs-lookup"><span data-stu-id="f9de0-199">Azure CLI</span></span>|<span data-ttu-id="f9de0-200">azurecli</span><span class="sxs-lookup"><span data-stu-id="f9de0-200">azurecli</span></span>|
|<span data-ttu-id="f9de0-201">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9de0-201">Azure PowerShell</span></span>|<span data-ttu-id="f9de0-202">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="f9de0-202">azurepowershell</span></span>|
|<span data-ttu-id="f9de0-203">C++</span><span class="sxs-lookup"><span data-stu-id="f9de0-203">C++</span></span>|<span data-ttu-id="f9de0-204">cpp</span><span class="sxs-lookup"><span data-stu-id="f9de0-204">cpp</span></span>|
|<span data-ttu-id="f9de0-205">C++/CX</span><span class="sxs-lookup"><span data-stu-id="f9de0-205">C++/CX</span></span>|<span data-ttu-id="f9de0-206">cppcx</span><span class="sxs-lookup"><span data-stu-id="f9de0-206">cppcx</span></span>|
|<span data-ttu-id="f9de0-207">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="f9de0-207">C++/WinRT</span></span>|<span data-ttu-id="f9de0-208">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="f9de0-208">cppwinrt</span></span>|
|<span data-ttu-id="f9de0-209">C#</span><span class="sxs-lookup"><span data-stu-id="f9de0-209">C#</span></span>|<span data-ttu-id="f9de0-210">csharp</span><span class="sxs-lookup"><span data-stu-id="f9de0-210">csharp</span></span>|
|<span data-ttu-id="f9de0-211">CSHTML</span><span class="sxs-lookup"><span data-stu-id="f9de0-211">CSHTML</span></span>|<span data-ttu-id="f9de0-212">cshtml</span><span class="sxs-lookup"><span data-stu-id="f9de0-212">cshtml</span></span>|
|<span data-ttu-id="f9de0-213">DAX</span><span class="sxs-lookup"><span data-stu-id="f9de0-213">DAX</span></span>|<span data-ttu-id="f9de0-214">dax</span><span class="sxs-lookup"><span data-stu-id="f9de0-214">dax</span></span>|
|<span data-ttu-id="f9de0-215">F#</span><span class="sxs-lookup"><span data-stu-id="f9de0-215">F#</span></span>|<span data-ttu-id="f9de0-216">fsharp</span><span class="sxs-lookup"><span data-stu-id="f9de0-216">fsharp</span></span>|
|<span data-ttu-id="f9de0-217">Go</span><span class="sxs-lookup"><span data-stu-id="f9de0-217">Go</span></span>|<span data-ttu-id="f9de0-218">go</span><span class="sxs-lookup"><span data-stu-id="f9de0-218">go</span></span>|
|<span data-ttu-id="f9de0-219">HTML</span><span class="sxs-lookup"><span data-stu-id="f9de0-219">HTML</span></span>|<span data-ttu-id="f9de0-220">html</span><span class="sxs-lookup"><span data-stu-id="f9de0-220">html</span></span>|
|<span data-ttu-id="f9de0-221">HTTP</span><span class="sxs-lookup"><span data-stu-id="f9de0-221">HTTP</span></span>|<span data-ttu-id="f9de0-222">http</span><span class="sxs-lookup"><span data-stu-id="f9de0-222">http</span></span>|
|<span data-ttu-id="f9de0-223">Java</span><span class="sxs-lookup"><span data-stu-id="f9de0-223">Java</span></span>|<span data-ttu-id="f9de0-224">java</span><span class="sxs-lookup"><span data-stu-id="f9de0-224">java</span></span>|
|<span data-ttu-id="f9de0-225">JavaScript</span><span class="sxs-lookup"><span data-stu-id="f9de0-225">JavaScript</span></span>|<span data-ttu-id="f9de0-226">javascript</span><span class="sxs-lookup"><span data-stu-id="f9de0-226">javascript</span></span>|
|<span data-ttu-id="f9de0-227">JSON</span><span class="sxs-lookup"><span data-stu-id="f9de0-227">JSON</span></span>|<span data-ttu-id="f9de0-228">json</span><span class="sxs-lookup"><span data-stu-id="f9de0-228">json</span></span>|
|<span data-ttu-id="f9de0-229">Markdown</span><span class="sxs-lookup"><span data-stu-id="f9de0-229">Markdown</span></span>|<span data-ttu-id="f9de0-230">md</span><span class="sxs-lookup"><span data-stu-id="f9de0-230">md</span></span>|
|<span data-ttu-id="f9de0-231">NodeJS</span><span class="sxs-lookup"><span data-stu-id="f9de0-231">NodeJS</span></span>|<span data-ttu-id="f9de0-232">nodejs</span><span class="sxs-lookup"><span data-stu-id="f9de0-232">nodejs</span></span>|
|<span data-ttu-id="f9de0-233">Objective-C</span><span class="sxs-lookup"><span data-stu-id="f9de0-233">Objective-C</span></span>|<span data-ttu-id="f9de0-234">objc</span><span class="sxs-lookup"><span data-stu-id="f9de0-234">objc</span></span>|
|<span data-ttu-id="f9de0-235">OData</span><span class="sxs-lookup"><span data-stu-id="f9de0-235">OData</span></span>|<span data-ttu-id="f9de0-236">odata</span><span class="sxs-lookup"><span data-stu-id="f9de0-236">odata</span></span>|
|<span data-ttu-id="f9de0-237">PHP</span><span class="sxs-lookup"><span data-stu-id="f9de0-237">PHP</span></span>|<span data-ttu-id="f9de0-238">php</span><span class="sxs-lookup"><span data-stu-id="f9de0-238">php</span></span>|
|<span data-ttu-id="f9de0-239">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="f9de0-239">Power Apps Formula</span></span>|<span data-ttu-id="f9de0-240">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="f9de0-240">powerappsfl</span></span>|
|<span data-ttu-id="f9de0-241">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9de0-241">PowerShell</span></span>|<span data-ttu-id="f9de0-242">powershell</span><span class="sxs-lookup"><span data-stu-id="f9de0-242">powershell</span></span>|
|<span data-ttu-id="f9de0-243">Python</span><span class="sxs-lookup"><span data-stu-id="f9de0-243">Python</span></span>|<span data-ttu-id="f9de0-244">python</span><span class="sxs-lookup"><span data-stu-id="f9de0-244">python</span></span>|
|<span data-ttu-id="f9de0-245">Q#</span><span class="sxs-lookup"><span data-stu-id="f9de0-245">Q#</span></span>|<span data-ttu-id="f9de0-246">qsharp</span><span class="sxs-lookup"><span data-stu-id="f9de0-246">qsharp</span></span>|
|<span data-ttu-id="f9de0-247">Ruby</span><span class="sxs-lookup"><span data-stu-id="f9de0-247">Ruby</span></span>|<span data-ttu-id="f9de0-248">ruby</span><span class="sxs-lookup"><span data-stu-id="f9de0-248">ruby</span></span>|
|<span data-ttu-id="f9de0-249">SQL</span><span class="sxs-lookup"><span data-stu-id="f9de0-249">SQL</span></span>|<span data-ttu-id="f9de0-250">sql</span><span class="sxs-lookup"><span data-stu-id="f9de0-250">sql</span></span>|
|<span data-ttu-id="f9de0-251">Swift</span><span class="sxs-lookup"><span data-stu-id="f9de0-251">Swift</span></span>|<span data-ttu-id="f9de0-252">swift</span><span class="sxs-lookup"><span data-stu-id="f9de0-252">swift</span></span>|
|<span data-ttu-id="f9de0-253">TypeScript</span><span class="sxs-lookup"><span data-stu-id="f9de0-253">TypeScript</span></span>|<span data-ttu-id="f9de0-254">typescript</span><span class="sxs-lookup"><span data-stu-id="f9de0-254">typescript</span></span>|
|<span data-ttu-id="f9de0-255">VB</span><span class="sxs-lookup"><span data-stu-id="f9de0-255">VB</span></span>|<span data-ttu-id="f9de0-256">vb</span><span class="sxs-lookup"><span data-stu-id="f9de0-256">vb</span></span>|
|<span data-ttu-id="f9de0-257">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="f9de0-257">VSTS CLI</span></span>|<span data-ttu-id="f9de0-258">vstscli</span><span class="sxs-lookup"><span data-stu-id="f9de0-258">vstscli</span></span>|
|<span data-ttu-id="f9de0-259">XAML</span><span class="sxs-lookup"><span data-stu-id="f9de0-259">XAML</span></span>|<span data-ttu-id="f9de0-260">xaml</span><span class="sxs-lookup"><span data-stu-id="f9de0-260">xaml</span></span>|
|<span data-ttu-id="f9de0-261">XML</span><span class="sxs-lookup"><span data-stu-id="f9de0-261">XML</span></span>|<span data-ttu-id="f9de0-262">xml</span><span class="sxs-lookup"><span data-stu-id="f9de0-262">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="f9de0-263">Exemplo: C\#</span><span class="sxs-lookup"><span data-stu-id="f9de0-263">Example: C\#</span></span>

<span data-ttu-id="f9de0-264">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="f9de0-264">__Markdown__</span></span>

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

<span data-ttu-id="f9de0-265">__Renderização__</span><span class="sxs-lookup"><span data-stu-id="f9de0-265">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="f9de0-266">Exemplo: SQL</span><span class="sxs-lookup"><span data-stu-id="f9de0-266">Example: SQL</span></span>

<span data-ttu-id="f9de0-267">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="f9de0-267">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="f9de0-268">__Renderização__</span><span class="sxs-lookup"><span data-stu-id="f9de0-268">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="f9de0-269">Extensões de Markdown personalizada do OPS</span><span class="sxs-lookup"><span data-stu-id="f9de0-269">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="f9de0-270">O OPS (Open Publishing Services) implementa o DFM (DocFX Flavored Markdown), que é altamente compatível com o GFM (GitHub Flavored Markdown).</span><span class="sxs-lookup"><span data-stu-id="f9de0-270">Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM), which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="f9de0-271">O DFM adiciona algumas funcionalidades por meio de extensões de Markdown.</span><span class="sxs-lookup"><span data-stu-id="f9de0-271">DFM adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="f9de0-272">Portanto, alguns artigos selecionados no Guia de Criação do OPS completo foram incluídos neste guia para referência.</span><span class="sxs-lookup"><span data-stu-id="f9de0-272">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="f9de0-273">(Por exemplo, consulte "DFM e extensões de Markdown" e "Trechos de código" no sumário.)</span><span class="sxs-lookup"><span data-stu-id="f9de0-273">(For example, see "DFM and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="f9de0-274">Os artigos do Docs usam o GFM para a maior parte da formatação do artigo, como parágrafos, links, listas e cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="f9de0-274">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="f9de0-275">Para uma formatação mais avançada, os artigos podem usar recursos de DFM, como:</span><span class="sxs-lookup"><span data-stu-id="f9de0-275">For richer formatting, articles can use DFM features such as:</span></span>

- <span data-ttu-id="f9de0-276">Blocos de nota</span><span class="sxs-lookup"><span data-stu-id="f9de0-276">Note blocks</span></span>
- <span data-ttu-id="f9de0-277">Inclusões</span><span class="sxs-lookup"><span data-stu-id="f9de0-277">Includes</span></span>
- <span data-ttu-id="f9de0-278">Seletores</span><span class="sxs-lookup"><span data-stu-id="f9de0-278">Selectors</span></span>
- <span data-ttu-id="f9de0-279">Vídeos incorporados</span><span class="sxs-lookup"><span data-stu-id="f9de0-279">Embedded videos</span></span>
- <span data-ttu-id="f9de0-280">Trechos/amostras de código</span><span class="sxs-lookup"><span data-stu-id="f9de0-280">Code snippets/samples</span></span>

<span data-ttu-id="f9de0-281">Para obter a lista completa, consulte "DFM e extensões de Markdown" e "Trechos de código" no sumário.</span><span class="sxs-lookup"><span data-stu-id="f9de0-281">For the complete list, refer to "DFM and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="f9de0-282">Blocos de nota</span><span class="sxs-lookup"><span data-stu-id="f9de0-282">Note blocks</span></span>

<span data-ttu-id="f9de0-283">Você pode escolher entre quatro tipos de blocos de notas para chamar atenção para um conteúdo específico:</span><span class="sxs-lookup"><span data-stu-id="f9de0-283">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="f9de0-284">OBSERVAÇÃO</span><span class="sxs-lookup"><span data-stu-id="f9de0-284">NOTE</span></span>
- <span data-ttu-id="f9de0-285">AVISO</span><span class="sxs-lookup"><span data-stu-id="f9de0-285">WARNING</span></span>
- <span data-ttu-id="f9de0-286">DICA</span><span class="sxs-lookup"><span data-stu-id="f9de0-286">TIP</span></span>
- <span data-ttu-id="f9de0-287">IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="f9de0-287">IMPORTANT</span></span>

<span data-ttu-id="f9de0-288">Em geral, os blocos de notas devem ser usados com moderação porque eles podem atrapalhar.</span><span class="sxs-lookup"><span data-stu-id="f9de0-288">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="f9de0-289">Embora eles também deem suporte para blocos de código, imagens, listas e links, tente manter seus blocos de nota simples e diretos.</span><span class="sxs-lookup"><span data-stu-id="f9de0-289">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="f9de0-290">Inclusões</span><span class="sxs-lookup"><span data-stu-id="f9de0-290">Includes</span></span>

<span data-ttu-id="f9de0-291">Quando você tiver um texto ou arquivos de imagem reutilizáveis que precisem ser incluídos nos arquivos do artigo, use uma referência ao arquivo de "inclusão" por meio do recurso de inclusão de arquivo do DFM.</span><span class="sxs-lookup"><span data-stu-id="f9de0-291">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the DFM file include feature.</span></span> <span data-ttu-id="f9de0-292">Esse recurso instrui o OPS a incluir o arquivo no arquivo do artigo no tempo de build, para que ele faça parte do artigo publicado.</span><span class="sxs-lookup"><span data-stu-id="f9de0-292">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="f9de0-293">Três tipos de inclusões estão disponíveis para ajudá-lo a reutilizar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="f9de0-293">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="f9de0-294">Embutido: reutilize um trecho de texto comum embutido dentro de outra frase.</span><span class="sxs-lookup"><span data-stu-id="f9de0-294">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="f9de0-295">Bloco: reutilize um arquivo Markdown inteiro como um bloco aninhado dentro de uma seção de um artigo.</span><span class="sxs-lookup"><span data-stu-id="f9de0-295">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="f9de0-296">Imagem: é como a inclusão de imagem padrão é implementada no Docs.</span><span class="sxs-lookup"><span data-stu-id="f9de0-296">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="f9de0-297">A inclusão de um embutido ou de um bloco é apenas um arquivo Markdown (.md) simples.</span><span class="sxs-lookup"><span data-stu-id="f9de0-297">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="f9de0-298">Ele pode conter qualquer Markdown válido.</span><span class="sxs-lookup"><span data-stu-id="f9de0-298">It can contain any valid Markdown.</span></span> <span data-ttu-id="f9de0-299">Todos os arquivos Markdown de inclusão devem ser colocados em um [subdiretório `/includes` comum](git-github-fundamentals.md#includes-subdirectory), na raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="f9de0-299">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="f9de0-300">Quando o artigo é publicado, o arquivo incluído fica perfeitamente integrado.</span><span class="sxs-lookup"><span data-stu-id="f9de0-300">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="f9de0-301">Aqui estão os requisitos e as considerações para inclusões:</span><span class="sxs-lookup"><span data-stu-id="f9de0-301">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="f9de0-302">Use inclusões sempre que precisar que o mesmo texto apareça em vários artigos.</span><span class="sxs-lookup"><span data-stu-id="f9de0-302">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="f9de0-303">Use inclusões em bloco para quantidades consideráveis de conteúdo, como um ou dois parágrafos, um procedimento compartilhado ou uma seção compartilhada.</span><span class="sxs-lookup"><span data-stu-id="f9de0-303">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="f9de0-304">Não use-os para nada menor do que uma sentença.</span><span class="sxs-lookup"><span data-stu-id="f9de0-304">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="f9de0-305">As inclusões não serão renderizadas no modo de exibição renderizado do GitHub do seu artigo, pois elas dependem de extensões DFM.</span><span class="sxs-lookup"><span data-stu-id="f9de0-305">Includes won't be rendered in the GitHub rendered view of your article, because they rely on DFM extensions.</span></span> <span data-ttu-id="f9de0-306">Elas serão renderizadas somente após a publicação.</span><span class="sxs-lookup"><span data-stu-id="f9de0-306">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="f9de0-307">Verifique se todo o texto em uma inclusão está escrito em sentenças ou frases completas que não dependem do texto anterior ou seguinte no artigo que faz referência à inclusão.</span><span class="sxs-lookup"><span data-stu-id="f9de0-307">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="f9de0-308">Se você ignorar essa orientação, criará uma cadeia de caracteres não traduzível no artigo que quebrará a experiência localizada.</span><span class="sxs-lookup"><span data-stu-id="f9de0-308">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="f9de0-309">Não incorpore inclusões dentro de outras inclusões.</span><span class="sxs-lookup"><span data-stu-id="f9de0-309">Don't embed includes within other includes.</span></span> <span data-ttu-id="f9de0-310">Não há suporte para isso.</span><span class="sxs-lookup"><span data-stu-id="f9de0-310">They are not supported.</span></span>
- <span data-ttu-id="f9de0-311">Coloque os arquivos de mídia em uma pasta de mídia específica para o subdiretório de inclusão, por exemplo, a pasta `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="f9de0-311">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="f9de0-312">O diretório de mídia não deve conter imagens em sua raiz.</span><span class="sxs-lookup"><span data-stu-id="f9de0-312">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="f9de0-313">Se a inclusão não tiver imagens, não será necessário ter um diretório de mídia correspondente.</span><span class="sxs-lookup"><span data-stu-id="f9de0-313">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="f9de0-314">Assim como ocorre com os artigos regulares, não compartilhe a mídia entre arquivos de inclusão.</span><span class="sxs-lookup"><span data-stu-id="f9de0-314">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="f9de0-315">Use um arquivo separado com um nome exclusivo para cada inclusão e artigo.</span><span class="sxs-lookup"><span data-stu-id="f9de0-315">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="f9de0-316">Armazene o arquivo de mídia na pasta de mídia associada à inclusão.</span><span class="sxs-lookup"><span data-stu-id="f9de0-316">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="f9de0-317">Não use uma inclusão como único conteúdo de um artigo.</span><span class="sxs-lookup"><span data-stu-id="f9de0-317">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="f9de0-318">As inclusões servem como complemento ao conteúdo do restante do artigo.</span><span class="sxs-lookup"><span data-stu-id="f9de0-318">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="f9de0-319">Seletores</span><span class="sxs-lookup"><span data-stu-id="f9de0-319">Selectors</span></span>

<span data-ttu-id="f9de0-320">Use seletores em artigos técnicos ao criar vários tipos do mesmo artigo, a fim de solucionar diferenças de implementação entre tecnologias e plataformas.</span><span class="sxs-lookup"><span data-stu-id="f9de0-320">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="f9de0-321">Normalmente, isso é mais aplicável ao nosso conteúdo de plataforma móvel para desenvolvedores.</span><span class="sxs-lookup"><span data-stu-id="f9de0-321">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="f9de0-322">No momento, há dois tipos diferentes de seletores no DFM, um seletor único e um seletor múltiplo.</span><span class="sxs-lookup"><span data-stu-id="f9de0-322">There are currently two different types of selectors in DFM, a single selector and a multi-selector.</span></span>

<span data-ttu-id="f9de0-323">Como o mesmo Markdown seletor vai para cada artigo na seleção, recomendamos posicionar o seletor do artigo em uma inclusão.</span><span class="sxs-lookup"><span data-stu-id="f9de0-323">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="f9de0-324">Em seguida, você poderá referenciar essa inclusão em todos os artigos que usarem o mesmo seletor.</span><span class="sxs-lookup"><span data-stu-id="f9de0-324">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="f9de0-325">Trechos de código</span><span class="sxs-lookup"><span data-stu-id="f9de0-325">Code snippets</span></span>

<span data-ttu-id="f9de0-326">O DFM também é compatível com a inclusão avançada de código em um artigo por meio de sua extensão de trecho de código.</span><span class="sxs-lookup"><span data-stu-id="f9de0-326">DFM supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="f9de0-327">Ela fornece renderização avançada que aproveita os recursos do GFM, como seleção de linguagem de programação e coloração de sintaxe, além de recursos incríveis como:</span><span class="sxs-lookup"><span data-stu-id="f9de0-327">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="f9de0-328">Inclusão de amostras/trechos de código centralizados de um repositório externo.</span><span class="sxs-lookup"><span data-stu-id="f9de0-328">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="f9de0-329">Interface do usuário com guias para mostrar várias versões de amostras de código em linguagens diferentes.</span><span class="sxs-lookup"><span data-stu-id="f9de0-329">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="f9de0-330">Armadilhas e solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f9de0-330">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="f9de0-331">Texto Alt</span><span class="sxs-lookup"><span data-stu-id="f9de0-331">Alt text</span></span>

<span data-ttu-id="f9de0-332">Textos Alt que contenham caracteres sublinhado não serão renderizados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="f9de0-332">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="f9de0-333">Por exemplo, em vez de usar isto:</span><span class="sxs-lookup"><span data-stu-id="f9de0-333">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="f9de0-334">Insira um escape para os sublinhados desta forma:</span><span class="sxs-lookup"><span data-stu-id="f9de0-334">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="f9de0-335">Apóstrofes e aspas</span><span class="sxs-lookup"><span data-stu-id="f9de0-335">Apostrophes and quotation marks</span></span>

<span data-ttu-id="f9de0-336">Se você copiar do Word para um editor de Markdown, o texto poderá conter apóstrofes ou aspas "inteligentes" (inglesas).</span><span class="sxs-lookup"><span data-stu-id="f9de0-336">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="f9de0-337">Eles precisam ser codificados ou alterados para apóstrofos ou aspas simples.</span><span class="sxs-lookup"><span data-stu-id="f9de0-337">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="f9de0-338">Caso contrário, quando o arquivo for publicado poderão ocorrer erros como: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="f9de0-338">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="f9de0-339">Estas são as codificações para as versões "inteligentes" dessas marcas de pontuação:</span><span class="sxs-lookup"><span data-stu-id="f9de0-339">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="f9de0-340">Aspas à esquerda (de abertura): `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="f9de0-340">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="f9de0-341">Aspas à direita (de fechamento): `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="f9de0-341">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="f9de0-342">Aspas simples à direita (de fechamento) ou apóstrofe: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="f9de0-342">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="f9de0-343">Aspas simples à esquerda (de abertura) (raramente usadas): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="f9de0-343">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="f9de0-344">Colchetes angulares</span><span class="sxs-lookup"><span data-stu-id="f9de0-344">Angle brackets</span></span>

<span data-ttu-id="f9de0-345">Se você usar colchetes angulares no texto (não no código) no arquivo, por exemplo, para indicar um espaço reservado, será necessário codificar manualmente os colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="f9de0-345">If you use angle brackets in text (not code) in your file--for example, to denote a placeholder--you need to manually encode the angle brackets.</span></span> <span data-ttu-id="f9de0-346">Caso contrário, o Markdown entenderá que eles são uma marca HTML.</span><span class="sxs-lookup"><span data-stu-id="f9de0-346">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="f9de0-347">Por exemplo, codifique `<script name>` como `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="f9de0-347">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="f9de0-348">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f9de0-348">See also</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="f9de0-349">Recursos do Markdown</span><span class="sxs-lookup"><span data-stu-id="f9de0-349">Markdown resources</span></span>

- [<span data-ttu-id="f9de0-350">Introdução a Markdown</span><span class="sxs-lookup"><span data-stu-id="f9de0-350">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="f9de0-351">Roteiro de Markdown do Docs</span><span class="sxs-lookup"><span data-stu-id="f9de0-351">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="f9de0-352">Noções básicas de Markdown do GitHub</span><span class="sxs-lookup"><span data-stu-id="f9de0-352">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
