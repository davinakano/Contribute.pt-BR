---
title: Pacote de criação de Docs para VS Code
description: Este artigo descreve o pacote de extensões do VS Code para facilitar a criação de Markdown para o docs.microsoft.com.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.openlocfilehash: b9fedce0a73c5c4212ffd0893c745fab56677c8c
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308906"
---
# <a name="docs-authoring-pack-for-vs-code"></a>Pacote de criação de Docs para VS Code

O Pacote de Criação de Docs é uma coleção de extensões do VS Code para auxiliar na criação de Markdown para o docs.microsoft.com. O pacote está [disponível no Marketplace do VS Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) e contém as seguintes extensões:

- [markdownlint:](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) um linter de Markdown popular criado por David Anson para ajudar a garantir que o Markdown siga as melhores práticas.
- [Verificador Ortográfico de Código](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): um verificador ortográfico totalmente off-line pela Street Side Software.
- [Preview do Docs](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): usa o CSS docs.microsoft.com para uma versão prévia do Markdown mais precisa, incluindo o Markdown personalizado.
- [Markdown do Docs:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) oferece auxílio na criação de Markdown para o conteúdo do docs.microsoft.com no OPS (Open Publishing System), incluindo suporte básico a Markdown e suporte para sintaxe de Markdown personalizada no OPS. O restante deste tópico descreve a extensão Markdown do Docs.
- [Modelos de Artigos do Docs](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): permite que os usuários apliquem o conteúdo de esqueleto do Markdown a novos arquivos.

## <a name="prerequisites-and-assumptions"></a>Pré-requisitos e suposições

Para inserir links relativos com precisão, imagens e outros conteúdos internos com a extensão Markdown do Docs, é necessário que o escopo do espaço de trabalho do VS Code esteja definido como a raiz do seu repositório Open Publishing System (OPS) clonado.

Algumas das sintaxes compatíveis com a extensão, como alertas e trechos de código, são Markdown para OPS personalizado, e não serão renderizadas corretamente a menos que publicadas por meio do OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Como usar a extensão Markdown do Docs

Para acessar o menu do Markdown do Docs, digite `ALT+M`. É possível clicar ou usar as setas para cima/para baixo para selecionar a função desejada ou digitar para iniciar a filtragem e, em seguida, pressionar `ENTER` quando a função desejada estiver realçada no menu. Os itens a seguir estão disponíveis:

