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
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2018
---
# <a name="using-links-in-documentation"></a>Usando links na documentação
Este artigo descreve como usar hiperlinks de páginas hospedadas em docs.microsoft.com. É fácil adicionar links em markdown com poucas variações de convenções. Os links direcionam os usuários para o conteúdo na mesma página, apontam para outras páginas vizinhas ou para sites e URLs externos.

O back-end do site docs.microsoft.com usa o OPS (Open Publishing System) que implementa o DFM (DocFX Flavored Markdown). O DFM é altamente compatível com GFM (GitHub Flavored Markdown), e o DFM adiciona uma funcionalidade adicional por meio de extensões de Markdown.

> [!IMPORTANT]
> Todos os links devem ser protegidos (`https` e não `http`) quando o destino tiver suporte para eles (a grande maioria tem).

## <a name="link-text"></a>Texto do link

As palavras que você inclui no texto do link devem ser amigáveis. Em outras palavras, devem ser palavras normais em português ou o título da página que o link abre.

> [!IMPORTANT]
> Não use "clique aqui". É ruim para SEO e não descreve adequadamente o destino.

**Correto:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Incorreto:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>Links de um artigo para outro

Para criar um link embutido de um artigo técnico do Docs para outro artigo técnico do Docs dentro do mesmo docset, use a seguinte sintaxe de link:

- Um artigo em um diretório é vinculado a outro artigo no mesmo diretório:

  `[link text](article-name.md)`

- Um artigo é vinculado de um subdiretório para um artigo no diretório raiz:

  `[link text](../article-name.md)`

- Um artigo no diretório raiz é vinculado a um artigo em um subdiretório:

  `[link text](./directory/article-name.md)`

- Um artigo em um subdiretório é vinculado a um artigo em outro subdiretório:

  `[link text](../directory/article-name.md)`

- Uma vinculação de artigos entre docsets (mesmo se estiverem no mesmo repositório): `[link text](./directory/article-name)`
  
## <a name="links-to-anchors"></a>Links para âncoras

Você não precisa criar âncoras. Elas são geradas automaticamente no momento da publicação para todos os títulos H2. A única coisa que você precisa fazer é criar links para as seções H2.

- Para vincular a um título no mesmo artigo:

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- Para vincular a uma âncora em outro artigo no mesmo subdiretório:

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- Para vincular a uma âncora em outro subdiretório do serviço:

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a>Links de inclusões

Como os arquivos de inclusão estão localizados em outro diretório, você deve usar caminhos relativos mais longos. Para vincular a um artigo de um arquivo de inclusão, use este formato:

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a>Links em seletores

Se você tiver seletores incorporados em uma inclusão, assim como a equipe de documentação do Azure, use a seguinte estrutura de link:

    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
    - [(Texto1 | Exemplo1 )](../articles/folder/article-name1.md)
    - [(Texto1 | Exemplo2 )](../articles/folder/article-name2.md)
    - [(Texto2 | Exemplo3 )](../articles/folder/article-name3.md)
    - [(Texto2 | Exemplo4 )](../articles/folder/article-name4.md) -->

## <a name="reference-style-links"></a>Links de estilo de referência

Você pode usar os links em estilo de referência para facilitar a leitura do conteúdo de origem. Os links em estilo de referência substituem a sintaxe do link embutido por uma sintaxe simplificada que permite mover as URLs longas para o final do artigo. Veja o exemplo do [Daring Fireball](https://daringfireball.net/projects/markdown/):

Texto embutido:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Referências de link ao final do artigo:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

Lembre-se de incluir o espaço após os dois-pontos, antes do link. Ao vincular com outros artigos técnicos, se você se esquecer de incluir o espaço, o link quebrará no artigo publicado.

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a>Links para páginas que não fazem parte do conjunto de documentação técnica

Para vincular a uma página em outra propriedade da Microsoft (como uma página de preço, uma página de SLA ou qualquer coisa que não seja um artigo de documentação), use uma URL absoluta, mas omita a localidade. O objetivo aqui é que os links funcionem no GitHub e no site renderizado:

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a>Links para sites de terceiros

A melhor experiência de usuário reduz ao máximo o envio do usuário para outro site. Portanto, os links para sites de terceiros, dos quais precisamos às vezes, devem ser baseados nestas informações:

- **Responsabilidade:** vincule ao conteúdo de terceiros quando as informações que você deseja compartilhar forem de terceiros. Por exemplo, não é papel da Microsoft informar às pessoas como usar as ferramentas para desenvolvedores do Android. Isso é responsabilidade do Google. Se precisarmos, podemos explicar como usar as ferramentas de desenvolvedor do Android *com* o Azure, mas o Google deve instruir como usar suas ferramentas.
- **Aprovação do PM**: solicite que a Microsoft aprove o conteúdo de terceiros. Ao vincular, estamos afirmando nossa confiança nesse conteúdo e nossas obrigações caso a pessoa siga as instruções.
- **Análises de atualização:** verifique se as informações de terceiros ainda estão atualizadas e corretas, se são relevantes e se o link não mudou.
- **Externo:** informe aos usuários que eles vão acessar outro site. Se o contexto não deixar isso claro, adicione uma frase de esclarecimento. Por exemplo: “Os pré-requisitos incluem as Ferramentas para Desenvolvedores do Android, que podem ser baixadas no site do Android Studio”.
- **Próximas etapas:** você pode adicionar um link para, por exemplo, um blog de MVP em uma seção de “Próximas etapas”. Mas, novamente, tenha certeza de que os usuários entenderão que estão saindo do site.
- **Jurídico:** estamos cobertos juridicamente em **Links para sites de terceiros** no rodapé dos **Termos de Uso** em todas as páginas do ms.com.

## <a name="links-to-msdn-or-technet"></a>Link para o MSDN ou o TechNet

Quando for necessário vincular ao MSDN ou ao TechNet, use o link completo para o tópico e remova a localidade de idioma "en-us" do link.

## <a name="links-to-azure-powershell-reference-content"></a>Links para conteúdo de referência do Azure PowerShell

O conteúdo de referência do Azure PowerShell passou por diversas alterações desde novembro de 2016. Use as diretrizes a seguir a fim de criar um link para esse conteúdo a partir de outros artigos no docs.microsoft.com.

Estrutura da URL:

* Para cmdlets:
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* Para tópicos conceituais:
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

A parte &lt;moniker-name&gt; é opcional. Se ela for omitida, você será direcionado à versão mais recente do conteúdo. A parte &lt;service-name&gt; é um dos exemplos mostrados nas seguintes URLs base:

- Conteúdo do Azure PowerShell (AzureRM): https://docs.microsoft.com/powershell/azure/
- Conteúdo do Azure PowerShell (ASM): https://docs.microsoft.com/powershell/azure/_servicemanagement_
- Conteúdo do Azure Active Directory (AzureAD) PowerShell: https://docs.microsoft.com/powershell/azure/_active-directory_
- Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_
- PowerShell da Proteção de Informações do Azure: https://docs.microsoft.com/powershell/azure/_aip_
- PowerShell de Trabalhos de BD Elástico do Azure: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_

Ao usar essas URLs, você será redirecionado para a versão mais recente do conteúdo. Dessa forma, você não precisa especificar o moniker de uma versão. E não haverá links para um conteúdo conceitual que precisarão ser atualizados quando a versão for alterada.

Para criar o link correto, localize no navegador a página à qual deseja vincular e copie a URL.
Depois, remova "https://docs.microsoft.com" e as informações de localidade.

Ao vincular por meio de um sumário, é necessário usar a URL completa sem as informações de localidade.

Markdown exemplo:

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
