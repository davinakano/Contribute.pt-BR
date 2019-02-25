---
title: Visão geral do guia do colaborador do Microsoft Docs
description: O guia descreve como é possível contribuir com a documentação da Microsoft do site docs.microsoft.com.
author: billwagner
ms.author: wiwagn
ms.date: 02/19/2019
---

# <a name="microsoft-docs-contributor-guide-overview"></a>Visão geral do guia do colaborador do Microsoft Docs

Bem-vindo ao Guia do Colaborador do [docs.microsoft.com](https://docs.microsoft.com) (Docs)!

Vários dos conjuntos de documentação da Microsoft são de software livre e estão hospedados no GitHub. Alguns conjuntos de documentos não são totalmente de software livre, porém muitos têm repositórios voltados para o público em que você é convidado a realizar solicitações de pull. Ele simplifica e aprimora a comunicação entre os engenheiros de produto, as equipes de conteúdo e nossos clientes. Trabalhar com software livre tem diversas vantagens:

- O planejamento de repositórios em software livre permite obter comentários sobre quais documentos são mais necessários.
- A análise de repositórios em software livre permite publicar o conteúdo mais útil em nossa primeira versão.
- A atualização de repositórios em software livre facilita o aprimoramento contínuo do conteúdo.

A experiência do usuário em [docs.microsoft.com](https://docs.microsoft.com) integra fluxos de trabalho do [GitHub](https://github.com) diretamente para tornar o uso ainda mais fácil. Comece [editando o documento que você está exibindo](#quick-edits-to-existing-documents). Ou então, ajude [analisando novos tópicos](#review-open-prs) ou [crie registros de problemas de qualidade](#create-quality-issues).

> [!IMPORTANT]
> Todos os repositórios que publicam no docs.microsoft.com adotaram o [Código de Conduta de Software Livre da Microsoft](https://opensource.microsoft.com/codeofconduct/) ou o [Código de Conduta de .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obter mais informações, consulte as [Perguntas frequentes do código de conduta](https://opensource.microsoft.com/codeofconduct/faq/). Ou entre em contato com [opencode@microsoft.com](mailto:opencode@microsoft.com) ou [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) com perguntas ou comentários.<br>
>
> As correções secundárias ou esclarecimentos para a documentação e exemplos de código em repositório públicos são cobertos pelos [Termos de Uso de docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). As alterações novas ou significativas geram um comentário na solicitação de pull, pedindo o envio de um CLA (Contrato de Licença de Contribuição) online, caso você não seja um funcionário da Microsoft. Você deve preencher o formulário online antes que possamos examinar ou aceitar sua solicitação de pull.

## <a name="quick-edits-to-existing-documents"></a>Edições rápidas a documentos existentes

As edições rápidas simplificam o processo de relatar e corrigir pequenos erros e omissões em documentos. Apesar de todos os esforços, pequenos erros gramaticais e ortográficos aparecem em nossos documentos publicados. Embora você possa criar registros de problemas para relatar erros, é mais fácil e rápido criar uma solicitação de pull para corrigir o problema, quando a opção estiver disponível.

1. Algumas páginas de documentos permitem a edição do conteúdo diretamente no navegador. Se esse for o caso, um botão **Editar** como o mostrado abaixo ficará visível na página. Clicar no botão **Editar** (ou localizado equivalente) leva você ao arquivo de origem no GitHub. Caso o botão **Editar** (ícone do lápis) não apareça, isso significa que a página da documentação não aceita alterações.

   ![Localização do link de edição](./media/index/edit-article.png)

2. Em seguida, clique no ícone do lápis para editar o artigo conforme mostrado. Se o ícone de lápis está esmaecido, você precisa fazer logon na sua conta do GitHub ou criar uma conta. 

   ![Localização do ícone de lápis](./media/index/edit-icon.png)


3. Faça suas alterações no editor da Web. Clique na guia **Visualizar alterações** para verificar a formatação da alteração.

4. Após ter feito suas alterações, role até a parte inferior da página. Insira um título e uma descrição para suas alterações e clique em **Propor alteração de arquivo** conforme mostrado na figura a seguir:

   ![Propor alteração de arquivo](./media/index/submit-pull-request.png)

5. Agora que você propôs sua alteração, você precisa pedir aos proprietários do repositório para "efetuar pull" de suas alterações para o repositório. Isso é feito usando algo chamado "solicitação de pull". Quando você clicou em **Propor alteração do arquivo** na figura acima, deveria ir para uma nova página semelhante à figura a seguir:

   ![criar solicitação de pull](media/index/create-pull-request.png)

   Clique em **Criar Solicitação Pull**, insira um título (e, opcionalmente, uma descrição) para a solicitação pull e clique em **Criar Solicitação Pull** novamente.

6. É isso! Membros de equipes de conteúdo examinarão e mesclarão sua solicitação de pull. Você poderá obter alguns comentários solicitando alterações caso você tenha feito alterações mais significativas.

A interface do usuário de edição do GitHub responde às suas permissões no repositório. As imagens anteriores são precisas para colaboradores que não têm permissões de gravação para o repositório de destino. O GitHub cria automaticamente um fork para o repositório de destino em sua conta. Se você tem acesso de gravação para o repositório de destino, o GitHub cria nele um novo branch. O nome do branch tem o formato **\<GitHubId\>-patch-n** usando sua ID do GitHub e um identificador numérico para o branch do patch.

Usamos solicitações de pull para todas as alterações, até mesmo para os colaboradores que têm acesso de gravação. A maioria dos repositórios tem o branch `master` protegido, de modo que as atualizações precisam ser emitidas como solicitações de pull.

A experiência de edição no navegador é a melhor para alterações secundárias ou esporádicas. Se você fizer colaborações grandes ou usar recursos avançados do Git (como gerenciamento de branch, resolução avançada de conflitos de mesclagem), precisará [criar um fork do repositório e trabalhar localmente](how-to-write-workflows-major.md).

> [!NOTE]
> Se habilitado, você pode editar um artigo em **qualquer idioma** e, com base no tipo de edição, ocorrerá o seguinte:
> 1. qualquer alteração linguística aprovada também ajudará a melhorar nosso mecanismo de tradução automática
> 2. qualquer edição que modifique significativamente o conteúdo do artigo será tratada internamente para enviar uma alteração para o mesmo artigo em inglês, a fim de que seja localizada em todos os idiomas, se aprovada.
> Portanto, as melhorias sugeridas não afetarão positivamente apenas os artigos em seu próprio idioma, mas em todos os idiomas disponíveis.

## <a name="review-open-prs"></a>Examinar as solicitações de pull em aberto

Você pode ler novos tópicos antes de eles serem publicados, verificando as solicitações de pull em aberto atualmente. As revisões seguem o processo do [fluxo do GitHub](https://guides.github.com/introduction/flow/). Você pode ver as atualizações propostas ou novos artigos em repositórios públicos. Revise-os e adicione seus comentários. Confira qualquer um dos nossos repositórios de documentos e verifique as PRs (solicitações de pull) em aberto para áreas que lhe interessam. Os comentários da comunidade sobre atualizações propostas ajudam toda a comunidade.

## <a name="create-quality-issues"></a>Criar registros de problemas de qualidade

Nossos documentos são um trabalho contínuo em andamento. Bons registros de problemas nos ajudam a concentrar nossos esforços nas maiores prioridades para a comunidade. Quanto mais detalhes você fornecer, mais útil será o registro do problema. Diga-nos quais informações você buscou. Diga-nos quais termos de pesquisa você usou. Se você não souber como começar, diga-nos como você deseja explorar tecnologia com a qual não está familiarizado.

Muitas das páginas de documentação da Microsoft têm uma seção de **Comentários** na parte inferior onde se pode clicar para enviar **Comentários sobre o produto** ou **Comentários sobre o conteúdo** para rastrear problemas específicos daquele artigo.

Os registros de problemas iniciam a conversa sobre o que é necessário. A equipe de conteúdo responderá a esses registros de problemas com ideias sobre o que podemos adicionar e pedirá suas opiniões. Quando criarmos um rascunho, pediremos a você que [revise a solicitação de pull](#review-open-prs).

## <a name="get-more-involved"></a>Aumente seu nível de envolvimento

Outros tópicos ajudam você a começar a contribuir de modo produtivo com o Microsoft Docs. Eles explicam o trabalho com repositórios do GitHub, ferramentas de Markdown e extensões usadas na plataforma do Microsoft Docs.
