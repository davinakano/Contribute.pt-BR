# <a name="tabbed-conceptual"></a><span data-ttu-id="0ba0e-101">Conceitual com guias</span><span class="sxs-lookup"><span data-stu-id="0ba0e-101">Tabbed conceptual</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ba0e-102">A sintaxe conceitual com guias foi preterida e novas guias não devem ser adicionadas.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-102">The tabbed conceptual syntax has been deprecated and new tabs should not be added.</span></span> <span data-ttu-id="0ba0e-103">As validações descritas neste artigo se aplicam aos conjuntos de conteúdo aprovados para usar o conceitual com guias até a funcionalidade de substituição ser disponibilizada.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-103">The validations described in this article apply to content sets that have been approved to use tabbed conceptual until replacement functionality is available.</span></span>

## <a name="tab-syntax"></a><span data-ttu-id="0ba0e-104">Sintaxe de guias</span><span class="sxs-lookup"><span data-stu-id="0ba0e-104">Tab syntax</span></span>

<span data-ttu-id="0ba0e-105">A sintaxe das guias é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="0ba0e-105">The syntax for tabs is as follows:</span></span>

<span data-ttu-id="0ba0e-106">Guia de nível único:</span><span class="sxs-lookup"><span data-stu-id="0ba0e-106">Single level tab:</span></span>

`# [Tab Display Name](#tab/tab-id)`

<span data-ttu-id="0ba0e-107">Guia dependente opcional:</span><span class="sxs-lookup"><span data-stu-id="0ba0e-107">Optional dependent tab:</span></span>

`# [Tab Display Name](#tab/tab-id/tab-condition)`

<span data-ttu-id="0ba0e-108">Exemplo de uma seção de guias de nível único com duas guias e o terminador do grupo de guias (---):</span><span class="sxs-lookup"><span data-stu-id="0ba0e-108">Example of a single-level tab section with two tabs and the tab group terminator (---):</span></span>

```markdown
# [Linux](#tab/linux)

Content for Linux...

# [Windows](#tab/windows)

Content for Windows...

---
```

<span data-ttu-id="0ba0e-109">Como opção, as guias podem conter guias secundárias ou de dependência.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-109">Tabs can optionally contain secondary tabs, or dependency tabs.</span></span> <span data-ttu-id="0ba0e-110">Dessa maneira, as guias ficam dependentes da seleção em outro conjunto de guias.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-110">This makes tabs dependent on the selection in another set of tabs.</span></span> <span data-ttu-id="0ba0e-111">Aqui está um exemplo:</span><span class="sxs-lookup"><span data-stu-id="0ba0e-111">Here's an example:</span></span>

```markdown
# [Azure CLI](#tab/azure-cli/linux)

Azure CLI content for Linux...

# [Azure CLI](#tab/azure-cli/windows)

Azure CLI content for Windows...

# [PowerShell](#tab/azure-powershell/linux)

PowerShell content for Linux...

# [PowerShell](#tab/azure-powershell/windows)

PowerShell content for Windows...

---
```

<span data-ttu-id="0ba0e-112">As validações a seguir se aplicam à sintaxe de guias:</span><span class="sxs-lookup"><span data-stu-id="0ba0e-112">The following validations apply to tab syntax:</span></span>

- <span data-ttu-id="0ba0e-113">A sintaxe da guia precisa estar correta.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-113">Tab syntax must be correct.</span></span>
- <span data-ttu-id="0ba0e-114">As guias dependentes precisam ter sido definidas em um grupo de guias anterior.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-114">Dependent tabs must have been defined in a previous tab group.</span></span>
- <span data-ttu-id="0ba0e-115">Somente um nível de dependência é permitido.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-115">Only one level of dependency is allowed.</span></span>
- <span data-ttu-id="0ba0e-116">Não é permitido menos de duas guias.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-116">No fewer than two tabs are allowed.</span></span>
- <span data-ttu-id="0ba0e-117">Não é permitido mais de quatro guias.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-117">No more than four tabs are allowed.</span></span>
- <span data-ttu-id="0ba0e-118">As guias precisam ser colocadas na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-118">Tabs must be whitelisted.</span></span>
- <span data-ttu-id="0ba0e-119">Os pares guia/ID precisam ser válidos.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-119">Tab/ID pairs must be valid.</span></span>
- <span data-ttu-id="0ba0e-120">Não é possível ter a mesma ID de guia várias vezes em um grupo de guias.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-120">Cannot have the same tab ID multiple times in one tab group.</span></span>

## <a name="tab-whitelist"></a><span data-ttu-id="0ba0e-121">Lista de permissões da guia</span><span class="sxs-lookup"><span data-stu-id="0ba0e-121">Tab whitelist</span></span>

