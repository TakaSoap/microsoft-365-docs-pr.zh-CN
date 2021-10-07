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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89ff7984e009f022984f4004a0195176c68a9bad
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194017"
---
# <a name="advanced-hunting-using-powershell"></a>通过 PowerShell 高级搜寻

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

使用 PowerShell 运行高级查询，请参阅[高级搜寻 API。](run-advanced-query-api.md)

在此部分中，我们将共享 PowerShell 示例以检索令牌并使用它运行查询。

## <a name="before-you-begin"></a>准备工作
首先需要 [创建应用](apis-intro.md)。

## <a name="preparation-instructions"></a>准备说明

- 打开一个 PowerShell 窗口。
- 如果策略不允许您运行 PowerShell 命令，可以运行以下命令：
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>有关详细信息，请参阅 [PowerShell 文档](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>获取令牌

- 运行下面的命令：

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

其中
- $tenantId：要代表其运行查询的租户的 ID (即，查询将针对此租户数据运行) 
- $appId：Azure AD 应用的 ID (应用必须拥有对 Defender for Endpoint) 
- $appSecret：Azure AD 应用机密

## <a name="run-query"></a>运行查询

运行以下查询：

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

- $results包含查询结果
- $schema包含查询结果的架构

### <a name="complex-queries"></a>复杂查询

如果要在多行或多 (中运行复杂查询) ，请保存文件中查询，而不是上述示例中的第一行，运行以下命令：

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>处理查询结果

现在您可以使用查询结果。

若要以 CSV 格式输出文件格式的查询结果，file1.csv执行下列操作：

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

若要以 JSON 格式输出 file1.json 格式的查询结果，可执行下列操作：

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>相关主题
- [适用于终结点的 Microsoft Defender API](apis-intro.md)
- [高级搜寻 API](run-advanced-query-api.md)
- [通过 Python 高级搜寻](run-advanced-query-sample-python.md)
