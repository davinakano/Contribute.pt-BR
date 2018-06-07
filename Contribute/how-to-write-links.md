---
title: Como usar links na documentação
description: Este artigo oferece orientação sobre como criar links para conteúdo dentro do docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 06/29/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1699e57ac6a4dc4c5a1ef099ea183b3cbc6307cd
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469522"
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="e2510-103">Usando links na documentação</span><span class="sxs-lookup"><span data-stu-id="e2510-103">Using links in documentation</span></span>
<span data-ttu-id="e2510-104">Este artigo descreve como usar hiperlinks de páginas hospedadas em docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e2510-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com.</span></span> <span data-ttu-id="e2510-105">É fácil adicionar links em markdown com poucas variações de convenções.</span><span class="sxs-lookup"><span data-stu-id="e2510-105">Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="e2510-106">Os links direcionam os usuários para o conteúdo na mesma página, apontam para outras páginas vizinhas ou para sites e URLs externos.</span><span class="sxs-lookup"><span data-stu-id="e2510-106">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="e2510-107">O back-end do site docs.microsoft.com usa o OPS (Open Publishing System) que implementa o DFM (DocFX Flavored Markdown).</span><span class="sxs-lookup"><span data-stu-id="e2510-107">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="e2510-108">O DFM é altamente compatível com GFM (GitHub Flavored Markdown), e o DFM adiciona uma funcionalidade adicional por meio de extensões de Markdown.</span><span class="sxs-lookup"><span data-stu-id="e2510-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2510-109">Todos os links devem ser protegidos (`https` e não `http`) quando o destino tiver suporte para eles (a grande maioria tem).</span><span class="sxs-lookup"><span data-stu-id="e2510-109">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="e2510-110">Texto do link</span><span class="sxs-lookup"><span data-stu-id="e2510-110">Link text</span></span>

<span data-ttu-id="e2510-111">As palavras que você inclui no texto do link devem ser amigáveis.</span><span class="sxs-lookup"><span data-stu-id="e2510-111">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="e2510-112">Em outras palavras, devem ser palavras normais em português ou o título da página que o link abre.</span><span class="sxs-lookup"><span data-stu-id="e2510-112">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2510-113">Não use "clique aqui".</span><span class="sxs-lookup"><span data-stu-id="e2510-113">Do not use "click here."</span></span> <span data-ttu-id="e2510-114">É ruim para SEO e não descreve adequadamente o destino.</span><span class="sxs-lookup"><span data-stu-id="e2510-114">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="e2510-115">**Correto:**</span><span class="sxs-lookup"><span data-stu-id="e2510-115">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="e2510-116">**Incorreto:**</span><span class="sxs-lookup"><span data-stu-id="e2510-116">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="e2510-117">Links de um artigo para outro</span><span class="sxs-lookup"><span data-stu-id="e2510-117">Links from one article to another</span></span>

