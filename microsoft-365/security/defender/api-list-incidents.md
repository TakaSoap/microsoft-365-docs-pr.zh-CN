---
title: 列出事件 API Microsoft 365 Defender
description: 了解如何在事件列表中列出事件 API Microsoft 365 Defender
keywords: 列表， 事件， 事件， api
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: 03fbcb70588158919b54c9153b5d8d32d416cc75
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172135"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>列出事件 API Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

## <a name="api-description"></a>API 说明

列表事件 API 允许你对事件进行排序，以创建明智的网络安全响应。 它将公开在环境保留策略中指定的时间范围内网络中标记的事件集合。 最新事件显示在列表顶部。 每个事件都包含一组相关警报及其相关实体。

API 支持以下 **OData** 运算符：

- `$filter` 在 `lastUpdateTime` 、 `createdTime` 、 和 `status` `assignedTo` 属性上
- `$top`，最大值为 **100**
- `$skip`

## <a name="limitations"></a>限制

1. 最大页面大小为 **100 个事件**。
2. 最大请求速率为每分钟 **50** 个呼叫和 **每小时 1500 个呼叫**。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅[Access Microsoft 365 Defender API](api-access.md)

权限类型|权限|权限显示名称
---|---|---
应用程序|Incident.Read.All|读取所有事件
应用程序|Incident.ReadWrite.All|读取和写入所有事件
委派（工作或学校帐户）|Incident.Read|读取事件
委派（工作或学校帐户）|Incident.ReadWrite|读取和写入事件

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户需要具有门户中事件的查看权限。
> - 该响应将仅包括向用户公开的事件。

## <a name="http-request"></a>HTTP 请求

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
---|---|---
Authorization|String|Bearer {token}。 **Required**

## <a name="request-body"></a>请求正文

无。

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 和 `200 OK` 事件列表。 [](api-incident.md)

## <a name="schema-mapping"></a>架构映射

### <a name="incident-metadata"></a>事件元数据

字段名|说明|示例值
---|---|---
incidentId|表示事件的唯一标识符|924565
redirectIncidentId|只有在将事件与另一个事件分组在一起时填充，作为事件处理逻辑的一部分。|924569
incidentName|可用于每个事件的字符串值。|勒索软件活动
createdTime|第一次创建事件的时间。|2020-09-06T14：46：57.0733333Z
lastUpdateTime|上次在后端更新事件的时间。 <p> 为检索事件的时间范围设置请求参数时，可以使用此字段。|2020-09-06T14：46：57.29Z
assignedTo|事件的所有者;如果没有分配 *所有者* ，则为空。|secop2@contoso.com
classification|事件的规范。 属性值为 *：Unknown、FalsePositive、TruePositive*  |未知
确定|指定事件的确定。 属性值包括：NotAvailable、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware、Other       |NotAvailable
detectionSource|指定检测源。|Defender for Cloud Apps
状态|将事件分类 (*活动"* 或"已解决 *) 。* 它可以帮助您组织和管理对事件的响应。|活动
severity|指示对资产可能的影响。 严重性越高，影响越大。 通常，严重性级别较高的项目需要最直接的关注。 <p> 下列值之一 *：Informational、Low、*Medium* 和 *High。* |中
标记|与事件关联的自定义标记数组，例如，用于标记一组具有共同特征的事件。|\[\]
comments|由 secops 在管理事件时创建的注释数组，例如有关分类选择的其他信息。|\[\]
警报|包含与事件相关的所有警报以及其他信息（如严重性、警报中涉及的实体以及警报来源）的数组。|\[\] (以下警报字段的详细信息) 

### <a name="alerts-metadata"></a>警报元数据

