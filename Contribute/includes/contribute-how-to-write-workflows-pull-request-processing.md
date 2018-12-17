## <a name="pull-request-processing"></a>Processamento de solicitação de pull

A primeira seção explicou o processo de envio das alterações propostas ao agrupá-las em uma nova PR (solicitação de pull), que é adicionada à fila da PR do repositório de destino. Uma solicitação de pull habilita o modelo de colaboração do GitHub ao solicitar que o pull das alterações da sua ramificação de trabalho seja realizado e que elas sejam mescladas com outra ramificação. Na maioria dos casos, na ramificação padrão/master no repositório principal.

### <a name="validation"></a>Validação

Antes que sua solicitação de pull possa ser mesclada na respectiva ramificação de destino, talvez seja necessário que ela passe por um ou mais processos de validação de PR. Os processos de validação podem variar, dependendo do escopo das alterações propostas e das regras do repositório de destino. Depois que sua solicitação de pull for enviada, você poderá esperar a ocorrência de um ou vários dos seguintes eventos:

- **Capacidade de mesclagem**: Um teste de capacidade de mesclagem do GitHub da linha de base ocorre primeiro, para verificar se as alterações propostas no branch não estão em conflito com o branch de destino. Se a solicitação de pull indicar que o teste falhou, você deverá reconciliar o conteúdo que está causando o conflito de mesclagem antes que o processamento possa continuar.
- **CLA**: Se você estiver contribuindo para um repositório público e não for um funcionário da Microsoft, dependendo da magnitude das alterações propostas, talvez seja solicitado que você preencha um pequeno CLA (Contrato de Licença de Contribuição) na primeira vez que enviar uma solicitação de pull para esse repositório. Após a etapa de CLA ser limpa, sua solicitação de pull é processada.
- **Rotulagem**: Os rótulos são automaticamente aplicados à solicitação de pull para indicar o estado dela conforme ela passa pelo fluxo de trabalho de validação. Por exemplo, novas solicitações de pull podem receber automaticamente o rótulo “não mesclar”, indicando que a solicitação de pull ainda não concluiu as etapas de validação, análise e encerramento.
- **Validação e build**: Verificações automatizadas conferem se as alterações são aprovadas nos testes de validação. Os testes de validação podem suspender avisos ou erros, exigindo que você faça alterações em um ou mais arquivos na sua solicitação de pull antes que ela possa ser mesclada. Os resultados do teste de validação são adicionados como um comentário na sua solicitação de pull para análise e podem ser enviados para você por email.
- **Preparo**: As páginas do artigo afetadas pelas alterações são implantadas automaticamente em um ambiente de preparo para revisão após a validação e o build. As URLs de visualização aparecem em um comentário de PR.
- **Mesclagem automática**: A solicitação de pull pode ser mesclada automaticamente caso passe no teste de validação e em determinados critérios. Nesse caso, você não precisa realizar nenhuma outra ação.

### <a name="review-and-sign-off"></a>Análise e encerramento

Depois que todo o processamento de PRs for concluído, você deverá examinar os resultados (comentários de PR, URLs de visualização etc.) para determinar se alterações adicionais aos arquivos serão necessárias antes de encerrar a mesclagem. Caso sua PR tenha sido analisada por um revisor de PR, ele também poderá fornecer comentários caso haja problemas/questões pendentes para resolver antes da mesclagem.

[!INCLUDE[contribute-how-to-pull-requests-apex-automation.md](contribute-how-to-pull-requests-apex-automation.md)]

Depois que a solicitação de pull estiver sem problemas e encerrada, suas alterações serão mescladas de volta na ramificação pai e a solicitação de pull será fechada.

### <a name="publishing"></a>Publicação

A solicitação de pull tem que ser mesclada pelo revisor de PR antes que as alterações possam ser incluídas na próxima execução de publicação agendada. As solicitações de pull são normalmente analisadas/mescladas na ordem que foram enviadas. Caso sua solicitação de pull exija mesclagem para uma execução de publicação específica, você precisará trabalhar com seu revisor de PR antecipadamente para garantir que a mesclagem ocorra antes da publicação.

Depois que suas contribuições forem aprovadas e mescladas, elas serão recolhidas pelo processo de publicação de docs.microsoft.com. Dependendo da equipe que gerencia o repositório que você está contribuindo, os horários de publicação podem variar. Os artigos publicados nos seguintes caminhos são normalmente implantados às 10h30 e 15h30, aproximadamente, Hora do Pacífico, de segunda a sexta:

- https://docs.microsoft.com/azure/
- https://docs.microsoft.com/aspnet/
- https://docs.microsoft.com/dotnet/
- https://docs.microsoft.com/enterprise-mobility-security

Pode levar até 45 minutos para que os artigos apareçam online após a publicação. Depois que o artigo é publicado, é possível verificar as alterações na URL apropriada: `https://docs.microsoft.com/<path-to-your-article-without-the-md-extension>`.
