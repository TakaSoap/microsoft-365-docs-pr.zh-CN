---
title: machineAction 资源类型
description: 了解 Microsoft Defender for Endpoint 中 MachineAction 资源类型的方法和属性。
keywords: api， 受支持的 api， 获取， machineaction， 最近
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
ms.technology: mde
ms.openlocfilehash: 0d2da96b421dfa594836698f2849f615e8f0ccf5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209437"
---
# <a name="machineaction-resource-type"></a>MachineAction 资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 有关详细信息，请参阅响应 [操作](respond-machine-alerts.md)。

|方法|返回类型|说明|
|---|---|---|
|[列出 MachineActions](get-machineactions-collection.md)|[计算机操作](machineaction.md)|列出 [计算机操作](machineaction.md) 实体。|
|[获取 MachineAction](get-machineaction-object.md)|[计算机操作](machineaction.md)|获取单个 [Machine Action](machineaction.md) 实体。|
|[收集调查程序包](collect-investigation-package.md)|[计算机操作](machineaction.md)|从计算机收集调查 [包](machine.md)。|
|[获取调查包 SAS URI](get-package-sas-uri.md)|[计算机操作](machineaction.md)|获取用于下载调查包的 URI。|
|[隔离计算机](isolate-machine.md)|[计算机操作](machineaction.md)|将 [计算机](machine.md) 与网络隔离。|
|[从隔离释放计算机](unisolate-machine.md)|[计算机操作](machineaction.md)|解除 [计算机](machine.md) 隔离。|
|[限制应用执行](restrict-code-execution.md)|[计算机操作](machineaction.md)|限制应用程序执行。|
|[删除应用限制](unrestrict-code-execution.md)|[计算机操作](machineaction.md)|删除应用程序执行限制。|
|[运行防病毒扫描](run-av-scan.md)|[计算机操作](machineaction.md)|如果适用，请Windows Defender (AV) 。|
|[载出计算机](offboard-machine-api.md)|[计算机操作](machineaction.md)|从 Microsoft Defender [for](machine.md) Endpoint 载出计算机。|
|[停止和隔离文件](stop-and-quarantine-file.md)|[计算机操作](machineaction.md)|停止执行计算机上的文件并将其删除。|
|[运行实时响应](run-live-response.md)|[计算机操作](machineaction.md)|在设备上运行一系列实时响应命令|
|[获得实时响应结果](get-live-response-result.md)|URL 实体|按索引检索特定实时响应命令结果下载链接。|
|[取消计算机操作](cancel-machine-action.md)|[计算机操作](machineaction.md)|取消活动计算机操作。|

<br>

## <a name="properties"></a>属性

|属性|类型|说明|
|---|---|---|
|ID|Guid|计算机 [操作实体的](machineaction.md) 标识。|
|type|枚举|操作的类型。 可能的值包括："RunAntiVirusScan"、"Offboard"、"Live Response"、"CollectInvestigationPackage"、"Isolate"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution"和"UnrestrictCodeExecution"。|
|scope|string|操作的范围。 "完全"或"选择性"用于隔离，"快速"或"完全"用于防病毒扫描。|
|requestor|字符串|执行该操作的人的身份。|
|externalID|String|客户可以在自定义关联请求中提交的 ID。|
|requestSource|string|提交操作的用户/应用程序的名称。|
| 命令|数组|要运行的命令。 允许的值为 PutFile、RunScript、GetFile。|
|cancellationRequestor|String|取消操作的人的标识。|
|requestorComment|String|发出操作时写入的注释。|
|cancellationComment|String|取消操作时写入的注释。|
|status|枚举|命令的当前状态。 可能的值包括："Pending"、"InProgress"、"Succeeded"、"Failed"、"TimeOut"和"Cancelled"。|
|machineId|字符串|已 [执行](machine.md) 该操作的虚拟机的 ID。|
|computerDnsName|字符串|已 [执行](machine.md) 该操作计算机的名称。|
|creationDateTimeUtc|DateTimeOffset|创建该操作的日期和时间。|
|cancellationDateTimeUtc|DateTimeOffset|取消该操作的日期和时间。|
|lastUpdateDateTimeUtc|DateTimeOffset|上次更新操作状态的日期和时间。|
|title|String|计算机操作标题。|
|relatedFileInfo|类|包含两个属性。 string `fileIdentifier` ，具有 `fileIdentifierType` 可能值的 Enum："Sha1"、"Sha256"和"Md5"。|

## <a name="json-representation"></a>Json 表示形式

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
