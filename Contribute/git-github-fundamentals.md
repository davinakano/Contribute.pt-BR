---
title: Conceitos básicos do Git e do GitHub para Documentação
description: Este artigo explica uma visão geral do Git, do repositório do GitHub e como o conteúdo é organizado, além de convenções de nomenclatura usadas para docs.microsoft.com.
ms.date: 06/30/2017
ms.openlocfilehash: 05c758845007f859382014166e88fd9614cdb873
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805690"
---
# <a name="git-and-github-essentials-for-docs"></a>Conceitos básicos do Git e do GitHub para o Docs

## <a name="overview"></a>Visão geral

Como colaborador do conteúdo do Docs, você interagirá com várias ferramentas e processos. Você trabalhará em paralelo com outros colaboradores no mesmo projeto, possivelmente com o mesmo conteúdo exato e até mesmo simultaneamente. Isso tudo é possibilitado por meio do Git e do software GitHub.

O Git é um sistema de controle de versão de código-fonte aberto. Ele facilita esse tipo de colaboração no projeto por meio do *controle de versão distribuído* de arquivos que residem em *repositórios*. Em essência, o Git possibilita a integração de fluxos de trabalho realizados por vários colaboradores com o passar do tempo, para um determinado repositório.

O GitHub é um serviço de hospedagem na Web para repositórios git, como os usados para armazenar conteúdo do [docs.microsoft.com](https://docs.microsoft.com). Para qualquer projeto, o GitHub hospeda o repositório principal, do qual os colaboradores podem fazer cópias para seus próprios trabalhos.

## <a name="git"></a>Git

Se estiver familiarizado com sistemas de controle de versão centralizados (como Team Foundation Server, SharePoint ou Visual SourceSafe), você observará que o Git tem um fluxo de trabalho de contribuição e uma terminologia exclusivos para dar suporte ao modelo distribuído. Por exemplo, não há um bloqueio de arquivo normalmente associado a operações de check-out/check-in. Na verdade, o Git se preocupa com alterações em um nível ainda maior, comparando arquivos byte por byte.

O Git também usa uma estrutura em camadas para armazenar e gerenciar o conteúdo de um projeto:

- *Repositório*: também conhecido como *repo*, é a maior unidade de armazenamento. Um repositório contém um ou mais branches.
- *Branch*: uma unidade de armazenamento que contém os arquivos e as pastas que compõem o conjunto de conteúdo de um projeto. Os branches separam fluxos de trabalho (normalmente conhecidos como versões). As contribuições sempre são feitas para um branch específico e estão no escopo do mesmo. Todos os repositórios contêm um branch padrão (normalmente chamado “mestre”) e um ou mais branches que serão mesclados novamente no branch mestre. O branch mestre funciona como a versão atual e "única fonte de verdade" para o projeto. Ele é o pai e todos os outros branches no repositório são criados dele.

Os colaboradores interagem com o Git para atualizar e manipular repositórios nos níveis local e do GitHub:

- Localmente, por meio de ferramentas como o console Git Bash, que dá suporte a comandos do Git para gerenciamento de repositórios locais e comunicação com os repositórios do GitHub.
- Por meio do site [www.github.com](https://www.github.com), que integra o Git para gerenciar a reconciliação de contribuições que retornam ao repositório principal.

## <a name="github"></a>GitHub

> [!NOTE]
> Embora a orientação do Docs seja baseada no uso do GitHub, algumas equipes usam o Visual Studio Team Services para hospedar repositórios do Git. O cliente Team Explorer para Visual Studio fornece uma GUI para interagir com os repositórios do Team Services, que é uma alternativa ao uso de comandos do Git por meio de uma linha de comando.
> </br>
> Além disso, muitas das diretrizes a seguir foram desenvolvidas como práticas recomendadas após anos de experiência em hospedagem de conteúdo do serviço do Azure no GitHub. Elas podem ser necessárias em alguns repositórios do Docs.

Todos os fluxos de trabalho começam e terminam no nível do GitHub, no qual o repositório principal de qualquer projeto do Docs é armazenado. As cópias que os colaboradores criam para uso próprio são distribuídas entre vários computadores. Essas cópias são eventualmente reconciliadas novamente no repositório principal do projeto no GitHub.

### <a name="directory-organization"></a>Organização de diretório

Conforme mencionado antes, o branch padrão/mestre de um projeto funciona como a versão atual do conteúdo do projeto. O conteúdo no branch mestre (e nos branches criados dele) é alinhado sem muita rigidez com a organização dos artigos nas páginas do Docs correspondentes. Os subdiretórios são usados para separação de conteúdos parecidos (como serviços), conteúdo de mídia (como arquivos de imagem) e arquivos de "inclusão", que permitem a reutilização de conteúdo.

Normalmente, é possível encontrar um diretório `articles` principal fora da raiz do repositório. O diretório de artigos contém um conjunto de subdiretórios. Os artigos nos subdiretórios são formatados como arquivos Markdown que usam a extensão *.md*. Alguns repositórios com suporte a vários serviços usam um subdiretório `/articles` genérico, como o repositório [Azure-Docs](https://github.com/MicrosoftDocs/Azure-Docs). Outros podem usar um nome específico do serviço, assim como o repositório [IntuneDocs](https://github.com/MicrosoftDocs/IntuneDocs), que usa `/IntuneDocs`.

Na raiz deste diretório, você pode encontrar artigos gerais relacionados ao serviço ou produto geral. E, normalmente, é possível encontrar outra série de subdiretórios que correspondem aos recursos/serviços ou cenários comuns. Por exemplo, os artigos sobre "máquina virtual" do Azure estão no subdiretório `/virtual-machines` e os artigos sobre "entender e explorar" do Intune estão no subdiretório `/understand-explore`.

### <a name="media-subdirectory"></a>Subdiretório de mídia

Cada diretório de artigo contém um subdiretório `/media` para os arquivos de mídia correspondentes. Os arquivos de mídia contêm as imagens usadas pelos artigos que têm referências de imagem.

### <a name="includes-subdirectory"></a>Inclui subdiretório

Sempre que houver conteúdo reutilizável compartilhado entre dois ou mais artigos, ele será colocado em um subdiretório `/includes` fora do diretório `articles` principal. Em um arquivo Markdown que use o arquivo de inclusão, uma extensão de Markdown "include" correspondente será colocada no local em que o arquivo de inclusão deve ser referenciado.

Consulte [Como usar o Markdown: inclusões](how-to-write-use-markdown.md#includes) para obter orientação adicional.

### <a name="markdown-file-template"></a>Modelo de arquivo Markdown

Para sua conveniência, o diretório raiz de cada repositório normalmente contém um arquivo de modelo de Markdown chamado `template.md`. Você poderá usar esse arquivo de modelo como um “arquivo inicial” se precisar criar um novo artigo para ser enviado ao repositório. O arquivo contém:

- O **cabeçalho de metadados** na parte superior do arquivo, delimitado por duas linhas de três hifens. Ele contém as várias marcas usadas para rastrear informações relacionadas ao artigo. Os metadados do artigo habilitam algumas funcionalidades, como atribuição de autor, atribuição de colaborador, trilhas e descrições do artigo. Ele também inclui otimizações de SEO e processos de relatórios que a Microsoft usa para avaliar o desempenho do conteúdo. Portanto, os metadados são importantes!
- A **seção de metadados** que descreve as várias marcas e valores de metadados. Se não tiver certeza dos valores a serem usados para a seção de metadados, deixe-os em branco ou comente com uma hashtag à esquerda (#), e eles serão revisados/preenchidos pelo revisor da solicitação de pull do repositório.
- Vários **exemplos de uso de Markdown** para formatar os elementos de um artigo.
- **Instruções gerais sobre o uso de extensões de Markdown**, que podem ser usadas para vários tipos de alertas.
- Exemplos de **incorporação de vídeo** usando um iframe.
- **Instruções gerais sobre o uso de extensões do docs.microsoft.com**, que podem ser usadas para controles especiais, como botões e seletores.

## <a name="pull-requests"></a>Solicitações Pull

Uma *solicitação de pull* é uma maneira fácil para um colaborador propor um conjunto de alterações que serão aplicadas ao branch padrão. As alterações (também conhecidas como *confirmações*) são armazenadas no branch de um colaborador, permitindo que o GitHub modele primeiro o impacto da *mesclagem* deles no branch padrão. Uma solicitação de pull também serve como um mecanismo para fornecer ao colaborador comentários de um processo de build/validação, do revisor da solicitação de pull, a fim de resolver possíveis problemas ou perguntas antes de mesclar as alterações no branch padrão.

Há duas maneiras de contribuir por solicitação de pull, dependendo do tamanho das alterações que você deseja propor. Abordaremos isso detalhadamente mais adiante na seção [Fluxo de trabalho do GitHub](how-to-write-workflows-major.md) deste guia.

<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
<!---- NOTE: these links are saved for future use in another/new article; no longer used above in this article --->
[Visual-Studio-Page]:(https://docs.microsoft.com/en-us/visualstudio/index)
[Visual-Studio-Repo-Internal]:(https://github.com/Microsoft/vsdocs)
[Visual-Studio-Repo-External]:(https://github.com/Microsoft/visualstudio-docs)
[Visual-Studio-SO]: (https://stackoverflow.com/search?q=Visual+Studio+2017)
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp
[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: https://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: https://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: https://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: https://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: https://stackoverflow.com/tags
[Forum-SO-Intune]: https://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: https://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: https://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: https://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/