<span data-ttu-id="0ba0e-122">Os pares de nome da guia/ID da guia a seguir estão na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-122">The following tab name/tab ID pairs are whitelisted.</span></span> <span data-ttu-id="0ba0e-123">As IDs das guias dependentes não são emparelhadas, mas precisam ser válidas, de acordo com a coluna de ID da guia.</span><span class="sxs-lookup"><span data-stu-id="0ba0e-123">Dependent tab IDs are not paired but must be valid per the Tab ID column.</span></span> <span data-ttu-id="0ba0e-124">Os valores diferenciam maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0ba0e-124">The values are case-sensitive</span></span>

|<span data-ttu-id="0ba0e-125">Nome da guia</span><span class="sxs-lookup"><span data-stu-id="0ba0e-125">Tab name</span></span>              |<span data-ttu-id="0ba0e-126">ID da guia</span><span class="sxs-lookup"><span data-stu-id="0ba0e-126">Tab ID</span></span>            |
|----------------------|------------------|
|`[.NET]`              |`(#tab/dotnet)`   |
|`[.NET Core 1.x]`     |`(#tab/netcore1x)`|
|`[.NET Core 2.x]`     |`(#tab/netcore2x)`|
|`[.NET Core 2.0]`     |`(#tab/netcore20)`|
|`[.NET Core 2.1]`     |`(#tab/netcore21)`|
|`[.NET Core 2.2]`     |`(#tab/netcore22)`|
|`[.NET Core 3.x]`     |`(#tab/netcore3x)`|
|`[.NET Core 3.0]`     |`(#tab/netcore30)`|
|`[.NET Core CLI]`     |`(#tab/netcore-cli)`|
|`[Azure CLI]`         |`(#tab/azure-cli)`|
|`[Android]`           |`(#tab/android)`  |
|`[Browser]`           |`(#tab/browser)`  |
|`[C#]`                |`(#tab/csharp)`   |
|`[C# Script]`         |`(#tab/csharp-script)`|
|`[CentOS]`            |`(#tab/centos)`|
|`[Command Line]`      |`(#tab/command-line)`|
|`[Debian]`            |`(#tab/debian)`|
|`[Docker Hub]`        |`(#tab/docker-hub)`|
|`[F#]`                |`(#tab/fsharp)`|
|`[Fedora]`            |`(#tab/fedora)`|
|`[iOS]`               |`(#tab/ios)`      |
|`[Java]`              |`(#tab/java)`|
|`[JavaScript]`        |`(#tab/javascript)`|
|`[Linux]`             |`(#tab/linux)`    |
|`[macOS]`             |`(#tab/macos)`    |
|`[Managed Kubernetes]`|`(#tab/kubernetes-managed)`|
|`[Maven]`             |`(#tab/maven)`|
|`[Mint]`              |`(#tab/mint)`|
|`[Node.js]`           |`(#tab/nodejs)`|
|`[npm]`               |`(#tab/npm)` |
|`[NuGet]`             |`(#tab/nuget)`|
|`[openSUSE]`          |`(#tab/opensuse)`|
|`[Other]`             |`(#tab/other)` |
|`[Oracle Linux]`      |`(#tab/oracle-linux)`|
|`[Package Manager]`   |`(#tab/package-manager)` |
|`[PEAR]`              |`(#tab/pear)`|
|`[pip]`               |`(#tab/pip)`|
|`[Portal]`            |`(#tab/azure-portal)`    |
|`[PowerShell]`        |`(#tab/azure-powershell)`|
|`[Private Registry]`  |`(#tab/private-registry)`|
|`[Python]`            |`(#tab/python)`|
|`[Resource Manager Template]`|`(#tab/azure-resource-manager)`|
|`[RHEL]`              |`(#tab/rhel)`|
|`[RubyGems]`          |`(#tab/rubygems)`|
|`[SQL Server]`        |`(#tab/sql-server)`|
|`[SQLite]`            |`(#tab/sqlite)`|
|`[TypeScript]`        |`(#tab/typescript)`|
|`[Visual Basic]`      |`(#tab/vb)` |
|`[Visual Studio]`     |`(#tab/visual-studio)`|
|`[Visual Studio 15.6 and earlier]`|`(#tab/vs156)`|
|`[Visual Studio 15.7 and later]`  |`(#tab/vs157)`|
|`[Visual Studio Code]`            |`(#tab/visual-studio-code)`|
|`[Visual Studio for Mac]`         |`(#tab/visual-studio-mac)`|
|`[Ubuntu]`                        |`(#tab/ubuntu)`|
|`[Unmanaged Kubernetes]`          |`(#tab/kubernetes-unmanaged)`|
|`[Windows]`   |`(#tab/windows)`   |