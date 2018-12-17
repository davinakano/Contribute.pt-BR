---
title: Processo de contribuição para repositórios de documentos do .NET
description: Este artigo fornece uma breve introdução à contribuição com repositórios de documentos do .NET. Você aprenderá quais repositórios são usados, o processo para organizar o conteúdo e as políticas para gerenciar exemplos de código e outros ativos.
ms.date: 11/07/2018
ms.openlocfilehash: 0e7199b72cf9b94d00a09fb180ffef0558c59a53
ms.sourcegitcommit: 21c9ac71e1abff946466cddf17a1ee97bc349ec5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245839"
---
# <a name="process-for-contributing-to-net-docs"></a>Processo para contribuir com documentos do .NET

Nós agradecemos as contribuições da comunidade em nossos documentos. A lista a seguir mostra algumas regras gerais que você precisa ter em mente ao contribuir com a documentação do .NET:

- **NÃO** nos surpreenda com grandes solicitações de pull. Em vez disso, registre um problema e inicie uma discussão para que possamos chegar a um consenso antes de você investir uma grande quantidade de tempo.
- **SIGA** estas instruções e as diretrizes de [tom e comunicação](dotnet-voice-tone.md).
- **USE** o arquivo de [modelo](dotnet-style-guide.md) como ponto inicial de seu trabalho.
- **CRIE** um branch separado em seu fork antes de trabalhar nos arquivos.
- **SIGA** o [fluxo de trabalho o GitHub](https://guides.github.com/introduction/flow/).
- **DIVULGUE** em seu blog e Twitter (ou onde for) suas contribuições, frequentemente!

Seguir estas diretrizes garantirá uma melhor experiência para você e para nós.

## <a name="make-a-contribution-to-net-docs"></a>Contribuir com documentos do .NET

**Etapa 1:** Ignore esta etapa no caso de alterações pequenas. Se estiver interessado em escrever novo conteúdo ou em revisar minuciosamente o conteúdo existente, registre um [problema](https://github.com/dotnet/docs/issues) descrevendo o que você deseja fazer.

O conteúdo na pasta **docs** é organizado em seções que são refletidas no Sumário. Defina onde o tópico ficará localizado no Sumário. Receba comentários sobre sua proposta.

– ou –

Você também pode escolher entre problemas existentes para os quais contribuições da comunidade são bem vindas. [Projetos para colaboradores da Comunidade do .NET](https://github.com/dotnet/docs/projects/35) lista muitos dos problemas que estão disponíveis para colaboradores da comunidade. Dependendo de seus interesses e nível de compromisso, você pode escolher entre problemas nas seguintes categorias:

- **Manutenção**. Esta categoria inclui contribuições simples, como corrigir links desfeitos ou incorretos, adicionar exemplos de código ausentes ou solucionar problemas de conteúdo limitado. Em alguns casos, esses problemas podem estar presentes em um grande número de arquivos. Nesse caso, você precisa nos informar no que gostaria de trabalhar antes de começar. Adicione um comentário ao problema e nos informe que você está trabalhando nele.

- **Atualizações de conteúdo**. Dada a enormidade do conjunto de documentos, o conteúdo fica desatualizado facilmente e precisa de revisão. Além disso, por diversos motivos, alguns conteúdos foram duplicados e até mesmo triplicados. A atualização do conteúdo envolve garantir que tópicos individuais estejam atualizados ou revisar o conteúdo sobre uma área de recurso para eliminar a duplicação e garantir que todo conteúdo exclusivo seja preservado no menor conjunto de documentação.

- **Criação de novo conteúdo**. Caso esteja interessado em criar um tópico próprio, esses problemas listam tópicos que nós já sabemos que gostaríamos de adicionar ao nosso conjunto de documentos. No entanto, informe-nos antes de começar a trabalhar em um tópico. Se tiver interesse em escrever um tópico que não está listado aqui, registre um problema.

Você também pode examinar nossa lista de [problemas em aberto](https://github.com/dotnet/docs/issues) e se voluntariar para trabalhar naqueles em que tem interesse. Nós usamos o rótulo [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) (disponível) para marcar problemas identificados para contribuição da comunidade. Normalmente, eles precisam de pouco contexto e são adequados para serem os primeiros problemas de que alguém trata. Incentivamos colaboradores experientes de nossa comunidade a ver se há problemas de seu interesse. Quando encontrar um problema, adicione um comentário a ele perguntando se está em aberto.

Depois de escolher uma tarefa na qual trabalhar, siga o guia de [introdução](get-started-setup-github.md) para criar uma conta do GitHub e configurar seu ambiente.

**Etapa 2:** Crie um fork dos repositórios `/dotnet/docs`, `dotnet/samples`, `dotnet/dotnet-api-docs`, `dotnet/roslyn-api-docs` ou `dotnet/ml-api-docs` conforme necessário e crie um branch para suas alterações.

Para alterações pequenas, confira as instruções sobre edição no GitHub na [página inicial](index.md#quick-edits-to-existing-documents) do guia para colaboradores.

**Etapa 3:** Faça as alterações nesse novo branch.

Caso de trate de um novo tópico, você pode usar este [arquivo de modelo](dotnet-style-guide.md) como ponto de partida. Ele contém as diretrizes de escrita e explica os metadados necessários para cada artigo, como as informações sobre o autor.

Navegue até a pasta que corresponde à localização no Sumário determinada para seu artigo na etapa 1. A pasta contém os arquivos Markdown dos artigos na seção. Se necessário, crie uma pasta para colocar os arquivos de seu conteúdo. O artigo principal dessa seção se chama *index.md*. Para imagens e outros recursos estáticos, crie uma subpasta chamada **media** dentro da pasta que contém seu artigo, caso ela ainda não exista. Dentro da pasta **media**, crie uma subpasta com o nome do artigo (exceto para o arquivo index). O exemplo de código deve ficar no repositório `dotnet/samples`, conforme descrito na seção sobre [exemplos](#contributing-to-samples).

Certifique-se de seguir toda a sintaxe de Markdown adequada. Para ver exemplos comuns, confira a [folha de referência de modelos e de markdown](dotnet-style-guide.md).

## <a name="example-structure"></a>Estrutura de exemplo

    docs
      /about
      /core
        /porting
          porting-overview.md
          /media
            /porting-overview
                portability_report.png

**Etapa 4:** Envie uma PR (solicitação de pull) do seu branch para o branch mestre.

> [!IMPORTANT]
> A funcionalidade de [automação de comentários](how-to-write-workflows-major.md#review-and-sign-off) não está disponível em nenhum dos repositórios de documentos do .NET no momento. Membros da equipe de documentos do .NET examinarão e mesclarão sua PR.

Normalmente, cada PR deve tratar de um problema por vez. A PR pode modificar um ou vários arquivos. Se estiver tratando de diversas correções em arquivos diferentes, use PRs separadas. Se estiver criando exemplos e atualizando o markdown, você precisará criar uma PR separada para os exemplos.

Se a PR corrigir um problema existente, adicione a palavra-chave `Fixes #Issue_Number` à mensagem de confirmação ou à descrição da PR. Dessa forma, o problema será encerrado automaticamente quando a PR for mesclada. Para obter mais informações, confira [Encerrar problemas usando mensagens de confirmação](https://help.github.com/articles/closing-issues-via-commit-messages/).

A equipe do .NET examinará sua PR e informará se forem necessárias atualizações/alterações para aprová-la.

**Etapa 5:** Faça as atualizações necessárias em seu branch conforme discutido com a equipe.

Os profissionais responsáveis pela manutenção mesclarão sua PR ao branch mestre quando os comentários tiverem sido aplicados e sua alteração for aprovada.

Nós enviamos todas as confirmações por push regularmente do branch mestre para o branch ativo e, em seguida, você poderá ver sua contribuição ativa em https://docs.microsoft.com/dotnet/. Normalmente, publicamos diariamente durante dias úteis. Atividades de manutenção podem atrasar a publicação em alguns dias.

## <a name="contributing-to-samples"></a>Contribuição com exemplos

O repositório [dotnet/samples](https://github.com/dotnet/samples) contém todo o exemplo de código que faz parte de qualquer tópico da documentação do .NET. Há vários projetos diferentes organizados em subpastas. Essas subpastas são organizadas de forma semelhante à organização dos documentos do .NET.

Nós fazemos a seguinte distinção para código que já existe em nosso repositório:

- Exemplos: os leitores podem baixar e executar os exemplos. Todos os exemplos devem ser aplicativos ou bibliotecas completas. Quando os exemplos criam uma biblioteca, eles devem incluir testes de unidade ou um aplicativo que permite que os leitores executem o código. Frequentemente, eles usam mais de uma tecnologia, recurso ou kit de ferramentas. O arquivo readme.md de cada exemplo fará referência ao artigo, para que você possa ler mais sobre os conceitos abordados em cada exemplo.
- Trechos: ilustram um conceito ou tarefa menor. Eles são compilados, mas não têm a finalidade de ser aplicativos completos. Eles devem ser executados corretamente, mas não são um aplicativo de exemplo para um cenário típico. Em vez disso, têm o objetivo de ter o menor tamanho possível para ilustrar um único conceito ou recurso. Eles não devem ter mais de uma tela de código.

Todo o código fica no repositório [dotnet/samples](https://github.com/dotnet/samples). Estamos trabalhando na criação de um modelo em que a estrutura de nossa pasta de exemplos seja correspondente à estrutura de nossa pasta de documentos. Nós adotamos os seguintes padrões:

- A pasta de *snippets* de nível superior contém trechos de exemplos pequenos, com foco específico.
- Exemplos de referência de API são colocados em uma pasta este padrão: *snippets/\<idioma>/api/\<namespace>/\<nomedaapi>*.
- Outras pastas de nível superior correspondem às pastas de nível superior no repositório de *documentos*. Por exemplo, o repositório de documentos tem uma pasta *machine-learning/tutorials* e os exemplos de tutoriais de aprendizado de máquina estão na pasta *samples/machine-learning/tutorials*.

Além disso, todos os exemplos nas pastas *core* e *standard* devem ser compilados e executados em todas as plataformas com suporte do .NET Core. Nosso sistema de build de CI build imporá isso. A pasta *framework* de nível superior contém exemplos que são compilados e validados somente no Windows.

Projetos de exemplo devem ser compilados e executados na maior gama de plataformas possível para o exemplo dado. Na prática, isso significa compilar aplicativos de console baseados em .NET Core quando possível. Exemplos específicos da Web ou de uma estrutura de interface do usuário devem adicionar essas estruturas conforme for necessário. Exemplos incluem aplicativos Web, aplicativos móveis, aplicativos do WPF ou WinForms e assim por diante.

Estamos trabalhando para ter um sistema de CI em vigor para todo o código. Quando fizer atualizações nos exemplos, certifique-se de que cada atualização faça parte de um projeto compilável. Idealmente, adicione testes para avaliar a correção dos exemplos também.

Cada exemplo completo que você criar deverá conter um arquivo *readme.md*. Este arquivo deve conter uma breve descrição do exemplo (um ou dois parágrafos). Seu *readme.md* deverá informar aos leitores o que eles aprenderão explorando esse exemplo. O arquivo *readme.md* também deve conter um link para o documento ativo no [site da documentação do .NET](https://docs.microsoft.com/dotnet/welcome). Para determinar para onde um determinado arquivo do repositório é mapeado para o site, substitua `/docs` no caminho do repositório por `http://docs.microsoft.com/dotnet`.

Seu tópico também conterá links para o exemplo. Vincule diretamente à pasta de exemplos no GitHub.

### <a name="writing-a-new-snippet-or-sample"></a>Escrever um novo snippet ou exemplo

1. Seu exemplo **deve fazer parte de um projeto compilável**. Quando possível, os projetos devem ser compilados em todas as plataformas com suporte do .NET Core. São exceções exemplos que demonstram um recurso ou uma ferramenta específica de uma plataforma.

2. Seu exemplo deve estar em conformidade com o [estilo de código CoreFX](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md) para manter a uniformidade.

    - Além disso, damos preferência ao uso de métodos `static` em vez de métodos de instância ao demonstrar algo que não exige instanciar um novo objeto.

3. Seu exemplo deve incluir o **tratamento de exceções adequado**. Ele deve tratar de todas as exceções que têm probabilidade de ser geradas no contexto do exemplo. Por exemplo, um exemplo que chama o método [Console.ReadLine](https://docs.microsoft.com/dotnet/api/system.console.readline) para recuperar a entrada do usuário deve usar o tratamento de exceções adequado quando a cadeia de caracteres de entrada é passada como um argumento para um método. De forma semelhante, se o exemplo esperar que uma chamada de método falhe, a exceção resultante deverá ser tratada. Sempre trate das exceções específicas geradas pelo método, em vez de exceções de classe base como [Exception](https://docs.microsoft.com/dotnet/api/system.exception) ou [SystemException](https://docs.microsoft.com/dotnet/api/system.systemexception).

4. Se o exemplo compilar um pacote autônomo, você deverá incluir os tempos de execução usados pelo seu sistema de build de CI, além dos tempos de execução usados pelo exemplo:
    - `win7-x64`
    - `win8-x64`
    - `win81-x64`
    - `ubuntu.16.04-x64`

Em breve, teremos um sistema de CI em vigor para compilar esses projetos.

Para criar um exemplo:

1. Registre um [problema](https://github.com/dotnet/docs/issues) ou adicione um comentário a um problema existente no qual você está trabalhando.
2. Escreva o tópico que explica os conceitos demonstrados em seu exemplo (exemplo: `docs/standard/linq/where-clause.md`).
3. Escreva o exemplo (exemplo: `WhereClause-Sample1.cs`).
4. Crie um Program.cs com um ponto de entrada principal que chama seus exemplos. Se já houver um, adicione a chamada ao exemplo:

    ```csharp
    public class Program
    {
        public void Main(string[] args)
        {
            WhereClause1.QuerySyntaxExample();

            // Add the method syntax as an example.
            WhereClause1.MethodSyntaxExample();
        }
    }
    ```

Você compila qualquer snippet ou exemplo do .NET Core usando a CLI do .NET Core, que pode ser instalada com o [SDK do .NET Core](https://www.microsoft.com/net/download). Para compilar e executar seu exemplo:

1. Vá até a pasta de exemplos e compile para verificar se há erros:

    ```console
    dotnet build
    ```
2. Execute seu exemplo:

    ```console
    dotnet run
    ```

3. Adicione um readme.md ao diretório raiz do exemplo. 

   Ele deve incluir uma breve descrição do código e direcionar as pessoas ao artigo que faz referência ao exemplo.

Exceto quando observado, todos os exemplos são compilados na linha de comando de qualquer plataforma com suporte do .NET Core. Há alguns exemplos que são específicos do Visual Studio e requerem o Visual Studio 2017 ou posterior. Além disso, alguns exemplos mostram funcionalidades específicas de uma plataforma e exigirão a plataforma específica. Outros exemplos e trechos requerem o .NET Framework e serão executados em plataformas Windows, sendo que precisarão do Pacote do Desenvolvedor da versão de destino do Framework.

## <a name="the-c-interactive-experience"></a>A experiência do C# Interativo

Todos os exemplos incluídos em um artigo usam uma [tag de linguagem](how-to-write-use-markdown.md#code-snippets) para indicar a linguagem do código-fonte. Exemplos de código curtos em C# podem usar a tag de linguagem `csharp-interactive` para especificar um exemplo em C# que é executado no navegador. (Exemplos de código embutido usam a tag `csharp-interactive`, para trechos incluídos da origem, use a tag `code-csharp-interactive`.) Esses exemplos de código exibem uma janela de código e uma janela de Saída no artigo. A janela de Saída exibe uma saída da execução do código interativo após o usuário ter executado o exemplo.

A experiência do C# Interativo muda a forma como trabalhamos como amostras. Os visitantes podem executar o exemplo para ver os resultados. Uma série de fatores ajuda a determinar se o exemplo ou o texto correspondente deve incluir informações sobre a saída.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Quando exibir a saída esperada sem executar o exemplo

- Artigos voltados para iniciantes devem fornecer a saída para que os leitores possam comparar a saída de seu trabalho com a resposta esperada.
- Os exemplos em que a saída faz parte do tópico devem exibir essa saída. Por exemplo, artigos sobre texto formatado devem mostrar o formato do texto sem executar o exemplo.
- Quando o exemplo e a saída esperada são curtos, considere mostrar o exemplo. Isso economiza tempo.
- Artigos que explicam como a cultura atual ou a cultura invariável afeta a saída devem explicar a saída esperada. O REPL (Read Evaluate Print Loop) interativo é executado em um host baseado em Linux. A cultura padrão e a cultura invariável produzem saídas diferentes em sistemas operacionais e computadores diferentes. O artigo deve explicar a saída nos sistemas Windows, Linux e Mac.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Quando excluir a saída esperada do exemplo

- Artigos em que o exemplo gera uma saída maior não devem incluí-la nos comentários. Isso esconde o código após a execução do exemplo.
- Artigos em que o exemplo demonstra um tópico, mas em que a saída não é fundamental para sua compreensão. Por exemplo, um código que executa uma consulta de LINQ para explicar uma sintaxe de consulta e exibe cada item na coleção de saída.

> [!NOTE]
> Você poderá observar que atualmente alguns dos tópicos não sequem todas as diretrizes especificadas aqui. Estamos trabalhando para ter uniformidade em todo o site. Confira a lista de [problemas em aberto](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3A%22%3Abookmark_tabs%3A+Information+Architecture%22) que estamos acompanhando tendo em vista essa meta específica.

## <a name="contributor-license-agreement"></a>Contrato de licença do colaborador

Você precisa assinar o [CLA (Contrato de Licença de Contribuição) da .NET Foundation](https://cla.dotnetfoundation.org) para que sua PR seja mesclada. Trata-se de um requisito único para projetos na .NET Foundation. Leia mais sobre o [CLA (Contrato de Licença de Contribuição)](http://en.wikipedia.org/wiki/Contributor_License_Agreement) na Wikipédia.

O contrato: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

Você não precisa assinar o contrato previamente. Você pode clonar, criar o fork e enviar a PR como de costume. Quando sua PR for criada, ela será classificada por um bot do CLA. Se a alteração for pequena (por exemplo, você corrigiu um erro de digitação), a PR receberá o rótulo `cla-not-required`. Caso contrário, ela será classificada como `cla-required`. Após você assinar a CLA, a atual solicitação de pull, bem como as posteriores, receberão o rótulo `cla-signed`.
