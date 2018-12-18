---
title: Referência de Markdown para docs.microsoft.com
description: O guia da plataforma Docs para Markdown.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
audience: internal,external
ms.openlocfilehash: 1023f3036e5c1facd0bcd4c31069e6faf3c95483
ms.sourcegitcommit: 21c9ac71e1abff946466cddf17a1ee97bc349ec5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245862"
---
# <a name="markdown-reference"></a>Referência de Markdown

Markdown é uma linguagem de marcação leve com sintaxe de formatação de texto sem formatação. A plataforma Docs é compatível com o padrão CommonMark para Markdown, além de algumas extensões personalizadas de Markdown projetadas para oferecer conteúdo mais avançado no docs.microsoft.com. Este artigo oferece uma referência alfabética para uso de Markdown no docs.microsoft.com.

É possível usar qualquer editor de texto para criar em Markdown. Para editores que facilitam a inserção da sintaxe padrão Markdown e das extensões personalizadas do Docs, recomendamos o [VS Code](https://code.visualstudio.com/) com o [Pacote de Criação de Docs](https://aka.ms/DocsAuthoringPack) instalado.

O Docs usa o mecanismo de Markdown Markdig. É possível testar a renderização de Markdown no Markdig em relação aos outros mecanismos em [https://babelmark.github.io/](https://babelmark.github.io/).

## <a name="alerts-note-tip-important-caution-warning"></a>Alertas (Anotação, Dica, Importante, Atenção, Aviso)

"Alertas" é uma extensão de Markdown do Docs para criar citações em bloco que renderizam no docs.microsoft.com com cores e ícones que indicam a importância do conteúdo. Os seguintes tipos de alerta tem suporte:

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

Esses alertas terão a seguinte aparência no docs.microsoft.com:

> [!NOTE]
> Informações que o usuário deverá notar mesmo se estiver fazendo uma leitura rápida.

> [!TIP]
> Informações opcionais para ajudar um usuário a ter mais êxito.

> [!IMPORTANT]
> Informações essenciais obrigatórias para o êxito do usuário.

> [!CAUTION]
> Possíveis consequências negativas de uma ação.

> [!WARNING]
> Determinadas consequências perigosas de uma ação.

## <a name="code-snippets"></a>Snippets de código

É possível inserir snippets de código nos arquivos Markdown:

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a>Títulos

O Docs é compatível com seis níveis de cabeçalhos do Markdown:

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- É necessário um espaço entre o último `#` e o texto do cabeçalho.
- Cada arquivo Markdown precisa ter somente um H1.
- O H1 precisa ser o primeiro conteúdo no arquivo após o bloco de metadados YML.
- O H2s aparece automaticamente no menu de navegação direito do arquivo publicado. Os cabeçalhos dos níveis inferiores não, então, use os H2s estrategicamente, de modo a ajudar os leitores a navegarem pelo conteúdo.
- Os cabeçalhos HTML, tais como `<h1>`, não são recomendados. Em alguns casos, eles gerarão avisos de build.
- É possível criar links para cabeçalhos individuais em um arquivo por meio de [indicadores](#bookmark-links).

## <a name="html"></a>HTML

Embora o Markdown seja compatível com HTML embutido, não é recomendável usá-lo para publicar no Docs, exceto no caso de uma lista de valores limitada causar erros de build ou avisos. <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a>Imagens

A sintaxe para incluir uma imagem é:

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

Em que `alt text` é uma breve descrição da imagem e `<folder path>` é um caminho relativo para a imagem. O texto alternativo é obrigatório para os leitores de tela para portadores de deficiências visuais. Ele também é útil se há um bug de site em que a imagem não pode ser renderizada.

As imagens devem ser armazenadas em uma pasta `/media` dentro do conjunto de documentos. Os seguintes tipos de arquivo para imagens têm suporte por padrão:

- .jpg
- .png

É possível adicionar suporte a outros tipos de imagem, adicionando-as como recursos ao arquivo docfx.json<!--add link to reference when available--> no conjunto de documentos.

## <a name="links"></a>Links

Na maioria dos casos, o Docs usa links padrão de Markdown para outros arquivos e páginas. Os tipos de links serão descritos nas próximas subseções.

> [!TIP]
> O Pacote de Criação de Docs para VS Code pode ajudar a inserir links relativos e indicadores corretamente sem o tédio de ter que adivinhar os caminhos!

> [!IMPORTANT]
> Não inclua códigos de localidade, como en-us, nos links para sites da Microsoft. Os códigos de localidade embutidos em código impedem que o conteúdo localizado seja renderizado, o que é uma experiência do cliente ruim para os usuários de outros locais e gera grandes custos de localização. Ao copiar uma URL de um navegador, o código de localidade é incluído por padrão. Então, é necessário excluí-lo manualmente ao criar o link. Por exemplo, use:
>
> `[Microsoft](https://www.microsoft.com)`
>
> E não:
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a>Links relativos para arquivos no mesmo conjunto de documentos

Um caminho relativo é o caminho para o arquivo de destino relativo ao arquivo atual. No Docs, é possível usar um caminho relativo para criar um link para outro arquivo do mesmo conjunto de documentos. A sintaxe do caminho relativo é assim:

```markdown
[link text](../../folder/filename.md)
```

Em que `../` indica um nível acima na hierarquia.

- O caminho relativo será resolvido durante o build, incluindo a remoção da extensão .md.
- Você pode usar "../" para vincular ao arquivo na pasta pai, mas esse arquivo precisa estar no mesmo conjunto de documentos. Você não pode usar "../" para vincular a um arquivo em outra pasta do conjunto de documentos.
- O Docs também é compatível com um formato especial de caminho relativo que começa com "~" (por exemplo, ~/foo/bar.md). Essa sintaxe indica um arquivo relativo à pasta raiz de um conjunto de documentos. Esse tipo de caminho também será validado e resolvido durante o build.

> [!IMPORTANT]
> Inclua a extensão de arquivo no caminho relativo. O build valida a existência do arquivo de destino desse caminho relativo. Se o caminho relativo não incluir a extensão de arquivo, provavelmente o build enviará um aviso de link desfeito. Por exemplo, use:
>
> `[link text](../../folder/filename.md)`
>
> E não:
>
> `[link text](../../folder/filename)`

### <a name="site-relative-links-to-other-files-on-docs"></a>Links relativos do site para outros arquivos no Docs

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

Não inclua a extensão de arquivo (.md). Isso vincula ao arquivo de visão geral do Linux de fora do conjunto de documentos de "artigos" do Azure.

### <a name="links-to-external-sites"></a>Links para sites externos

```markdown
[Microsoft](https://www.microsoft.com)
```

Link baseado em URL para outra página da Web (precisa incluir https://).

### <a name="bookmark-links"></a>Links com indicadores

Link com indicador para um cabeçalho em outro arquivo no mesmo repositório:

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

Link com indicador para um cabeçalho no arquivo atual:

```markdown
[Managed Disks](#managed-disks)
```

Use uma hashtag seguida pelas palavras do cabeçalho com a pontuação removida e os espaços substituídos por traços.

### <a name="explicit-anchor-links"></a>Links do tipo âncora explícitos

Os links do tipo âncora explícitos que usam a marca HTML `<a>` não são **obrigatórios ou recomendados**, exceto em páginas de hub e de aterrissagem. Use os indicadores conforme descrito acima nos arquivos Markdown em geral. Para páginas de hub e de aterrissagem, use as âncoras desta forma:

`## <a id="AnchorText"> </a>Header text` ou `## <a name="AnchorText"> </a>Header text`

Para criar links para âncoras explícitas, use a seguinte sintaxe:

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a>Links XREF (referência cruzada)

Para criar links para páginas de referências de API geradas automaticamente no conjunto de documentos atual ou em outros conjuntos de documentos, use links XREF com a UID (ID exclusiva).

> [!NOTE]
> Para referenciar páginas de referência de API em outros conjuntos de documentos, é necessário adicionar a configuração `xrefService` no arquivo `docfx.json`.
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

O UID equivale ao nome de classe e membro totalmente qualificado. Se você adicionar um * após o UID, o link representará a página de sobrecarga, e não uma API específica. Por exemplo, use `List<T>.BinarySearch*` para criar um link para a página BinarySearch Method em vez de para uma sobrecarga específica, como `List<T>.BinarySearch(T, IComparer<T>)`.

Você pode usar uma das seguintes sintaxes:

- Vincule automaticamente: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`

  O parâmetro de consulta `displayProperty` opcional produz um texto de link totalmente qualificado. Por padrão, o texto do link mostra apenas o nome do membro ou do tipo.

- Link de Markdown: `[link text](xref:UID)`
  
  Use para personalizar o texto do link exibido.

Exemplos:

- `<xref:System.String>` é renderizado como "String".
- `<xref:System.String?displayProperty=nameWithType>` é renderizado como "System.String".
- `[String class](xref:System.String)` é renderizado como "classe String".

No momento, não há uma maneira simples de localizar os UIDs. <!-- ? -->A melhor maneira de localizar o UID de uma API é exibir a origem da página da API à qual você deseja vincular e localizar o valor de ms.assetid. Os valores de sobrecarga individuais não são mostrados na origem. Estamos trabalhando para fornecer um sistema mais eficiente no futuro.

Quando o UID contém os caracteres especiais \`, \# ou \*, o valor do UID deve ser codificado em HTML como `%60`, `%23` e `%2A`, respectivamente. Às vezes, você verá parênteses codificados, mas, isso não é um requisito.

Exemplos:

- System.Threading.Tasks.Task\`1 se torna `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor se torna `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se torna `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a>Listas (Numerada, Com Marcadores, Lista de Verificação)

### <a name="numbered-list"></a>Lista numerada

Para criar uma lista numerada, é possível usar todos os 1s, que são renderizados como uma lista sequencial quando publicados. Para aumentar a legibilidade da origem, é possível aumentar as listas.

Não use letras nas listas, incluindo listas aninhadas. Elas não são renderizadas corretamente quando publicadas no Docs. As listas aninhadas usando números renderizarão como letras minúsculas quando publicadas. Por exemplo:

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

Isso será renderizado da seguinte forma:

1. Esta é
1. uma lista numerada pai
   1. e esta é
   1. uma lista numerada aninhada
1. (fim)

### <a name="bulleted-list"></a>Lista com marcadores

Para criar uma lista com marcadores, use `-` seguido de um espaço no início de cada linha:

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

Isso será renderizado da seguinte forma:

- Esta é
- uma lista com marcadores pai
  - e esta é
  - uma lista com marcadores aninhada
- Concluído!

### <a name="checklist"></a>Lista de verificação

As listas de verificação estão disponíveis para uso no docs.microsoft.com (somente) por meio de uma extensão de Markdown personalizada:

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

Esse exemplo é renderizado no docs.microsoft.com desta forma:

> [!div class="checklist"]
> * Item de lista 1
> * Item de lista 2
> * Item de lista 3

Use as listas de verificação no início ou no fim de um artigo para resumir o conteúdo "O que você aprenderá" ou "O que você aprendeu". Não adicione listas de verificação aleatórias ao longo dos seus artigos.
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a>Ação da próxima etapa

É possível usar uma extensão personalizada para adicionar um botão de ação da próxima etapa a páginas no docs.microsoft.com (somente).

A sintaxe é assim:

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

Por exemplo:

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

Isso será renderizado da seguinte forma:

> [!div class="nextstepaction"]
> [Saiba mais sobre o estilo básico](style-quick-start.md)

É possível usar qualquer link com suporte em uma ação de próxima etapa, incluindo um link de Markdown para outra página da Web. Na maioria dos casos, o link de próxima ação será um link relativo a outro arquivo no mesmo conjunto de documentos.

## <a name="section-definition"></a>Definição de seção

<!-- more info about this would be helpful! --> É possível que você precise definir uma seção. Essa sintaxe é mais usada para tabelas de códigos.
Veja o exemplo a seguir:

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

O texto de Markdown do blockquote anterior será renderizado como:
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a>Seletores

<!-- could be more clear! --> Você pode usar um seletor quando quiser se conectar a diferentes páginas do mesmo artigo. Depois, os leitores podem alternar entre essas páginas.

> [!NOTE]
> Essa extensão funciona de forma diferente entre o docs.microsoft.com e o MSDN. <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a>Seletor único

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

… será renderizada desta forma:

> [!div class="op_single_selector"]
> - [Universal do Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a>Seletor múltiplo

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

… será renderizada desta forma:

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

## <a name="tables"></a>Tabelas

A maneira mais simples de criar uma tabela em Markdown é usar barras verticais e linhas. Para criar uma tabela padrão com um cabeçalho, siga a primeira linha com uma linha tracejada:

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

Isso será renderizado da seguinte forma:

|Este é   |um simples   |cabeçalho de tabela|
|----------|-----------|------------|
|tabela     |dados       |aqui        |
|não precisa|se   |alinhar corretamente!||

Também é possível criar uma tabela sem um cabeçalho. Por exemplo, para criar uma lista com várias colunas:

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

Isso será renderizado da seguinte forma:

|   |   |
| - | - |
| Esta | tabela |
| não tem | cabeçalho |

Você pode alinhar as colunas usando dois-pontos:

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

É renderizado da seguinte forma:

|                  |
|------------------|
|    alinhado à direita:|
|: alinhado à esquerda     |
|: centralizado        :|

> [!TIP]
> A Extensão de Criação de Docs para VS Code facilita a adição de tabelas básicas de Markdown!
>
> Também é possível usar um [gerador de tabelas online](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a>mx-tdBreakAll

> [!IMPORTANT]
> Isso só funciona no site do docs.microsoft.com.

Se você criar uma tabela em Markdown, a tabela poderá se expandir para a barra de navegação direita, ficando ilegível. Você pode resolver isso facilmente permitindo que a renderização do Docs quebre a tabela quando necessário. Basta encapsular a tabela na classe personalizada `[!div class="mx-tdBreakAll"]`.

Aqui temos um exemplo de Markdown de uma tabela com três linhas que será encapsulada por um `div` com o nome de classe `mx-tdBreakAll`.

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

Ela será renderizada da seguinte forma:

> [!div class="mx-tdBreakAll"]
> |Nome|Sintaxe|Obrigatório para instalação silenciosa?|Descrição|
> |-------------|----------|---------|---------|
> |Silencioso|/quiet|Sim|Executa o instalador sem exibir interface do usuário e nem prompts.|
> |NoRestart|/norestart|Não|Suprime as tentativas de reinício. Por padrão, a interface do usuário avisará antes de reiniciar.|
> |Ajuda|/help|Não|Oferece ajuda e referência rápida. Exibe o uso correto do comando de instalação, incluindo uma lista com todas as opções e comportamentos.|

### <a name="mx-tdcol2breakall"></a>mx-tdCol2BreakAll

> [!IMPORTANT]
> Isso só funciona no site do docs.microsoft.com.

Algumas vezes, pode ser que você tenha palavras muito longas na segunda coluna de uma tabela. Para garantir que elas sejam divididas da melhor maneira, você pode aplicar a classe `mx-tdCol2BreakAll` usando a sintaxe de wrapper `div`, conforme mostrado anteriormente.

### <a name="html-tables"></a>Tabelas HTML

As tabelas HTML não são recomendadas para o docs.microsoft.com. Elas não são legíveis por humanos na origem – o que é um princípio fundamental do Markdown.

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a>Vídeos

### <a name="embedding-videos-into-a-markdown-page"></a>Inserir vídeos em uma página Markdown

No momento, o Docs é compatível com vídeos publicados em um de três locais:

- YouTube
- Channel 9
- Sistema 'One Player' da Microsoft

Você pode inserir um vídeo com a sintaxe a seguir e o Docs o renderizará.

```markdown
> [!VIDEO <embedded_video_link>]
```

Exemplo:

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

... será renderizado como:

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

E será exibido nas páginas publicadas desta forma:

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> A URL do vídeo do CH9 deve começar com `https` e terminar com `/player`. Caso contrário, a página inteira será inserida, em vez de apenas o vídeo.

### <a name="uploading-new-videos"></a>Fazendo upload de novos vídeos

O upload de todos os novos vídeos devem ser feitos usando o seguinte processo:

1. Entre no grupo **docs_video_users** no IDWEB.
1. Acesse https://aka.ms/VideoUploadRequest e preencha os detalhes do vídeo. Você precisará de (observe que nenhum destes itens será visível para o público):
    1. Um título para o vídeo.
    1. Uma lista de produtos/serviços que tenham relação com seu vídeo.
    1. A página de destino ou (se você ainda não tiver uma página) o conjunto de documentos em que o vídeo será hospedado.
    1. Um link para o arquivo MP4 do vídeo (se você não tiver um local para colocar o arquivo, coloque-o aqui temporariamente: `\\scratch2\scratch\apex`). Os arquivos MP4 precisam ter 720p ou mais.
    1. Uma descrição do vídeo.
1. Envie (salve) o item.
1. Em dois dias úteis, o upload do vídeo será concluído. O link que você precisa inserir será colocado no item de trabalho e enviado *de volta para você*.
1. Quando você tiver o link, feche o item de trabalho.
1. Em seguida, o link do vídeo poderá ser adicionado à postagem com o uso desta sintaxe:

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
