---
title: Modelo e folha de referências para artigos do .NET
description: Este artigo contém um modelo útil que você pode usar para criar novos artigos para os repositórios de documentos do .NET
ms.date: 11/07/2018
ms.openlocfilehash: 15f64ec86c475e2da2f6539c8f388d076389c4e0
ms.sourcegitcommit: 68d81b61ffa60aba16acfed023760449e16de91b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2018
ms.locfileid: "52299650"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a><span data-ttu-id="b8b3d-103">Modelo de metadados e Markdown para documentos do .NET</span><span class="sxs-lookup"><span data-stu-id="b8b3d-103">Metadata and Markdown template for .NET docs</span></span>

<span data-ttu-id="b8b3d-104">Este modelo de dotnet/documentos contém exemplos de sintaxe de Markdown, bem como orientações para configurar os metadados.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-104">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span>

<span data-ttu-id="b8b3d-105">Ao criar um arquivo de Markdown, você deve copiar o modelo incluído para um novo arquivo, preencher os metadados conforme especificado abaixo e definir o cabeçalho H1 acima como o título do artigo.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-105">When creating a Markdown file, you should copy the included template to a new file, fill out the metadata as specified below, and set the H1 heading above to the title of the article.</span></span>

## <a name="metadata"></a><span data-ttu-id="b8b3d-106">Metadados</span><span class="sxs-lookup"><span data-stu-id="b8b3d-106">Metadata</span></span>

