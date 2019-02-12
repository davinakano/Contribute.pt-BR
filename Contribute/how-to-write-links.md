---
title: Como usar links na documentação
description: Este artigo oferece orientação sobre como criar links para conteúdo dentro do docs.microsoft.com.
author: gewarren
ms.author: gewarren
ms.date: 10/31/2018
ms.openlocfilehash: 9dc1b6dc2ac19b8f28a5a137817245f9a8c34eaf
ms.sourcegitcommit: fbdd61ae4fb3761aec072732eefcbf2c2dca8011
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55887242"
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="a36af-103">Usando links na documentação</span><span class="sxs-lookup"><span data-stu-id="a36af-103">Using links in documentation</span></span>
<span data-ttu-id="a36af-104">Este artigo descreve como usar hiperlinks de páginas hospedadas em docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a36af-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com.</span></span> <span data-ttu-id="a36af-105">É fácil adicionar links em markdown com poucas variações de convenções.</span><span class="sxs-lookup"><span data-stu-id="a36af-105">Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="a36af-106">Os links direcionam os usuários para o conteúdo na mesma página, apontam para outras páginas vizinhas ou para sites e URLs externos.</span><span class="sxs-lookup"><span data-stu-id="a36af-106">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="a36af-107">O back-end do site docs.microsoft.com usa o OPS (Open Publishing System) que oferece suporte ao markdown [CommonMark](https://commonmark.org/) analisado pelo [Markdig](https://github.com/lunet-io/markdig) e também oferece suporte ao [DocFX Flavored Markdown (DFM)](https://dotnet.github.io/docfx/).</span><span class="sxs-lookup"><span data-stu-id="a36af-107">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which supports [CommonMark](https://commonmark.org/) compliant markdown parsed through [Markdig](https://github.com/lunet-io/markdig) and also supports [DocFX Flavored Markdown (DFM)](https://dotnet.github.io/docfx/).</span></span> <span data-ttu-id="a36af-108">Esses tipos de markdown são compatíveis principalmente com o [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), já que a maioria dos documentos são armazenados no GitHub e podem ser editados lá.</span><span class="sxs-lookup"><span data-stu-id="a36af-108">These markdown flavors are mostly compatible with [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), as most docs are stored in GitHub and can be edited there.</span></span> <span data-ttu-id="a36af-109">Mais funcionalidades são adicionadas pelas extensões de Markdown.</span><span class="sxs-lookup"><span data-stu-id="a36af-109">Additional functionality is added through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a36af-110">Todos os links devem ser protegidos (`https` e não `http`) quando o destino tiver suporte para eles (a grande maioria tem).</span><span class="sxs-lookup"><span data-stu-id="a36af-110">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="a36af-111">Texto do link</span><span class="sxs-lookup"><span data-stu-id="a36af-111">Link text</span></span>

<span data-ttu-id="a36af-112">As palavras que você inclui no texto do link devem ser amigáveis.</span><span class="sxs-lookup"><span data-stu-id="a36af-112">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="a36af-113">Em outras palavras, devem ser palavras normais em português ou o título da página que o link abre.</span><span class="sxs-lookup"><span data-stu-id="a36af-113">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a36af-114">Não use "clique aqui".</span><span class="sxs-lookup"><span data-stu-id="a36af-114">Do not use "click here."</span></span> <span data-ttu-id="a36af-115">É ruim para a otimização do mecanismo de pesquisa e não descreve adequadamente o destino.</span><span class="sxs-lookup"><span data-stu-id="a36af-115">It's bad for search engine optimization, and doesn't adequately describe the target.</span></span>

<span data-ttu-id="a36af-116">**Correto:**</span><span class="sxs-lookup"><span data-stu-id="a36af-116">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="a36af-117">**Incorreto:**</span><span class="sxs-lookup"><span data-stu-id="a36af-117">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="a36af-118">Links de um artigo para outro</span><span class="sxs-lookup"><span data-stu-id="a36af-118">Links from one article to another</span></span>

<span data-ttu-id="a36af-119">Para criar um link embutido de um artigo técnico do Docs para outro artigo técnico do Docs dentro do mesmo docset, use a seguinte sintaxe de link:</span><span class="sxs-lookup"><span data-stu-id="a36af-119">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="a36af-120">Um artigo em um diretório é vinculado a outro artigo no mesmo diretório:</span><span class="sxs-lookup"><span data-stu-id="a36af-120">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="a36af-121">Um artigo é vinculado de um subdiretório para um artigo no diretório raiz:</span><span class="sxs-lookup"><span data-stu-id="a36af-121">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="a36af-122">Um artigo no diretório raiz é vinculado a um artigo em um subdiretório:</span><span class="sxs-lookup"><span data-stu-id="a36af-122">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="a36af-123">Um artigo em um subdiretório é vinculado a um artigo em outro subdiretório:</span><span class="sxs-lookup"><span data-stu-id="a36af-123">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="a36af-124">Uma vinculação de artigos entre docsets (mesmo se estiverem no mesmo repositório):  `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="a36af-124">An article linking across docsets (even if in the same repository):  `[link text](./directory/article-name)`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a36af-125">Nenhum dos exemplos acima usa `~/` como parte do link.</span><span class="sxs-lookup"><span data-stu-id="a36af-125">None of the above examples use the `~/` as part of the link.</span></span> <span data-ttu-id="a36af-126">Se você estiver vinculado a um caminho na raiz do repositório, comece com `/`.</span><span class="sxs-lookup"><span data-stu-id="a36af-126">If you are linking to a path at the root of the repository, start with the `/`.</span></span> <span data-ttu-id="a36af-127">A inclusão de `~/` gera links inválidos ao navegar pelos repositórios de origem no GitHub.</span><span class="sxs-lookup"><span data-stu-id="a36af-127">Including the `~/` produces invalid links when navigating the source repositories on GitHub.</span></span> <span data-ttu-id="a36af-128">Iniciar o caminho com `/` resolve este problema corretamente.</span><span class="sxs-lookup"><span data-stu-id="a36af-128">Starting the path with `/` resolves correctly.</span></span>

## <a name="links-to-anchors"></a><span data-ttu-id="a36af-129">Links para âncoras</span><span class="sxs-lookup"><span data-stu-id="a36af-129">Links to anchors</span></span>

<span data-ttu-id="a36af-130">Você não precisa criar âncoras.</span><span class="sxs-lookup"><span data-stu-id="a36af-130">You do not have to create anchors.</span></span> <span data-ttu-id="a36af-131">Elas são geradas automaticamente no momento da publicação para todos os títulos H2.</span><span class="sxs-lookup"><span data-stu-id="a36af-131">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="a36af-132">A única coisa que você precisa fazer é criar links para as seções H2.</span><span class="sxs-lookup"><span data-stu-id="a36af-132">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="a36af-133">Para vincular a um título no mesmo artigo:</span><span class="sxs-lookup"><span data-stu-id="a36af-133">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="a36af-134">Para vincular a uma âncora em outro artigo no mesmo subdiretório:</span><span class="sxs-lookup"><span data-stu-id="a36af-134">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="a36af-135">Para vincular a uma âncora em outro subdiretório do serviço:</span><span class="sxs-lookup"><span data-stu-id="a36af-135">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="a36af-136">Links de inclusões</span><span class="sxs-lookup"><span data-stu-id="a36af-136">Links from includes</span></span>

<span data-ttu-id="a36af-137">Como os arquivos de inclusão estão localizados em outro diretório, você deve usar caminhos relativos mais longos.</span><span class="sxs-lookup"><span data-stu-id="a36af-137">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="a36af-138">Para vincular a um artigo de um arquivo de inclusão, use este formato:</span><span class="sxs-lookup"><span data-stu-id="a36af-138">To link to an article from an include file, use this format:</span></span>

   ```markdown
   [link text](../articles/folder/article-name.md)
   ```

## <a name="links-in-selectors"></a><span data-ttu-id="a36af-139">Links em seletores</span><span class="sxs-lookup"><span data-stu-id="a36af-139">Links in selectors</span></span>

<span data-ttu-id="a36af-140">Um seletor é um componente da navegação que aparece em artigos de documentação como uma lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a36af-140">A selector is a navigation component that appears in a docs article as a drop-down list.</span></span> <span data-ttu-id="a36af-141">Quando um leitor seleciona um valor na lista suspensa, o navegador abre o artigo selecionado.</span><span class="sxs-lookup"><span data-stu-id="a36af-141">When a reader selects a value in the drop-down, the browser opens the selected article.</span></span> <span data-ttu-id="a36af-142">Normalmente, a lista do seletor contém links para artigos com relação próxima, por exemplo, com o mesmo tema em diversas linguagens de programação ou uma série de artigos com relação próxima.</span><span class="sxs-lookup"><span data-stu-id="a36af-142">Typically the selector list contains links to closely related articles, for example the same subject matter in multiple programming languages or a closely related series of articles.</span></span> 

<span data-ttu-id="a36af-143">Se você tiver seletores inseridos em uma inclusão, use a seguinte estrutura de link:</span><span class="sxs-lookup"><span data-stu-id="a36af-143">If you have selectors that are embedded in an include, use the following link structure:</span></span>

   ```markdown
   > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
   - [(Text1 | Example1 )](../articles/folder/article-name1.md)
   - [(Text1 | Example2 )](../articles/folder/article-name2.md)
   - [(Text2 | Example3 )](../articles/folder/article-name3.md)
   - [(Text2 | Example4 )](../articles/folder/article-name4.md) -->
   ```

## <a name="reference-style-links"></a><span data-ttu-id="a36af-144">Links de estilo de referência</span><span class="sxs-lookup"><span data-stu-id="a36af-144">Reference-style links</span></span>

<span data-ttu-id="a36af-145">Você pode usar os links em estilo de referência para facilitar a leitura do conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="a36af-145">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="a36af-146">Os links em estilo de referência substituem a sintaxe do link embutido por uma sintaxe simplificada que permite mover as URLs longas para o final do artigo.</span><span class="sxs-lookup"><span data-stu-id="a36af-146">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="a36af-147">Veja o exemplo do [Daring Fireball](https://daringfireball.net/projects/markdown/):</span><span class="sxs-lookup"><span data-stu-id="a36af-147">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="a36af-148">Texto embutido:</span><span class="sxs-lookup"><span data-stu-id="a36af-148">Inline text:</span></span>

   ```markdown
   I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].
   ```

<span data-ttu-id="a36af-149">Referências de link ao final do artigo:</span><span class="sxs-lookup"><span data-stu-id="a36af-149">Link references at the end of the article:</span></span>

   ```markdown
   <!--Reference links in article-->
   [1]: http://google.com/
   [2]: http://search.yahoo.com/
   [3]: http://search.msn.com/
   ```
   
<span data-ttu-id="a36af-150">Lembre-se de incluir o espaço após os dois-pontos, antes do link.</span><span class="sxs-lookup"><span data-stu-id="a36af-150">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="a36af-151">Ao vincular com outros artigos técnicos, se você se esquecer de incluir o espaço, o link quebrará no artigo publicado.</span><span class="sxs-lookup"><span data-stu-id="a36af-151">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="a36af-152">Links para páginas que não fazem parte do conjunto de documentação técnica</span><span class="sxs-lookup"><span data-stu-id="a36af-152">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="a36af-153">Para vincular a uma página em outra propriedade da Microsoft (como uma página de preço, uma página de SLA ou qualquer coisa que não seja um artigo de documentação), use uma URL absoluta, mas omita a localidade.</span><span class="sxs-lookup"><span data-stu-id="a36af-153">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="a36af-154">O objetivo aqui é que os links funcionem no GitHub e no site renderizado:</span><span class="sxs-lookup"><span data-stu-id="a36af-154">The goal here is that links work in GitHub and on the rendered site:</span></span>

   ```markdown
   [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)
   ```
   
## <a name="links-to-third-party-sites"></a><span data-ttu-id="a36af-155">Links para sites de terceiros</span><span class="sxs-lookup"><span data-stu-id="a36af-155">Links to third-party sites</span></span>

<span data-ttu-id="a36af-156">A melhor experiência de usuário reduz ao máximo o envio do usuário para outro site.</span><span class="sxs-lookup"><span data-stu-id="a36af-156">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="a36af-157">Portanto, os links para sites de terceiros, dos quais precisamos às vezes, devem ser baseados nestas informações:</span><span class="sxs-lookup"><span data-stu-id="a36af-157">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="a36af-158">**Responsabilidade**: vincule ao conteúdo de terceiros quando as informações que você deseja compartilhar forem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a36af-158">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="a36af-159">Por exemplo, não é papel da Microsoft informar às pessoas como usar as ferramentas para desenvolvedores do Android. Isso é responsabilidade do Google.</span><span class="sxs-lookup"><span data-stu-id="a36af-159">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="a36af-160">Se precisarmos, podemos explicar como usar as ferramentas de desenvolvedor do Android *com* o Azure, mas o Google deve instruir como usar suas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="a36af-160">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="a36af-161">**Aprovação do PM**: solicite que a Microsoft aprove o conteúdo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a36af-161">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="a36af-162">Ao vincular, estamos afirmando nossa confiança nesse conteúdo e nossas obrigações caso a pessoa siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="a36af-162">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="a36af-163">**Análises de atualização**: verifique se as informações de terceiros ainda estão atualizadas e corretas, se são relevantes e se o link não mudou.</span><span class="sxs-lookup"><span data-stu-id="a36af-163">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="a36af-164">**Externo**: informe aos usuários que eles acessarão outro site.</span><span class="sxs-lookup"><span data-stu-id="a36af-164">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="a36af-165">Se o contexto não deixar isso claro, adicione uma frase de esclarecimento.</span><span class="sxs-lookup"><span data-stu-id="a36af-165">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="a36af-166">Por exemplo: “Os pré-requisitos incluem as Ferramentas para Desenvolvedores do Android, que podem ser baixadas no site do Android Studio”.</span><span class="sxs-lookup"><span data-stu-id="a36af-166">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="a36af-167">**Próximas etapas**: você pode adicionar um link para, por exemplo, um blog de MVP em uma seção de “Próximas etapas”.</span><span class="sxs-lookup"><span data-stu-id="a36af-167">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="a36af-168">Mas, novamente, tenha certeza de que os usuários entenderão que estão saindo do site.</span><span class="sxs-lookup"><span data-stu-id="a36af-168">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="a36af-169">**Jurídico**: estamos cobertos juridicamente em **Links para sites de terceiros** no rodapé **Termos de Uso** de todas as páginas do ms.com.</span><span class="sxs-lookup"><span data-stu-id="a36af-169">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="a36af-170">Link para o MSDN ou o TechNet</span><span class="sxs-lookup"><span data-stu-id="a36af-170">Links to MSDN or TechNet</span></span>

<span data-ttu-id="a36af-171">Quando for necessário vincular ao MSDN ou ao TechNet, use o link completo para o tópico e remova a localidade de idioma "en-us" do link.</span><span class="sxs-lookup"><span data-stu-id="a36af-171">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="a36af-172">Links para conteúdo de referência do Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="a36af-172">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="a36af-173">O conteúdo de referência do Azure PowerShell passou por diversas alterações desde novembro de 2016.</span><span class="sxs-lookup"><span data-stu-id="a36af-173">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="a36af-174">Use as diretrizes a seguir a fim de criar um link para esse conteúdo a partir de outros artigos no docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a36af-174">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="a36af-175">Estrutura da URL:</span><span class="sxs-lookup"><span data-stu-id="a36af-175">Structure of the URL:</span></span>

* <span data-ttu-id="a36af-176">Para cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a36af-176">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="a36af-177">Para tópicos conceituais:</span><span class="sxs-lookup"><span data-stu-id="a36af-177">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="a36af-178">A parte `<moniker-name>` é opcional.</span><span class="sxs-lookup"><span data-stu-id="a36af-178">The `<moniker-name>` portion is optional.</span></span> <span data-ttu-id="a36af-179">Se ela for omitida, você será direcionado à versão mais recente do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a36af-179">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="a36af-180">A parte `<service-name>` é um dos exemplos mostrados nas seguintes URLs base:</span><span class="sxs-lookup"><span data-stu-id="a36af-180">The `<service-name>` portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="a36af-181">Conteúdo do Azure PowerShell (AzureRM): [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="a36af-181">Azure PowerShell (AzureRM) content: [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span></span>
- <span data-ttu-id="a36af-182">Conteúdo do Azure PowerShell (ASM): [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span><span class="sxs-lookup"><span data-stu-id="a36af-182">Azure PowerShell (ASM) content: [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span></span>
- <span data-ttu-id="a36af-183">Conteúdo do PowerShell do Azure Active Directory (AzureAD): [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span><span class="sxs-lookup"><span data-stu-id="a36af-183">Azure Active Directory (AzureAD) PowerShell content: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span></span>
- <span data-ttu-id="a36af-184">PowerShell do Azure Service Fabric: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)</span><span class="sxs-lookup"><span data-stu-id="a36af-184">Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)</span></span>
- <span data-ttu-id="a36af-185">PowerShell da Proteção de Informações do Azure: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span><span class="sxs-lookup"><span data-stu-id="a36af-185">Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span></span>
- <span data-ttu-id="a36af-186">PowerShell de Trabalhos de BD Elástico do Azure: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span><span class="sxs-lookup"><span data-stu-id="a36af-186">Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span></span>

<span data-ttu-id="a36af-187">Ao usar essas URLs, você será redirecionado para a versão mais recente do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a36af-187">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="a36af-188">Dessa forma, você não precisa especificar o moniker de uma versão.</span><span class="sxs-lookup"><span data-stu-id="a36af-188">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="a36af-189">E não haverá links para um conteúdo conceitual que precisarão ser atualizados quando a versão for alterada.</span><span class="sxs-lookup"><span data-stu-id="a36af-189">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="a36af-190">Para criar o link correto, localize no navegador a página à qual deseja vincular e copie a URL.</span><span class="sxs-lookup"><span data-stu-id="a36af-190">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="a36af-191">Depois, remova `https://docs.microsoft.com` e as informações de localidade.</span><span class="sxs-lookup"><span data-stu-id="a36af-191">Then, remove  `https://docs.microsoft.com` and the locale info.</span></span>

<span data-ttu-id="a36af-192">Ao vincular por meio de um sumário, é necessário usar a URL completa sem as informações de localidade.</span><span class="sxs-lookup"><span data-stu-id="a36af-192">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="a36af-193">Markdown exemplo:</span><span class="sxs-lookup"><span data-stu-id="a36af-193">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