字段名|说明|示例值
---|---|---
alertId|表示警报的唯一标识符|caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId|表示与此警报关联的事件的唯一标识符|924565
serviceSource|警报源自的服务，例如 Microsoft Defender for Endpoint、Microsoft Defender for Cloud Apps、Microsoft Defender for Identity 或 Microsoft Defender for Office 365。|MicrosoftCloudAppSecurity
creationTime|首次创建警报的时间。|2020-09-06T14：46：55.7182276Z
lastUpdatedTime|上次在后端更新警报的时间。|2020-09-06T14：46：57.2433333Z
resolvedTime|警报解决的时间。|2020-09-10T05：22：59Z
firstActivity|警报首次报告在后端更新活动的时间。|2020-09-04T05：22：59Z
title|简要标识可用于每个警报的字符串值。|勒索软件活动
说明|描述每个警报的字符串值。|用户 Test User2 (testUser2@contoso.com) 处理了 99 个扩展名以不常见的扩展 *名 herunterladen 结尾的文件*。 这是异常多的文件操作，是潜在勒索软件攻击的表示。
“类别”|有关攻击在击杀链上的进度的可视和数值视图。 与 [MITRE ATT&CK™一致](https://attack.mitre.org/)。|影响
状态|将警报分类为 *(、活动或* 已解决 *) 。* 它可以帮助你组织和管理对警报的响应。|新增
severity|指示对资产可能的影响。 严重性越高，影响越大。 通常，严重性级别较高的项目需要最直接的关注。<br>下列值之一 *：Informational、Low、Medium* 和 *High。* |中
investigationId|此警报触发的自动调查 ID。|1234
investigationState|有关调查的当前状态的信息。 下列值之一：Unknown、Terminated、SuccessfullyRemediated、Successfully、Failed、PartiallyRemediated、Running、PendingApproval、PendingResource、PartiallyInvestigated、TerminatedByUser、TerminatedBySystem、Queued、InnerFailure、PreexistingAlert、UnsupportedOs、UnsupportedAlertType 、                  *SuppressedAlert*。|UnsupportedAlertType
classification|事件的规范。 属性值包括：Unknown、FalsePositive、TruePositive 或 null   |未知
确定|指定事件的确定。 属性值包括：NotAvailable、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware、Other或 null      |Apt
assignedTo|事件的所有者;如果没有分配 *所有者* ，则为空。|secop2@contoso.com
actorName|与此警报关联的活动组（如果有）。|一个
threatFamilyName|与此警报关联的威胁系列。|空
mitreTechniques|攻击技术，与 [MITRE ATT](https://attack.mitre.org/)和 CK&CK ™一致。|\[\]
设备|已发送与事件相关的警报的所有设备。|\[\] (下面实体字段的详细信息) 

### <a name="device-format"></a>设备格式

字段名|说明|示例值
---|---|---
DeviceId|在 Microsoft Defender for Endpoint 中指定的设备 ID。|24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId|中指定的设备 ID [Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-whatis) 仅适用于已加入域的设备。|空
deviceDnsName|设备的完全限定域名。|user5cx.middleeast.corp.contoso.com
osPlatform|设备正在运行的操作系统平台。|WindowsServer2016
osBuild|设备正在运行的操作系统的生成版本。|14393
rbacGroupName|基于 [角色的访问控制 (](/azure/role-based-access-control/overview) 与) 关联的 RBAC 组。|WDATP-Ring0
firstSeen|首次看到设备的时间。|2020-02-06T14：16：01.9330135Z
healthStatus|设备的运行状况。|活动
riskScore|设备的风险评分。|高
entities|已标识为给定警报的一部分或与给定警报相关的所有实体。|\[\] (下面实体字段的详细信息) 

### <a name="entity-format"></a>实体格式

字段名|说明|示例值
---|---|---
entityType|已标识为给定警报的一部分或与给定警报相关的实体。<br>属性值包括：User、Ip、Url、File、Process、MailBox、MailMessage、MailCluster、Registry         |用户
sha1|如果 entityType 为 File ， *则可用*。<br>与文件或进程关联的警报的文件哈希。|5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256|如果 entityType 为 File ， *则可用*。<br>与文件或进程关联的警报的文件哈希。|28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName|如果 entityType 为 File ， *则可用*。<br>与文件或进程关联的警报的文件名|Detector.UnitTests.dll
filePath|如果 entityType 为 File ， *则可用*。<br>与文件或进程关联的警报的文件路径|C： \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId|如果 entityType 为 Process ， *则可用*。|24348
processCommandLine|如果 entityType 为 Process ， *则可用*。|"你的文件已准备好下载 \_1911150169.exe"
processCreationTime|如果 entityType 为 Process ， *则可用*。|2020-07-18T03：25：38.5269993Z
parentProcessId|如果 entityType 为 Process ， *则可用*。|16840
parentProcessCreationTime|如果 entityType 为 Process ， *则可用*。|2020-07-18T02：12：32.8616797Z
ipAddress|如果 entityType 为 *Ip，则可用*。 <br>与网络事件关联的警报（如到恶意网络目标的通信）的 IP *地址*。|62.216.203.204
url|如果 entityType 为 *Url，则可用*。 <br>与网络事件（例如，到恶意网络目标的通信）*关联的警报的 URL。*|down.esales360.cn
accountName|如果 entityType 为 User ， *则可用*。|testUser2
domainName|如果 entityType 为 User ， *则可用*。|europe.corp.contoso
userSid|如果 entityType 为 User ， *则可用*。|S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId|如果 entityType 为 User ， *则可用*。|fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName|如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。|testUser2@contoso.com
mailboxDisplayName|如果 entityType 为 *MailBox ，则可用*。|test User2
mailboxAddress|如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。|testUser2@contoso.com
clusterBy|如果 entityType 为  *MailCluster，则可用*。|主题;P2SenderDomain;ContentType
sender|如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。|user.abc@mail.contoso.co.in
recipient|如果 entityType 为 *MailMessage ，则可用*。|testUser2@contoso.com
subject|如果 entityType 为 *MailMessage ，则可用*。|\[外部 \] 关注
deliveryAction|如果 entityType 为 *MailMessage ，则可用*。|已传递
securityGroupId|如果 entityType 为  *SecurityGroup，则可用*。|301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName|如果 entityType 为  *SecurityGroup，则可用*。|网络配置运算符
registryHive|如果 entityType 为  *Registry ，则可用*。|HKEY \_ 本地 \_ 计算机|
registryKey|如果 entityType 为  *Registry ，则可用*。|SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType|如果 entityType 为  *Registry ，则可用*。|String
registryValue|如果 entityType 为  *Registry ，则可用*。|31-00-00-00
deviceId|与实体相关的设备的 ID（如果有）。|986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

### <a name="response-example"></a>响应示例

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>相关文章

- [访问Microsoft 365 Defender API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [事件概述](incidents-overview.md)
- [事件 API](api-incident.md)
- [更新事件 API](api-update-incidents.md)
