---
title: Pacote de criação de Docs para VS Code
description: Este artigo descreve o pacote de extensões do VS Code para facilitar a criação de Markdown para o docs.microsoft.com.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: d0d61db2faf88598ecd2c800fb5fbe8df8ec44f5
ms.sourcegitcommit: 7b668124f25b8ad0442937a3ad05b19a47af5970
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="docs-authoring-pack-for-vs-code"></a>Pacote de criação de Docs para VS Code

O Pacote de Criação de Docs é uma coleção de extensões do VS Code para auxiliar na criação de Markdown para o docs.microsoft.com. O pacote está [disponível no Marketplace do VS Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) e contém as seguintes extensões:

- **DocFx:** oferece uma versão prévia de Markdown específica para o docs.microsoft.com. Para obter mais informações, consulte [DocFx](https://marketplace.visualstudio.com/items?itemName=ms-docfx.DocFX).
- **markdownlint:** um linter de Markdown popular criado por David Anson para ajudar a garantir que o Markdown siga as melhores práticas. Para obter mais informações, consulte [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint).
- **Markdown de documentos:** oferece auxílio na criação de Markdown para o conteúdo do docs.microsoft.com no OPS (Open Publishing System), incluindo suporte básico a Markdown e suporte para sintaxe de Markdown personalizada no OPS. O restante deste tópico descreve a extensão Markdown do Docs.

## <a name="prerequisites-and-assumptions"></a>Pré-requisitos e suposições

Para inserir links relativos com precisão, imagens e outros conteúdos internos com a extensão Markdown do Docs, é necessário que o escopo do espaço de trabalho do VS Code esteja definido como a raiz do seu repositório OPS clonado.

Algumas das sintaxes compatíveis com a extensão, como alertas e trechos de código, são Markdown para OPS personalizado, e não serão renderizadas corretamente a menos que publicadas por meio do OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Como usar a extensão Markdown do Docs

Para acessar o menu do Markdown do Docs, digite `ALT+M`. É possível clicar ou usar as setas para cima/para baixo para selecionar a função desejada ou digitar para iniciar a filtragem e, em seguida, pressionar `ENTER` quando a função desejada estiver realçada no menu. Os itens a seguir estão disponíveis:

|Função     |Comando             |Descrição           |
|-------------|--------------------|----------------------|
|Negrito         |`formatBold`        |Formata o texto em **negrito**.|
|Itálico       |`formatItalic`      |Formata o texto em *itálico*.|
|Código         |`formatCode`        |Se uma linha ou menos for selecionada, formatará o texto como `inline code`.<br><br>Se várias linhas forem selecionadas, isso as formatará como um bloco de código isolado e permitirá que você selecione uma linguagem de programação compatível com OPS.|
|Alerta        |`insertAlert`       |Insere uma Observação, Importante, Aviso ou Dica.<br><br>Selecione Alerta no menu. Em seguida, selecione o tipo de alerta. Se anteriormente você tiver selecionado um texto, ele ficará cercado com a sintaxe do alerta selecionado. Se nenhum texto for selecionado, um novo alerta será adicionado com o texto do espaço reservado.|
|Lista numerada|`insertNumberedList` |Insere uma nova lista numerada.<br><br> Se várias linhas forem selecionadas, cada uma será um item de lista. Observe que todas as listas numeradas são mostradas no Markdown como 1s, mas são renderizadas no docs.microsoft.com como números sequenciais ou, para listas aninhadas, letras. Para criar uma lista numerada aninhada, clique em Tab de dentro da lista pai.|
|Lista com marcadores|`insertBulletedList` |Insere uma nova lista com marcadores.|
|Tabela        |`insertTable`        |Insere uma estrutura de tabela do Markdown.<br><br>Após selecionar o comando de tabela, especifique o número de colunas e de linhas no formato colunas:linhas, tal como 3:4. Observe que o número máximo de colunas que você pode especificar por meio desta extensão é 5, que é o número máximo recomendado para que haja legibilidade.|
|Link         |`selectLinkType`      |Insere um link. Ao selecionar este comando, o submenu a seguir é exibido.<br><br>`External`: link para uma página da Web por URI. Deve incluir "http" ou "https".<br>`Internal`: insira um link relativo para outro arquivo no mesmo repositório. Após selecionar esta opção, digite, na janela de comando, para filtrar arquivos por nome; em seguida, selecione o arquivo desejado. <br>`Bookmark in this file`: escolha dentre uma lista de cabeçalhos no arquivo atual para inserir um indicador devidamente formatado.<br>`Bookmark in another file`: primeiro, filtre por nome do arquivo e selecione o arquivo ao qual ele será vinculado. Em seguida, escolha o cabeçalho adequado dentro da imagem selecionada.|
|Imagem        |`insertImage`     |Digite um texto alternativo (necessário para acessibilidade) e selecione-o. Em seguida, chame esse comando para filtrar a lista de arquivos de imagem compatíveis no repositório e selecione o que você desejar. Se você não tiver selecionado o texto alternativo ao chamar esse comando, você deverá selecioná-lo antes de selecionar um arquivo de imagem.|
|Incluir      |`insertInclude`   |Encontre um arquivo a ser inserido no arquivo atual.|
|Trecho de código      |`insertSnippet`   |Encontre um trecho de código no repositório a ser inserido no arquivo atual.|
|Vídeo        |`insertVideo`     |Adicione um vídeo inserido.|
|Versão prévia      |`previewTopic`    |Visualize o tópico ativo em uma janela lado a lado usando a extensão DocFX.  Se a extensão DocFX não estiver instalada ou se estiver instalada, mas desabilitada, o tópico não será renderizado.


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

## <a name="how-to-show-the-legacy-gauntlet-toolbar"></a>Como mostrar a barra de ferramentas "Gauntlet" herdada

Os antigos funcionários do "Gauntlet" nomeado pelo código de extensão observarão que a barra de ferramentas de criação não será mais exibida na parte inferior da janela do VS Code quando a extensão Markdown do Docs estiver instalada. Isso ocorre porque a barra de ferramentas ocupou muito espaço na barra de status do VS Code e não seguiu as práticas recomendadas para experiência do usuário de extensão, por isso ela foi preterida na nova extensão. No entanto, é possível exibir a barra de ferramentas opcionalmente atualizando seu arquivo settings.json do VS Code da seguinte forma:

1. No VS Code, acesse Arquivo -> Preferências -> Configurações (`CTRL+Comma`).
1. Selecione Configurações do usuário para alterar as configurações de todos os espaços de trabalho do VS Code ou as Configurações de Espaço de Trabalho para alterá-las apenas para o espaço de trabalho atual.
1. No painel Configurações Padrão, encontre a Configuração de Extensão de Criação de Documentos e selecione o ícone de lápis ao lado da configuração desejada. Em seguida, será solicitado que você selecione `true` ou `false`. Depois de fazer sua seleção, o VS Code adicionará automaticamente o valor ao arquivo settings.json e você deverá recarregar a janela para que as alterações entrem em vigor.

## <a name="known-issues"></a>Problemas conhecidos

- Versão prévia do DocFX: no MacOS e no Linux, a Versão prévia do DocFX não inicia a versão prévia corretamente (a versão prévia assume, por padrão, a versão prévia do Markdown do VS Code para essas plataformas).
- Versão prévia do DocFx: em todas as plataformas, a sintaxe, como links xref (referência cruzada) para APIs, não é renderizada corretamente na versão prévia, deixando, em alguns casos, lacunas de conteúdo.
- Indicadores externos: no Linux, a lista de arquivos é exibida, mas nenhum cabeçalho é mostrado para ser selecionado.
- Inclui: no Linux, a lista de arquivos é exibida, mas nenhum link é adicionado após uma seleção ser feita.
