---
title: 在设备上运行实时响应命令
description: 了解如何在设备上运行实时响应命令序列。
keywords: api， 图形 api， 受支持的 api， 上载到库
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e81c235105a7c7479a917c7cb7cc404e2553f2f1
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323509"
---
# <a name="run-live-response-commands-on-a-device"></a>在设备上运行实时响应命令

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)


[!include[Prerelease information](../../includes/prerelease.md)]

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

在设备上运行一系列实时响应命令

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 10 次 (HTTP 429 请求响应其他) 。

2. 25 个并发运行的 (超出限制的请求将收到"429 - 请求过多"响应) 。

3. 如果计算机不可用，会话将排入队列最多 3 天。

4. RunScript 命令在 10 分钟后超时。

5. 实时响应命令无法排入队列，一次只能执行一个。

6. 如果你尝试运行此 API 调用的机器位于未分配自动修正级别的 RBAC 设备组中，你至少需要为给定的设备组启用最低修正级别。

7. 可以在单个 API 调用中运行多个实时响应命令。 但是，当实时响应命令失败时，将不会执行所有后续操作。

## <a name="minimum-requirements"></a>最低要求

在设备上启动会话之前，请确保满足以下要求：

- **验证是否正在运行受支持的** Windows。

  设备必须运行以下版本的设备之一Windows

  - **Windows 11**
  
  - **Windows 10**
    - [版本 1909](/windows/whats-new/whats-new-windows-10-version-1909) 或更高版本
    - [版本 1903](/windows/whats-new/whats-new-windows-10-version-1903) [和 KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - [版本 1809 (RS 5) ](/windows/whats-new/whats-new-windows-10-version-1809) [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [版本 1803 (RS 4) ](/windows/whats-new/whats-new-windows-10-version-1803) [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [版本 1709 (RS 3) ](/windows/whats-new/whats-new-windows-10-version-1709) [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **Windows Server 2019 - 仅适用于公共预览版**
    - 版本 1903 或 ([KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384) 版本) 更高版本
    - 版本 1809 ([KB4537818) ](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    
  - **Windows Server 2022**

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。

|权限类型|权限|权限显示名称|
|---|---|---|
|应用程序|Machine.LiveResponse|在特定的计算机上运行实时响应|
|委派（工作或学校帐户）|Machine.LiveResponse|在特定的计算机上运行实时响应|

## <a name="http-request"></a>HTTP 请求

```HTTP
POST https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>请求标头

|名称|类型|说明|
|---|---|---|
|Authorization|String|Bearer\<token>\. 必需。|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>请求正文

|参数|类型|说明|
|---|---|---|
|评论|字符串|要与操作关联的注释。|
|命令|数组|要运行的命令。 允许的值为 PutFile、RunScript、GetFile。|

## <a name="commands"></a>命令

|命令类型|参数|说明|
|---|---|---|
|PutFile|项：FileName <p> 值：\<file name\>|将库中的文件置于设备。 文件保存在工作文件夹中，在设备默认重启时将被删除。
|RunScript|键：ScriptName <br> 值：\<Script from library\> <p> 键：Args <br> 值：\<Script arguments\>|在设备上从库中运行脚本。 <p>  Args 参数将传递给您的脚本。 <p> 10 分钟后超时。|
|GetFile|键：路径 <br> 值：\<File path\>|从设备收集文件。 注意：路径中的反杠必须转义。|

## <a name="response"></a>响应

- 如果成功，此方法返回 201 Created。

  Action 实体。 如果未找到具有指定 ID 的机器 - 404 未找到。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```HTTP
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

```HTTP
HTTP/1.1 200 Ok
```

Content-type： application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}
```

## <a name="related-topics"></a>相关主题

- [获取计算机操作 API](get-machineaction-object.md)
- [获得实时响应结果](get-live-response-result.md)
- [取消计算机操作](cancel-machine-action.md)
