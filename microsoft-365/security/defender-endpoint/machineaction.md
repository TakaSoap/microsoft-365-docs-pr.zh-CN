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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187378"
---
# <a name="machineaction-resource-type"></a>MachineAction 资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 有关详细信息，请参阅响应 [操作](respond-machine-alerts.md)。 

| 方法                                                            | 返回类型                        | 说明                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [列出 MachineActions](get-machineactions-collection.md)           | [计算机操作](machineaction.md) | 列出 [计算机操作](machineaction.md) 实体。           |
| [获取 MachineAction](get-machineaction-object.md)                  | [计算机操作](machineaction.md) | 获取单个 [Machine Action](machineaction.md) 实体。     |
| [收集调查包](collect-investigation-package.md) | [计算机操作](machineaction.md) | 从计算机收集调查 [包](machine.md)。 |
| [获取调查包 SAS URI](get-package-sas-uri.md)       | [计算机操作](machineaction.md) | 获取用于下载调查包的 URI。          |
| [隔离计算机](isolate-machine.md)                             | [计算机操作](machineaction.md) | 将 [计算机](machine.md) 与网络隔离。                 |
| [解除计算机隔离](unisolate-machine.md)            | [计算机操作](machineaction.md) | 解除 [计算机](machine.md) 隔离。               |
| [限制应用执行](restrict-code-execution.md)              | [计算机操作](machineaction.md) | 限制应用程序执行。                             |
| [删除应用限制](unrestrict-code-execution.md)            | [计算机操作](machineaction.md) | 删除应用程序执行限制。                   |
| [运行防病毒扫描](run-av-scan.md)                              | [计算机操作](machineaction.md) | 如果适用，请Windows Defender (AV) 。    |
| [载出计算机](offboard-machine-api.md)                       | [计算机操作](machineaction.md) | 从 Microsoft Defender [for](machine.md) Endpoint 载出计算机。 |
| [停止和隔离文件](stop-and-quarantine-file.md)           | [计算机操作](machineaction.md) | 停止执行计算机上的文件并将其删除。        |

<br>

## <a name="properties"></a>属性

| 属性            | 类型           | 说明                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | 计算机 [操作实体的](machineaction.md) 标识。                                                                                                                                                     |
| type                | 枚举           | 操作的类型。 可能的值包括："RunAntiVirusScan"、"Offboard"、"CollectInvestigationPackage"、"Isolate"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution"和"UnrestrictCodeExecution" |
| scope               | string         | 操作的范围。 "完全"或"选择性"用于隔离，"快速"或"完全"用于防病毒扫描。                                                                                                   |
| requestor           | String         | 执行该操作的人的身份。                                                                                                                                                               |
| requestorComment    | String         | 发出操作时写入的注释。                                                                                                                                                              |
| 状态              | 枚举           | 命令的当前状态。 可能的值包括："Pending"、"InProgress"、"Succeeded"、"Failed"、"TimeOut"和"Canceled"。                                                                                 |
| machineId           | String         | 已 [执行](machine.md) 该操作的虚拟机的 ID。                                                                                                                                              |
| machineId           | String         | 已 [执行](machine.md) 该操作计算机的名称。                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | 创建该操作的日期和时间。                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | 上次更新操作状态的日期和时间。                                                                                                                                                     |
| relatedFileInfo     | 类          | 包含两个属性。 string ```fileIdentifier``` ```fileIdentifierType``` ，Enum，可能的值："Sha1"、"Sha256"和"Md5"。                                                                         |


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
