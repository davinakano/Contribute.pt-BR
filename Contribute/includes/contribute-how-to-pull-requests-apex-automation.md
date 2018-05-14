A automação de comentário permite que os usuários de nível de leitura (usuários que não têm permissões de gravação em um repositório) executem uma ação de nível de gravação, atribuindo o rótulo apropriado a uma solicitação de pull. Se você estiver trabalhando em um repositório no qual automação de comentário tenha sido implementada, use os comentários de hashtag listados na tabela a seguir para atribuir rótulos, alterar rótulos ou fechar uma solicitação de pull. Os funcionários da Microsoft também serão notificados por email para revisão e aprovação das PRs de repositório público, sempre que forem propostas alterações em artigos de sua autoria.


| Comentário de hashtag | O que ele faz | Disponibilidade de repositório |
| --- | --- | --- |
| #sign-off |Quando o autor de um artigo digitar o comentário **#sign-off** no fluxo de comentários, o rótulo **ready-to-merge** será atribuído. Esse rótulo permite que os revisores no repositório saibam quando uma solicitação de pull está pronta para revisão/mesclagem. |Público e privado |
| #sign-off |Se um colaborador que *não* seja o autor listado tentar aprovar uma solicitação de pull pública usando o comentário **#sign-off**, uma mensagem será escrita na solicitação de pull indicando que somente o autor pode atribuir o rótulo. |Público |
| #hold-off |Os autores poderão digitar **#hold-off** em um comentário de PR para remover o rótulo **ready-to-merge** caso mudem de ideia ou cometam algum erro. No repositório privado, isso atribui o rótulo **do-not-merge**. |Público e privado |
| #please-close |Os autores poderão digitar **#please-close** no fluxo de comentário para fechar a solicitação de pull caso decidam não mesclar as alterações. |Público |
