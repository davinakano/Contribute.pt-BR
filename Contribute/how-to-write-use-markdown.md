---
title: Como usar o Markdown para escrever Docs
description: Este artigo descreve as noções básicas e informações de referência para a linguagem Markdown usada para escrever artigos do docs.microsoft.com.
ms.date: 07/13/2017
ms.openlocfilehash: 8613d525afc11caf9ec760c4f15ea44010781634
ms.sourcegitcommit: 21c9ac71e1abff946466cddf17a1ee97bc349ec5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245885"
---
# <a name="how-to-use-markdown-for-writing-docs"></a>Como usar o Markdown para escrever Docs

Os artigos do [docs.microsoft.com](http://docs.microsoft.com) são escritos em uma linguagem de marcação leve chamada [Markdown](https://daringfireball.net/projects/markdown/), que é fácil de ler e aprender. Por isso, tornou-se rapidamente um padrão do setor.

Como o conteúdo do Docs é armazenado no GitHub, ele pode usar um superconjunto de Markdown chamado [GFM (GitHub Flavored Markdown)](https://help.github.com/categories/writing-on-github/), que fornece mais funcionalidades para necessidades de formatação comuns. Além disso, o OPS (Open Publishing Services) implementa o Analisador de Markdown Markdig. O Markdig é altamente compatível com o GFM, agregando funcionalidades para habilitar recursos específicos do Docs.

* O Markdig é um processador de Markdown extensível, em conformidade com CommonMark potente e rápido para .NET.
* https://github.com/lunet-io/markdig
* Melhor suporte da comunidade
* Melhor suporte de padrões

## <a name="markdown-basics"></a>Noções básicas de markdown

### <a name="headings"></a>Títulos

Para criar um título, use uma marca de hash (#), da seguinte forma:

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

Os cabeçalhos devem ter o estilo atx, ou seja, usar 1 a 6 caracteres de hash (#) no início da linha para indicar um cabeçalho, correspondente aos cabeçalhos HTML H1 a H6. Exemplos de cabeçalhos de primeiro a quarto nível são usados acima.

**Deve** haver pelo menos um cabeçalho de primeiro nível (H1) em seu tópico, que será exibido como o título de página.

Se o cabeçalho terminar com um caractere `#`, você precisará adicionar um caractere `#` extra ao final para que o título seja renderizado corretamente. Por exemplo, `# Async Programming in F# #`.

Cabeçalhos de segundo nível geram o Sumário na página que aparece na seção "Neste artigo" abaixo do título de página.

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

### <a name="blockquotes"></a>Citações em bloco

Citações em bloco são criadas usando o caractere `>`:

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

O exemplo anterior é renderizado da seguinte forma:

> A seca já dura dez milhões de anos, e o reino dos terríveis lagartos terminou há muito tempo. Aqui no Equador, no continente que um dia seria conhecido com África, a luta pela existência chegou ao ápice da ferocidade e o vencedor ainda não está à vista. Nestas terras estéreis e áridas, somente os pequenos, os rápidos ou os fortes podem prosperar ou até mesmo esperar sobreviver.

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
1. Second instruction
1. Third instruction
```

será renderizado como:

1. Primeira instrução
2. Segunda instrução
3. Terceira instrução

Para aninhar uma lista em outra lista, recue os itens de lista filha. Por exemplo, o Markdown a seguir:

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

será renderizado como:

1. Primeira instrução
   1. Subinstrução
   2. Subinstrução
2. Segunda instrução

Observe que usamos '1.' para todas as entradas. Isso facilita a análise de comparações quando atualizações posteriores incluírem novas etapas ou removerem etapas existentes.

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

- O [recurso de encapsulamento da tabela](#table-wrapping) do Markdig, que pode ajudar com a formatação de tabelas grandes.
- [Organizar informações com tabelas](https://help.github.com/articles/organizing-information-with-tables/) do GitHub.
- O aplicativo Web [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables).
- [Folha de referências do Markdown de Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).
- [Markdown Extra de Michel Fortin](https://michelf.ca/projects/php-markdown/extra/#table).
- [Converta tabelas HTML para Markdown](https://jmalarcon.github.io/markdowntables/).

### <a name="links"></a>Links

A sintaxe do Markdown para um link embutido é composta pela parte `[link text]`, que é o texto que receberá o hiperlink, seguida pela parte `(file-name.md)`, que é a URL ou o nome do arquivo de destino do link:

 `[link text](file-name.md)`

Para saber mais sobre vinculação, confira:

- O [guia de sintaxe do Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obter detalhes sobre o suporte à vinculação de base do Markdown.
- A seção [Links](how-to-write-links.md) deste guia para obter detalhes sobre a sintaxe de vinculação adicional que o Markdig fornece.

### <a name="code-snippets"></a>Snippets de código

O Markdown é compatível com o posicionamento de snippets de código, seja embutido em uma sentença, seja como um bloco "isolado" e separado entre as sentenças. Para obter detalhes, consulte:

- [Suporte nativo do Markdown para blocos de código](https://daringfireball.net/projects/markdown/syntax#precode)
- [Suporte do GFM para isolamento de código e destaque de sintaxe](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Os blocos de código isolados representam uma maneira fácil de habilitar o destaque de sintaxe para seus snippets de código. O formato geral dos blocos de código isolados é:

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
|C# no navegador|csharp-interactive|
|Console|console|
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
|R|r|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|VSTS CLI|vstscli|
|XAML|xaml|
|XML|xml|

O nome `csharp-interactive` especifica a linguagem C#, bem como a capacidade de executar os exemplos no navegador. Esses trechos são compilados e executados em um contêiner do Docker e os resultados da execução do programa são exibidos na janela do navegador do usuário.

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
> O OPS (Open Publishing Services) implementa um Analisador de Markdown Markdig, que é altamente compatível com o GFM (GitHub Flavored Markdown). O Markdig adiciona algumas funcionalidades por meio de extensões de Markdown. Portanto, alguns artigos selecionados no Guia de Criação do OPS completo foram incluídos neste guia para referência. (Por exemplo, veja "extensões de Markdown e Markdig" e "Snippets de código" no sumário.)

Os artigos do Docs usam o GFM para a maior parte da formatação do artigo, como parágrafos, links, listas e cabeçalhos. Para uma formatação mais avançada, os artigos podem usar recursos do Markdig, como:

- Blocos de nota
- Arquivos de inclusão
- Seletores
- Vídeos incorporados
- Snippets/amostras de código

Para obter a lista completa, veja "extensões de Markdown e Markdig" e "Snippets de código" no sumário.

### <a name="note-blocks"></a>Blocos de nota

Você pode escolher entre quatro tipos de blocos de notas para chamar atenção para um conteúdo específico:

- OBSERVAÇÃO
- AVISO
- DICA
- IMPORTANTE

Em geral, os blocos de notas devem ser usados com moderação porque eles podem atrapalhar. Embora eles também deem suporte para blocos de código, imagens, listas e links, tente manter seus blocos de nota simples e diretos.

Exemplos:

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

Eles são renderizados da seguinte forma:

> [!NOTE]
> Isto é uma ANOTAÇÃO

> [!WARNING]
> Isto é um AVISO

> [!TIP]
> Isto é uma DICA

> [!IMPORTANT]
> Isto é IMPORTANTE

### <a name="include-files"></a>Arquivos de inclusão

Quando você tiver um texto ou arquivos de imagem reutilizáveis que precisem ser incluídos nos arquivos do artigo, use uma referência ao arquivo de "inclusão" por meio do recurso de inclusão de arquivo do Markdig. Esse recurso instrui o OPS a incluir o arquivo no arquivo do artigo no tempo de build, para que ele faça parte do artigo publicado. Três tipos de referências de inclusão estão disponíveis para ajudar você a reutilizar o conteúdo:

- Embutido: Reutilize um snippet de texto comum embutido dentro de outra sentença.
- Bloco: Reutilize um arquivo Markdown inteiro como um bloco aninhado dentro de uma seção de um artigo.
- Imagem: É como a inclusão de imagem padrão é implementada no Docs.

Um arquivo de inclusão embutido ou de bloco é apenas um arquivo Markdown (.md) simples. Ele pode conter qualquer Markdown válido. Todos os arquivos Markdown de inclusão devem ser colocados em um [subdiretório `/includes` comum](git-github-fundamentals.md#includes-subdirectory), na raiz do repositório. Quando o artigo é publicado, o arquivo incluído fica perfeitamente integrado.

Aqui estão os requisitos e as considerações para arquivos de inclusão:

- Use um arquivo de inclusão sempre que precisar que o mesmo texto apareça em vários artigos.
- Use uma referência de inclusão em bloco para quantidades consideráveis de conteúdo, como um ou dois parágrafos, um procedimento compartilhado ou uma seção compartilhada. Não use-os para nada menor do que uma sentença.
- As referências de inclusão não serão renderizadas na exibição do artigo renderizada do GitHub, pois elas dependem de extensões do Markdig. Elas serão renderizadas somente após a publicação.
- Verifique se todo o texto em um arquivo de inclusão está escrito em sentenças ou frases completas que não dependem do texto anterior ou seguinte no artigo que faz referência ao arquivo de inclusão. Se você ignorar essa orientação, criará uma cadeia de caracteres não traduzível no artigo que quebrará a experiência localizada.
- Não insira referências de inclusão em outros arquivos de inclusão. Não há suporte para isso.
- Coloque os arquivos de mídia em uma pasta de mídia específica para o subdiretório de inclusão, por exemplo, a pasta `<repo>`/includes/media. O diretório de mídia não deve conter imagens em sua raiz. Se o arquivo de inclusão não tiver imagens, não será necessário ter um diretório de mídia correspondente.
- Assim como ocorre com os artigos regulares, não compartilhe a mídia entre arquivos de inclusão. Use um arquivo separado com um nome exclusivo para cada artigo e arquivo de inclusão. Armazene o arquivo de mídia na pasta de mídia associada ao arquivo de inclusão.
- Não use um arquivo de inclusão como o único conteúdo de um artigo.  Os arquivos de inclusão servem como complemento ao conteúdo do restante do artigo.

Exemplo:

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a>Seletores

Use seletores em artigos técnicos ao criar vários tipos do mesmo artigo, a fim de solucionar diferenças de implementação entre tecnologias e plataformas. Normalmente, isso é mais aplicável ao nosso conteúdo de plataforma móvel para desenvolvedores. No momento, há dois tipos diferentes de seletores no Markdig, um seletor único e um seletor múltiplo.

Já que o mesmo Markdown seletor vai para cada artigo na seleção, é recomendável posicionar o seletor do artigo em um arquivo de inclusão. Em seguida, você poderá referenciar esse arquivo de inclusão em todos os artigos que usarem o mesmo seletor.

A seguir, é mostrado um seletor de exemplo:

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

Você pode ver um exemplo dos seletores em ação nos [Documentos do Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).

### <a name="code-include-references"></a>Referências de inclusão de código

O Markdig também é compatível com a inclusão avançada de código em um artigo por meio de sua extensão de snippet de código. Ela fornece renderização avançada que aproveita os recursos do GFM, como seleção de linguagem de programação e coloração de sintaxe, além de recursos incríveis como:

- Inclusão de amostras/trechos de código centralizados de um repositório externo.
- Interface do usuário com guias para mostrar várias versões de amostras de código em linguagens diferentes.

## <a name="gotchas-and-troubleshooting"></a>Armadilhas e solução de problemas

### <a name="alt-text"></a>Texto Alt

Textos Alt que contenham caracteres sublinhado não serão renderizados adequadamente. Por exemplo, em vez de usar isto:

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Insira um escape para os sublinhados desta forma:

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Apóstrofes e aspas

Se você copiar do Word para um editor de Markdown, o texto poderá conter apóstrofes ou aspas "inteligentes" (inglesas). Eles precisam ser codificados ou alterados para apóstrofos ou aspas simples. Caso contrário, quando o arquivo for publicado, poderão ocorrer erros como: Itâ€™s

Estas são as codificações para as versões "inteligentes" dessas marcas de pontuação:

- Aspas à esquerda (de abertura): `&#8220;`
- Aspas à direita (de fechamento): `&#8221;`
- Aspas simples à direita (de fechamento) ou apóstrofe: `&#8217;`
- Aspas simples à esquerda (de abertura) (raramente usadas): `&#8216;`

### <a name="angle-brackets"></a>Colchetes angulares

É comum usar colchetes angulares para denotar um espaço reservado. Ao fazer isso em um texto (não no código), é necessário codificar os colchetes angulares. Caso contrário, o Markdown entenderá que eles são uma marca HTML.

Por exemplo, codifique `<script name>` como `&lt;script name&gt;`

## <a name="see-also"></a>Confira também:

### <a name="markdown-resources"></a>Recursos do Markdown

- [Introdução a Markdown](https://daringfireball.net/projects/markdown/syntax)
- [Roteiro de Markdown do Docs](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [Noções básicas de Markdown do GitHub](https://help.github.com/articles/markdown-basics/)
- [Guia de Markdown](https://www.markdownguide.org/)
