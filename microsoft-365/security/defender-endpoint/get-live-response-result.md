---
title: 获取实时响应结果
description: 了解如何按其索引检索特定实时响应命令结果。
keywords: api， 图形 api， 受支持的 api， 上传到库
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8fde75f8f7b65f9d74362a40b881b335129e4bee
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2021
ms.locfileid: "53652182"
---
#  <a name="get-live-response-results"></a>获取实时响应结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

按索引检索特定实时响应命令结果。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。

|权限类型|权限|权限显示名称|
|---|---|---|
|应用程序|Machine.LiveResponse|在特定的计算机上运行实时响应|
|委派（工作或学校帐户）|Machine.LiveResponse|在特定的计算机上运行实时响应|

## <a name="http-request"></a>HTTP 请求

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>请求标头

|名称|类型|说明|
|---|---|---|
|Authorization|字符串|Bearer {token}。必需。|

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功，此方法返回 200 正常响应代码，该对象包含指向 value 属性中的命令 *结果* 的链接。 此链接的有效期为 30 分钟，应该立即用于将程序包下载到本地存储。 另一个调用可以重新创建已过期的链接，并且无需再次运行实时响应。

*Runscript 脚本属性：*

|属性|说明|
|---|---|
|name|已执行的脚本名称|
|exit_code|已执行的脚本退出代码|
|script_output|已执行的脚本标准输出|
|script_error|已执行的脚本标准错误输出|

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

HTTP/1.1 200 正常

Content-type： application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*文件内容：*

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>相关主题

- [获取计算机操作 API](get-machineaction-object.md)
- [取消计算机操作](cancel-machine-action.md)
- [运行实时响应](run-live-response.md) 
