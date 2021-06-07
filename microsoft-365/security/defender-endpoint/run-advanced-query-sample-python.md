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
# <a name="advanced-hunting-using-python"></a>通过 Python 高级搜寻

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

使用 Python 运行高级查询，请参阅[高级搜寻 API。](run-advanced-query-api.md)

在此部分中，我们将共享 Python 示例以检索令牌并使用它运行查询。

>**先决条件**：首先需要 [创建应用](apis-intro.md)。

## <a name="get-token"></a>获取令牌

- 运行以下命令：

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

其中
- tenantId：要代表其运行查询的租户的 ID (即，查询将针对此租户数据运行) 
- appId：Azure AD 应用的 ID (应用必须具有对适用于终结点应用的 Microsoft Defender 的"运行高级查询") 
- appSecret：Azure AD 应用机密

## <a name="run-query"></a>运行查询

 运行以下查询：

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

- schema 包含查询结果的架构
- 结果包含查询的结果

### <a name="complex-queries"></a>复杂查询

如果要运行复杂查询 (或多行查询) ，请保存文件中查询，而不是上面的示例中的第一行，运行以下命令：

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>处理查询结果

现在您可以使用查询结果。

若要对结果进行访问，可执行下列操作：

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


若要以 CSV 格式输出文件格式的查询结果，file1.csv执行下列操作：

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

若要将查询结果输出为 JSON 格式，file1.js以下操作：

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>相关主题
- [适用于终结点的 Microsoft Defender API](apis-intro.md)
- [高级搜寻 API](run-advanced-query-api.md)
- [通过 PowerShell 高级搜寻](run-advanced-query-sample-powershell.md)