<span data-ttu-id="b8b3d-107">O bloco de metadados necessário está no seguinte bloco de metadados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-107">The required metadata block is in the following sample metadata block:</span></span>

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- <span data-ttu-id="b8b3d-108">Você **precisa** ter um espaço entre os dois-pontos (:) e o valor de um elemento de metadados.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-108">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="b8b3d-109">Os dois-pontos em um valor (por exemplo, um título) interrompem o analisador de metadados.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-109">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="b8b3d-110">Nesse caso, coloque o título entre aspas duplas (por exemplo, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-110">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="b8b3d-111">**title**: aparece nos resultados do mecanismo de pesquisa resultados.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-111">**title**: Appears in search engine results.</span></span> <span data-ttu-id="b8b3d-112">O título não deve ser idêntico ao título em seu cabeçalho H1 e deve contar no máximo 60 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-112">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="b8b3d-113">**description**: resume o conteúdo do artigo.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-113">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="b8b3d-114">Normalmente, é mostrado na página de resultados da pesquisa, mas não é usado para classificação na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-114">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="b8b3d-115">O tamanho deve ser de 115 a 145 caracteres, incluindo os espaços.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-115">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="b8b3d-116">**author**: o campo de autor deve contar o **nome de usuário do GitHub** do autor.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-116">**author**: The author field should contain the **GitHub username** of the author.</span></span>
- <span data-ttu-id="b8b3d-117">**ms.date**: a data da última atualização significativa.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-117">**ms.date**: The date of the last significant update.</span></span> <span data-ttu-id="b8b3d-118">Atualize em artigos existentes se você tiver revisado e atualizado o artigo inteiro.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-118">Update this on existing articles if you reviewed and updated the entire article.</span></span> <span data-ttu-id="b8b3d-119">Correções pequenas, como de erros de digitação ou semelhante, não garantem uma atualização.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-119">Small fixes, such as typos or similar do not warrant an update.</span></span>

<span data-ttu-id="b8b3d-120">Outros metadados são anexados a cada artigo, mas normalmente nós aplicamos a maior parte dos valores de metadados no nível da pasta, especificado em **docfx.json**.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-120">Other metadata is attached to each article, but we typically apply most metadata values at the folder level, specified in **docfx.json**.</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="b8b3d-121">Markdown básico, GFM e caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="b8b3d-121">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="b8b3d-122">Você pode aprender os princípios básicos das extensões específicas de Markdown, GitHub Flavored Markdown (GFM) e OPS nos artigos gerais sobre [Markdown](how-to-write-use-markdown.md) e [Referência de Markdown](markdown-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-122">You can learn the basics of Markdown, GitHub Flavored Markdown (GFM), and OPS specific extensions in the general articles on [Markdown](how-to-write-use-markdown.md) and [Markdown reference](markdown-reference.md).</span></span>

<span data-ttu-id="b8b3d-123">O Markdown usa caracteres especiais como \*, \` e \# para formatação.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-123">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="b8b3d-124">Se quiser incluir um desses caracteres em seu conteúdo, você precisará aditar uma das duas medidas a seguir:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-124">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="b8b3d-125">Colocar uma barra antes do caractere especial como forma de "escape" (por exemplo, `\*` para um \*)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-125">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="b8b3d-126">Use o [Código de entidade HTML](http://www.ascii.cl/htmlcodes.htm) para o caractere (por exemplo, `&#42;` para um &#42;).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-126">Use the [HTML entity code](http://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-names"></a><span data-ttu-id="b8b3d-127">Nomes de arquivo</span><span class="sxs-lookup"><span data-stu-id="b8b3d-127">File names</span></span>

<span data-ttu-id="b8b3d-128">Os nomes de arquivo usam as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-128">File names use the following rules:</span></span>

* <span data-ttu-id="b8b3d-129">Contêm apenas letras minúsculas, números e hifens.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-129">Contain only lowercase letters, numbers, and hyphens.</span></span>
* <span data-ttu-id="b8b3d-130">Sem espaços nem caracteres de pontuação.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-130">No spaces or punctuation characters.</span></span> <span data-ttu-id="b8b3d-131">Usar os hifens para separar palavras e números no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-131">Use the hyphens to separate words and numbers in the file name.</span></span>
* <span data-ttu-id="b8b3d-132">Usar verbos de ação específicos, como desenvolver, comprar, compilar, solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-132">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="b8b3d-133">Sem palavras terminando em -ndo.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-133">No -ing words.</span></span>
* <span data-ttu-id="b8b3d-134">Sem palavras pequenas – não inclua um, uma, e, o, a, em, ou, etc.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-134">No small words - don't include a, and, the, in, or, etc.</span></span>
* <span data-ttu-id="b8b3d-135">Deve estar em Markdown e usar a extensão de arquivo .md.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-135">Must be in Markdown and use the .md file extension.</span></span>
* <span data-ttu-id="b8b3d-136">Manter os nomes de arquivo razoavelmente curtos.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-136">Keep file names reasonably short.</span></span> <span data-ttu-id="b8b3d-137">Eles fazem parte da URL de seus artigos.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-137">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="b8b3d-138">Títulos</span><span class="sxs-lookup"><span data-stu-id="b8b3d-138">Headings</span></span>

<span data-ttu-id="b8b3d-139">Use a capitalização com estilo de frase.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-139">Use sentence-style capitalization.</span></span> <span data-ttu-id="b8b3d-140">Sempre coloque em maiúsculas a primeira palavra de um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-140">Always capitalize the first word of a heading.</span></span>

## <a name="text-styling"></a><span data-ttu-id="b8b3d-141">Estilo do texto</span><span class="sxs-lookup"><span data-stu-id="b8b3d-141">Text styling</span></span>

<span data-ttu-id="b8b3d-142">*Itálico* Use para arquivos, pastas, caminhos (para itens longos, divida cada um em sua própria linha), novos termos.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-142">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="b8b3d-143">**Negrito** Use para elementos da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-143">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="b8b3d-144">`Code` Use para código embutido, palavras-chave da linguagem, nomes de pacotes NuGet, comandos da linha de comando, nomes de coluna e tabelas de banco de dados e URLs que você não deseja que sejam clicáveis.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-144">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="b8b3d-145">Links</span><span class="sxs-lookup"><span data-stu-id="b8b3d-145">Links</span></span>

<span data-ttu-id="b8b3d-146">Confira o artigo sobre [Links](how-to-write-links.md) para obter informações sobre âncoras, links internos, links para outros documentos, inclusões de código e links externos.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-146">See the general article on [Links](how-to-write-links.md) for information about anchors, internal links, links to other documents, code includes, and external links.</span></span>

<span data-ttu-id="b8b3d-147">A equipe de documentos do .NET usa as seguintes convenções:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-147">The .NET docs team uses the following conventions:</span></span>

- <span data-ttu-id="b8b3d-148">Na maioria dos casos, usamos os links relativos e não incentivamos o uso de `~/` nos links porque links relativos são resolvidos na origem no GitHub.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-148">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="b8b3d-149">No entanto, sempre que criamos um link para um arquivo em um repositório independente, usamos o caractere `~/` para fornecer o caminho.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-149">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="b8b3d-150">Como os arquivos no repositório dependente ficam em uma localização diferente no GitHub, os links não serão resolvidos corretamente com os links relativos, independentemente de como foram escritos.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-150">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>
- <span data-ttu-id="b8b3d-151">A especificação da linguagem C# e a especificação da linguagem de Visual Basic são incluídas nos documentos do .NET incluindo a origem dos repositórios de linguagem.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-151">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="b8b3d-152">As origens de Markdown são gerenciadas nos repositórios [csharplang](https://github.com/dotnet/csharplang) e [vblang](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-152">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [vblang](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="b8b3d-153">Links para as especificações devem apontar para os diretórios de origem em que as especificações estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-153">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="b8b3d-154">Para C#, é **~/_csharplang/spec** e para VB, é **~/_vblang/spec**, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-154">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**, as in the following example:</span></span>

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a><span data-ttu-id="b8b3d-155">Links para APIs</span><span class="sxs-lookup"><span data-stu-id="b8b3d-155">Links to APIs</span></span>

<span data-ttu-id="b8b3d-156">O sistema de build tem algumas extensões que nos permitem criar links para APIs do .NET sem precisar usar links externos.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-156">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span> <span data-ttu-id="b8b3d-157">Você pode usar uma das seguintes sintaxes:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-157">You use one of the following syntax:</span></span>

1. <span data-ttu-id="b8b3d-158">Vincular automaticamente: `<xref:UID>` ou `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="b8b3d-158">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="b8b3d-159">O parâmetro de consulta `displayProperty` produz um texto de link totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-159">The `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="b8b3d-160">Por padrão, o texto do link mostra apenas o nome do membro ou do tipo.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-160">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="b8b3d-161">Link de Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="b8b3d-161">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="b8b3d-162">Use para personalizar o texto do link exibido.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-162">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="b8b3d-163">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-163">Examples:</span></span>

- <span data-ttu-id="b8b3d-164">`<xref:System.String>` é renderizado como [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-164">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="b8b3d-165">`<xref:System.String?displayProperty=nameWithType>` é renderizado como [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-165">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="b8b3d-166">`[String class](xref:System.String)` é renderizado como [classe String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-166">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="b8b3d-167">Para saber mais sobre como usar essa notação, confira [Uso da referência cruzada](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-167">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="b8b3d-168">Alguns UIDs contêm os caracteres especiais \`, \# ou \*, o valor do UID deve ser codificado em HTML como `%60`, `%23` e `%2A`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-168">Some UIDs contain the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="b8b3d-169">Às vezes, você verá parênteses codificados, mas, isso não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-169">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="b8b3d-170">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-170">Examples:</span></span>

- <span data-ttu-id="b8b3d-171">System.Threading.Tasks.Task\`1 se torna `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="b8b3d-171">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="b8b3d-172">System.Exception.\#ctor se torna `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="b8b3d-172">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="b8b3d-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se torna `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="b8b3d-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<span data-ttu-id="b8b3d-174">Você pode encontrar os UIDs dos tipos, uma lista de sobrecarga de membros ou um membro com sobrecarga particular de `https://xref.docs.microsoft.com/autocomplete`.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-174">You can find the UIDs of types, a member overload list, or a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="b8b3d-175">A cadeia de caracteres de consulta `?text=*\<type-member-name>*` identifica o tipo ou o membro cujos UIDs você gostaria de ver.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-175">The query string `?text=*\<type-member-name>*` identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="b8b3d-176">Por exemplo, `https://xref.docs.microsoft.com/autocomplete?text=string.format` recupera as sobrecargas de [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-176">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span> <span data-ttu-id="b8b3d-177">A ferramenta pesquisa pelo parâmetro de consulta `text` fornecido em qualquer parte do UID.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-177">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="b8b3d-178">Por exemplo, você pode pesquisar pelo nome do membro (ToString), pelo nome do membro parcial (ToStri), pelo nome e tipo do membro (Double.ToString) etc.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-178">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="b8b3d-179">Se você adicionar um \* (ou `%2A`) depois do UID, o link representará a página de sobrecarga, e não uma API específica.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-179">If you add a \* (or `%2A`) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="b8b3d-180">Por exemplo, você pode usar isso quando deseja vincular à página do Método [List\<T>.BinarySearch](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) de uma maneira genérica, em vez de usar uma sobrecarga específica, como [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-180">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="b8b3d-181">Você pode usar \* para criar um link para uma página de membro quando o membro não está sobrecarregado; com isso, você não precisa incluir a lista de parâmetros no UID.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-181">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="b8b3d-182">Para vincular a uma sobrecarga de método específico, você precisa incluir o nome do tipo totalmente qualificado de cada um dos parâmetros do método.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-182">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="b8b3d-183">Por exemplo, \<xref:System.DateTime.ToString> é vinculado ao método [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) sem parâmetro, enquanto \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> é vinculado ao método [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-183">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span>

<span data-ttu-id="b8b3d-184">Para vincular a um tipo genérico, como [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), você usa o caractere \` (`%60`) seguido do número de parâmetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-184">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (`%60`) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="b8b3d-185">Por exemplo, `<xref:System.Nullable%601>` vincula ao tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), enquanto `<xref:System.Func%602>` vincula ao delegado [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-185">For example, `<xref:System.Nullable%601>` links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while `<xref:System.Func%602>` links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

## <a name="code"></a><span data-ttu-id="b8b3d-186">Código</span><span class="sxs-lookup"><span data-stu-id="b8b3d-186">Code</span></span>

<span data-ttu-id="b8b3d-187">A melhor maneira de incluir código é incluir trechos de um exemplo em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-187">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="b8b3d-188">Crie seu exemplo seguindo as instruções no artigo sobre [contribuição com o .NET](dotnet-contribute-process.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-188">Create your sample following the instructions in the [contributing to .NET](dotnet-contribute-process.md#contributing-to-samples) article.</span></span> <span data-ttu-id="b8b3d-189">As regras básicas para incluir código ficam localizadas nas orientações gerais no [código](how-to-write-use-markdown.md#code-includes).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-189">The basic rules for including code are located in the general guidance on [code](how-to-write-use-markdown.md#code-includes).</span></span>

<span data-ttu-id="b8b3d-190">Você pode incluir o código usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-190">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* <span data-ttu-id="b8b3d-191">`-<language>` (*opcional*, mas *recomendado*)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-191">`-<language>` (*optional* but *recommended*)</span></span>
  * <span data-ttu-id="b8b3d-192">Linguagem do snippet de código sendo referido.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-192">Language of the code snippet being referenced.</span></span> <span data-ttu-id="b8b3d-193">Para ver uma lista dos valores com suporte, confira [Linguagens com suporte](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-193">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

* <span data-ttu-id="b8b3d-194">`<name>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-194">`<name>` (*optional*)</span></span>
  * <span data-ttu-id="b8b3d-195">Nome do snippet de código.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-195">Name for the code snippet.</span></span> <span data-ttu-id="b8b3d-196">Não tem nenhum impacto no HTML de saída, mas pode ser usado para melhorar a legibilidade da fonte do Markdown.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-196">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

* <span data-ttu-id="b8b3d-197">`<pathToFile>` (*obrigatório*)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-197">`<pathToFile>` (*mandatory*)</span></span>
  * <span data-ttu-id="b8b3d-198">O caminho relativo no sistema de arquivos que indica o arquivo de snippet de código a ser referenciado.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-198">Relative path in the file system that indicates the code snippet file to reference.</span></span> <span data-ttu-id="b8b3d-199">Isso pode ser complicado pelos diferentes repositórios que compõem o conjunto de documentos do .NET.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-199">This can be complicated by the different repos that make up the .NET doc set.</span></span> <span data-ttu-id="b8b3d-200">Es exemplos do .NET estão repositório dotnet/samples.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-200">The .NET samples are in the dotnet/samples repo.</span></span> <span data-ttu-id="b8b3d-201">Todos os caminhos dos snippets devem ser iniciados com `~/samples`, com o restante do caminho sendo o cainho para a origem da raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-201">All snippet paths would start with `~/samples`, the rest of the path being the path to the source from the root of that repo.</span></span>

* <span data-ttu-id="b8b3d-202">`<queryoption>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-202">`<queryoption>` (*optional*)</span></span>
  * <span data-ttu-id="b8b3d-203">Usado para especificar como o código deve ser recuperado do arquivo:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-203">Used to specify how the code should be retrieved from the file:</span></span>
    * <span data-ttu-id="b8b3d-204">`#`: `#{tagname}` (nome da tag) *ou* `#L{startlinenumber}-L{endlinenumber}` (intervalo de linhas).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-204">`#`:  `#{tagname}` (tag name) *or* `#L{startlinenumber}-L{endlinenumber}` (line range).</span></span>
    <span data-ttu-id="b8b3d-205">Nós não incentivamos o uso de números de linha porque eles são muito frágeis.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-205">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="b8b3d-206">O nome da tag é o modo preferencial de referenciar trechos de código.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-206">Tag name is the preferred way of referencing code snippets.</span></span> <span data-ttu-id="b8b3d-207">Use nomes de tag significativos.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-207">Use meaningful tag names.</span></span> <span data-ttu-id="b8b3d-208">(Muitos trechos foram migrados de uma plataforma anterior e as tags têm nomes como `Snippet1`, `Snippet2`, etc. Essa prática é muito mais difícil de manter.)</span><span class="sxs-lookup"><span data-stu-id="b8b3d-208">(Many snippets were migrated from a previous platform and the tags have names such as `Snippet1`, `Snippet2` etc. That practice is much harder to maintain.)</span></span>
    * <span data-ttu-id="b8b3d-209">`range`: `?range=1,3-5` um intervalo de linhas.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-209">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="b8b3d-210">Este exemplo inclui as linhas 1, 3, 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-210">This example includes lines 1, 3, 4, and 5.</span></span>

<span data-ttu-id="b8b3d-211">Recomendamos usar a opção de nome de tag sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-211">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="b8b3d-212">O nome da tag é o nome de uma região ou de um comentário no código no formato do `Snippettagname` presente no código-fonte.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-212">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="b8b3d-213">O seguinte exemplo mostra como fazer referência ao nome de tag `BasicThrow`:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-213">The following example shows how to refer to the tag name `BasicThrow`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

<span data-ttu-id="b8b3d-214">O caminho relativo para a origem no repositório **dotnet/samples** segue o caminho `~/samples`.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-214">The relative path to the source in the **dotnet/samples** repo follows the `~/samples` path.</span></span>

<span data-ttu-id="b8b3d-215">E você pode ver como as tags do snippet são estruturadas [neste arquivo de origem](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-215">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs).</span></span> <span data-ttu-id="b8b3d-216">Para obter detalhes sobre a representação do nome da marca em arquivos de origem de snippet de código por linguagem, consulte as [Diretrizes do DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-216">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="b8b3d-217">O exemplo a seguir mostra o código incluído em todas as três linguagens do .NET:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-217">The following example shows code included in all three .NET languages:</span></span>

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

<span data-ttu-id="b8b3d-218">Incluir trechos de programas inteiros garante que todo o código passe por nosso sistema de CI (Integração Contínua).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-218">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="b8b3d-219">No entanto, se precisar mostrar algo que causa erros de tempo de execução ou tempo de compilação, você poderá usar blocos de código embutido.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-219">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

## <a name="images"></a><span data-ttu-id="b8b3d-220">Imagens</span><span class="sxs-lookup"><span data-stu-id="b8b3d-220">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="b8b3d-221">Imagem estática ou GIF animado</span><span class="sxs-lookup"><span data-stu-id="b8b3d-221">Static image or animated GIF</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a><span data-ttu-id="b8b3d-222">Imagem vinculada</span><span class="sxs-lookup"><span data-stu-id="b8b3d-222">Linked image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a><span data-ttu-id="b8b3d-223">Vídeos</span><span class="sxs-lookup"><span data-stu-id="b8b3d-223">Videos</span></span>

<span data-ttu-id="b8b3d-224">Atualmente, você pode inserir vídeos do Channel 9 e do YouTube usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-224">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="b8b3d-225">Channel 9</span><span class="sxs-lookup"><span data-stu-id="b8b3d-225">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="b8b3d-226">Para obter a URL correta do vídeo, selecione a guia **Inserir** abaixo do quadro de vídeo e copie a URL do elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-226">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="b8b3d-227">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-227">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="b8b3d-228">YouTube</span><span class="sxs-lookup"><span data-stu-id="b8b3d-228">YouTube</span></span>

<span data-ttu-id="b8b3d-229">Para obter a URL correta do vídeo, clique com o botão direito do mouse no vídeo, selecione **Copiar Código de Inserção** e copie a URL do elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-229">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="b8b3d-230">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-230">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="b8b3d-231">Extensões docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="b8b3d-231">docs.microsoft extensions</span></span>

<span data-ttu-id="b8b3d-232">docs.microsoft fornece algumas extensões adicionais do GitHub Flavored Markdown.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-232">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="checked-lists"></a><span data-ttu-id="b8b3d-233">Listas com caixas de seleção</span><span class="sxs-lookup"><span data-stu-id="b8b3d-233">Checked lists</span></span>

<span data-ttu-id="b8b3d-234">Há um estilo personalizado disponível para listas.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-234">A custom style is available for lists.</span></span> <span data-ttu-id="b8b3d-235">Você pode renderizar listas com marcas de verificação verdes.</span><span class="sxs-lookup"><span data-stu-id="b8b3d-235">You can render lists with green check marks.</span></span>

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

<span data-ttu-id="b8b3d-236">Isso será renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-236">This renders as:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="b8b3d-237">Como criar um aplicativo .NET Core</span><span class="sxs-lookup"><span data-stu-id="b8b3d-237">How to create a .NET Core app</span></span>
> * <span data-ttu-id="b8b3d-238">Como adicionar uma referência ao pacote Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="b8b3d-238">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="b8b3d-239">Como editar seu MyApp.csproj para adicionar dependências</span><span class="sxs-lookup"><span data-stu-id="b8b3d-239">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="b8b3d-240">Como adicionar uma classe e um XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="b8b3d-240">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="b8b3d-241">Como compilar e executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="b8b3d-241">How to build and run the application</span></span>

<span data-ttu-id="b8b3d-242">Você pode ver um exemplo das listas verificadas em ação nos [Documentos do .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-242">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="b8b3d-243">Botões</span><span class="sxs-lookup"><span data-stu-id="b8b3d-243">Buttons</span></span>

<span data-ttu-id="b8b3d-244">Links de botão:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-244">Button links:</span></span>

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

<span data-ttu-id="b8b3d-245">Isso será renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b8b3d-245">This renders as:</span></span>

> [!div class="button"]
[<span data-ttu-id="b8b3d-246">links de botão</span><span class="sxs-lookup"><span data-stu-id="b8b3d-246">button links</span></span>](dotnet-contribute.md)

<span data-ttu-id="b8b3d-247">Você pode ver um exemplo dos botões em ação nos [Documentos do Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-247">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="b8b3d-248">Instruções passo a passo</span><span class="sxs-lookup"><span data-stu-id="b8b3d-248">Step-by-steps</span></span>

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

<span data-ttu-id="b8b3d-249">Você pode ver um exemplo das instruções passo a passo em ação no [Guia de C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="b8b3d-249">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
