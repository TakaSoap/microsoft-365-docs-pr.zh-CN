---
title: 高级搜寻与 PowerShell API 基础知识
ms.reviewer: ''
description: 了解使用 PowerShell 查询 Microsoft Defender for Endpoint API 的基础知识。
keywords: api， 受支持的 api， 高级搜寻， 查询
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 20c63daaf61b85f35aaceccb540b6d50824c801d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198667"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="18a27-104">使用 PowerShell 的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="18a27-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="18a27-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="18a27-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="18a27-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="18a27-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="18a27-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="18a27-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="18a27-108">使用 PowerShell 运行高级查询，请参阅[高级搜寻 API。](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="18a27-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="18a27-109">在此部分中，我们将共享 PowerShell 示例以检索令牌并使用它运行查询。</span><span class="sxs-lookup"><span data-stu-id="18a27-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="18a27-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="18a27-110">Before you begin</span></span>
<span data-ttu-id="18a27-111">首先需要 [创建应用](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="18a27-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="18a27-112">准备说明</span><span class="sxs-lookup"><span data-stu-id="18a27-112">Preparation instructions</span></span>

- <span data-ttu-id="18a27-113">打开一个 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="18a27-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="18a27-114">如果策略不允许您运行 PowerShell 命令，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="18a27-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="18a27-115">有关详细信息，请参阅 [PowerShell 文档](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="18a27-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="18a27-116">获取令牌</span><span class="sxs-lookup"><span data-stu-id="18a27-116">Get token</span></span>

- <span data-ttu-id="18a27-117">运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="18a27-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="18a27-118">其中</span><span class="sxs-lookup"><span data-stu-id="18a27-118">where</span></span>
- <span data-ttu-id="18a27-119">$tenantId：要代表其运行查询的租户的 ID (即，查询将针对此租户数据运行) </span><span class="sxs-lookup"><span data-stu-id="18a27-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="18a27-120">$appId：Azure AD 应用的 ID (应用必须具有 Defender for Endpoint) 的"运行高级查询"权限</span><span class="sxs-lookup"><span data-stu-id="18a27-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="18a27-121">$appSecret：Azure AD 应用机密</span><span class="sxs-lookup"><span data-stu-id="18a27-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="18a27-122">运行查询</span><span class="sxs-lookup"><span data-stu-id="18a27-122">Run query</span></span>

<span data-ttu-id="18a27-123">运行以下查询：</span><span class="sxs-lookup"><span data-stu-id="18a27-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="18a27-124">$results查询的结果</span><span class="sxs-lookup"><span data-stu-id="18a27-124">$results contain the results of your query</span></span>
- <span data-ttu-id="18a27-125">$schema包含查询结果的架构</span><span class="sxs-lookup"><span data-stu-id="18a27-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="18a27-126">复杂查询</span><span class="sxs-lookup"><span data-stu-id="18a27-126">Complex queries</span></span>

<span data-ttu-id="18a27-127">如果要运行复杂查询 (或多行查询) ，请保存文件中查询，而不是上面的示例中的第一行，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="18a27-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="18a27-128">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="18a27-128">Work with query results</span></span>

<span data-ttu-id="18a27-129">现在您可以使用查询结果。</span><span class="sxs-lookup"><span data-stu-id="18a27-129">You can now use the query results.</span></span>

<span data-ttu-id="18a27-130">若要以 CSV 格式输出文件格式的查询结果，file1.csv执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="18a27-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="18a27-131">若要将查询结果输出为 JSON 格式，file1.js以下操作：</span><span class="sxs-lookup"><span data-stu-id="18a27-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="18a27-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="18a27-132">Related topic</span></span>
- [<span data-ttu-id="18a27-133">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="18a27-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="18a27-134">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="18a27-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="18a27-135">使用 Python 的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="18a27-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
