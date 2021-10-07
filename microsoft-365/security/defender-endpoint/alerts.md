---
title: 获取警报 API
description: 了解 Microsoft Defender for Endpoint 中警报资源类型的方法和属性。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
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
ms.openlocfilehash: 96f5f043ba49e01bd03f23c8eb430e56f88a5856
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197145"
---
# <a name="alert-resource-type"></a>警报资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="methods"></a>方法

<br>

****

|方法|返回类型|说明|
|---|---|---|
|[获取警报](get-alert-info-by-id.md)|[提醒](alerts.md)|获取单个 [alert](alerts.md) 对象。|
|[列出警报](get-alerts.md)|[警报](alerts.md) 集合|列出 [警报](alerts.md) 集合。|
|[更新警报](update-alert.md)|[提醒](alerts.md)|更新特定 [警报](alerts.md)。|
|[批量更新警报](batch-update-alerts.md)||更新一批 [警报](alerts.md)。|
|[创建警报](create-alert-by-reference.md)|[提醒](alerts.md)|根据从高级搜寻 获取的事件数据 [创建警报](run-advanced-query-api.md)。|
|[列出相关域](get-alert-related-domain-info.md)|域集合|列出与警报关联的 URL。|
|[列出相关文件](get-alert-related-files-info.md)|[文件](files.md) 集合|列出 [与](files.md) 警报关联的文件 [实体](alerts.md)。|
|[列出相关 IP](get-alert-related-ip-info.md)|IP 集合|列出与警报关联的 IP。|
|[获取相关计算机](get-alert-related-machine-info.md)|[计算机](machine.md)|[与](machine.md)警报关联的[计算机](alerts.md)。|
|[获取相关用户](get-alert-related-user-info.md)|[用户](user.md)|[与](user.md)警报关联的[用户](alerts.md)。|
|

## <a name="properties"></a>属性

<br>

****

|属性|类型|说明|
|---|---|---|
|id|String|警报 ID。|
|title|String|警报标题。|
|说明|String|警报说明。|
|alertCreationTime|Nullable DateTimeOffset|创建警报时 (UTC) 日期和时间。|
|lastEventTime|Nullable DateTimeOffset|在同一设备上触发警报的事件的最后一次发生次数。|
|firstEventTime|Nullable DateTimeOffset|在该设备上触发警报的事件的第一次发生。|
|lastUpdateTime|Nullable DateTimeOffset|上次更新警报 (UTC) 日期和时间。|
|resolvedTime|Nullable DateTimeOffset|警报状态更改为"已解决"的日期和时间。|
|incidentId|Nullable Long|[警报](view-incidents-queue.md)的事件 ID。|
|investigationId|Nullable Long|与 [警报](automated-investigations.md) 相关的调查 ID。|
|investigationState|Nullable Enum|调查 的当前 [状态](automated-investigations.md)。 可能的值包括："Unknown"、"Terminated"、 "SuccessfullyRemediated"、"Benign"、"Failed"、"PartiallyRemediated"、"Running"、"PendingApproval"、"PendingResource"、"PartiallyInvestigated"、"TerminatedByUser"、"TerminatedBySystem"、"Queued"、"InnerFailure"、"PreexistingAlert"、"UnsupportedOs"、"UnsupportedAlertType"和"SuppressedAlert"。|
|assignedTo|String|警报的所有者。|
|rbacGroupName|String|RBAC 设备组名称。|
|mitreTechniques|字符串|Mitre Enterprise技术 ID。|
|relatedUser|String|与特定警报相关的用户的详细信息。|
|severity|枚举|警报的严重性。 可能的值包括："UnSpecified"、"Informational"、"Low"、"Medium"和"High"。|
|status|枚举|指定警报的当前状态。 可能的值包括："Unknown"、"New"、"InProgress"和"Resolved"。|
|classification|Nullable Enum|警报的规范。 可能的值是："Unknown"、"FalsePositive"、"TruePositive"。|
|确定|Nullable Enum|指定警报的确定。 可能的值包括："NotAvailable"、"Apt"、"Malware"、SecurityPersonnel、"SecurityTesting"、"UnwantedSoftware"和"Other"。|
|“类别”|String|警报的类别。|
|detectionSource|字符串|检测源。|
|threatFamilyName|String|威胁系列。|
|threatName|String|威胁名称。|
|machineId|字符串|与 [警报关联的](machine.md) 计算机实体的 ID。|
|computerDnsName|String|[计算机](machine.md) 完全限定的名称。|
|aadTenantId|String|用户Azure Active Directory ID。|
|一个|String|触发警报的检测器的 ID。|
|comments|警报注释列表|Alert Comment 对象包含：注释字符串、createdBy 字符串和 createTime 日期时间。|
|证据|警报证据列表|与警报相关的证据。 请参阅下面的示例。|
|

### <a name="response-example-for-getting-single-alert"></a>获取单个警报的响应示例：

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "DOMAIN"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "name",
            "domainName": "DOMAIN",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
