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
# <a name="metadata-and-markdown-template-for-net-docs"></a>Modelo de metadados e Markdown para documentos do .NET

Este modelo de dotnet/documentos contém exemplos de sintaxe de Markdown, bem como orientações para configurar os metadados.

Ao criar um arquivo de Markdown, você deve copiar o modelo incluído para um novo arquivo, preencher os metadados conforme especificado abaixo e definir o cabeçalho H1 acima como o título do artigo.

## <a name="metadata"></a>Metadados

O bloco de metadados necessário está no seguinte bloco de metadados de exemplo:

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- Você **precisa** ter um espaço entre os dois-pontos (:) e o valor de um elemento de metadados.
- Os dois-pontos em um valor (por exemplo, um título) interrompem o analisador de metadados. Nesse caso, coloque o título entre aspas duplas (por exemplo, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: aparece nos resultados do mecanismo de pesquisa resultados. O título não deve ser idêntico ao título em seu cabeçalho H1 e deve contar no máximo 60 caracteres.
- **description**: resume o conteúdo do artigo. Normalmente, é mostrado na página de resultados da pesquisa, mas não é usado para classificação na pesquisa. O tamanho deve ser de 115 a 145 caracteres, incluindo os espaços.
- **author**: o campo de autor deve contar o **nome de usuário do GitHub** do autor.
- **ms.date**: a data da última atualização significativa. Atualize em artigos existentes se você tiver revisado e atualizado o artigo inteiro. Correções pequenas, como de erros de digitação ou semelhante, não garantem uma atualização.

Outros metadados são anexados a cada artigo, mas normalmente nós aplicamos a maior parte dos valores de metadados no nível da pasta, especificado em **docfx.json**.

## <a name="basic-markdown-gfm-and-special-characters"></a>Markdown básico, GFM e caracteres especiais

Você pode aprender os princípios básicos das extensões específicas de Markdown, GitHub Flavored Markdown (GFM) e OPS nos artigos gerais sobre [Markdown](how-to-write-use-markdown.md) e [Referência de Markdown](markdown-reference.md).

O Markdown usa caracteres especiais como \*, \` e \# para formatação. Se quiser incluir um desses caracteres em seu conteúdo, você precisará aditar uma das duas medidas a seguir:

- Colocar uma barra antes do caractere especial como forma de "escape" (por exemplo, `\*` para um \*)
- Use o [Código de entidade HTML](http://www.ascii.cl/htmlcodes.htm) para o caractere (por exemplo, `&#42;` para um &#42;).

## <a name="file-names"></a>Nomes de arquivo

Os nomes de arquivo usam as seguintes regras:

* Contêm apenas letras minúsculas, números e hifens.
* Sem espaços nem caracteres de pontuação. Usar os hifens para separar palavras e números no nome do arquivo.
* Usar verbos de ação específicos, como desenvolver, comprar, compilar, solucionar problemas. Sem palavras terminando em -ndo.
* Sem palavras pequenas – não inclua um, uma, e, o, a, em, ou, etc.
* Deve estar em Markdown e usar a extensão de arquivo .md.
* Manter os nomes de arquivo razoavelmente curtos. Eles fazem parte da URL de seus artigos.

## <a name="headings"></a>Títulos

Use a capitalização com estilo de frase. Sempre coloque em maiúsculas a primeira palavra de um cabeçalho.

## <a name="text-styling"></a>Estilo do texto

*Itálico* Use para arquivos, pastas, caminhos (para itens longos, divida cada um em sua própria linha), novos termos.

**Negrito** Use para elementos da interface do usuário.

`Code` Use para código embutido, palavras-chave da linguagem, nomes de pacotes NuGet, comandos da linha de comando, nomes de coluna e tabelas de banco de dados e URLs que você não deseja que sejam clicáveis.

## <a name="links"></a>Links

Confira o artigo sobre [Links](how-to-write-links.md) para obter informações sobre âncoras, links internos, links para outros documentos, inclusões de código e links externos.

A equipe de documentos do .NET usa as seguintes convenções:

- Na maioria dos casos, usamos os links relativos e não incentivamos o uso de `~/` nos links porque links relativos são resolvidos na origem no GitHub. No entanto, sempre que criamos um link para um arquivo em um repositório independente, usamos o caractere `~/` para fornecer o caminho. Como os arquivos no repositório dependente ficam em uma localização diferente no GitHub, os links não serão resolvidos corretamente com os links relativos, independentemente de como foram escritos.
- A especificação da linguagem C# e a especificação da linguagem de Visual Basic são incluídas nos documentos do .NET incluindo a origem dos repositórios de linguagem. As origens de Markdown são gerenciadas nos repositórios [csharplang](https://github.com/dotnet/csharplang) e [vblang](https://github.com/dotnet/vblang).

Links para as especificações devem apontar para os diretórios de origem em que as especificações estão incluídas. Para C#, é **~/_csharplang/spec** e para VB, é **~/_vblang/spec**, como no exemplo a seguir:

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a>Links para APIs

O sistema de build tem algumas extensões que nos permitem criar links para APIs do .NET sem precisar usar links externos. Você pode usar uma das seguintes sintaxes:

1. Vincular automaticamente: `<xref:UID>` ou `<xref:UID?displayProperty=nameWithType>`

   O parâmetro de consulta `displayProperty` produz um texto de link totalmente qualificado. Por padrão, o texto do link mostra apenas o nome do membro ou do tipo.

2. Link de Markdown: `[link text](xref:UID)`

   Use para personalizar o texto do link exibido.

Exemplos:

- `<xref:System.String>` é renderizado como [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` é renderizado como [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` é renderizado como [classe String](https://docs.microsoft.com/dotnet/api/system.string)

Para saber mais sobre como usar essa notação, confira [Uso da referência cruzada](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).

Alguns UIDs contêm os caracteres especiais \`, \# ou \*, o valor do UID deve ser codificado em HTML como `%60`, `%23` e `%2A`, respectivamente. Às vezes, você verá parênteses codificados, mas, isso não é um requisito.

Exemplos:

- System.Threading.Tasks.Task\`1 se torna `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor se torna `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se torna `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

Você pode encontrar os UIDs dos tipos, uma lista de sobrecarga de membros ou um membro com sobrecarga particular de `https://xref.docs.microsoft.com/autocomplete`. A cadeia de caracteres de consulta `?text=*\<type-member-name>*` identifica o tipo ou o membro cujos UIDs você gostaria de ver. Por exemplo, `https://xref.docs.microsoft.com/autocomplete?text=string.format` recupera as sobrecargas de [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format). A ferramenta pesquisa pelo parâmetro de consulta `text` fornecido em qualquer parte do UID. Por exemplo, você pode pesquisar pelo nome do membro (ToString), pelo nome do membro parcial (ToStri), pelo nome e tipo do membro (Double.ToString) etc.

Se você adicionar um \* (ou `%2A`) depois do UID, o link representará a página de sobrecarga, e não uma API específica. Por exemplo, você pode usar isso quando deseja vincular à página do Método [List\<T>.BinarySearch](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) de uma maneira genérica, em vez de usar uma sobrecarga específica, como [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_). Você pode usar \* para criar um link para uma página de membro quando o membro não está sobrecarregado; com isso, você não precisa incluir a lista de parâmetros no UID.

Para vincular a uma sobrecarga de método específico, você precisa incluir o nome do tipo totalmente qualificado de cada um dos parâmetros do método. Por exemplo, \<xref:System.DateTime.ToString> é vinculado ao método [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) sem parâmetro, enquanto \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> é vinculado ao método [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).

Para vincular a um tipo genérico, como [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), você usa o caractere \` (`%60`) seguido do número de parâmetros de tipo genérico. Por exemplo, `<xref:System.Nullable%601>` vincula ao tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), enquanto `<xref:System.Func%602>` vincula ao delegado [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).

## <a name="code"></a>Código

A melhor maneira de incluir código é incluir trechos de um exemplo em funcionamento. Crie seu exemplo seguindo as instruções no artigo sobre [contribuição com o .NET](dotnet-contribute-process.md#contributing-to-samples). As regras básicas para incluir código ficam localizadas nas orientações gerais no [código](how-to-write-use-markdown.md#code-includes).

Você pode incluir o código usando a seguinte sintaxe:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* `-<language>` (*opcional*, mas *recomendado*)
  * Linguagem do snippet de código sendo referido. Para ver uma lista dos valores com suporte, confira [Linguagens com suporte](#supported-languages).

* `<name>` (*opcional*)
  * Nome do snippet de código. Não tem nenhum impacto no HTML de saída, mas pode ser usado para melhorar a legibilidade da fonte do Markdown.

* `<pathToFile>` (*obrigatório*)
  * O caminho relativo no sistema de arquivos que indica o arquivo de snippet de código a ser referenciado. Isso pode ser complicado pelos diferentes repositórios que compõem o conjunto de documentos do .NET. Es exemplos do .NET estão repositório dotnet/samples. Todos os caminhos dos snippets devem ser iniciados com `~/samples`, com o restante do caminho sendo o cainho para a origem da raiz do repositório.

* `<queryoption>` (*opcional*)
  * Usado para especificar como o código deve ser recuperado do arquivo:
    * `#`: `#{tagname}` (nome da tag) *ou* `#L{startlinenumber}-L{endlinenumber}` (intervalo de linhas).
    Nós não incentivamos o uso de números de linha porque eles são muito frágeis. O nome da tag é o modo preferencial de referenciar trechos de código. Use nomes de tag significativos. (Muitos trechos foram migrados de uma plataforma anterior e as tags têm nomes como `Snippet1`, `Snippet2`, etc. Essa prática é muito mais difícil de manter.)
    * `range`: `?range=1,3-5` um intervalo de linhas. Este exemplo inclui as linhas 1, 3, 4 e 5.

Recomendamos usar a opção de nome de tag sempre que possível. O nome da tag é o nome de uma região ou de um comentário no código no formato do `Snippettagname` presente no código-fonte. O seguinte exemplo mostra como fazer referência ao nome de tag `BasicThrow`:

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

O caminho relativo para a origem no repositório **dotnet/samples** segue o caminho `~/samples`.

E você pode ver como as tags do snippet são estruturadas [neste arquivo de origem](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs). Para obter detalhes sobre a representação do nome da marca em arquivos de origem de snippet de código por linguagem, consulte as [Diretrizes do DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

O exemplo a seguir mostra o código incluído em todas as três linguagens do .NET:

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

Incluir trechos de programas inteiros garante que todo o código passe por nosso sistema de CI (Integração Contínua). No entanto, se precisar mostrar algo que causa erros de tempo de execução ou tempo de compilação, você poderá usar blocos de código embutido.

## <a name="images"></a>Imagens

### <a name="static-image-or-animated-gif"></a>Imagem estática ou GIF animado

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a>Imagem vinculada

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a>Vídeos

Atualmente, você pode inserir vídeos do Channel 9 e do YouTube usando a seguinte sintaxe:

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

Para obter a URL correta do vídeo, selecione a guia **Inserir** abaixo do quadro de vídeo e copie a URL do elemento `<iframe>`. Por exemplo:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Para obter a URL correta do vídeo, clique com o botão direito do mouse no vídeo, selecione **Copiar Código de Inserção** e copie a URL do elemento `<iframe>`.

```markdown
> [!VIDEO <youtube_video_link>]
```

Por exemplo:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>Extensões docs.microsoft

docs.microsoft fornece algumas extensões adicionais do GitHub Flavored Markdown.

### <a name="checked-lists"></a>Listas com caixas de seleção

Há um estilo personalizado disponível para listas. Você pode renderizar listas com marcas de verificação verdes.

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

Isso será renderizado da seguinte forma:

> [!div class="checklist"]
> * Como criar um aplicativo .NET Core
> * Como adicionar uma referência ao pacote Microsoft.XmlSerializer.Generator
> * Como editar seu MyApp.csproj para adicionar dependências
> * Como adicionar uma classe e um XmlSerializer
> * Como compilar e executar o aplicativo

Você pode ver um exemplo das listas verificadas em ação nos [Documentos do .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Botões

Links de botão:

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

Isso será renderizado da seguinte forma:

> [!div class="button"]
[links de botão](dotnet-contribute.md)

Você pode ver um exemplo dos botões em ação nos [Documentos do Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="step-by-steps"></a>Instruções passo a passo

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

Você pode ver um exemplo das instruções passo a passo em ação no [Guia de C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
