---
title: 使用 REST API 拉取 Microsoft Defender 的终结点检测
description: 了解如何调用 Microsoft Defender for Endpoint API 终结点，以使用 SIEM REST API 拉取 JSON 格式的检测。
keywords: 检测， 拉取检测， rest api， 请求， 响应
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: f4f5dbcde4a80b01c3df7ee7c32b41afc89dbba6
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301002"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>使用 SIEM REST API 拉取 Microsoft Defender 的终结点检测

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

> [!NOTE]
>
> - [Microsoft Defender 终结点警报](alerts.md) 由一个或多个检测组成。
> - [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。
> s-Microsoft Defender for Endpoint Alert API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。 有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。

Microsoft Defender for Endpoint 支持 OAuth 2.0 协议从 API 拉取检测。

通常，OAuth 2.0 协议支持四种类型的流：

- 授权流
- 隐式流
- 客户端凭据流
- 资源所有者流

有关 OAuth 规范详细信息，请参阅 [OAuth 网站](http://www.oauth.net)。

Microsoft Defender for Endpoint 支持 _授权_ 授予流和 _客户端_ 凭据流来获取拉取检测的访问权限，Azure Active Directory (AAD) 授权服务器。

授权 _授予流_ 使用用户凭据获取授权代码，然后使用授权代码获取访问令牌。

客户端 _凭据流_ 使用客户端凭据针对 Microsoft Defender for Endpoint 终结点 URL 进行身份验证。 此流适用于 OAuth 客户端创建对不需要用户凭据的 API 的请求的情况。

使用 Microsoft Defender for Endpoint API 中的以下方法拉取 JSON 格式的检测。

> [!NOTE]
> Microsoft Defender 安全中心将类似的警报检测合并到单个警报中。 此 API 基于您设置的查询参数，以原始形式拉取警报检测，从而使您可以应用自己的分组和筛选。

## <a name="before-you-begin"></a>开始之前

- 在调用 Microsoft Defender for Endpoint 终结点以拉取检测之前，你需要在 Azure Active Directory (AAD) 中启用 SIEM 集成应用程序。 有关详细信息，请参阅在 [Microsoft Defender for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)。

- 请记下 Azure 应用程序注册过程中的下列值。需要使用这些值在服务或守护程序应用中配置 OAuth 流：
  - 应用程序 ID（应用程序专用）
  - 应用密钥或机密（应用程序专用）
  - 应用 OAuth 2.0 令牌终结点
    - 在应用页面中，单击 Azure 管理门户底部的“**查看终结点**”，找到此值。终结点看起来像 `https://login.microsoftonline.com/{tenantId}/oauth2/token`。

## <a name="get-an-access-token"></a>获取访问令牌

在创建对 终结点的调用之前，需要获取访问令牌。

你将使用访问令牌访问受保护的资源，这是 Microsoft Defender for Endpoint 中的检测。

若要获取访问令牌，您需要对令牌颁发终结点执行 POST 请求。 下面是一个示例请求：

```http
POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```

响应将包含访问令牌和过期信息。

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```

你现在可以在对 *Defender* for Endpoint API 的请求access_token字段的值。

## <a name="request"></a>请求

借助访问令牌，你的应用可以向 Microsoft Defender for Endpoint API 提出经过身份验证的请求。 您的应用必须将访问令牌附加到各个请求的授权头中。

### <a name="request-syntax"></a>请求语法

方法|请求 URI
---|---
GET|使用适用于你地区的 URI。 <p> **对于欧盟**： `https://wdatp-alertexporter-eu.windows.com/api/alerts` <p> **对于美国**： `https://wdatp-alertexporter-us.windows.com/api/alerts` <p> **对于英国**： `https://wdatp-alertexporter-uk.windows.com/api/alerts`

### <a name="request-header"></a>请求标头

标头|类型|说明|
---|---|---
Authorization|string|必填。 The Azure AD access token in the form **Bearer** &lt; *token* &gt; .|

### <a name="request-parameters"></a>请求参数

使用可选的查询参数指定和控制响应中返回的数据量。 如果调用此方法时不带参数，响应将包含组织中过去 2 小时内的所有警报。

名称|值|说明
---|---|---
sinceTimeUtc|日期时间|根据字段定义从中检索下限的警报： <p> `LastProcessedTimeUtc` <p> 该时间范围将为：从 sinceTimeUtc 时间到当前时间。 <p> **注意**：如果未指定，将检索过去两小时内生成的所有警报。
untilTimeUtc|日期时间|定义检索的上限警报。 <p> 该时间范围将为： `sinceTimeUtc` 从一次一 `untilTimeUtc` 次到一次。 <p> **注意**：如果未指定，默认值将为当前时间。
ago|string|在下列时间范围内拉取警报： `(current_time - ago)` 时而 `current_time` 时。 <p> 值应按照 ISO **8601 持续时间格式** 进行设置 <p> 示例： `ago=PT10M` 将拉取过去 10 分钟内收到的警报。
limit|int|定义要检索的警报数。 将基于定义的号码检索最新警报。<p> **注意**：如果未指定，将检索该时间范围内可用的所有警报。
machinegroups|string|指定要拉取警报的设备组。 <p> **注意**：如果未指定，将检索来自所有设备组的警报。 <p> 示例： <br><br> `https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines`
DeviceCreatedMachineTags|string|注册表中的单个设备标记。
CloudCreatedMachineTags|string|在应用程序中创建的设备Microsoft Defender 安全中心。

### <a name="request-example"></a>请求示例

以下示例演示如何检索组织的所有检测。

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

以下示例演示了自 2016-09-12 00：00：00 以来获取最近 20 个检测的请求。

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>响应

返回值是 JSON 格式的警报对象的数组。

下面是一个返回值的示例：

```json
[
{
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>代码示例

### <a name="get-access-token"></a>获取访问令牌

以下代码示例演示如何获取用于调用适用于 Endpoint SIEM API 的 Microsoft Defender 的访问令牌。

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials"|cut -d "{" -f2|cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]}|cut -d "\"" -f2|cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>使用令牌连接到检测终结点

以下代码示例演示如何使用访问令牌调用 Defender for Endpoint SIEM API 获取警报。

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token"
}

#Send the webrequest and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results. This works for SIEM API:
$alerts =  $response.Content|ConvertFrom-Json|ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o|foreach {$_ -replace ":", "."}

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw|ConvertFrom-Json|Select-Object -ExpandProperty value|Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token"|cut -d "[" -f2|cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>错误代码

Microsoft Defender for Endpoint REST API 返回由无效请求导致的以下错误代码。

HTTP 错误代码|说明
---|---
401|请求格式不正确或令牌无效。
403|未经授权异常 - 任何域不由租户管理员管理或租户状态被删除。
500|服务出错。

## <a name="related-topics"></a>相关主题

- [在 Microsoft Defender for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)
- [配置 ArcSight 以拉取适用于终结点检测的 Microsoft Defender](configure-arcsight.md)
- [将检测拉取到 SIEM 工具](configure-siem.md)
- [适用于终结点检测字段的 Microsoft Defender](api-portal-mapping.md)
- [SIEM 工具集成问题疑难解答](troubleshoot-siem.md)
