---
title: 高级搜寻与 Python API 指南
ms.reviewer: ''
description: 通过示例，了解如何使用 Microsoft Defender for Endpoint API（使用 Python）进行查询。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771435"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="b2941-104">通过 Python 高级搜寻</span><span class="sxs-lookup"><span data-stu-id="b2941-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2941-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b2941-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b2941-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b2941-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b2941-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b2941-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b2941-108">使用 Python 运行高级查询，请参阅[高级搜寻 API。](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="b2941-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="b2941-109">在此部分中，我们将共享 Python 示例以检索令牌并使用它运行查询。</span><span class="sxs-lookup"><span data-stu-id="b2941-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="b2941-110">**先决条件**：首先需要 [创建应用](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="b2941-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="b2941-111">获取令牌</span><span class="sxs-lookup"><span data-stu-id="b2941-111">Get token</span></span>

- <span data-ttu-id="b2941-112">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b2941-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="b2941-113">其中</span><span class="sxs-lookup"><span data-stu-id="b2941-113">where</span></span>
- <span data-ttu-id="b2941-114">tenantId：要代表其运行查询的租户的 ID (即，查询将针对此租户数据运行) </span><span class="sxs-lookup"><span data-stu-id="b2941-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="b2941-115">appId：Azure AD 应用的 ID (应用必须具有对适用于终结点应用的 Microsoft Defender 的"运行高级查询") </span><span class="sxs-lookup"><span data-stu-id="b2941-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="b2941-116">appSecret：Azure AD 应用机密</span><span class="sxs-lookup"><span data-stu-id="b2941-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="b2941-117">运行查询</span><span class="sxs-lookup"><span data-stu-id="b2941-117">Run query</span></span>

 <span data-ttu-id="b2941-118">运行以下查询：</span><span class="sxs-lookup"><span data-stu-id="b2941-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="b2941-119">schema 包含查询结果的架构</span><span class="sxs-lookup"><span data-stu-id="b2941-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="b2941-120">结果包含查询的结果</span><span class="sxs-lookup"><span data-stu-id="b2941-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="b2941-121">复杂查询</span><span class="sxs-lookup"><span data-stu-id="b2941-121">Complex queries</span></span>

<span data-ttu-id="b2941-122">如果要运行复杂查询 (或多行查询) ，请保存文件中查询，而不是上面的示例中的第一行，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b2941-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="b2941-123">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="b2941-123">Work with query results</span></span>

<span data-ttu-id="b2941-124">现在您可以使用查询结果。</span><span class="sxs-lookup"><span data-stu-id="b2941-124">You can now use the query results.</span></span>

<span data-ttu-id="b2941-125">若要对结果进行访问，可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b2941-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="b2941-126">若要以 CSV 格式输出文件格式的查询结果，file1.csv执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b2941-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="b2941-127">若要将查询结果输出为 JSON 格式，file1.js以下操作：</span><span class="sxs-lookup"><span data-stu-id="b2941-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="b2941-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="b2941-128">Related topic</span></span>
- [<span data-ttu-id="b2941-129">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="b2941-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="b2941-130">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="b2941-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="b2941-131">通过 PowerShell 高级搜寻</span><span class="sxs-lookup"><span data-stu-id="b2941-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
