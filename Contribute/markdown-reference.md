---
title: Referência de Markdown para docs.microsoft.com
description: Conheça os recursos e a sintaxe do Markdown usados na plataforma do Microsoft Docs.
author: meganbradley
ms.author: mbradley
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.openlocfilehash: 17bc6d3bf2de5077f490bea2f03cddf23d925b78
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55712937"
---
# <a name="markdown-reference"></a><span data-ttu-id="c5313-103">Referência de Markdown</span><span class="sxs-lookup"><span data-stu-id="c5313-103">Markdown Reference</span></span>

<span data-ttu-id="c5313-104">Markdown é uma linguagem de marcação leve com sintaxe de formatação de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="c5313-104">Markdown is a lightweight markup language with plain text formatting syntax.</span></span> <span data-ttu-id="c5313-105">A plataforma Docs é compatível com o padrão CommonMark para Markdown, além de algumas extensões personalizadas de Markdown projetadas para oferecer conteúdo mais avançado no docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c5313-105">The Docs platform supports the CommonMark standard for Markdown, plus some custom Markdown extensions designed to provide richer content on docs.microsoft.com.</span></span> <span data-ttu-id="c5313-106">Este artigo oferece uma referência alfabética para uso de Markdown no docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c5313-106">This article provides an alphabetical reference for using Markdown for docs.microsoft.com.</span></span>

