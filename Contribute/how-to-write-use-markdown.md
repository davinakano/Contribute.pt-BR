---
title: Como usar o Markdown para escrever Docs
description: Este artigo descreve as noções básicas e informações de referência para a linguagem Markdown usada para escrever artigos do docs.microsoft.com.
ms.date: 07/13/2017
ms.openlocfilehash: ef75ffd59b75db5757822642f651d863906cf14c
ms.sourcegitcommit: 18c271ebec920bb976a4bc901f4ab8c1d36b02fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53615825"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="9b69d-103">Como usar o Markdown para escrever Docs</span><span class="sxs-lookup"><span data-stu-id="9b69d-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="9b69d-104">Os artigos do [docs.microsoft.com](http://docs.microsoft.com) são escritos em uma linguagem de marcação leve chamada [Markdown](https://daringfireball.net/projects/markdown/), que é fácil de ler e aprender.</span><span class="sxs-lookup"><span data-stu-id="9b69d-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="9b69d-105">Por isso, tornou-se rapidamente um padrão do setor.</span><span class="sxs-lookup"><span data-stu-id="9b69d-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="9b69d-106">Como o conteúdo do Docs é armazenado no GitHub, ele pode usar um superconjunto de Markdown chamado [GFM (GitHub Flavored Markdown)](https://help.github.com/categories/writing-on-github/), que fornece mais funcionalidades para necessidades de formatação comuns.</span><span class="sxs-lookup"><span data-stu-id="9b69d-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="9b69d-107">Além disso, o OPS (Open Publishing Services) implementa o Analisador de Markdown Markdig.</span><span class="sxs-lookup"><span data-stu-id="9b69d-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="9b69d-108">O Markdig é altamente compatível com o GFM, agregando funcionalidades para habilitar recursos específicos do Docs.</span><span class="sxs-lookup"><span data-stu-id="9b69d-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="9b69d-109">O Markdig é um processador de Markdown extensível, em conformidade com CommonMark potente e rápido para .NET.</span><span class="sxs-lookup"><span data-stu-id="9b69d-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="9b69d-110">Melhor suporte da comunidade</span><span class="sxs-lookup"><span data-stu-id="9b69d-110">Better community support</span></span>
* <span data-ttu-id="9b69d-111">Melhor suporte de padrões</span><span class="sxs-lookup"><span data-stu-id="9b69d-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="9b69d-112">Noções básicas de markdown</span><span class="sxs-lookup"><span data-stu-id="9b69d-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="9b69d-113">Títulos</span><span class="sxs-lookup"><span data-stu-id="9b69d-113">Headings</span></span>

<span data-ttu-id="9b69d-114">Para criar um título, use uma marca de hash (#), da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9b69d-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

<span data-ttu-id="9b69d-115">Os cabeçalhos devem ter o estilo atx, ou seja, usar 1 a 6 caracteres de hash (#) no início da linha para indicar um cabeçalho, correspondente aos cabeçalhos HTML H1 a H6.</span><span class="sxs-lookup"><span data-stu-id="9b69d-115">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="9b69d-116">Exemplos de cabeçalhos de primeiro a quarto nível são usados acima.</span><span class="sxs-lookup"><span data-stu-id="9b69d-116">Examples of first- through fourth-level headers are used above.</span></span>

<span data-ttu-id="9b69d-117">**Deve** haver pelo menos um cabeçalho de primeiro nível (H1) em seu tópico, que será exibido como o título de página.</span><span class="sxs-lookup"><span data-stu-id="9b69d-117">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="9b69d-118">Se o cabeçalho terminar com um caractere `#`, você precisará adicionar um caractere `#` extra ao final para que o título seja renderizado corretamente.</span><span class="sxs-lookup"><span data-stu-id="9b69d-118">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="9b69d-119">Por exemplo, `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="9b69d-119">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="9b69d-120">Cabeçalhos de segundo nível geram o Sumário na página que aparece na seção "Neste artigo" abaixo do título de página.</span><span class="sxs-lookup"><span data-stu-id="9b69d-120">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="bold-and-italic-text"></a><span data-ttu-id="9b69d-121">Texto em negrito e em itálico</span><span class="sxs-lookup"><span data-stu-id="9b69d-121">Bold and italic text</span></span>

<span data-ttu-id="9b69d-122">Para formatar o texto como **negrito**, coloque dois asteriscos de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="9b69d-122">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="9b69d-123">Para formatar o texto como *itálico*, coloque um único asterisco de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="9b69d-123">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="9b69d-124">Para formatar o texto como ***negrito e itálico***, coloque três asteriscos de cada lado do texto:</span><span class="sxs-lookup"><span data-stu-id="9b69d-124">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a><span data-ttu-id="9b69d-125">Citações em bloco</span><span class="sxs-lookup"><span data-stu-id="9b69d-125">Blockquotes</span></span>

<span data-ttu-id="9b69d-126">Citações em bloco são criadas usando o caractere `>`:</span><span class="sxs-lookup"><span data-stu-id="9b69d-126">Blockquotes are created using the `>` character:</span></span>

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

<span data-ttu-id="9b69d-127">O exemplo anterior é renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9b69d-127">The preceding example renders as follows:</span></span>

> <span data-ttu-id="9b69d-128">A seca já dura dez milhões de anos, e o reino dos terríveis lagartos terminou há muito tempo.</span><span class="sxs-lookup"><span data-stu-id="9b69d-128">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="9b69d-129">Aqui no Equador, no continente que um dia seria conhecido com África, a luta pela existência chegou ao ápice da ferocidade e o vencedor ainda não está à vista.</span><span class="sxs-lookup"><span data-stu-id="9b69d-129">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="9b69d-130">Nestas terras estéreis e áridas, somente os pequenos, os rápidos ou os fortes podem prosperar ou até mesmo esperar sobreviver.</span><span class="sxs-lookup"><span data-stu-id="9b69d-130">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

### <a name="lists"></a><span data-ttu-id="9b69d-131">Listas</span><span class="sxs-lookup"><span data-stu-id="9b69d-131">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="9b69d-132">Lista não ordenada</span><span class="sxs-lookup"><span data-stu-id="9b69d-132">Unordered list</span></span>

<span data-ttu-id="9b69d-133">Para formatar uma lista não ordenada/com marcador, use asteriscos ou traços.</span><span class="sxs-lookup"><span data-stu-id="9b69d-133">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="9b69d-134">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b69d-134">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="9b69d-135">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="9b69d-135">will be rendered as:</span></span>

- <span data-ttu-id="9b69d-136">Item de lista 1</span><span class="sxs-lookup"><span data-stu-id="9b69d-136">List item 1</span></span>
- <span data-ttu-id="9b69d-137">Item de lista 2</span><span class="sxs-lookup"><span data-stu-id="9b69d-137">List item 2</span></span>
- <span data-ttu-id="9b69d-138">Item de lista 3</span><span class="sxs-lookup"><span data-stu-id="9b69d-138">List item 3</span></span>

<span data-ttu-id="9b69d-139">Para aninhar uma lista em outra lista, recue os itens de lista filha.</span><span class="sxs-lookup"><span data-stu-id="9b69d-139">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="9b69d-140">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b69d-140">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="9b69d-141">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="9b69d-141">will be rendered as:</span></span>

- <span data-ttu-id="9b69d-142">Item de lista 1</span><span class="sxs-lookup"><span data-stu-id="9b69d-142">List item 1</span></span>
  - <span data-ttu-id="9b69d-143">Item de lista A</span><span class="sxs-lookup"><span data-stu-id="9b69d-143">List item A</span></span>
  - <span data-ttu-id="9b69d-144">Item de lista B</span><span class="sxs-lookup"><span data-stu-id="9b69d-144">List item B</span></span>
- <span data-ttu-id="9b69d-145">Item de lista 2</span><span class="sxs-lookup"><span data-stu-id="9b69d-145">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="9b69d-146">Lista ordenada</span><span class="sxs-lookup"><span data-stu-id="9b69d-146">Ordered list</span></span>

<span data-ttu-id="9b69d-147">Para formatar uma lista ordenada/gradual, use números correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9b69d-147">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="9b69d-148">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b69d-148">For example, the following Markdown:</span></span>

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

<span data-ttu-id="9b69d-149">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="9b69d-149">will be rendered as:</span></span>

1. <span data-ttu-id="9b69d-150">Primeira instrução</span><span class="sxs-lookup"><span data-stu-id="9b69d-150">First instruction</span></span>
2. <span data-ttu-id="9b69d-151">Segunda instrução</span><span class="sxs-lookup"><span data-stu-id="9b69d-151">Second instruction</span></span>
3. <span data-ttu-id="9b69d-152">Terceira instrução</span><span class="sxs-lookup"><span data-stu-id="9b69d-152">Third instruction</span></span>

<span data-ttu-id="9b69d-153">Para aninhar uma lista em outra lista, recue os itens de lista filha.</span><span class="sxs-lookup"><span data-stu-id="9b69d-153">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="9b69d-154">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b69d-154">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

<span data-ttu-id="9b69d-155">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="9b69d-155">will be rendered as:</span></span>

1. <span data-ttu-id="9b69d-156">Primeira instrução</span><span class="sxs-lookup"><span data-stu-id="9b69d-156">First instruction</span></span>
   1. <span data-ttu-id="9b69d-157">Subinstrução</span><span class="sxs-lookup"><span data-stu-id="9b69d-157">Sub-instruction</span></span>
   2. <span data-ttu-id="9b69d-158">Subinstrução</span><span class="sxs-lookup"><span data-stu-id="9b69d-158">Sub-instruction</span></span>
2. <span data-ttu-id="9b69d-159">Segunda instrução</span><span class="sxs-lookup"><span data-stu-id="9b69d-159">Second instruction</span></span>

<span data-ttu-id="9b69d-160">Observe que usamos '1.'</span><span class="sxs-lookup"><span data-stu-id="9b69d-160">Note that we use '1.'</span></span> <span data-ttu-id="9b69d-161">para todas as entradas.</span><span class="sxs-lookup"><span data-stu-id="9b69d-161">for all entries.</span></span> <span data-ttu-id="9b69d-162">Isso facilita a análise de comparações quando atualizações posteriores incluírem novas etapas ou removerem etapas existentes.</span><span class="sxs-lookup"><span data-stu-id="9b69d-162">It makes diffs easier to review when later updates include new steps or remove existing steps.</span></span>

### <a name="tables"></a><span data-ttu-id="9b69d-163">Tabelas</span><span class="sxs-lookup"><span data-stu-id="9b69d-163">Tables</span></span>

<span data-ttu-id="9b69d-164">As tabelas não fazem parte da especificação principal do Markdown, mas são compatíveis com o GFM.</span><span class="sxs-lookup"><span data-stu-id="9b69d-164">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="9b69d-165">Você pode criar tabelas usando os caracteres barra vertical (|) e hífen (-).</span><span class="sxs-lookup"><span data-stu-id="9b69d-165">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="9b69d-166">Os hifens criam o cabeçalho de cada coluna e as barras verticais separam cada coluna.</span><span class="sxs-lookup"><span data-stu-id="9b69d-166">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="9b69d-167">Inclua uma linha em branco antes da sua tabela para que a renderização ocorra corretamente.</span><span class="sxs-lookup"><span data-stu-id="9b69d-167">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="9b69d-168">Por exemplo, o Markdown a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b69d-168">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="9b69d-169">será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="9b69d-169">will be rendered as:</span></span>

| <span data-ttu-id="9b69d-170">Diversão</span><span class="sxs-lookup"><span data-stu-id="9b69d-170">Fun</span></span>                  | <span data-ttu-id="9b69d-171">Com</span><span class="sxs-lookup"><span data-stu-id="9b69d-171">With</span></span>                 | <span data-ttu-id="9b69d-172">Tabelas</span><span class="sxs-lookup"><span data-stu-id="9b69d-172">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="9b69d-173">coluna alinhada à esquerda</span><span class="sxs-lookup"><span data-stu-id="9b69d-173">left-aligned column</span></span>  | <span data-ttu-id="9b69d-174">coluna alinhada à direita</span><span class="sxs-lookup"><span data-stu-id="9b69d-174">right-aligned column</span></span> | <span data-ttu-id="9b69d-175">coluna centralizada</span><span class="sxs-lookup"><span data-stu-id="9b69d-175">centered column</span></span> |
| <span data-ttu-id="9b69d-176">$100</span><span class="sxs-lookup"><span data-stu-id="9b69d-176">$100</span></span>                 | <span data-ttu-id="9b69d-177">$100</span><span class="sxs-lookup"><span data-stu-id="9b69d-177">$100</span></span>                 | <span data-ttu-id="9b69d-178">$100</span><span class="sxs-lookup"><span data-stu-id="9b69d-178">$100</span></span>            |
| <span data-ttu-id="9b69d-179">$10</span><span class="sxs-lookup"><span data-stu-id="9b69d-179">$10</span></span>                  | <span data-ttu-id="9b69d-180">$10</span><span class="sxs-lookup"><span data-stu-id="9b69d-180">$10</span></span>                  | <span data-ttu-id="9b69d-181">$10</span><span class="sxs-lookup"><span data-stu-id="9b69d-181">$10</span></span>             |
| <span data-ttu-id="9b69d-182">$1</span><span class="sxs-lookup"><span data-stu-id="9b69d-182">$1</span></span>                   | <span data-ttu-id="9b69d-183">$1</span><span class="sxs-lookup"><span data-stu-id="9b69d-183">$1</span></span>                   | <span data-ttu-id="9b69d-184">$1</span><span class="sxs-lookup"><span data-stu-id="9b69d-184">$1</span></span>              |

<span data-ttu-id="9b69d-185">Para saber mais sobre como criar tabelas, consulte:</span><span class="sxs-lookup"><span data-stu-id="9b69d-185">For more information on creating tables, see:</span></span>

- <span data-ttu-id="9b69d-186">O [recurso de encapsulamento da tabela](#table-wrapping) do Markdig, que pode ajudar com a formatação de tabelas grandes.</span><span class="sxs-lookup"><span data-stu-id="9b69d-186">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="9b69d-187">[Organizar informações com tabelas](https://help.github.com/articles/organizing-information-with-tables/) do GitHub.</span><span class="sxs-lookup"><span data-stu-id="9b69d-187">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="9b69d-188">O aplicativo Web [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="9b69d-188">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="9b69d-189">[Folha de referências do Markdown de Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span><span class="sxs-lookup"><span data-stu-id="9b69d-189">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="9b69d-190">[Markdown Extra de Michel Fortin](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="9b69d-190">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="9b69d-191">[Converta tabelas HTML para Markdown](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="9b69d-191">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="9b69d-192">Links</span><span class="sxs-lookup"><span data-stu-id="9b69d-192">Links</span></span>

<span data-ttu-id="9b69d-193">A sintaxe do Markdown para um link embutido é composta pela parte `[link text]`, que é o texto que receberá o hiperlink, seguida pela parte `(file-name.md)`, que é a URL ou o nome do arquivo de destino do link:</span><span class="sxs-lookup"><span data-stu-id="9b69d-193">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="9b69d-194">Para saber mais sobre vinculação, confira:</span><span class="sxs-lookup"><span data-stu-id="9b69d-194">For more information on linking, see:</span></span>

- <span data-ttu-id="9b69d-195">O [guia de sintaxe do Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obter detalhes sobre o suporte à vinculação de base do Markdown.</span><span class="sxs-lookup"><span data-stu-id="9b69d-195">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="9b69d-196">A seção [Links](how-to-write-links.md) deste guia para obter detalhes sobre a sintaxe de vinculação adicional que o Markdig fornece.</span><span class="sxs-lookup"><span data-stu-id="9b69d-196">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="9b69d-197">Snippets de código</span><span class="sxs-lookup"><span data-stu-id="9b69d-197">Code snippets</span></span>

<span data-ttu-id="9b69d-198">O Markdown é compatível com o posicionamento de snippets de código, seja embutido em uma sentença, seja como um bloco "isolado" e separado entre as sentenças.</span><span class="sxs-lookup"><span data-stu-id="9b69d-198">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="9b69d-199">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="9b69d-199">For details, see:</span></span>

- [<span data-ttu-id="9b69d-200">Suporte nativo do Markdown para blocos de código</span><span class="sxs-lookup"><span data-stu-id="9b69d-200">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="9b69d-201">Suporte do GFM para isolamento de código e destaque de sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b69d-201">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="9b69d-202">Os blocos de código isolados representam uma maneira fácil de habilitar o destaque de sintaxe para seus snippets de código.</span><span class="sxs-lookup"><span data-stu-id="9b69d-202">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="9b69d-203">O formato geral dos blocos de código isolados é:</span><span class="sxs-lookup"><span data-stu-id="9b69d-203">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="9b69d-204">O alias após os três caracteres de acento grave (\`) iniciais define o destaque de sintaxe a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9b69d-204">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="9b69d-205">Veja a seguir uma lista de linguagens de programação normalmente usadas no conteúdo do Docs e no rótulo correspondente:</span><span class="sxs-lookup"><span data-stu-id="9b69d-205">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="9b69d-206">Essas linguagens têm o suporte de nome amigável e a maioria tem realce de linguagem.</span><span class="sxs-lookup"><span data-stu-id="9b69d-206">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="9b69d-207">Nome</span><span class="sxs-lookup"><span data-stu-id="9b69d-207">Name</span></span>|<span data-ttu-id="9b69d-208">Rótulo de Markdown</span><span class="sxs-lookup"><span data-stu-id="9b69d-208">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="9b69d-209">Console do .NET</span><span class="sxs-lookup"><span data-stu-id="9b69d-209">.NET Console</span></span>|<span data-ttu-id="9b69d-210">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="9b69d-210">dotnetcli</span></span>|
|<span data-ttu-id="9b69d-211">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="9b69d-211">ASP.NET (C#)</span></span>|<span data-ttu-id="9b69d-212">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="9b69d-212">aspx-csharp</span></span>|
|<span data-ttu-id="9b69d-213">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="9b69d-213">ASP.NET (VB)</span></span>|<span data-ttu-id="9b69d-214">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="9b69d-214">aspx-vb</span></span>|
|<span data-ttu-id="9b69d-215">AzCopy</span><span class="sxs-lookup"><span data-stu-id="9b69d-215">AzCopy</span></span>|<span data-ttu-id="9b69d-216">azcopy</span><span class="sxs-lookup"><span data-stu-id="9b69d-216">azcopy</span></span>|
|<span data-ttu-id="9b69d-217">CLI do Azure</span><span class="sxs-lookup"><span data-stu-id="9b69d-217">Azure CLI</span></span>|<span data-ttu-id="9b69d-218">azurecli</span><span class="sxs-lookup"><span data-stu-id="9b69d-218">azurecli</span></span>|
|<span data-ttu-id="9b69d-219">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b69d-219">Azure PowerShell</span></span>|<span data-ttu-id="9b69d-220">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="9b69d-220">azurepowershell</span></span>|
|<span data-ttu-id="9b69d-221">C++</span><span class="sxs-lookup"><span data-stu-id="9b69d-221">C++</span></span>|<span data-ttu-id="9b69d-222">cpp</span><span class="sxs-lookup"><span data-stu-id="9b69d-222">cpp</span></span>|
|<span data-ttu-id="9b69d-223">C++/CX</span><span class="sxs-lookup"><span data-stu-id="9b69d-223">C++/CX</span></span>|<span data-ttu-id="9b69d-224">cppcx</span><span class="sxs-lookup"><span data-stu-id="9b69d-224">cppcx</span></span>|
|<span data-ttu-id="9b69d-225">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="9b69d-225">C++/WinRT</span></span>|<span data-ttu-id="9b69d-226">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="9b69d-226">cppwinrt</span></span>|
|<span data-ttu-id="9b69d-227">C#</span><span class="sxs-lookup"><span data-stu-id="9b69d-227">C#</span></span>|<span data-ttu-id="9b69d-228">csharp</span><span class="sxs-lookup"><span data-stu-id="9b69d-228">csharp</span></span>|
|<span data-ttu-id="9b69d-229">C# no navegador</span><span class="sxs-lookup"><span data-stu-id="9b69d-229">C# in browser</span></span>|<span data-ttu-id="9b69d-230">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="9b69d-230">csharp-interactive</span></span>|
|<span data-ttu-id="9b69d-231">Console</span><span class="sxs-lookup"><span data-stu-id="9b69d-231">Console</span></span>|<span data-ttu-id="9b69d-232">console</span><span class="sxs-lookup"><span data-stu-id="9b69d-232">console</span></span>|
|<span data-ttu-id="9b69d-233">CSHTML</span><span class="sxs-lookup"><span data-stu-id="9b69d-233">CSHTML</span></span>|<span data-ttu-id="9b69d-234">cshtml</span><span class="sxs-lookup"><span data-stu-id="9b69d-234">cshtml</span></span>|
|<span data-ttu-id="9b69d-235">DAX</span><span class="sxs-lookup"><span data-stu-id="9b69d-235">DAX</span></span>|<span data-ttu-id="9b69d-236">dax</span><span class="sxs-lookup"><span data-stu-id="9b69d-236">dax</span></span>|
|<span data-ttu-id="9b69d-237">F#</span><span class="sxs-lookup"><span data-stu-id="9b69d-237">F#</span></span>|<span data-ttu-id="9b69d-238">fsharp</span><span class="sxs-lookup"><span data-stu-id="9b69d-238">fsharp</span></span>|
|<span data-ttu-id="9b69d-239">Go</span><span class="sxs-lookup"><span data-stu-id="9b69d-239">Go</span></span>|<span data-ttu-id="9b69d-240">go</span><span class="sxs-lookup"><span data-stu-id="9b69d-240">go</span></span>|
|<span data-ttu-id="9b69d-241">HTML</span><span class="sxs-lookup"><span data-stu-id="9b69d-241">HTML</span></span>|<span data-ttu-id="9b69d-242">html</span><span class="sxs-lookup"><span data-stu-id="9b69d-242">html</span></span>|
|<span data-ttu-id="9b69d-243">HTTP</span><span class="sxs-lookup"><span data-stu-id="9b69d-243">HTTP</span></span>|<span data-ttu-id="9b69d-244">http</span><span class="sxs-lookup"><span data-stu-id="9b69d-244">http</span></span>|
|<span data-ttu-id="9b69d-245">Java</span><span class="sxs-lookup"><span data-stu-id="9b69d-245">Java</span></span>|<span data-ttu-id="9b69d-246">java</span><span class="sxs-lookup"><span data-stu-id="9b69d-246">java</span></span>|
|<span data-ttu-id="9b69d-247">JavaScript</span><span class="sxs-lookup"><span data-stu-id="9b69d-247">JavaScript</span></span>|<span data-ttu-id="9b69d-248">javascript</span><span class="sxs-lookup"><span data-stu-id="9b69d-248">javascript</span></span>|
|<span data-ttu-id="9b69d-249">JSON</span><span class="sxs-lookup"><span data-stu-id="9b69d-249">JSON</span></span>|<span data-ttu-id="9b69d-250">json</span><span class="sxs-lookup"><span data-stu-id="9b69d-250">json</span></span>|
|<span data-ttu-id="9b69d-251">Markdown</span><span class="sxs-lookup"><span data-stu-id="9b69d-251">Markdown</span></span>|<span data-ttu-id="9b69d-252">md</span><span class="sxs-lookup"><span data-stu-id="9b69d-252">md</span></span>|
|<span data-ttu-id="9b69d-253">NodeJS</span><span class="sxs-lookup"><span data-stu-id="9b69d-253">NodeJS</span></span>|<span data-ttu-id="9b69d-254">nodejs</span><span class="sxs-lookup"><span data-stu-id="9b69d-254">nodejs</span></span>|
|<span data-ttu-id="9b69d-255">Objective-C</span><span class="sxs-lookup"><span data-stu-id="9b69d-255">Objective-C</span></span>|<span data-ttu-id="9b69d-256">objc</span><span class="sxs-lookup"><span data-stu-id="9b69d-256">objc</span></span>|
|<span data-ttu-id="9b69d-257">OData</span><span class="sxs-lookup"><span data-stu-id="9b69d-257">OData</span></span>|<span data-ttu-id="9b69d-258">odata</span><span class="sxs-lookup"><span data-stu-id="9b69d-258">odata</span></span>|
|<span data-ttu-id="9b69d-259">PHP</span><span class="sxs-lookup"><span data-stu-id="9b69d-259">PHP</span></span>|<span data-ttu-id="9b69d-260">php</span><span class="sxs-lookup"><span data-stu-id="9b69d-260">php</span></span>|
|<span data-ttu-id="9b69d-261">PowerApps (separador decimal por ponto)</span><span class="sxs-lookup"><span data-stu-id="9b69d-261">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="9b69d-262">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="9b69d-262">powerapps-dot</span></span>|
|<span data-ttu-id="9b69d-263">PowerApps (separador decimal por vírgula)</span><span class="sxs-lookup"><span data-stu-id="9b69d-263">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="9b69d-264">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="9b69d-264">powerapps-comma</span></span>|
|<span data-ttu-id="9b69d-265">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b69d-265">PowerShell</span></span>|<span data-ttu-id="9b69d-266">powershell</span><span class="sxs-lookup"><span data-stu-id="9b69d-266">powershell</span></span>|
|<span data-ttu-id="9b69d-267">Python</span><span class="sxs-lookup"><span data-stu-id="9b69d-267">Python</span></span>|<span data-ttu-id="9b69d-268">python</span><span class="sxs-lookup"><span data-stu-id="9b69d-268">python</span></span>|
|<span data-ttu-id="9b69d-269">Q#</span><span class="sxs-lookup"><span data-stu-id="9b69d-269">Q#</span></span>|<span data-ttu-id="9b69d-270">qsharp</span><span class="sxs-lookup"><span data-stu-id="9b69d-270">qsharp</span></span>|
|<span data-ttu-id="9b69d-271">R</span><span class="sxs-lookup"><span data-stu-id="9b69d-271">R</span></span>|<span data-ttu-id="9b69d-272">r</span><span class="sxs-lookup"><span data-stu-id="9b69d-272">r</span></span>|
|<span data-ttu-id="9b69d-273">Ruby</span><span class="sxs-lookup"><span data-stu-id="9b69d-273">Ruby</span></span>|<span data-ttu-id="9b69d-274">ruby</span><span class="sxs-lookup"><span data-stu-id="9b69d-274">ruby</span></span>|
|<span data-ttu-id="9b69d-275">SQL</span><span class="sxs-lookup"><span data-stu-id="9b69d-275">SQL</span></span>|<span data-ttu-id="9b69d-276">sql</span><span class="sxs-lookup"><span data-stu-id="9b69d-276">sql</span></span>|
|<span data-ttu-id="9b69d-277">Swift</span><span class="sxs-lookup"><span data-stu-id="9b69d-277">Swift</span></span>|<span data-ttu-id="9b69d-278">swift</span><span class="sxs-lookup"><span data-stu-id="9b69d-278">swift</span></span>|
|<span data-ttu-id="9b69d-279">TypeScript</span><span class="sxs-lookup"><span data-stu-id="9b69d-279">TypeScript</span></span>|<span data-ttu-id="9b69d-280">typescript</span><span class="sxs-lookup"><span data-stu-id="9b69d-280">typescript</span></span>|
|<span data-ttu-id="9b69d-281">VB</span><span class="sxs-lookup"><span data-stu-id="9b69d-281">VB</span></span>|<span data-ttu-id="9b69d-282">vb</span><span class="sxs-lookup"><span data-stu-id="9b69d-282">vb</span></span>|
|<span data-ttu-id="9b69d-283">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="9b69d-283">VSTS CLI</span></span>|<span data-ttu-id="9b69d-284">vstscli</span><span class="sxs-lookup"><span data-stu-id="9b69d-284">vstscli</span></span>|
|<span data-ttu-id="9b69d-285">XAML</span><span class="sxs-lookup"><span data-stu-id="9b69d-285">XAML</span></span>|<span data-ttu-id="9b69d-286">xaml</span><span class="sxs-lookup"><span data-stu-id="9b69d-286">xaml</span></span>|
|<span data-ttu-id="9b69d-287">XML</span><span class="sxs-lookup"><span data-stu-id="9b69d-287">XML</span></span>|<span data-ttu-id="9b69d-288">xml</span><span class="sxs-lookup"><span data-stu-id="9b69d-288">xml</span></span>|

<span data-ttu-id="9b69d-289">O nome `csharp-interactive` especifica a linguagem C#, bem como a capacidade de executar os exemplos no navegador.</span><span class="sxs-lookup"><span data-stu-id="9b69d-289">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="9b69d-290">Esses trechos são compilados e executados em um contêiner do Docker e os resultados da execução do programa são exibidos na janela do navegador do usuário.</span><span class="sxs-lookup"><span data-stu-id="9b69d-290">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

#### <a name="example-c"></a><span data-ttu-id="9b69d-291">Exemplo: C\#</span><span class="sxs-lookup"><span data-stu-id="9b69d-291">Example: C\#</span></span>

<span data-ttu-id="9b69d-292">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="9b69d-292">__Markdown__</span></span>

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

<span data-ttu-id="9b69d-293">__Renderização__</span><span class="sxs-lookup"><span data-stu-id="9b69d-293">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="9b69d-294">Exemplo: SQL</span><span class="sxs-lookup"><span data-stu-id="9b69d-294">Example: SQL</span></span>

<span data-ttu-id="9b69d-295">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="9b69d-295">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="9b69d-296">__Renderização__</span><span class="sxs-lookup"><span data-stu-id="9b69d-296">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="9b69d-297">Extensões de Markdown personalizada do OPS</span><span class="sxs-lookup"><span data-stu-id="9b69d-297">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="9b69d-298">O OPS (Open Publishing Services) implementa um Analisador de Markdown Markdig, que é altamente compatível com o GFM (GitHub Flavored Markdown).</span><span class="sxs-lookup"><span data-stu-id="9b69d-298">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="9b69d-299">O Markdig adiciona algumas funcionalidades por meio de extensões de Markdown.</span><span class="sxs-lookup"><span data-stu-id="9b69d-299">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="9b69d-300">Portanto, alguns artigos selecionados no Guia de Criação do OPS completo foram incluídos neste guia para referência.</span><span class="sxs-lookup"><span data-stu-id="9b69d-300">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="9b69d-301">(Por exemplo, veja "extensões de Markdown e Markdig" e "Snippets de código" no sumário.)</span><span class="sxs-lookup"><span data-stu-id="9b69d-301">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="9b69d-302">Os artigos do Docs usam o GFM para a maior parte da formatação do artigo, como parágrafos, links, listas e cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="9b69d-302">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="9b69d-303">Para uma formatação mais avançada, os artigos podem usar recursos do Markdig, como:</span><span class="sxs-lookup"><span data-stu-id="9b69d-303">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="9b69d-304">Blocos de nota</span><span class="sxs-lookup"><span data-stu-id="9b69d-304">Note blocks</span></span>
- <span data-ttu-id="9b69d-305">Arquivos de inclusão</span><span class="sxs-lookup"><span data-stu-id="9b69d-305">Include files</span></span>
- <span data-ttu-id="9b69d-306">Seletores</span><span class="sxs-lookup"><span data-stu-id="9b69d-306">Selectors</span></span>
- <span data-ttu-id="9b69d-307">Vídeos incorporados</span><span class="sxs-lookup"><span data-stu-id="9b69d-307">Embedded videos</span></span>
- <span data-ttu-id="9b69d-308">Snippets/amostras de código</span><span class="sxs-lookup"><span data-stu-id="9b69d-308">Code snippets/samples</span></span>

<span data-ttu-id="9b69d-309">Para obter a lista completa, veja "extensões de Markdown e Markdig" e "Snippets de código" no sumário.</span><span class="sxs-lookup"><span data-stu-id="9b69d-309">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="9b69d-310">Blocos de nota</span><span class="sxs-lookup"><span data-stu-id="9b69d-310">Note blocks</span></span>

<span data-ttu-id="9b69d-311">Você pode escolher entre quatro tipos de blocos de notas para chamar atenção para um conteúdo específico:</span><span class="sxs-lookup"><span data-stu-id="9b69d-311">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="9b69d-312">OBSERVAÇÃO</span><span class="sxs-lookup"><span data-stu-id="9b69d-312">NOTE</span></span>
- <span data-ttu-id="9b69d-313">AVISO</span><span class="sxs-lookup"><span data-stu-id="9b69d-313">WARNING</span></span>
- <span data-ttu-id="9b69d-314">DICA</span><span class="sxs-lookup"><span data-stu-id="9b69d-314">TIP</span></span>
- <span data-ttu-id="9b69d-315">IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="9b69d-315">IMPORTANT</span></span>

<span data-ttu-id="9b69d-316">Em geral, os blocos de notas devem ser usados com moderação porque eles podem atrapalhar.</span><span class="sxs-lookup"><span data-stu-id="9b69d-316">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="9b69d-317">Embora eles também deem suporte para blocos de código, imagens, listas e links, tente manter seus blocos de nota simples e diretos.</span><span class="sxs-lookup"><span data-stu-id="9b69d-317">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

<span data-ttu-id="9b69d-318">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="9b69d-318">Examples:</span></span>

```markdown
> [!NOTE]
> This is a NOTE

> [!WARNING]
> This is a WARNING

> [!TIP]
> This is a TIP

> [!IMPORTANT]
> This is IMPORTANT
```

<span data-ttu-id="9b69d-319">Eles são renderizados da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9b69d-319">These render as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="9b69d-320">Isto é uma ANOTAÇÃO</span><span class="sxs-lookup"><span data-stu-id="9b69d-320">This is a NOTE</span></span>

> [!WARNING]
> <span data-ttu-id="9b69d-321">Isto é um AVISO</span><span class="sxs-lookup"><span data-stu-id="9b69d-321">This is a WARNING</span></span>

> [!TIP]
> <span data-ttu-id="9b69d-322">Isto é uma DICA</span><span class="sxs-lookup"><span data-stu-id="9b69d-322">This is a TIP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b69d-323">Isto é IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="9b69d-323">This is IMPORTANT</span></span>

### <a name="include-files"></a><span data-ttu-id="9b69d-324">Arquivos de inclusão</span><span class="sxs-lookup"><span data-stu-id="9b69d-324">Include files</span></span>

<span data-ttu-id="9b69d-325">Quando você tiver um texto ou arquivos de imagem reutilizáveis que precisem ser incluídos nos arquivos do artigo, use uma referência ao arquivo de "inclusão" por meio do recurso de inclusão de arquivo do Markdig.</span><span class="sxs-lookup"><span data-stu-id="9b69d-325">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="9b69d-326">Esse recurso instrui o OPS a incluir o arquivo no arquivo do artigo no tempo de build, para que ele faça parte do artigo publicado.</span><span class="sxs-lookup"><span data-stu-id="9b69d-326">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="9b69d-327">Três tipos de referências de inclusão estão disponíveis para ajudar você a reutilizar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="9b69d-327">Three types of include references are available to help you reuse content:</span></span>

- <span data-ttu-id="9b69d-328">Embutido: Reutilize um snippet de texto comum embutido dentro de outra sentença.</span><span class="sxs-lookup"><span data-stu-id="9b69d-328">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="9b69d-329">Bloco: Reutilize um arquivo Markdown inteiro como um bloco aninhado dentro de uma seção de um artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69d-329">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="9b69d-330">Imagem: É como a inclusão de imagem padrão é implementada no Docs.</span><span class="sxs-lookup"><span data-stu-id="9b69d-330">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="9b69d-331">Um arquivo de inclusão embutido ou de bloco é apenas um arquivo Markdown (.md) simples.</span><span class="sxs-lookup"><span data-stu-id="9b69d-331">An inline or block include file is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="9b69d-332">Ele pode conter qualquer Markdown válido.</span><span class="sxs-lookup"><span data-stu-id="9b69d-332">It can contain any valid Markdown.</span></span> <span data-ttu-id="9b69d-333">Todos os arquivos Markdown de inclusão devem ser colocados em um [subdiretório `/includes` comum](git-github-fundamentals.md#includes-subdirectory), na raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="9b69d-333">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="9b69d-334">Quando o artigo é publicado, o arquivo incluído fica perfeitamente integrado.</span><span class="sxs-lookup"><span data-stu-id="9b69d-334">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="9b69d-335">Aqui estão os requisitos e as considerações para arquivos de inclusão:</span><span class="sxs-lookup"><span data-stu-id="9b69d-335">Here are requirements and considerations for include files:</span></span>

- <span data-ttu-id="9b69d-336">Use um arquivo de inclusão sempre que precisar que o mesmo texto apareça em vários artigos.</span><span class="sxs-lookup"><span data-stu-id="9b69d-336">Use an include file whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="9b69d-337">Use uma referência de inclusão em bloco para quantidades consideráveis de conteúdo, como um ou dois parágrafos, um procedimento compartilhado ou uma seção compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9b69d-337">Use a block include reference for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="9b69d-338">Não use-os para nada menor do que uma sentença.</span><span class="sxs-lookup"><span data-stu-id="9b69d-338">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="9b69d-339">As referências de inclusão não serão renderizadas na exibição do artigo renderizada do GitHub, pois elas dependem de extensões do Markdig.</span><span class="sxs-lookup"><span data-stu-id="9b69d-339">Include references won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="9b69d-340">Elas serão renderizadas somente após a publicação.</span><span class="sxs-lookup"><span data-stu-id="9b69d-340">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="9b69d-341">Verifique se todo o texto em um arquivo de inclusão está escrito em sentenças ou frases completas que não dependem do texto anterior ou seguinte no artigo que faz referência ao arquivo de inclusão.</span><span class="sxs-lookup"><span data-stu-id="9b69d-341">Ensure that all the text in an include file is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include file.</span></span> <span data-ttu-id="9b69d-342">Se você ignorar essa orientação, criará uma cadeia de caracteres não traduzível no artigo que quebrará a experiência localizada.</span><span class="sxs-lookup"><span data-stu-id="9b69d-342">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="9b69d-343">Não insira referências de inclusão em outros arquivos de inclusão.</span><span class="sxs-lookup"><span data-stu-id="9b69d-343">Don't embed include references within other include files.</span></span> <span data-ttu-id="9b69d-344">Não há suporte para isso.</span><span class="sxs-lookup"><span data-stu-id="9b69d-344">They are not supported.</span></span>
- <span data-ttu-id="9b69d-345">Coloque os arquivos de mídia em uma pasta de mídia específica para o subdiretório de inclusão, por exemplo, a pasta `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="9b69d-345">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="9b69d-346">O diretório de mídia não deve conter imagens em sua raiz.</span><span class="sxs-lookup"><span data-stu-id="9b69d-346">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="9b69d-347">Se o arquivo de inclusão não tiver imagens, não será necessário ter um diretório de mídia correspondente.</span><span class="sxs-lookup"><span data-stu-id="9b69d-347">If the include file does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="9b69d-348">Assim como ocorre com os artigos regulares, não compartilhe a mídia entre arquivos de inclusão.</span><span class="sxs-lookup"><span data-stu-id="9b69d-348">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="9b69d-349">Use um arquivo separado com um nome exclusivo para cada artigo e arquivo de inclusão.</span><span class="sxs-lookup"><span data-stu-id="9b69d-349">Use a separate file with a unique name for each include file and article.</span></span> <span data-ttu-id="9b69d-350">Armazene o arquivo de mídia na pasta de mídia associada ao arquivo de inclusão.</span><span class="sxs-lookup"><span data-stu-id="9b69d-350">Store the media file in the media folder that's associated with the include file.</span></span>
- <span data-ttu-id="9b69d-351">Não use um arquivo de inclusão como o único conteúdo de um artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69d-351">Don't use an include file as the only content of an article.</span></span>  <span data-ttu-id="9b69d-352">Os arquivos de inclusão servem como complemento ao conteúdo do restante do artigo.</span><span class="sxs-lookup"><span data-stu-id="9b69d-352">Include files are meant to be supplemental to the content in the rest of the article.</span></span>

<span data-ttu-id="9b69d-353">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="9b69d-353">Example:</span></span>

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a><span data-ttu-id="9b69d-354">Seletores</span><span class="sxs-lookup"><span data-stu-id="9b69d-354">Selectors</span></span>

<span data-ttu-id="9b69d-355">Use seletores em artigos técnicos ao criar vários tipos do mesmo artigo, a fim de solucionar diferenças de implementação entre tecnologias e plataformas.</span><span class="sxs-lookup"><span data-stu-id="9b69d-355">Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="9b69d-356">Normalmente, isso é mais aplicável ao nosso conteúdo de plataforma móvel para desenvolvedores.</span><span class="sxs-lookup"><span data-stu-id="9b69d-356">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="9b69d-357">No momento, há dois tipos diferentes de seletores no Markdig, um seletor único e um seletor múltiplo.</span><span class="sxs-lookup"><span data-stu-id="9b69d-357">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="9b69d-358">Já que o mesmo Markdown seletor vai para cada artigo na seleção, é recomendável posicionar o seletor do artigo em um arquivo de inclusão.</span><span class="sxs-lookup"><span data-stu-id="9b69d-358">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include file.</span></span> <span data-ttu-id="9b69d-359">Em seguida, você poderá referenciar esse arquivo de inclusão em todos os artigos que usarem o mesmo seletor.</span><span class="sxs-lookup"><span data-stu-id="9b69d-359">Then you can reference that include file in all your articles that use the same selector.</span></span>

<span data-ttu-id="9b69d-360">A seguir, é mostrado um seletor de exemplo:</span><span class="sxs-lookup"><span data-stu-id="9b69d-360">The following shows an example selector:</span></span>

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

<span data-ttu-id="9b69d-361">Você pode ver um exemplo dos seletores em ação nos [Documentos do Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="9b69d-361">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="code-include-references"></a><span data-ttu-id="9b69d-362">Referências de inclusão de código</span><span class="sxs-lookup"><span data-stu-id="9b69d-362">Code include references</span></span>

<span data-ttu-id="9b69d-363">O Markdig também é compatível com a inclusão avançada de código em um artigo por meio de sua extensão de snippet de código.</span><span class="sxs-lookup"><span data-stu-id="9b69d-363">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="9b69d-364">Ela fornece renderização avançada que aproveita os recursos do GFM, como seleção de linguagem de programação e coloração de sintaxe, além de recursos incríveis como:</span><span class="sxs-lookup"><span data-stu-id="9b69d-364">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="9b69d-365">Inclusão de amostras/trechos de código centralizados de um repositório externo.</span><span class="sxs-lookup"><span data-stu-id="9b69d-365">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="9b69d-366">Interface do usuário com guias para mostrar várias versões de amostras de código em linguagens diferentes.</span><span class="sxs-lookup"><span data-stu-id="9b69d-366">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="9b69d-367">Armadilhas e solução de problemas</span><span class="sxs-lookup"><span data-stu-id="9b69d-367">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="9b69d-368">Texto Alt</span><span class="sxs-lookup"><span data-stu-id="9b69d-368">Alt text</span></span>

<span data-ttu-id="9b69d-369">Textos Alt que contenham caracteres sublinhado não serão renderizados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="9b69d-369">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="9b69d-370">Por exemplo, em vez de usar isto:</span><span class="sxs-lookup"><span data-stu-id="9b69d-370">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="9b69d-371">Insira um escape para os sublinhados desta forma:</span><span class="sxs-lookup"><span data-stu-id="9b69d-371">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="9b69d-372">Apóstrofes e aspas</span><span class="sxs-lookup"><span data-stu-id="9b69d-372">Apostrophes and quotation marks</span></span>

<span data-ttu-id="9b69d-373">Se você copiar do Word para um editor de Markdown, o texto poderá conter apóstrofes ou aspas "inteligentes" (inglesas).</span><span class="sxs-lookup"><span data-stu-id="9b69d-373">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="9b69d-374">Eles precisam ser codificados ou alterados para apóstrofos ou aspas simples.</span><span class="sxs-lookup"><span data-stu-id="9b69d-374">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="9b69d-375">Caso contrário, quando o arquivo for publicado, poderão ocorrer erros como: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="9b69d-375">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="9b69d-376">Estas são as codificações para as versões "inteligentes" dessas marcas de pontuação:</span><span class="sxs-lookup"><span data-stu-id="9b69d-376">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="9b69d-377">Aspas à esquerda (de abertura): `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="9b69d-377">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="9b69d-378">Aspas à direita (de fechamento): `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="9b69d-378">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="9b69d-379">Aspas simples à direita (de fechamento) ou apóstrofe: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="9b69d-379">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="9b69d-380">Aspas simples à esquerda (de abertura) (raramente usadas): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="9b69d-380">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="9b69d-381">Colchetes angulares</span><span class="sxs-lookup"><span data-stu-id="9b69d-381">Angle brackets</span></span>

<span data-ttu-id="9b69d-382">É comum usar colchetes angulares para denotar um espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="9b69d-382">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="9b69d-383">Ao fazer isso em um texto (não no código), é necessário codificar os colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="9b69d-383">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="9b69d-384">Caso contrário, o Markdown entenderá que eles são uma marca HTML.</span><span class="sxs-lookup"><span data-stu-id="9b69d-384">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="9b69d-385">Por exemplo, codifique `<script name>` como `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="9b69d-385">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="9b69d-386">Confira também:</span><span class="sxs-lookup"><span data-stu-id="9b69d-386">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="9b69d-387">Recursos do Markdown</span><span class="sxs-lookup"><span data-stu-id="9b69d-387">Markdown resources</span></span>

- [<span data-ttu-id="9b69d-388">Introdução a Markdown</span><span class="sxs-lookup"><span data-stu-id="9b69d-388">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="9b69d-389">Roteiro de Markdown do Docs</span><span class="sxs-lookup"><span data-stu-id="9b69d-389">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="9b69d-390">Noções básicas de Markdown do GitHub</span><span class="sxs-lookup"><span data-stu-id="9b69d-390">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
- [<span data-ttu-id="9b69d-391">Guia de Markdown</span><span class="sxs-lookup"><span data-stu-id="9b69d-391">The Markdown Guide</span></span>](https://www.markdownguide.org/)
