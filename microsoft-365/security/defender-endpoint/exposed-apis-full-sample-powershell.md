---
title: 高级搜寻与 PowerShell API 指南
ms.reviewer: ''
description: 使用这些代码示例，查询多个 Microsoft Defender for Endpoint API。
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: 9913d1b0b0d5d0462fdee0b9c576a590bd3ddbc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198315"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="c81d8-104">使用 PowerShell 的 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="c81d8-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c81d8-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c81d8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="c81d8-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c81d8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c81d8-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c81d8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="c81d8-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c81d8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c81d8-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c81d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="c81d8-110">使用来自 Microsoft Defender for Endpoint 的多个 API 的完整方案。</span><span class="sxs-lookup"><span data-stu-id="c81d8-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="c81d8-111">在此部分中，我们将 PowerShell 示例共享到</span><span class="sxs-lookup"><span data-stu-id="c81d8-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="c81d8-112">检索令牌</span><span class="sxs-lookup"><span data-stu-id="c81d8-112">Retrieve a token</span></span> 
- <span data-ttu-id="c81d8-113">使用令牌检索 Microsoft Defender for Endpoint 中的最新警报</span><span class="sxs-lookup"><span data-stu-id="c81d8-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="c81d8-114">对于每个警报，如果警报具有中优先级或高优先级，并且仍在处理中，请检查设备已连接到可疑 URL 多少次。</span><span class="sxs-lookup"><span data-stu-id="c81d8-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="c81d8-115">**先决条件**：首先需要 [创建应用](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="c81d8-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="c81d8-116">准备说明</span><span class="sxs-lookup"><span data-stu-id="c81d8-116">Preparation instructions</span></span>

- <span data-ttu-id="c81d8-117">打开一个 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="c81d8-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="c81d8-118">如果策略不允许您运行 PowerShell 命令，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c81d8-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="c81d8-119">有关详细信息，请参阅 [PowerShell 文档](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="c81d8-119">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="c81d8-120">获取令牌</span><span class="sxs-lookup"><span data-stu-id="c81d8-120">Get token</span></span>

<span data-ttu-id="c81d8-121">运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="c81d8-121">Run the below:</span></span>

- <span data-ttu-id="c81d8-122">$tenantId：要代表其运行查询的租户的 ID (即查询将针对此租户数据运行) </span><span class="sxs-lookup"><span data-stu-id="c81d8-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="c81d8-123">$appId：AAD 应用的 ID (应用必须具有 Defender for Endpoint) </span><span class="sxs-lookup"><span data-stu-id="c81d8-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="c81d8-124">$appSecret：Azure AD 应用机密</span><span class="sxs-lookup"><span data-stu-id="c81d8-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="c81d8-125">$suspiciousUrl：URL</span><span class="sxs-lookup"><span data-stu-id="c81d8-125">$suspiciousUrl: The URL</span></span>


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a><span data-ttu-id="c81d8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c81d8-126">See also</span></span>
- [<span data-ttu-id="c81d8-127">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="c81d8-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="c81d8-128">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="c81d8-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="c81d8-129">使用 Python 的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="c81d8-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