<span data-ttu-id="c5313-107">É possível usar qualquer editor de texto para criar em Markdown.</span><span class="sxs-lookup"><span data-stu-id="c5313-107">You can use any text editor to author Markdown.</span></span> <span data-ttu-id="c5313-108">Para editores que facilitam a inserção da sintaxe padrão Markdown e das extensões personalizadas do Docs, recomendamos o [VS Code](https://code.visualstudio.com/) com o [Pacote de Criação de Docs](https://aka.ms/DocsAuthoringPack) instalado.</span><span class="sxs-lookup"><span data-stu-id="c5313-108">For an editor that facilitates inserting both standard Markdown syntax and custom Docs extensions, we recommend [VS Code](https://code.visualstudio.com/) with the [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) installed.</span></span>

<span data-ttu-id="c5313-109">O Docs usa o mecanismo de Markdown Markdig.</span><span class="sxs-lookup"><span data-stu-id="c5313-109">Docs uses the Markdig Markdown engine.</span></span> <span data-ttu-id="c5313-110">É possível testar a renderização de Markdown no Markdig em relação aos outros mecanismos em [https://babelmark.github.io/](https://babelmark.github.io/).</span><span class="sxs-lookup"><span data-stu-id="c5313-110">You can test the rendering of Markdown in Markdig vs. other engines at [https://babelmark.github.io/](https://babelmark.github.io/).</span></span>

## <a name="alerts-note-tip-important-caution-warning"></a><span data-ttu-id="c5313-111">Alertas (Anotação, Dica, Importante, Atenção, Aviso)</span><span class="sxs-lookup"><span data-stu-id="c5313-111">Alerts (Note, Tip, Important, Caution, Warning)</span></span>

<span data-ttu-id="c5313-112">"Alertas" é uma extensão de Markdown do Docs para criar citações em bloco que renderizam no docs.microsoft.com com cores e ícones que indicam a importância do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c5313-112">Alerts are a Docs Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="c5313-113">Os seguintes tipos de alerta tem suporte:</span><span class="sxs-lookup"><span data-stu-id="c5313-113">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="c5313-114">Esses alertas terão a seguinte aparência no docs.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="c5313-114">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="c5313-115">Informações que o usuário deverá notar mesmo se estiver fazendo uma leitura rápida.</span><span class="sxs-lookup"><span data-stu-id="c5313-115">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="c5313-116">Informações opcionais para ajudar um usuário a ter mais êxito.</span><span class="sxs-lookup"><span data-stu-id="c5313-116">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5313-117">Informações essenciais obrigatórias para o êxito do usuário.</span><span class="sxs-lookup"><span data-stu-id="c5313-117">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="c5313-118">Possíveis consequências negativas de uma ação.</span><span class="sxs-lookup"><span data-stu-id="c5313-118">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="c5313-119">Determinadas consequências perigosas de uma ação.</span><span class="sxs-lookup"><span data-stu-id="c5313-119">Dangerous certain consequences of an action.</span></span>

## <a name="code-snippets"></a><span data-ttu-id="c5313-120">Snippets de código</span><span class="sxs-lookup"><span data-stu-id="c5313-120">Code snippets</span></span>

<span data-ttu-id="c5313-121">É possível inserir snippets de código nos arquivos Markdown:</span><span class="sxs-lookup"><span data-stu-id="c5313-121">You can embed code snippets in your Markdown files:</span></span>

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a><span data-ttu-id="c5313-122">Títulos</span><span class="sxs-lookup"><span data-stu-id="c5313-122">Headings</span></span>

<span data-ttu-id="c5313-123">O Docs é compatível com seis níveis de cabeçalhos do Markdown:</span><span class="sxs-lookup"><span data-stu-id="c5313-123">Docs supports six levels of Markdown headings:</span></span>

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- <span data-ttu-id="c5313-124">É necessário um espaço entre o último `#` e o texto do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c5313-124">There must be a space between the last `#` and heading text.</span></span>
- <span data-ttu-id="c5313-125">Cada arquivo Markdown precisa ter somente um H1.</span><span class="sxs-lookup"><span data-stu-id="c5313-125">Each Markdown file must have one and only one H1.</span></span>
- <span data-ttu-id="c5313-126">O H1 precisa ser o primeiro conteúdo no arquivo após o bloco de metadados YML.</span><span class="sxs-lookup"><span data-stu-id="c5313-126">The H1 must be the first content in the file after the YML metadata block.</span></span>
- <span data-ttu-id="c5313-127">O H2s aparece automaticamente no menu de navegação direito do arquivo publicado.</span><span class="sxs-lookup"><span data-stu-id="c5313-127">H2s automatically appear in the right-hand navigating menu of the published file.</span></span> <span data-ttu-id="c5313-128">Os cabeçalhos dos níveis inferiores não, então, use os H2s estrategicamente, de modo a ajudar os leitores a navegarem pelo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c5313-128">Lower-level headings do not, so use H2s strategically to help readers navigate your content.</span></span>
- <span data-ttu-id="c5313-129">Os cabeçalhos HTML, tais como `<h1>`, não são recomendados. Em alguns casos, eles gerarão avisos de build.</span><span class="sxs-lookup"><span data-stu-id="c5313-129">HMTL headings, such as `<h1>`, are not recommended and in some cases will cause build warnings.</span></span>
- <span data-ttu-id="c5313-130">É possível criar links para cabeçalhos individuais em um arquivo por meio de [indicadores](#bookmark-links).</span><span class="sxs-lookup"><span data-stu-id="c5313-130">You can link to individual headings in a file via [bookmarks](#bookmark-links).</span></span>

## <a name="html"></a><span data-ttu-id="c5313-131">HTML</span><span class="sxs-lookup"><span data-stu-id="c5313-131">HTML</span></span>

<span data-ttu-id="c5313-132">Embora o Markdown seja compatível com HTML embutido, não é recomendável usá-lo para publicar no Docs, exceto no caso de uma lista de valores limitada causar erros de build ou avisos.</span><span class="sxs-lookup"><span data-stu-id="c5313-132">Although Markdown supports inline HTML, HTML is not recommended for publishing to Docs, and except for a limited list of values will cause build errors or warnings.</span></span> <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a><span data-ttu-id="c5313-133">Imagens</span><span class="sxs-lookup"><span data-stu-id="c5313-133">Images</span></span>

<span data-ttu-id="c5313-134">A sintaxe para incluir uma imagem é:</span><span class="sxs-lookup"><span data-stu-id="c5313-134">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

<span data-ttu-id="c5313-135">Em que `alt text` é uma breve descrição da imagem e `<folder path>` é um caminho relativo para a imagem.</span><span class="sxs-lookup"><span data-stu-id="c5313-135">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="c5313-136">O texto alternativo é obrigatório para os leitores de tela para portadores de deficiências visuais.</span><span class="sxs-lookup"><span data-stu-id="c5313-136">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="c5313-137">Ele também é útil se há um bug de site em que a imagem não pode ser renderizada.</span><span class="sxs-lookup"><span data-stu-id="c5313-137">It is also useful if there is a site bug where the image cannot render.</span></span>

<span data-ttu-id="c5313-138">As imagens devem ser armazenadas em uma pasta `/media` dentro do conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-138">Images should be stored in a `/media` folder within your doc set.</span></span> <span data-ttu-id="c5313-139">Os seguintes tipos de arquivo para imagens têm suporte por padrão:</span><span class="sxs-lookup"><span data-stu-id="c5313-139">The following file types are supported by default for images:</span></span>

- <span data-ttu-id="c5313-140">.jpg</span><span class="sxs-lookup"><span data-stu-id="c5313-140">.jpg</span></span>
- <span data-ttu-id="c5313-141">.png</span><span class="sxs-lookup"><span data-stu-id="c5313-141">.png</span></span>

<span data-ttu-id="c5313-142">É possível adicionar suporte a outros tipos de imagem, adicionando-as como recursos ao arquivo docfx.json<!--add link to reference when available--> no conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-142">You can add support for other image types by adding them as resources to the docfx.json file<!--add link to reference when available--> for your doc set.</span></span>

## <a name="links"></a><span data-ttu-id="c5313-143">Links</span><span class="sxs-lookup"><span data-stu-id="c5313-143">Links</span></span>

<span data-ttu-id="c5313-144">Na maioria dos casos, o Docs usa links padrão de Markdown para outros arquivos e páginas.</span><span class="sxs-lookup"><span data-stu-id="c5313-144">In most cases, Docs uses standard Markdown links to other files and pages.</span></span> <span data-ttu-id="c5313-145">Os tipos de links serão descritos nas próximas subseções.</span><span class="sxs-lookup"><span data-stu-id="c5313-145">The types of links are described in subsections below.</span></span>

> [!TIP]
> <span data-ttu-id="c5313-146">O Pacote de Criação de Docs para VS Code pode ajudar a inserir links relativos e indicadores corretamente sem o tédio de ter que adivinhar os caminhos!</span><span class="sxs-lookup"><span data-stu-id="c5313-146">The Docs Authoring Pack for VS Code can help insert relative links and bookmarks correctly without the tedium of figuring out the paths!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5313-147">Não inclua códigos de localidade, como en-us, nos links para sites da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5313-147">Do not include locale codes, such as en-us, in your links to Microsoft sites.</span></span> <span data-ttu-id="c5313-148">Os códigos de localidade embutidos em código impedem que o conteúdo localizado seja renderizado, o que é uma experiência do cliente ruim para os usuários de outros locais e gera grandes custos de localização.</span><span class="sxs-lookup"><span data-stu-id="c5313-148">Hard-coded locale codes prevent localized content from rendering, which is a bad customer experience for users in other locales and incurs significant localization costs.</span></span> <span data-ttu-id="c5313-149">Ao copiar uma URL de um navegador, o código de localidade é incluído por padrão. Então, é necessário excluí-lo manualmente ao criar o link.</span><span class="sxs-lookup"><span data-stu-id="c5313-149">When you copy a URL from a browser, the locale code is included by default, so you need to manually delete it when you create your link.</span></span> <span data-ttu-id="c5313-150">Por exemplo, use:</span><span class="sxs-lookup"><span data-stu-id="c5313-150">For example, use:</span></span>
>
> `[Microsoft](https://www.microsoft.com)`
>
> <span data-ttu-id="c5313-151">E não:</span><span class="sxs-lookup"><span data-stu-id="c5313-151">Not:</span></span>
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a><span data-ttu-id="c5313-152">Links relativos para arquivos no mesmo conjunto de documentos</span><span class="sxs-lookup"><span data-stu-id="c5313-152">Relative links to files in the same doc set</span></span>

<span data-ttu-id="c5313-153">Um caminho relativo é o caminho para o arquivo de destino relativo ao arquivo atual.</span><span class="sxs-lookup"><span data-stu-id="c5313-153">A relative path is the path to the target file relative to the current file.</span></span> <span data-ttu-id="c5313-154">No Docs, é possível usar um caminho relativo para criar um link para outro arquivo do mesmo conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-154">In Docs, you can use a relative path to link to another file within the same doc set.</span></span> <span data-ttu-id="c5313-155">A sintaxe do caminho relativo é assim:</span><span class="sxs-lookup"><span data-stu-id="c5313-155">The syntax for a relative path is as follows:</span></span>

```markdown
[link text](../../folder/filename.md)
```

<span data-ttu-id="c5313-156">Em que `../` indica um nível acima na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="c5313-156">Where `../` indicates one level above in the hierarchy.</span></span>

- <span data-ttu-id="c5313-157">O caminho relativo será resolvido durante o build, incluindo a remoção da extensão .md.</span><span class="sxs-lookup"><span data-stu-id="c5313-157">The relative path will be resolved during the build, including removal of the .md extension.</span></span>
- <span data-ttu-id="c5313-158">Você pode usar "../" para vincular ao arquivo na pasta pai, mas esse arquivo precisa estar no mesmo conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-158">You can use "../" to link to a file in the parent folder, but that file has to be in the same doc set.</span></span> <span data-ttu-id="c5313-159">Você não pode usar "../" para vincular a um arquivo em outra pasta do conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-159">You cannot use "../" to link to a file in another doc set folder.</span></span>
- <span data-ttu-id="c5313-160">O Docs também é compatível com um formato especial de caminho relativo que começa com "~" (por exemplo, ~/foo/bar.md).</span><span class="sxs-lookup"><span data-stu-id="c5313-160">Docs also supports a special form of relative path that starts with "~" (for example, ~/foo/bar.md).</span></span> <span data-ttu-id="c5313-161">Essa sintaxe indica um arquivo relativo à pasta raiz de um conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-161">This syntax indicates a file relative to the root folder of a doc set.</span></span> <span data-ttu-id="c5313-162">Esse tipo de caminho também será validado e resolvido durante o build.</span><span class="sxs-lookup"><span data-stu-id="c5313-162">This kind of path is also validated and resolved during the build.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5313-163">Inclua a extensão de arquivo no caminho relativo.</span><span class="sxs-lookup"><span data-stu-id="c5313-163">Include the file extension in the relative path.</span></span> <span data-ttu-id="c5313-164">O build valida a existência do arquivo de destino desse caminho relativo.</span><span class="sxs-lookup"><span data-stu-id="c5313-164">Build validates the existence of the target file of that relative path.</span></span> <span data-ttu-id="c5313-165">Se o caminho relativo não incluir a extensão de arquivo, provavelmente o build enviará um aviso de link desfeito.</span><span class="sxs-lookup"><span data-stu-id="c5313-165">If relative path does not include file extension, it is likely build will report a warning of broken link.</span></span> <span data-ttu-id="c5313-166">Por exemplo, use:</span><span class="sxs-lookup"><span data-stu-id="c5313-166">For example, use:</span></span>
>
> `[link text](../../folder/filename.md)`
>
> <span data-ttu-id="c5313-167">E não:</span><span class="sxs-lookup"><span data-stu-id="c5313-167">Not:</span></span>
>
> `[link text](../../folder/filename)`

### <a name="site-relative-links-to-other-files-on-docs"></a><span data-ttu-id="c5313-168">Links relativos do site para outros arquivos no Docs</span><span class="sxs-lookup"><span data-stu-id="c5313-168">Site relative links to other files on Docs</span></span>

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

<span data-ttu-id="c5313-169">Não inclua a extensão de arquivo (.md).</span><span class="sxs-lookup"><span data-stu-id="c5313-169">Do not include the file extension (.md).</span></span> <span data-ttu-id="c5313-170">Isso vincula ao arquivo de visão geral do Linux de fora do conjunto de documentos de "artigos" do Azure.</span><span class="sxs-lookup"><span data-stu-id="c5313-170">This links to the Linux overview file from outside the Azure "articles" doc set.</span></span>

### <a name="links-to-external-sites"></a><span data-ttu-id="c5313-171">Links para sites externos</span><span class="sxs-lookup"><span data-stu-id="c5313-171">Links to external sites</span></span>

```markdown
[Microsoft](https://www.microsoft.com)
```

<span data-ttu-id="c5313-172">Link baseado em URL para outra página da Web (precisa incluir https://).</span><span class="sxs-lookup"><span data-stu-id="c5313-172">URL-based link to another web page (must include https://).</span></span>

### <a name="bookmark-links"></a><span data-ttu-id="c5313-173">Links com indicadores</span><span class="sxs-lookup"><span data-stu-id="c5313-173">Bookmark links</span></span>

<span data-ttu-id="c5313-174">Link com indicador para um cabeçalho em outro arquivo no mesmo repositório:</span><span class="sxs-lookup"><span data-stu-id="c5313-174">Bookmark link to a heading in another file in the same repo:</span></span>

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<span data-ttu-id="c5313-175">Link com indicador para um cabeçalho no arquivo atual:</span><span class="sxs-lookup"><span data-stu-id="c5313-175">Bookmark link to a heading in the current file:</span></span>

```markdown
[Managed Disks](#managed-disks)
```

<span data-ttu-id="c5313-176">Use uma hashtag seguida pelas palavras do cabeçalho com a pontuação removida e os espaços substituídos por traços.</span><span class="sxs-lookup"><span data-stu-id="c5313-176">Use a hash tag followed by the words of the heading with punctuation removed and spaces replaced with dashes.</span></span>

### <a name="explicit-anchor-links"></a><span data-ttu-id="c5313-177">Links do tipo âncora explícitos</span><span class="sxs-lookup"><span data-stu-id="c5313-177">Explicit anchor links</span></span>

<span data-ttu-id="c5313-178">Os links do tipo âncora explícitos que usam a marca HTML `<a>` não são **obrigatórios ou recomendados**, exceto em páginas de hub e de aterrissagem.</span><span class="sxs-lookup"><span data-stu-id="c5313-178">Explicit anchor links using the `<a>` HTML tag are **not required or recommended** except in hub and landing pages.</span></span> <span data-ttu-id="c5313-179">Use os indicadores conforme descrito acima nos arquivos Markdown em geral.</span><span class="sxs-lookup"><span data-stu-id="c5313-179">Use bookmarks as described above in general Markdown files.</span></span> <span data-ttu-id="c5313-180">Para páginas de hub e de aterrissagem, use as âncoras desta forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-180">For hub and landing pages, use anchors as follows:</span></span>

<span data-ttu-id="c5313-181">`## <a id="AnchorText"> </a>Header text` ou `## <a name="AnchorText"> </a>Header text`</span><span class="sxs-lookup"><span data-stu-id="c5313-181">`## <a id="AnchorText"> </a>Header text` or `## <a name="AnchorText"> </a>Header text`</span></span>

<span data-ttu-id="c5313-182">Para criar links para âncoras explícitas, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c5313-182">To link to explicit anchors, use the following syntax:</span></span>

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a><span data-ttu-id="c5313-183">Links XREF (referência cruzada)</span><span class="sxs-lookup"><span data-stu-id="c5313-183">XREF (cross reference) links</span></span>

<span data-ttu-id="c5313-184">Para criar links para páginas de referências de API geradas automaticamente no conjunto de documentos atual ou em outros conjuntos de documentos, use links XREF com a UID (ID exclusiva).</span><span class="sxs-lookup"><span data-stu-id="c5313-184">To link to auto-generated API references pages in the current doc set or other doc sets, use XREF links with the unique ID (UID).</span></span>

> [!NOTE]
> <span data-ttu-id="c5313-185">Para referenciar páginas de referência de API em outros conjuntos de documentos, é necessário adicionar a configuração `xrefService` no arquivo `docfx.json`.</span><span class="sxs-lookup"><span data-stu-id="c5313-185">To reference API reference pages in other doc sets, you need to add `xrefService` configuration in `docfx.json` file.</span></span>
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

<span data-ttu-id="c5313-186">O UID equivale ao nome de classe e membro totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="c5313-186">The UID equates to the fully qualified class and member name.</span></span> <span data-ttu-id="c5313-187">Se você adicionar um \* após o UID, o link representará a página de sobrecarga, e não uma API específica.</span><span class="sxs-lookup"><span data-stu-id="c5313-187">If you add a \* after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="c5313-188">Por exemplo, use `List<T>.BinarySearch*` para criar um link para a página BinarySearch Method em vez de para uma sobrecarga específica, como `List<T>.BinarySearch(T, IComparer<T>)`.</span><span class="sxs-lookup"><span data-stu-id="c5313-188">For example, use `List<T>.BinarySearch*` to link to the BinarySearch Method page instead of linking to a specific overload such as `List<T>.BinarySearch(T, IComparer<T>)`.</span></span>

<span data-ttu-id="c5313-189">Você pode usar uma das seguintes sintaxes:</span><span class="sxs-lookup"><span data-stu-id="c5313-189">You can use one of the following syntaxes:</span></span>

- <span data-ttu-id="c5313-190">Vincule automaticamente: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="c5313-190">Auto-link: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span></span>

  <span data-ttu-id="c5313-191">O parâmetro de consulta `displayProperty` opcional produz um texto de link totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="c5313-191">The optional `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="c5313-192">Por padrão, o texto do link mostra apenas o nome do membro ou do tipo.</span><span class="sxs-lookup"><span data-stu-id="c5313-192">By default, link text shows only the member or type name.</span></span>

- <span data-ttu-id="c5313-193">Link de Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="c5313-193">Markdown link: `[link text](xref:UID)`</span></span>
  
  <span data-ttu-id="c5313-194">Use para personalizar o texto do link exibido.</span><span class="sxs-lookup"><span data-stu-id="c5313-194">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="c5313-195">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="c5313-195">Examples:</span></span>

- <span data-ttu-id="c5313-196">`<xref:System.String>` é renderizado como "String".</span><span class="sxs-lookup"><span data-stu-id="c5313-196">`<xref:System.String>` renders as "String".</span></span>
- <span data-ttu-id="c5313-197">`<xref:System.String?displayProperty=nameWithType>` é renderizado como "System.String".</span><span class="sxs-lookup"><span data-stu-id="c5313-197">`<xref:System.String?displayProperty=nameWithType>` renders as "System.String".</span></span>
- <span data-ttu-id="c5313-198">`[String class](xref:System.String)` é renderizado como "classe String".</span><span class="sxs-lookup"><span data-stu-id="c5313-198">`[String class](xref:System.String)` renders as "String class".</span></span>

<span data-ttu-id="c5313-199">No momento, não há uma maneira simples de localizar os UIDs.</span><span class="sxs-lookup"><span data-stu-id="c5313-199">Right now, there is no easy way to find the UIDs.</span></span> <span data-ttu-id="c5313-200"><!-- ? -->A melhor maneira de localizar o UID de uma API é exibir a origem da página da API à qual você deseja vincular e localizar o valor de ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="c5313-200"><!-- ? -->The best way to find the UID for an API is to view the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="c5313-201">Os valores de sobrecarga individuais não são mostrados na origem.</span><span class="sxs-lookup"><span data-stu-id="c5313-201">Individual overload values are not shown in the source.</span></span> <span data-ttu-id="c5313-202">Estamos trabalhando para fornecer um sistema mais eficiente no futuro.</span><span class="sxs-lookup"><span data-stu-id="c5313-202">We're working on having a better system in the future.</span></span>

<span data-ttu-id="c5313-203">Quando o UID contém os caracteres especiais \`, \# ou \*, o valor do UID deve ser codificado em HTML como `%60`, `%23` e `%2A`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c5313-203">When the UID contains the special characters \`, \#, or \*, the UID value needs to be HTML encoded as `%60`, `%23`, and `%2A`, respectively.</span></span> <span data-ttu-id="c5313-204">Às vezes, você verá parênteses codificados, mas, isso não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="c5313-204">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="c5313-205">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="c5313-205">Examples:</span></span>

- <span data-ttu-id="c5313-206">System.Threading.Tasks.Task\`1 se torna `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="c5313-206">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="c5313-207">System.Exception.\#ctor se torna `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="c5313-207">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="c5313-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se torna `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="c5313-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a><span data-ttu-id="c5313-209">Listas (Numerada, Com Marcadores, Lista de Verificação)</span><span class="sxs-lookup"><span data-stu-id="c5313-209">Lists (Numbered, Bulleted, Checklist)</span></span>

### <a name="numbered-list"></a><span data-ttu-id="c5313-210">Lista numerada</span><span class="sxs-lookup"><span data-stu-id="c5313-210">Numbered list</span></span>

<span data-ttu-id="c5313-211">Para criar uma lista numerada, é possível usar todos os 1s, que são renderizados como uma lista sequencial quando publicados.</span><span class="sxs-lookup"><span data-stu-id="c5313-211">To create a numbered list, you can use all 1s, which are rendered as a sequential list when published.</span></span> <span data-ttu-id="c5313-212">Para aumentar a legibilidade da origem, é possível aumentar as listas.</span><span class="sxs-lookup"><span data-stu-id="c5313-212">For increased source readability, you can increment your lists.</span></span>

<span data-ttu-id="c5313-213">Não use letras nas listas, incluindo listas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="c5313-213">Do not use letters in lists, including nested lists.</span></span> <span data-ttu-id="c5313-214">Elas não são renderizadas corretamente quando publicadas no Docs. As listas aninhadas usando números renderizarão como letras minúsculas quando publicadas.</span><span class="sxs-lookup"><span data-stu-id="c5313-214">They do not render correctly when published to Docs. Nested lists using numbers will render as lowercase letters when published.</span></span> <span data-ttu-id="c5313-215">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c5313-215">For example:</span></span>

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

<span data-ttu-id="c5313-216">Isso será renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-216">This renders as follows:</span></span>

1. <span data-ttu-id="c5313-217">Esta é</span><span class="sxs-lookup"><span data-stu-id="c5313-217">This is</span></span>
1. <span data-ttu-id="c5313-218">uma lista numerada pai</span><span class="sxs-lookup"><span data-stu-id="c5313-218">a parent numbered list</span></span>
   1. <span data-ttu-id="c5313-219">e esta é</span><span class="sxs-lookup"><span data-stu-id="c5313-219">and this is</span></span>
   1. <span data-ttu-id="c5313-220">uma lista numerada aninhada</span><span class="sxs-lookup"><span data-stu-id="c5313-220">a nested numbered list</span></span>
1. <span data-ttu-id="c5313-221">(fim)</span><span class="sxs-lookup"><span data-stu-id="c5313-221">(fin)</span></span>

### <a name="bulleted-list"></a><span data-ttu-id="c5313-222">Lista com marcadores</span><span class="sxs-lookup"><span data-stu-id="c5313-222">Bulleted list</span></span>

<span data-ttu-id="c5313-223">Para criar uma lista com marcadores, use `-` seguido de um espaço no início de cada linha:</span><span class="sxs-lookup"><span data-stu-id="c5313-223">To create a bulleted list, use `-` followed by a space at the beginning of each line:</span></span>

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

<span data-ttu-id="c5313-224">Isso será renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-224">This renders as follows:</span></span>

- <span data-ttu-id="c5313-225">Esta é</span><span class="sxs-lookup"><span data-stu-id="c5313-225">This is</span></span>
- <span data-ttu-id="c5313-226">uma lista com marcadores pai</span><span class="sxs-lookup"><span data-stu-id="c5313-226">a parent bulleted list</span></span>
  - <span data-ttu-id="c5313-227">e esta é</span><span class="sxs-lookup"><span data-stu-id="c5313-227">and this is</span></span>
  - <span data-ttu-id="c5313-228">uma lista com marcadores aninhada</span><span class="sxs-lookup"><span data-stu-id="c5313-228">a nested bulleted list</span></span>
- <span data-ttu-id="c5313-229">Concluído!</span><span class="sxs-lookup"><span data-stu-id="c5313-229">All done!</span></span>

### <a name="checklist"></a><span data-ttu-id="c5313-230">Lista de verificação</span><span class="sxs-lookup"><span data-stu-id="c5313-230">Checklist</span></span>

<span data-ttu-id="c5313-231">As listas de verificação estão disponíveis para uso no docs.microsoft.com (somente) por meio de uma extensão de Markdown personalizada:</span><span class="sxs-lookup"><span data-stu-id="c5313-231">Checklists are available for use on docs.microsoft.com (only) via a custom Markdown extension:</span></span>

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

<span data-ttu-id="c5313-232">Esse exemplo é renderizado no docs.microsoft.com desta forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-232">This example renders on docs.microsoft.com like this:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="c5313-233">Item de lista 1</span><span class="sxs-lookup"><span data-stu-id="c5313-233">List item 1</span></span>
> * <span data-ttu-id="c5313-234">Item de lista 2</span><span class="sxs-lookup"><span data-stu-id="c5313-234">List item 2</span></span>
> * <span data-ttu-id="c5313-235">Item de lista 3</span><span class="sxs-lookup"><span data-stu-id="c5313-235">List item 3</span></span>

<span data-ttu-id="c5313-236">Use as listas de verificação no início ou no fim de um artigo para resumir o conteúdo "O que você aprenderá" ou "O que você aprendeu".</span><span class="sxs-lookup"><span data-stu-id="c5313-236">Use checklists at the beginning or end of an article to summarize "What will you learn" or "What have you learned" content.</span></span> <span data-ttu-id="c5313-237">Não adicione listas de verificação aleatórias ao longo dos seus artigos.</span><span class="sxs-lookup"><span data-stu-id="c5313-237">Do not add random checklists throughout your articles.</span></span>
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a><span data-ttu-id="c5313-238">Ação da próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c5313-238">Next step action</span></span>

<span data-ttu-id="c5313-239">É possível usar uma extensão personalizada para adicionar um botão de ação da próxima etapa a páginas no docs.microsoft.com (somente).</span><span class="sxs-lookup"><span data-stu-id="c5313-239">You can use a custom extension to add a next step action button to pages on docs.microsoft.com (only).</span></span>

<span data-ttu-id="c5313-240">A sintaxe é assim:</span><span class="sxs-lookup"><span data-stu-id="c5313-240">The syntax is as follows:</span></span>

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

<span data-ttu-id="c5313-241">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c5313-241">For example:</span></span>

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

<span data-ttu-id="c5313-242">Isso será renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-242">This renders as follows:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c5313-243">Saiba mais sobre o estilo básico</span><span class="sxs-lookup"><span data-stu-id="c5313-243">Learn about basic style</span></span>](style-quick-start.md)

<span data-ttu-id="c5313-244">É possível usar qualquer link com suporte em uma ação de próxima etapa, incluindo um link de Markdown para outra página da Web.</span><span class="sxs-lookup"><span data-stu-id="c5313-244">You can use any supported link in a next step action, including a Markdown link to another web page.</span></span> <span data-ttu-id="c5313-245">Na maioria dos casos, o link de próxima ação será um link relativo a outro arquivo no mesmo conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-245">In most cases, the next action link will be a relative link to another file in the same doc set.</span></span>

## <a name="section-definition"></a><span data-ttu-id="c5313-246">Definição de seção</span><span class="sxs-lookup"><span data-stu-id="c5313-246">Section definition</span></span>

<span data-ttu-id="c5313-247"><!-- more info about this would be helpful! --> É possível que você precise definir uma seção.</span><span class="sxs-lookup"><span data-stu-id="c5313-247"><!-- more info about this would be helpful! --> You might need to define a section.</span></span> <span data-ttu-id="c5313-248">Essa sintaxe é mais usada para tabelas de códigos.</span><span class="sxs-lookup"><span data-stu-id="c5313-248">This syntax is mostly used for code tables.</span></span>
<span data-ttu-id="c5313-249">Veja o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c5313-249">See the following example:</span></span>

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

<span data-ttu-id="c5313-250">O texto de Markdown do blockquote anterior será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="c5313-250">The preceding blockquote Markdown text will be rendered as:</span></span>
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a><span data-ttu-id="c5313-251">Seletores</span><span class="sxs-lookup"><span data-stu-id="c5313-251">Selectors</span></span>

<span data-ttu-id="c5313-252"><!-- could be more clear! --> Você pode usar um seletor quando quiser se conectar a diferentes páginas do mesmo artigo.</span><span class="sxs-lookup"><span data-stu-id="c5313-252"><!-- could be more clear! --> You can use a selector when you want to connect different pages for the same article.</span></span> <span data-ttu-id="c5313-253">Depois, os leitores podem alternar entre essas páginas.</span><span class="sxs-lookup"><span data-stu-id="c5313-253">Readers can then switch between those pages.</span></span>

> [!NOTE]
> <span data-ttu-id="c5313-254">Essa extensão funciona de forma diferente entre o docs.microsoft.com e o MSDN.</span><span class="sxs-lookup"><span data-stu-id="c5313-254">This extension works differently between docs.microsoft.com and MSDN.</span></span> <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a><span data-ttu-id="c5313-255">Seletor único</span><span class="sxs-lookup"><span data-stu-id="c5313-255">Single selector</span></span>

```
> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)
```

<span data-ttu-id="c5313-256">… será renderizada desta forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-256">... will be rendered like this:</span></span>

> [!div class="op_single_selector"]
> - [Universal do Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a><span data-ttu-id="c5313-265">Seletor múltiplo</span><span class="sxs-lookup"><span data-stu-id="c5313-265">Multi-selector</span></span>

```
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)
```

<span data-ttu-id="c5313-266">… será renderizada desta forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-266">... will be rendered like this:</span></span>

> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Universal do Windows C# | .NET)](how-to-write-workflows-major.md)
> - [(Universal do Windows C# | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | JavaScript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | JavaScript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | JavaScript)](how-to-write-workflows-major.md)

## <a name="tables"></a><span data-ttu-id="c5313-277">Tabelas</span><span class="sxs-lookup"><span data-stu-id="c5313-277">Tables</span></span>

<span data-ttu-id="c5313-278">A maneira mais simples de criar uma tabela em Markdown é usar barras verticais e linhas.</span><span class="sxs-lookup"><span data-stu-id="c5313-278">The simplest way to create a table in Markdown is to use pipes and lines.</span></span> <span data-ttu-id="c5313-279">Para criar uma tabela padrão com um cabeçalho, siga a primeira linha com uma linha tracejada:</span><span class="sxs-lookup"><span data-stu-id="c5313-279">To create a standard table with a header, follow the first line with dashed line:</span></span>

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

<span data-ttu-id="c5313-280">Isso será renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-280">This renders as follows:</span></span>

|<span data-ttu-id="c5313-281">Este é</span><span class="sxs-lookup"><span data-stu-id="c5313-281">This is</span></span>   |<span data-ttu-id="c5313-282">um simples</span><span class="sxs-lookup"><span data-stu-id="c5313-282">a simple</span></span>   |<span data-ttu-id="c5313-283">cabeçalho de tabela</span><span class="sxs-lookup"><span data-stu-id="c5313-283">table header</span></span>|
|----------|-----------|------------|
|<span data-ttu-id="c5313-284">tabela</span><span class="sxs-lookup"><span data-stu-id="c5313-284">table</span></span>     |<span data-ttu-id="c5313-285">dados</span><span class="sxs-lookup"><span data-stu-id="c5313-285">data</span></span>       |<span data-ttu-id="c5313-286">aqui</span><span class="sxs-lookup"><span data-stu-id="c5313-286">here</span></span>        |
|<span data-ttu-id="c5313-287">não precisa</span><span class="sxs-lookup"><span data-stu-id="c5313-287">it doesn't</span></span>|<span data-ttu-id="c5313-288">se</span><span class="sxs-lookup"><span data-stu-id="c5313-288">actually</span></span>   |<span data-ttu-id="c5313-289">alinhar corretamente!</span><span class="sxs-lookup"><span data-stu-id="c5313-289">have to line up nicely!</span></span>||

<span data-ttu-id="c5313-290">Também é possível criar uma tabela sem um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c5313-290">You can also create a table without a header.</span></span> <span data-ttu-id="c5313-291">Por exemplo, para criar uma lista com várias colunas:</span><span class="sxs-lookup"><span data-stu-id="c5313-291">For example, to create a multiple-column list:</span></span>

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

<span data-ttu-id="c5313-292">Isso será renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-292">This renders like this:</span></span>

|   |   |
| - | - |
| <span data-ttu-id="c5313-293">Esta</span><span class="sxs-lookup"><span data-stu-id="c5313-293">This</span></span> | <span data-ttu-id="c5313-294">tabela</span><span class="sxs-lookup"><span data-stu-id="c5313-294">table</span></span> |
| <span data-ttu-id="c5313-295">não tem</span><span class="sxs-lookup"><span data-stu-id="c5313-295">has no</span></span> | <span data-ttu-id="c5313-296">cabeçalho</span><span class="sxs-lookup"><span data-stu-id="c5313-296">header</span></span> |

<span data-ttu-id="c5313-297">Você pode alinhar as colunas usando dois-pontos:</span><span class="sxs-lookup"><span data-stu-id="c5313-297">You can align the columns by using colons:</span></span>

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

<span data-ttu-id="c5313-298">É renderizado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-298">Renders as follows:</span></span>

|                  |
|------------------|
|    <span data-ttu-id="c5313-299">alinhado à direita:</span><span class="sxs-lookup"><span data-stu-id="c5313-299">right aligned:</span></span>|
|<span data-ttu-id="c5313-300">: alinhado à esquerda</span><span class="sxs-lookup"><span data-stu-id="c5313-300">:left aligned</span></span>     |
|<span data-ttu-id="c5313-301">: centralizado        :</span><span class="sxs-lookup"><span data-stu-id="c5313-301">:centered        :</span></span>|

> [!TIP]
> A Extensão de Criação de Docs para VS Code facilita a adição de tabelas básicas de Markdown!
>
> Também é possível usar um [gerador de tabelas online](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a><span data-ttu-id="c5313-304">mx-tdBreakAll</span><span class="sxs-lookup"><span data-stu-id="c5313-304">mx-tdBreakAll</span></span>

> [!IMPORTANT]
> Isso só funciona no site do docs.microsoft.com.

<span data-ttu-id="c5313-306">Se você criar uma tabela em Markdown, a tabela poderá se expandir para a barra de navegação direita, ficando ilegível.</span><span class="sxs-lookup"><span data-stu-id="c5313-306">If you create a table in Markdown, the table might expand to the right navigation and become unreadable.</span></span> <span data-ttu-id="c5313-307">Você pode resolver isso facilmente permitindo que a renderização do Docs quebre a tabela quando necessário.</span><span class="sxs-lookup"><span data-stu-id="c5313-307">You can solve that by allowing Docs rendering to break the table when needed.</span></span> <span data-ttu-id="c5313-308">Basta encapsular a tabela na classe personalizada `[!div class="mx-tdBreakAll"]`.</span><span class="sxs-lookup"><span data-stu-id="c5313-308">Just wrap up the table with the custom class `[!div class="mx-tdBreakAll"]`.</span></span>

<span data-ttu-id="c5313-309">Aqui temos um exemplo de Markdown de uma tabela com três linhas que será encapsulada por um `div` com o nome de classe `mx-tdBreakAll`.</span><span class="sxs-lookup"><span data-stu-id="c5313-309">Here is a Markdown sample of a table with three rows that will be wrapped by a `div` with the class name `mx-tdBreakAll`.</span></span>

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

<span data-ttu-id="c5313-310">Ela será renderizada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-310">It will be rendered like this:</span></span>

> [!div class="mx-tdBreakAll"]
> |<span data-ttu-id="c5313-311">Nome</span><span class="sxs-lookup"><span data-stu-id="c5313-311">Name</span></span>|<span data-ttu-id="c5313-312">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c5313-312">Syntax</span></span>|<span data-ttu-id="c5313-313">Obrigatório para instalação silenciosa?</span><span class="sxs-lookup"><span data-stu-id="c5313-313">Mandatory for silent installation?</span></span>|<span data-ttu-id="c5313-314">Descrição</span><span class="sxs-lookup"><span data-stu-id="c5313-314">Description</span></span>|
> |-------------|----------|---------|---------|
> |<span data-ttu-id="c5313-315">Silencioso</span><span class="sxs-lookup"><span data-stu-id="c5313-315">Quiet</span></span>|<span data-ttu-id="c5313-316">/quiet</span><span class="sxs-lookup"><span data-stu-id="c5313-316">/quiet</span></span>|<span data-ttu-id="c5313-317">Sim</span><span class="sxs-lookup"><span data-stu-id="c5313-317">Yes</span></span>|<span data-ttu-id="c5313-318">Executa o instalador sem exibir interface do usuário e nem prompts.</span><span class="sxs-lookup"><span data-stu-id="c5313-318">Runs the installer, displaying no UI and no prompts.</span></span>|
> |<span data-ttu-id="c5313-319">NoRestart</span><span class="sxs-lookup"><span data-stu-id="c5313-319">NoRestart</span></span>|<span data-ttu-id="c5313-320">/norestart</span><span class="sxs-lookup"><span data-stu-id="c5313-320">/norestart</span></span>|<span data-ttu-id="c5313-321">Não</span><span class="sxs-lookup"><span data-stu-id="c5313-321">No</span></span>|<span data-ttu-id="c5313-322">Suprime as tentativas de reinício.</span><span class="sxs-lookup"><span data-stu-id="c5313-322">Suppresses any attempts to restart.</span></span> <span data-ttu-id="c5313-323">Por padrão, a interface do usuário avisará antes de reiniciar.</span><span class="sxs-lookup"><span data-stu-id="c5313-323">By default, the UI will prompt before restart.</span></span>|
> |<span data-ttu-id="c5313-324">Ajuda</span><span class="sxs-lookup"><span data-stu-id="c5313-324">Help</span></span>|<span data-ttu-id="c5313-325">/help</span><span class="sxs-lookup"><span data-stu-id="c5313-325">/help</span></span>|<span data-ttu-id="c5313-326">Não</span><span class="sxs-lookup"><span data-stu-id="c5313-326">No</span></span>|<span data-ttu-id="c5313-327">Oferece ajuda e referência rápida.</span><span class="sxs-lookup"><span data-stu-id="c5313-327">Provides help and quick reference.</span></span> <span data-ttu-id="c5313-328">Exibe o uso correto do comando de instalação, incluindo uma lista com todas as opções e comportamentos.</span><span class="sxs-lookup"><span data-stu-id="c5313-328">Displays the correct use of the setup command, including a list of all options and behaviors.</span></span>|

### <a name="mx-tdcol2breakall"></a><span data-ttu-id="c5313-329">mx-tdCol2BreakAll</span><span class="sxs-lookup"><span data-stu-id="c5313-329">mx-tdCol2BreakAll</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5313-330">Isso só funciona no site do docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c5313-330">This only works on the docs.microsoft.com site.</span></span>

<span data-ttu-id="c5313-331">Algumas vezes, pode ser que você tenha palavras muito longas na segunda coluna de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="c5313-331">From time to time, you might have very long words in the second column of a table.</span></span> <span data-ttu-id="c5313-332">Para garantir que elas sejam divididas da melhor maneira, você pode aplicar a classe `mx-tdCol2BreakAll` usando a sintaxe de wrapper `div`, conforme mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c5313-332">To ensure they are broken apart nicely, you can apply the class `mx-tdCol2BreakAll` by using the `div` wrapper syntax as shown earlier.</span></span>

### <a name="html-tables"></a><span data-ttu-id="c5313-333">Tabelas HTML</span><span class="sxs-lookup"><span data-stu-id="c5313-333">HTML Tables</span></span>

<span data-ttu-id="c5313-334">As tabelas HTML não são recomendadas para o docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c5313-334">HTML tables are not recommended for docs.microsoft.com.</span></span> <span data-ttu-id="c5313-335">Elas não são legíveis por humanos na origem – o que é um princípio fundamental do Markdown.</span><span class="sxs-lookup"><span data-stu-id="c5313-335">They are not human readable in the source - which is a key principle of Markdown.</span></span>

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a><span data-ttu-id="c5313-336">Vídeos</span><span class="sxs-lookup"><span data-stu-id="c5313-336">Videos</span></span>

### <a name="embedding-videos-into-a-markdown-page"></a><span data-ttu-id="c5313-337">Inserir vídeos em uma página Markdown</span><span class="sxs-lookup"><span data-stu-id="c5313-337">Embedding videos into a Markdown page</span></span>

<span data-ttu-id="c5313-338">No momento, o Docs é compatível com vídeos publicados em um de três locais:</span><span class="sxs-lookup"><span data-stu-id="c5313-338">Currently, Docs can support videos published to one of three locations:</span></span>

- <span data-ttu-id="c5313-339">YouTube</span><span class="sxs-lookup"><span data-stu-id="c5313-339">YouTube</span></span>
- <span data-ttu-id="c5313-340">Channel 9</span><span class="sxs-lookup"><span data-stu-id="c5313-340">Channel 9</span></span>
- <span data-ttu-id="c5313-341">Sistema 'One Player' da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5313-341">Microsoft's own 'One Player' system</span></span>

<span data-ttu-id="c5313-342">Você pode inserir um vídeo com a sintaxe a seguir e o Docs o renderizará.</span><span class="sxs-lookup"><span data-stu-id="c5313-342">You can embed a video with the following syntax, and Docs will render it.</span></span>

```markdown
> [!VIDEO <embedded_video_link>]
```

<span data-ttu-id="c5313-343">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c5313-343">Example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

<span data-ttu-id="c5313-344">... será renderizado como:</span><span class="sxs-lookup"><span data-stu-id="c5313-344">... will be rendered as:</span></span>

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

<span data-ttu-id="c5313-345">E será exibido nas páginas publicadas desta forma:</span><span class="sxs-lookup"><span data-stu-id="c5313-345">And it will be displayed like this on published pages:</span></span>

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> <span data-ttu-id="c5313-346">A URL do vídeo do CH9 deve começar com `https` e terminar com `/player`.</span><span class="sxs-lookup"><span data-stu-id="c5313-346">The CH9 video URL should start with `https` and end with `/player`.</span></span> <span data-ttu-id="c5313-347">Caso contrário, a página inteira será inserida, em vez de apenas o vídeo.</span><span class="sxs-lookup"><span data-stu-id="c5313-347">Otherwise, it will embed the whole page instead of the video only.</span></span>

### <a name="uploading-new-videos"></a><span data-ttu-id="c5313-348">Fazendo upload de novos vídeos</span><span class="sxs-lookup"><span data-stu-id="c5313-348">Uploading new videos</span></span>

<span data-ttu-id="c5313-349">O upload de todos os novos vídeos devem ser feitos usando o seguinte processo:</span><span class="sxs-lookup"><span data-stu-id="c5313-349">Any new videos should be uploaded using the following process:</span></span>

1. <span data-ttu-id="c5313-350">Entre no grupo **docs_video_users** no IDWEB.</span><span class="sxs-lookup"><span data-stu-id="c5313-350">Join the **docs_video_users** group on IDWEB.</span></span>
1. <span data-ttu-id="c5313-351">Acesse https://aka.ms/VideoUploadRequest e preencha os detalhes do vídeo.</span><span class="sxs-lookup"><span data-stu-id="c5313-351">Go to https://aka.ms/VideoUploadRequest and fill in the details for your video.</span></span> <span data-ttu-id="c5313-352">Você precisará de (observe que nenhum destes itens será visível para o público):</span><span class="sxs-lookup"><span data-stu-id="c5313-352">You will need (note that none of these items will be visible to the public):</span></span>
    1. <span data-ttu-id="c5313-353">Um título para o vídeo.</span><span class="sxs-lookup"><span data-stu-id="c5313-353">A title for your video.</span></span>
    1. <span data-ttu-id="c5313-354">Uma lista de produtos/serviços que tenham relação com seu vídeo.</span><span class="sxs-lookup"><span data-stu-id="c5313-354">A list of products/services that your video is related to.</span></span>
    1. <span data-ttu-id="c5313-355">A página de destino ou (se você ainda não tiver uma página) o conjunto de documentos em que o vídeo será hospedado.</span><span class="sxs-lookup"><span data-stu-id="c5313-355">The target page or (if you don’t have the page yet) doc set that your video will be hosted on.</span></span>
    1. <span data-ttu-id="c5313-356">Um link para o arquivo MP4 do vídeo (se você não tiver um local para colocar o arquivo, coloque-o aqui temporariamente: `\\scratch2\scratch\apex`).</span><span class="sxs-lookup"><span data-stu-id="c5313-356">A link to the MP4 file for your video (if you don’t have a location to put the file, you can put it here temporarily:   `\\scratch2\scratch\apex`).</span></span> <span data-ttu-id="c5313-357">Os arquivos MP4 precisam ter 720p ou mais.</span><span class="sxs-lookup"><span data-stu-id="c5313-357">MP4 files should be 720p or higher.</span></span>
    1. <span data-ttu-id="c5313-358">Uma descrição do vídeo.</span><span class="sxs-lookup"><span data-stu-id="c5313-358">A description of the video.</span></span>
1. <span data-ttu-id="c5313-359">Envie (salve) o item.</span><span class="sxs-lookup"><span data-stu-id="c5313-359">Submit (save) that item.</span></span>
1. <span data-ttu-id="c5313-360">Em dois dias úteis, o upload do vídeo será concluído.</span><span class="sxs-lookup"><span data-stu-id="c5313-360">Within two business days, the video will get uploaded.</span></span> <span data-ttu-id="c5313-361">O link que você precisa inserir será colocado no item de trabalho e enviado *de volta para você*.</span><span class="sxs-lookup"><span data-stu-id="c5313-361">The link you need for embedding will be placed into the work item, and it will be resolved *back to you*.</span></span>
1. <span data-ttu-id="c5313-362">Quando você tiver o link, feche o item de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c5313-362">Once you have grabbed the video link, close the work item.</span></span>
1. <span data-ttu-id="c5313-363">Em seguida, o link do vídeo poderá ser adicionado à postagem com o uso desta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c5313-363">The video link can then be added to your post, using this syntax:</span></span>

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