<span data-ttu-id="e2510-118">Para criar um link embutido de um artigo técnico do Docs para outro artigo técnico do Docs dentro do mesmo docset, use a seguinte sintaxe de link:</span><span class="sxs-lookup"><span data-stu-id="e2510-118">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="e2510-119">Um artigo em um diretório é vinculado a outro artigo no mesmo diretório:</span><span class="sxs-lookup"><span data-stu-id="e2510-119">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="e2510-120">Um artigo é vinculado de um subdiretório para um artigo no diretório raiz:</span><span class="sxs-lookup"><span data-stu-id="e2510-120">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="e2510-121">Um artigo no diretório raiz é vinculado a um artigo em um subdiretório:</span><span class="sxs-lookup"><span data-stu-id="e2510-121">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="e2510-122">Um artigo em um subdiretório é vinculado a um artigo em outro subdiretório:</span><span class="sxs-lookup"><span data-stu-id="e2510-122">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="e2510-123">Uma vinculação de artigos entre docsets (mesmo se estiverem no mesmo repositório): `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="e2510-123">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>
  
## <a name="links-to-anchors"></a><span data-ttu-id="e2510-124">Links para âncoras</span><span class="sxs-lookup"><span data-stu-id="e2510-124">Links to anchors</span></span>

<span data-ttu-id="e2510-125">Você não precisa criar âncoras.</span><span class="sxs-lookup"><span data-stu-id="e2510-125">You do not have to create anchors.</span></span> <span data-ttu-id="e2510-126">Elas são geradas automaticamente no momento da publicação para todos os títulos H2.</span><span class="sxs-lookup"><span data-stu-id="e2510-126">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="e2510-127">A única coisa que você precisa fazer é criar links para as seções H2.</span><span class="sxs-lookup"><span data-stu-id="e2510-127">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="e2510-128">Para vincular a um título no mesmo artigo:</span><span class="sxs-lookup"><span data-stu-id="e2510-128">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="e2510-129">Para vincular a uma âncora em outro artigo no mesmo subdiretório:</span><span class="sxs-lookup"><span data-stu-id="e2510-129">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="e2510-130">Para vincular a uma âncora em outro subdiretório do serviço:</span><span class="sxs-lookup"><span data-stu-id="e2510-130">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="e2510-131">Links de inclusões</span><span class="sxs-lookup"><span data-stu-id="e2510-131">Links from includes</span></span>

<span data-ttu-id="e2510-132">Como os arquivos de inclusão estão localizados em outro diretório, você deve usar caminhos relativos mais longos.</span><span class="sxs-lookup"><span data-stu-id="e2510-132">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="e2510-133">Para vincular a um artigo de um arquivo de inclusão, use este formato:</span><span class="sxs-lookup"><span data-stu-id="e2510-133">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="e2510-134">Links em seletores</span><span class="sxs-lookup"><span data-stu-id="e2510-134">Links in selectors</span></span>

<span data-ttu-id="e2510-135">Se você tiver seletores incorporados em uma inclusão, assim como a equipe de documentação do Azure, use a seguinte estrutura de link:</span><span class="sxs-lookup"><span data-stu-id="e2510-135">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="e2510-136">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span><span class="sxs-lookup"><span data-stu-id="e2510-136">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="e2510-137">(Texto1 | Exemplo1 )</span><span class="sxs-lookup"><span data-stu-id="e2510-137">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="e2510-138">(Texto1 | Exemplo2 )</span><span class="sxs-lookup"><span data-stu-id="e2510-138">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="e2510-139">(Texto2 | Exemplo3 )</span><span class="sxs-lookup"><span data-stu-id="e2510-139">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="e2510-140">[(Texto2 | Exemplo4 )](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="e2510-140">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="e2510-141">Links de estilo de referência</span><span class="sxs-lookup"><span data-stu-id="e2510-141">Reference-style links</span></span>

<span data-ttu-id="e2510-142">Você pode usar os links em estilo de referência para facilitar a leitura do conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="e2510-142">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="e2510-143">Os links em estilo de referência substituem a sintaxe do link embutido por uma sintaxe simplificada que permite mover as URLs longas para o final do artigo.</span><span class="sxs-lookup"><span data-stu-id="e2510-143">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="e2510-144">Veja o exemplo do [Daring Fireball](https://daringfireball.net/projects/markdown/):</span><span class="sxs-lookup"><span data-stu-id="e2510-144">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="e2510-145">Texto embutido:</span><span class="sxs-lookup"><span data-stu-id="e2510-145">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="e2510-146">Referências de link ao final do artigo:</span><span class="sxs-lookup"><span data-stu-id="e2510-146">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="e2510-147">Lembre-se de incluir o espaço após os dois-pontos, antes do link.</span><span class="sxs-lookup"><span data-stu-id="e2510-147">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="e2510-148">Ao vincular com outros artigos técnicos, se você se esquecer de incluir o espaço, o link quebrará no artigo publicado.</span><span class="sxs-lookup"><span data-stu-id="e2510-148">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="e2510-149">Links para páginas que não fazem parte do conjunto de documentação técnica</span><span class="sxs-lookup"><span data-stu-id="e2510-149">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="e2510-150">Para vincular a uma página em outra propriedade da Microsoft (como uma página de preço, uma página de SLA ou qualquer coisa que não seja um artigo de documentação), use uma URL absoluta, mas omita a localidade.</span><span class="sxs-lookup"><span data-stu-id="e2510-150">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="e2510-151">O objetivo aqui é que os links funcionem no GitHub e no site renderizado:</span><span class="sxs-lookup"><span data-stu-id="e2510-151">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="e2510-152">Links para sites de terceiros</span><span class="sxs-lookup"><span data-stu-id="e2510-152">Links to third-party sites</span></span>

<span data-ttu-id="e2510-153">A melhor experiência de usuário reduz ao máximo o envio do usuário para outro site.</span><span class="sxs-lookup"><span data-stu-id="e2510-153">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="e2510-154">Portanto, os links para sites de terceiros, dos quais precisamos às vezes, devem ser baseados nestas informações:</span><span class="sxs-lookup"><span data-stu-id="e2510-154">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="e2510-155">**Responsabilidade:** vincule ao conteúdo de terceiros quando as informações que você deseja compartilhar forem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e2510-155">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="e2510-156">Por exemplo, não é papel da Microsoft informar às pessoas como usar as ferramentas para desenvolvedores do Android. Isso é responsabilidade do Google.</span><span class="sxs-lookup"><span data-stu-id="e2510-156">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="e2510-157">Se precisarmos, podemos explicar como usar as ferramentas de desenvolvedor do Android *com* o Azure, mas o Google deve instruir como usar suas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e2510-157">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="e2510-158">**Aprovação do PM**: solicite que a Microsoft aprove o conteúdo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e2510-158">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="e2510-159">Ao vincular, estamos afirmando nossa confiança nesse conteúdo e nossas obrigações caso a pessoa siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="e2510-159">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="e2510-160">**Análises de atualização:** verifique se as informações de terceiros ainda estão atualizadas e corretas, se são relevantes e se o link não mudou.</span><span class="sxs-lookup"><span data-stu-id="e2510-160">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="e2510-161">**Externo:** informe aos usuários que eles vão acessar outro site.</span><span class="sxs-lookup"><span data-stu-id="e2510-161">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="e2510-162">Se o contexto não deixar isso claro, adicione uma frase de esclarecimento.</span><span class="sxs-lookup"><span data-stu-id="e2510-162">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="e2510-163">Por exemplo: “Os pré-requisitos incluem as Ferramentas para Desenvolvedores do Android, que podem ser baixadas no site do Android Studio”.</span><span class="sxs-lookup"><span data-stu-id="e2510-163">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="e2510-164">**Próximas etapas:** você pode adicionar um link para, por exemplo, um blog de MVP em uma seção de “Próximas etapas”.</span><span class="sxs-lookup"><span data-stu-id="e2510-164">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="e2510-165">Mas, novamente, tenha certeza de que os usuários entenderão que estão saindo do site.</span><span class="sxs-lookup"><span data-stu-id="e2510-165">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="e2510-166">**Jurídico:** estamos cobertos juridicamente em **Links para sites de terceiros** no rodapé dos **Termos de Uso** em todas as páginas do ms.com.</span><span class="sxs-lookup"><span data-stu-id="e2510-166">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="e2510-167">Link para o MSDN ou o TechNet</span><span class="sxs-lookup"><span data-stu-id="e2510-167">Links to MSDN or TechNet</span></span>

<span data-ttu-id="e2510-168">Quando for necessário vincular ao MSDN ou ao TechNet, use o link completo para o tópico e remova a localidade de idioma "en-us" do link.</span><span class="sxs-lookup"><span data-stu-id="e2510-168">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="e2510-169">Links para conteúdo de referência do Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2510-169">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="e2510-170">O conteúdo de referência do Azure PowerShell passou por diversas alterações desde novembro de 2016.</span><span class="sxs-lookup"><span data-stu-id="e2510-170">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="e2510-171">Use as diretrizes a seguir a fim de criar um link para esse conteúdo a partir de outros artigos no docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e2510-171">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="e2510-172">Estrutura da URL:</span><span class="sxs-lookup"><span data-stu-id="e2510-172">Structure of the URL:</span></span>

* <span data-ttu-id="e2510-173">Para cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e2510-173">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="e2510-174">Para tópicos conceituais:</span><span class="sxs-lookup"><span data-stu-id="e2510-174">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="e2510-175">A parte &lt;moniker-name&gt; é opcional.</span><span class="sxs-lookup"><span data-stu-id="e2510-175">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="e2510-176">Se ela for omitida, você será direcionado à versão mais recente do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e2510-176">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="e2510-177">A parte &lt;service-name&gt; é um dos exemplos mostrados nas seguintes URLs base:</span><span class="sxs-lookup"><span data-stu-id="e2510-177">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="e2510-178">Conteúdo do Azure PowerShell (AzureRM): https://docs.microsoft.com/powershell/azure/</span><span class="sxs-lookup"><span data-stu-id="e2510-178">Azure PowerShell (AzureRM) content: https://docs.microsoft.com/powershell/azure/</span></span>
- <span data-ttu-id="e2510-179">Conteúdo do Azure PowerShell (ASM): https://docs.microsoft.com/powershell/azure/_servicemanagement_</span><span class="sxs-lookup"><span data-stu-id="e2510-179">Azure PowerShell (ASM) content: https://docs.microsoft.com/powershell/azure/_servicemanagement_</span></span>
- <span data-ttu-id="e2510-180">Conteúdo do Azure Active Directory (AzureAD) PowerShell: https://docs.microsoft.com/powershell/azure/_active-directory_</span><span class="sxs-lookup"><span data-stu-id="e2510-180">Azure Active Directory (AzureAD) PowerShell content: https://docs.microsoft.com/powershell/azure/_active-directory_</span></span>
- <span data-ttu-id="e2510-181">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span><span class="sxs-lookup"><span data-stu-id="e2510-181">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span></span>
- <span data-ttu-id="e2510-182">PowerShell da Proteção de Informações do Azure: https://docs.microsoft.com/powershell/azure/_aip_</span><span class="sxs-lookup"><span data-stu-id="e2510-182">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span></span>
- <span data-ttu-id="e2510-183">PowerShell de Trabalhos de BD Elástico do Azure: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span><span class="sxs-lookup"><span data-stu-id="e2510-183">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span></span>

<span data-ttu-id="e2510-184">Ao usar essas URLs, você será redirecionado para a versão mais recente do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e2510-184">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="e2510-185">Dessa forma, você não precisa especificar o moniker de uma versão.</span><span class="sxs-lookup"><span data-stu-id="e2510-185">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="e2510-186">E não haverá links para um conteúdo conceitual que precisarão ser atualizados quando a versão for alterada.</span><span class="sxs-lookup"><span data-stu-id="e2510-186">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="e2510-187">Para criar o link correto, localize no navegador a página à qual deseja vincular e copie a URL.</span><span class="sxs-lookup"><span data-stu-id="e2510-187">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="e2510-188">Depois, remova "https://docs.microsoft.com" e as informações de localidade.</span><span class="sxs-lookup"><span data-stu-id="e2510-188">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="e2510-189">Ao vincular por meio de um sumário, é necessário usar a URL completa sem as informações de localidade.</span><span class="sxs-lookup"><span data-stu-id="e2510-189">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="e2510-190">Markdown exemplo:</span><span class="sxs-lookup"><span data-stu-id="e2510-190">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
