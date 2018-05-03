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
# <a name="how-to-use-markdown-for-writing-docs"></a>Como usar o Markdown para escrever Docs

Os artigos do docs.microsoft.com são escritos em uma linguagem de marcação leve chamada [Markdown](https://daringfireball.net/projects/markdown/), que é fácil de ler e fácil de aprender. Por isso, tornou-se rapidamente um padrão do setor.

Como o conteúdo do Docs é armazenado no GitHub, ele pode usar um superconjunto de Markdown chamado [GFM (GitHub Flavored Markdown)](https://help.github.com/categories/writing-on-github/), que fornece mais funcionalidades para necessidades de formatação comuns. Além disso, o OPS (Open Publishing Services) implementa o DFM (DocFX Flavored Markdown). O DFM é altamente compatível com o GFM (GitHub Flavored Markdown), agregando funcionalidades para habilitar recursos específicos do Docs.

## <a name="markdown-basics"></a>Noções básicas de markdown

### <a name="headings"></a>Títulos

Para criar um título, use uma marca de hash (#), da seguinte forma:

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a>Texto em negrito e em itálico

Para formatar o texto como **negrito**, coloque dois asteriscos de cada lado do texto:

```markdown
    This text is **bold**.
```

Para formatar o texto como *itálico*, coloque um único asterisco de cada lado do texto:

```markdown
    This text is *italic*.
```

Para formatar o texto como ***negrito e itálico***, coloque três asteriscos de cada lado do texto:

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a>Listas

#### <a name="unordered-list"></a>Lista não ordenada

Para formatar uma lista não ordenada/com marcador, use asteriscos ou traços. Por exemplo, o Markdown a seguir:

```markdown
- List item 1
- List item 2
- List item 3
```

será renderizado como:

- Item de lista 1
- Item de lista 2
- Item de lista 3

Para aninhar uma lista em outra lista, recue os itens de lista filha. Por exemplo, o Markdown a seguir:

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

será renderizado como:

- Item de lista 1
  - Item de lista A
  - Item de lista B
- Item de lista 2

#### <a name="ordered-list"></a>Lista ordenada

Para formatar uma lista ordenada/gradual, use números correspondentes. Por exemplo, o Markdown a seguir:

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

será renderizado como:

1. Primeira instrução
2. Segunda instrução
3. Terceira instrução

Para aninhar uma lista em outra lista, recue os itens de lista filha. Por exemplo, o Markdown a seguir:

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

será renderizado como:

1. Primeira instrução
    1. Subinstrução
    2. Subinstrução
2. Segunda instrução

### <a name="tables"></a>Tabelas

As tabelas não fazem parte da especificação principal do Markdown, mas são compatíveis com o GFM. Você pode criar tabelas usando os caracteres barra vertical (|) e hífen (-). Os hifens criam o cabeçalho de cada coluna e as barras verticais separam cada coluna. Inclua uma linha em branco antes da sua tabela para que a renderização ocorra corretamente.

Por exemplo, o Markdown a seguir:

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

será renderizado como:

| Diversão                  | Com                 | Tabelas          |
| :------------------- | -------------------: |:---------------:|
| coluna alinhada à esquerda  | coluna alinhada à direita | coluna centralizada |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |

Para saber mais sobre como criar tabelas, consulte:

- O [recurso de disposição da tabela](#table-wrapping) do DFM, que pode ajudar com a formatação de tabelas grandes
- [Organizar informações com tabelas](https://help.github.com/articles/organizing-information-with-tables/) do GitHub
- O aplicativo Web [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)
- [Markdown Cheatsheet de Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)
- [Markdown Extra de Michel Fortin](https://michelf.ca/projects/php-markdown/extra/#table)
- [Converta tabelas HTML para Markdown](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a>Links

A sintaxe do Markdown para um link embutido é composta pela parte `[link text]`, que é o texto que receberá o hiperlink, seguida pela parte `(file-name.md)`, que é a URL ou o nome do arquivo de destino do link:

 `[link text](file-name.md)`

Para saber mais sobre vinculação, confira:

- O [guia de sintaxe do Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obter detalhes sobre o suporte à vinculação de base do Markdown.
- A seção [Links](how-to-write-links.md) deste guia para obter detalhes sobre a sintaxe de vinculação adicional que o DFM fornece.

### <a name="code-snippets"></a>Trechos de código

O Markdown é compatível com o posicionamento de trechos de código, seja embutido em uma sentença, seja como um bloco "isolado" e separado entre as sentenças. Para obter detalhes, consulte:

- [Suporte nativo do Markdown para blocos de código](https://daringfireball.net/projects/markdown/syntax#precode)
- [Suporte do GFM para isolamento de código e destaque de sintaxe](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Os blocos de código isolados representam uma maneira fácil de habilitar o destaque de sintaxe para seus trechos de código. O formato geral dos blocos de código isolados é:

    ```alias
    ...
    your code goes in here
    ...
    ```

O alias após os três caracteres de acento grave (`) iniciais define o destaque de sintaxe a ser usado. Veja a seguir uma lista de linguagens de programação normalmente usadas no conteúdo do Docs e no rótulo correspondente:

Essas linguagens têm o suporte de nome amigável e a maioria tem realce de linguagem.

|Nome|Rótulo de Markdown|
|-----|-------|
|Console do .NET|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|AzCopy|azcopy|
|CLI do Azure|azurecli|
|Azure PowerShell|azurepowershell|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|CSHTML|cshtml|
|DAX|dax|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|Power Apps Formula|powerappsfl|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|VSTS CLI|vstscli|
|XAML|xaml|
|XML|xml|

#### <a name="example-c"></a>Exemplo: C\#

__Markdown__

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

__Renderização__

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

#### <a name="example-sql"></a>Exemplo: SQL

__Markdown__

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

__Renderização__

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a>Extensões de Markdown personalizada do OPS

> [!NOTE]
> O OPS (Open Publishing Services) implementa o DFM (DocFX Flavored Markdown), que é altamente compatível com o GFM (GitHub Flavored Markdown). O DFM adiciona algumas funcionalidades por meio de extensões de Markdown. Portanto, alguns artigos selecionados no Guia de Criação do OPS completo foram incluídos neste guia para referência. (Por exemplo, consulte "DFM e extensões de Markdown" e "Trechos de código" no sumário.)

Os artigos do Docs usam o GFM para a maior parte da formatação do artigo, como parágrafos, links, listas e cabeçalhos. Para uma formatação mais avançada, os artigos podem usar recursos de DFM, como:

- Blocos de nota
- Inclusões
- Seletores
- Vídeos incorporados
- Trechos/amostras de código

Para obter a lista completa, consulte "DFM e extensões de Markdown" e "Trechos de código" no sumário.

### <a name="note-blocks"></a>Blocos de nota

Você pode escolher entre quatro tipos de blocos de notas para chamar atenção para um conteúdo específico:

- OBSERVAÇÃO
- AVISO
- DICA
- IMPORTANTE

Em geral, os blocos de notas devem ser usados com moderação porque eles podem atrapalhar. Embora eles também deem suporte para blocos de código, imagens, listas e links, tente manter seus blocos de nota simples e diretos.

### <a name="includes"></a>Inclusões

Quando você tiver um texto ou arquivos de imagem reutilizáveis que precisem ser incluídos nos arquivos do artigo, use uma referência ao arquivo de "inclusão" por meio do recurso de inclusão de arquivo do DFM. Esse recurso instrui o OPS a incluir o arquivo no arquivo do artigo no tempo de build, para que ele faça parte do artigo publicado. Três tipos de inclusões estão disponíveis para ajudá-lo a reutilizar o conteúdo:

- Embutido: reutilize um trecho de texto comum embutido dentro de outra frase.
- Bloco: reutilize um arquivo Markdown inteiro como um bloco aninhado dentro de uma seção de um artigo.
- Imagem: é como a inclusão de imagem padrão é implementada no Docs.

A inclusão de um embutido ou de um bloco é apenas um arquivo Markdown (.md) simples. Ele pode conter qualquer Markdown válido. Todos os arquivos Markdown de inclusão devem ser colocados em um [subdiretório `/includes` comum](git-github-fundamentals.md#includes-subdirectory), na raiz do repositório. Quando o artigo é publicado, o arquivo incluído fica perfeitamente integrado.

Aqui estão os requisitos e as considerações para inclusões:

- Use inclusões sempre que precisar que o mesmo texto apareça em vários artigos.
- Use inclusões em bloco para quantidades consideráveis de conteúdo, como um ou dois parágrafos, um procedimento compartilhado ou uma seção compartilhada. Não use-os para nada menor do que uma sentença.
- As inclusões não serão renderizadas no modo de exibição renderizado do GitHub do seu artigo, pois elas dependem de extensões DFM. Elas serão renderizadas somente após a publicação.
- Verifique se todo o texto em uma inclusão está escrito em sentenças ou frases completas que não dependem do texto anterior ou seguinte no artigo que faz referência à inclusão. Se você ignorar essa orientação, criará uma cadeia de caracteres não traduzível no artigo que quebrará a experiência localizada.
- Não incorpore inclusões dentro de outras inclusões. Não há suporte para isso.
- Coloque os arquivos de mídia em uma pasta de mídia específica para o subdiretório de inclusão, por exemplo, a pasta `<repo>`/includes/media. O diretório de mídia não deve conter imagens em sua raiz. Se a inclusão não tiver imagens, não será necessário ter um diretório de mídia correspondente.
- Assim como ocorre com os artigos regulares, não compartilhe a mídia entre arquivos de inclusão. Use um arquivo separado com um nome exclusivo para cada inclusão e artigo. Armazene o arquivo de mídia na pasta de mídia associada à inclusão.
- Não use uma inclusão como único conteúdo de um artigo.  As inclusões servem como complemento ao conteúdo do restante do artigo.

### <a name="selectors"></a>Seletores

Use seletores em artigos técnicos ao criar vários tipos do mesmo artigo, a fim de solucionar diferenças de implementação entre tecnologias e plataformas. Normalmente, isso é mais aplicável ao nosso conteúdo de plataforma móvel para desenvolvedores. No momento, há dois tipos diferentes de seletores no DFM, um seletor único e um seletor múltiplo.

Como o mesmo Markdown seletor vai para cada artigo na seleção, recomendamos posicionar o seletor do artigo em uma inclusão. Em seguida, você poderá referenciar essa inclusão em todos os artigos que usarem o mesmo seletor.

### <a name="code-snippets"></a>Trechos de código

O DFM também é compatível com a inclusão avançada de código em um artigo por meio de sua extensão de trecho de código. Ela fornece renderização avançada que aproveita os recursos do GFM, como seleção de linguagem de programação e coloração de sintaxe, além de recursos incríveis como:

- Inclusão de amostras/trechos de código centralizados de um repositório externo.
- Interface do usuário com guias para mostrar várias versões de amostras de código em linguagens diferentes.

## <a name="gotchas-and-troubleshooting"></a>Armadilhas e solução de problemas

### <a name="alt-text"></a>Texto Alt

Textos Alt que contenham caracteres sublinhado não serão renderizados adequadamente. Por exemplo, em vez de usar isto:

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Insira um escape para os sublinhados desta forma:

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Apóstrofes e aspas

Se você copiar do Word para um editor de Markdown, o texto poderá conter apóstrofes ou aspas "inteligentes" (inglesas). Eles precisam ser codificados ou alterados para apóstrofos ou aspas simples. Caso contrário, quando o arquivo for publicado poderão ocorrer erros como: Itâ€™s

Estas são as codificações para as versões "inteligentes" dessas marcas de pontuação:

- Aspas à esquerda (de abertura): `&#8220;`
- Aspas à direita (de fechamento): `&#8221;`
- Aspas simples à direita (de fechamento) ou apóstrofe: `&#8217;`
- Aspas simples à esquerda (de abertura) (raramente usadas): `&#8216;`

### <a name="angle-brackets"></a>Colchetes angulares

Se você usar colchetes angulares no texto (não no código) no arquivo, por exemplo, para indicar um espaço reservado, será necessário codificar manualmente os colchetes angulares. Caso contrário, o Markdown entenderá que eles são uma marca HTML.

Por exemplo, codifique `<script name>` como `&lt;script name&gt;`

## <a name="see-also"></a>Consulte também

### <a name="markdown-resources"></a>Recursos do Markdown

- [Introdução a Markdown](https://daringfireball.net/projects/markdown/syntax)
- [Roteiro de Markdown do Docs](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [Noções básicas de Markdown do GitHub](https://help.github.com/articles/markdown-basics/)