|Função     |Descrição           |
|-------------|----------------------|
|Versão prévia      |Visualize o tópico ativo em uma janela lado a lado usando a extensão Preview do Docs. Esta opção só está disponível se a extensão Preview do Docs estiver instalada.|
|Negrito         |Formata o texto em **negrito**.|
|Itálico       |Formata o texto em *itálico*.|
|Código         |Se uma linha ou menos for selecionada, formatará o texto como `inline code`.<br><br>Se várias linhas forem selecionadas, isso as formatará como um bloco de código isolado e permitirá que você selecione uma linguagem de programação compatível com OPS.|
|Alerta        |Insere uma Observação, Importante, Aviso ou Dica.<br><br>Selecione Alerta no menu. Em seguida, selecione o tipo de alerta. Se anteriormente você tiver selecionado um texto, ele ficará cercado com a sintaxe do alerta selecionado. Se nenhum texto for selecionado, um novo alerta será adicionado com o texto do espaço reservado.|
|Lista numerada|Insere uma nova lista numerada.<br><br> Se várias linhas forem selecionadas, cada uma será um item de lista. Observe que todas as listas numeradas são mostradas no Markdown como 1s, mas são renderizadas no docs.microsoft.com como números sequenciais ou, para listas aninhadas, letras. Para criar uma lista numerada aninhada, clique em Tab de dentro da lista pai.|
|Lista com marcadores|Insere uma nova lista com marcadores.|
|Tabela        |Insere uma estrutura de tabela do Markdown.<br><br>Após selecionar o comando de tabela, especifique o número de colunas e de linhas no formato colunas:linhas, tal como 3:4. Observe que o número máximo de colunas que você pode especificar por meio desta extensão é 5, que é o número máximo recomendado para que haja legibilidade.|
|Link para arquivo no repositório|Insere um link relativo para outro arquivo no repositório atual. Após selecionar esta opção, digite, na janela de comando, para filtrar arquivos por nome; em seguida, selecione o arquivo desejado. Se você selecionou texto anteriormente, ele se tornará o texto do link. Caso contrário, o H1 do arquivo de destino será usado como texto do link.|
|Link para página da Web    |Insere um link para uma página da Web. Depois de selecionar essa opção, cole ou digite o URI na janela de comando. `https://` é necessário. Se você selecionou texto anteriormente, ele se tornará o texto do link. Caso contrário, o URI será usado como texto do link.|
|Link para cabeçalho     |Insere um link para um marcador no arquivo atual ou outro arquivo no repositório.<br>`Bookmark in this file`: escolha dentre uma lista de cabeçalhos no arquivo atual para inserir um indicador devidamente formatado.<br>`Bookmark in another file`: primeiro, filtre por nome do arquivo e selecione o arquivo ao qual ele será vinculado. Em seguida, escolha o cabeçalho adequado dentro da imagem selecionada.|
|Imagem        |Digite um texto alternativo (necessário para acessibilidade) e selecione-o. Em seguida, chame esse comando para filtrar a lista de arquivos de imagem compatíveis no repositório e selecione o que você desejar. Se você não tiver selecionado o texto alternativo ao chamar esse comando, você deverá selecioná-lo antes de selecionar um arquivo de imagem.|
|Incluir      |Encontre um arquivo a ser inserido no arquivo atual.|
|Trecho de código      |Encontre um trecho de código no repositório a ser inserido no arquivo atual.|
|Vídeo        |Adicione um vídeo inserido.|
|Modelo     |Crie um novo arquivo e aplique um modelo de Markdown. Confira [Modelos](#how-to-use-docs-templates) abaixo para saber mais.|

## <a name="how-to-assign-keyboard-shortcuts"></a>Como atribuir atalhos de teclado

1. Digite `CTRL+K` e depois `CTRL+S` para abrir a lista Atalhos de Teclado.
1. Pesquise o comando, tal como `formatBold`, para o qual você deseja criar uma associação de teclas personalizada.
1. Clique no sinal de mais exibido ao lado do nome do comando quando você passa o mouse sobre a linha.
1. Depois que uma nova caixa de entrada estiver visível, digite o atalho de teclado desejado a ser associado a esse comando específico. Por exemplo, para usar o atalho comum para negrito, digite `ctrl+b`.
1. É uma boa ideia inserir uma cláusula `when` em sua associação de teclas para que ela não esteja visível em outros arquivos que não do Markdown. Para fazer isso, abra *keybindings.json* e insira a linha a seguir embaixo do nome do comando (adicione uma vírgula entre as linhas):
   
    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    A associação de teclas personalizada completa deverá ter esta aparência no keybindings.json:

    ```json
    // Place your key bindings in this file to overwrite the defaults
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

1. Salve keybindings.json.

Consulte [Keybindings](https://code.visualstudio.com/docs/getstarted/keybindings) (Associação de teclas) nos documentos do VS Code para obter mais informações.

## <a name="how-to-show-the-legacy-toolbar"></a>Como mostrar a barra de ferramentas herdada

Os usuários da versão de pré-lançamento da extensão observarão que a barra de ferramentas de criação não será mais exibida na parte inferior da janela do VS Code quando a extensão Markdown do Docs estiver instalada. Isso ocorre porque a barra de ferramentas ocupou muito espaço na barra de status do VS Code e não seguiu as práticas recomendadas para experiência do usuário de extensão, por isso ela foi preterida na nova extensão. No entanto, é possível exibir a barra de ferramentas opcionalmente atualizando seu arquivo settings.json do VS Code da seguinte forma:

1. No VS Code, acesse Arquivo -> Preferências -> Configurações (`CTRL+Comma`).
1. Selecione Configurações do usuário para alterar as configurações de todos os espaços de trabalho do VS Code ou as Configurações de Espaço de Trabalho para alterá-las apenas para o espaço de trabalho atual.
1. No painel Configurações Padrão, encontre a Configuração de Extensão de Criação de Documentos e selecione o ícone de lápis ao lado da configuração desejada. Em seguida, será solicitado que você selecione `true` ou `false`. Depois de fazer sua seleção, o VS Code adicionará automaticamente o valor ao arquivo settings.json e você deverá recarregar a janela para que as alterações entrem em vigor.

## <a name="how-to-use-docs-templates"></a>Como usar modelos do Docs

A extensão Modelos de Artigos do Docs permite que os escritores no VS Code extraiam um modelo de Markdown de um repositório centralizado e apliquem em um arquivo. Os modelos podem ajudar a garantir que os metadados necessários sejam incluídos nos artigos, que os padrões de conteúdo sejam seguidos e assim por diante. Os modelos são gerenciados como arquivos Markdown em um repositório público do GitHub.

### <a name="to-apply-a-template-in-vs-code"></a>Para aplicar um modelo no VS Code

1. Se você não tiver a extensão Markdown do Docs instalada, pressione F1 para abrir a paleta de comando, comece a digitar "modelo" para filtrar e clique em `Docs: Template`. Se você tiver a extensão Markdown do Docs instalada, poderá usar a paleta de comandos ou clicar em `Alt+M` para exibir o menu do QuickPick de Markdown do Docs selecionar `Template` na lista.
1. Selecione o modelo desejado na lista exibida.

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>Para adicionar seu ID do GitHub e/ou alias da Microsoft às suas configurações do VS Code

A extensão Modelos oferece suporte a três campos de metadados dinâmicos: author, ms.author e ms.date. Isso significa que, se um criador de modelo usar esses campos no cabeçalho de metadados de um modelo Markdown, eles serão preenchidos automaticamente no arquivo quando você aplicar o modelo, da seguinte maneira:

|Metadados  |Valor|
|----------|---------------|
|author    |Sua ID do GitHub, se especificada no seu arquivo de configurações do VS Code.|
|ms.author |Seu alias da Microsoft, se especificado no seu arquivo de configurações do VS Code. Se você não for funcionário da Microsoft, deixe isso não especificado.|
|ms.date   |A data atual no formato compatível com Docs, MM/DD/AAAA. Observe que a data não será atualizada automaticamente se você atualizar o arquivo subsequentemente — você deve atualizá-lo manualmente para indicar a data de atualização do artigo.|

### <a name="to-set-author-github-id-andor-msauthor-microsoft-alias"></a>Para definir o author (ID do GitHub) e/ou ms.author (alias da Microsoft)

1. No VS Code, acesse Arquivo -> Preferências -> Configurações (`CTRL+Comma`).
1. Selecione Configurações do Usuário para alterar as configurações de todos os espaços de trabalho do VS Code ou as Configurações de Espaço de Trabalho para alterá-las apenas para o espaço de trabalho atual.
1. No painel Configurações Padrão à esquerda, encontre Configuração de Extensão de Modelos de Artigos do Docs, clique no ícone de lápis ao lado da configuração desejada e, em seguida, clique em Substituir nas configurações.
1. O painel Configurações do Usuário será aberto lado a lado, com uma nova entrada na parte inferior.
1. Adicione sua ID do GitHub ou alias de email da Microsoft, conforme apropriado, e salve o arquivo.
1. Pode ser necessário fechar e reiniciar o VS Code para que as alterações entrem em vigor.
1. Agora, quando você aplicar um modelo que use campos dinâmicos, seu ID do GitHub e/ou alias da Microsoft serão preenchidos automaticamente no cabeçalho de metadados.
