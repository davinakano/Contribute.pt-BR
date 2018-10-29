# <a name="locale-specific-links"></a><span data-ttu-id="8e7b3-101">Links específicos do local</span><span class="sxs-lookup"><span data-stu-id="8e7b3-101">Locale-specific links</span></span>

<span data-ttu-id="8e7b3-102">Os códigos de local, como `en-us`, não devem ser incluídos em links para determinados sites da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e7b3-102">Locale codes, such as `en-us`, should not be included in links to certain Microsoft sites.</span></span> <span data-ttu-id="8e7b3-103">Se você incluir um código de local em um link de um conteúdo em inglês, ele também será incluído nos links localizados, o que gerará uma experiência ruim de localização.</span><span class="sxs-lookup"><span data-stu-id="8e7b3-103">If you include a locale code in a link in English content, it will also be included in localized links, which leads to a bad localized experience.</span></span> <span data-ttu-id="8e7b3-104">Por exemplo, se um link para conteúdo localizado em alemão incluir `en-us`, os clientes alemães serão direcionados para o artigo em inglês, mesmo que a versão em alemão esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="8e7b3-104">For example, if a link in German localized content includes `en-us`, German customers will find themselves linking to the English article, even if a German version is available.</span></span>

<span data-ttu-id="8e7b3-105">Remova os códigos de local dos links para sites da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e7b3-105">Remove locale codes from links to Microsoft sites.</span></span> <span data-ttu-id="8e7b3-106">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="8e7b3-106">The following is an example.</span></span>

<span data-ttu-id="8e7b3-107">Antes:</span><span class="sxs-lookup"><span data-stu-id="8e7b3-107">Before:</span></span>

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="8e7b3-108">Depois:</span><span class="sxs-lookup"><span data-stu-id="8e7b3-108">After:</span></span>

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="8e7b3-109">Os sites a seguir estão no escopo desta validação:</span><span class="sxs-lookup"><span data-stu-id="8e7b3-109">The following sites are in scope for this validation:</span></span>

- <span data-ttu-id="8e7b3-110">azure.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8e7b3-110">azure.microsoft.com</span></span>
- <span data-ttu-id="8e7b3-111">docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8e7b3-111">docs.microsoft.com</span></span>
- <span data-ttu-id="8e7b3-112">msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8e7b3-112">msdn.microsoft.com</span></span>
- <span data-ttu-id="8e7b3-113">technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8e7b3-113">technet.microsoft.com</span></span>