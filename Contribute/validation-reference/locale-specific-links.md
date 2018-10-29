# <a name="locale-specific-links"></a>Links específicos do local

Os códigos de local, como `en-us`, não devem ser incluídos em links para determinados sites da Microsoft. Se você incluir um código de local em um link de um conteúdo em inglês, ele também será incluído nos links localizados, o que gerará uma experiência ruim de localização. Por exemplo, se um link para conteúdo localizado em alemão incluir `en-us`, os clientes alemães serão direcionados para o artigo em inglês, mesmo que a versão em alemão esteja disponível.

Remova os códigos de local dos links para sites da Microsoft. Veja o exemplo a seguir.

Antes:

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

Depois:

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

Os sites a seguir estão no escopo desta validação:

- azure.microsoft.com
- docs.microsoft.com
- msdn.microsoft.com
- technet.microsoft.com