---
title: Microsoft 威胁防护中的列表事件 API
description: 了解如何在 Microsoft 威胁防护中列出事件 API
keywords: 列表、事件、事件、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775107"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的列表事件 API

**适用于：**

- Microsoft 威胁防护

> [!IMPORTANT]
> 一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API 说明

事件 API 允许您对事件进行排序，以确定优先级并创建有通知的 cybersecurity 响应。 它公开在环境保留策略中指定的时间范围内，在网络中的设备、电子邮件帐户和用户中标记的事件的集合。 最近的事件显示在列表的顶部。 每个事件包含一系列相关警报及其相关的实体。

<br>API 支持以下 **OData** 运算符：
<br>```$filter``` 打开： ```lastUpdateTime``` 、 ```createdTime``` ```status``` 和 ```assignedTo``` 属性。
<br>```$top``` 最大值为 **100**
<br>```$skip```

## <a name="limitations"></a>限制

1. 页面大小的最大值为 **100 个事件**。
2. 请求的最大速率为 **每分钟50个呼叫** 和 **每小时的1500个呼叫**。

## <a name="permissions"></a>权限

若要调用此 API，必须有以下权限之一。 若要了解详细信息，包括如何选择权限，请参阅 [Access Microsoft 威胁 Protection api](api-access.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   事件：全部已读。所有 | "读取所有事件"
应用程序 |   事件 ReadWrite。 All | ' 读取和写入所有事件 '
委派（工作或学校帐户） | 事件。阅读 | "读取事件"
委派（工作或学校帐户） | 事件读写 | "读取和写入事件"

> [!Note]
> 使用用户凭据获取令牌时：
> - 用户需要具有门户中的事件的 "查看" 权限。
> - 响应将仅包括用户向其公开的事件。

## <a name="http-request"></a>HTTP 请求

```
GET /api/incidents
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | 持有者 {令牌}。 **** 必需。


## <a name="request-body"></a>请求正文
无。

## <a name="response"></a>响应
如果成功，此方法将返回 200 OK，以及响应正文中的 [事件](api-incident.md) 列表。

## <a name="schema-mapping"></a>架构映射

| 字段名                                | 说明                                                                                                                                                                                                                                                                                                                                                                                | 示例值                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **事件元数据**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| incidentId                                | 代表事件的唯一标识符。                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | 仅在事件处理逻辑过程中，将事件与另一个事件组合在一起时才填充。                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| incidentName                              | 可用于每个事件的字符串值。                                                                                                                                                                                                                                                                                                                                                  | 勒索软件活动                                                                                                                                                                                                                               |
| createdTime                               | 首次创建事件的时间。                                                                                                                                                                                                                                                                                                                                                      | 2020-06T14：46： 57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | 后端事件最后更新的时间。<br> 在为事件的检索时间范围设置 request 参数时，可以使用此字段。                                                                                                                                                                                                                      | 2020-06T14：46： 57.29 Z                                                                                                                                                                                                                           |
| assignedTo                                | 事件的所有者或 *null* （如果未分配所有者）。                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| classification                            | 事件的规范。 属性值为： *Unknown*、 *FalsePositive*、 *TruePositive*                                                                                                                                                                                                                                                                           | 未知                                                                                                                                                                                                                                           |
| 可用性                             | 指定事件的确定。 属性值为： *NotAvailable*、 *Apt.*、 *恶意软件*、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *其他*                                                                                                                                                                                                                | NotAvailable                                                                                                                                                                                                                                      |
| 状态                                    | 将事件分类 (为 *活动*或 *已解决*) 。 这可帮助您组织和管理对事件的响应。                                                                                                                                                                                                                                                                  | 活动                                                                                                                                                                                                                                            |
| severity                                  | 指示可能对资产产生的影响。 严重度越高，影响越大。 通常情况下，严重级别较高的项目需要最直接的关注。<br>以下值之一： *信息*、 *低*、* 中和 *高*。                                                                                                                                | 中                                                                                                                                                                                                                                            |
| tags                                      | 与事件相关联的自定义标记的数组，例如，用于标记具有共同特征的一组事件。                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| 警报                                    | 与事件相关的所有警报和其他信息（如严重性、警报中涉及的实体）的数组以及警报的来源。                                                                                                                                                                                                                     | \[\] (查看以下警报字段的详细信息)                                                                                                                                                                                                           |
| **警报元数据**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| alertId                                   | 代表警报的唯一标识符                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| incidentId                                | 代表与此通知关联的事件的唯一标识符                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| serviceSource                             | 通知源于的服务，例如 Microsoft Defender ATP、Microsoft 云应用安全性、Azure ATP 或 Office 365 ATP。                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| creationTime                              | 首次创建警报的时间。                                                                                                                                                                                                                                                                                                                                                         | 2020-06T14：46： 55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | 后端最后更新警报的时间。                                                                                                                                                                                                                                                                                                                                           | 2020-06T14：46： 57.2433333 Z                                                                                                                                                                                                                      |
| resolvedTime                              | 解决警报的时间。                                                                                                                                                                                                                                                                                                                                                              | 2020-10T05：22：59Z                                                                                                                                                                                                                              |
| firstActivity                             | 警报第一次报告后端已更新活动的时间。                                                                                                                                                                                                                                                                                                                             | 2020-04T05：22：59Z                                                                                                                                                                                                                              |
| title                                     | 可用于每个警报的简短标识字符串值。                                                                                                                                                                                                                                                                                                                                                     | 勒索软件活动                                                                                                                                                                                                                               |
| description                               | 描述每个警报的字符串值。                                                                                                                                                                                                                                                                                                                                                        | 用户测试用户 2 (testUser2@contoso.com) 使用不常见扩展 *herunterladen*的多个扩展名结尾的99文件。 这是一种不寻常的文件操作，并表明存在潜在的勒索软件攻击。 |
| “类别”                                  | 对攻击在终止链中的进展程度的直观和数字视图。 与 [MITRE ATT&CK™ framework](https://attack.mitre.org/)对齐。                                                                                                                                                                                                                           | 影响                                                                                                                                                                                                                                            |
| 状态                                    | 将警报 (为 *新*的、 *活动*的或 *已解决* 的) 进行分类。 这可帮助您组织和管理对警报的响应。                                                                                                                                                                                                                                                                   | 新式部署                                                                                                                                                                                                                                               |
| severity                                  | 指示可能对资产产生的影响。 严重度越高，影响越大。 通常情况下，严重级别较高的项目需要最直接的关注。<br>以下值之一： *信息*、 *低*、* 中和 *高*。                                                                                                                                   | 中                                                                                                                                                                                                                                            |
| investigationId                           | 此警报触发的自动调查 id。                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | 有关调查的当前状态的信息。 下列项之一：*未知*、已*终止*、 *SuccessfullyRemediated*、*良性*、*失败*、 *PartiallyRemediated*、*正在运行*、 *PendingApproval*、 *PendingResource*、PartiallyInvestigated *、TerminatedByUser、TerminatedBySystem* *、**排队*、InnerFailure *、PreexistingAlert、UnsupportedOs* *、UnsupportedAlertType* *、SuppressedAlert* *、、*、、。 *PartiallyInvestigated* *InnerFailure* | UnsupportedAlertType                                                                                                                                                                                                                              |
| classification                            | 事件的规范。 属性值为： *Unknown*、 *FalsePositive*、 *TruePositive* 或 *null*                                                                                                                                                                                                                                                                   | 未知                                                                                                                                                                                                                                           |
| 可用性                             | 指定事件的确定。 属性值为： *NotAvailable*、 *Apt.*、 *恶意软件*、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *Other* 或  *null*                                                                                                                                                                                                     | Apt.                                                                                                                                                                                                                                               |
| assignedTo                                | 事件的所有者或 *null* （如果未分配所有者）。                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actorName                                 | 与此通知关联的活动组（如果有）。                                                                                                                                                                                                                                                                                                                                        | BORON                                                                                                                                                                                                                                             |
| threatFamilyName                          | 与此警报关联的威胁系列。                                                                                                                                                                                                                                                                                                                                                   | 空                                                                                                                                                                                                                                              |
| mitreTechniques                           | 与 [MITRE ATT&CK](https://attack.mitre.org/)™框架相一致的攻击技术。                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| 驱动器                                   | 发送与事件相关的警报的所有设备。                                                                                                                                                                                                                                                                                                     | \[\] (查看以下实体字段的详细信息)                                                                                                                                                                                                          |
| **设备格式**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | 在 Microsoft Defender ATP 中指定的设备 ID。                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD) 中指定的设备 Id。 仅适用于加入域的设备。                                                                                                                                                                                                                                                                                                                              | 空                                                                                                                                                                                                                                              |
| deviceDnsName                             | 设备的完全限定的域名称。                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | 设备正在运行的操作系统平台。                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | 设备正在运行的操作系统的内部版本。                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | [基于角色的访问控制](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) 组与设备相关联。                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | 首次看到设备时的时间。                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06T14：16： 01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | 设备的运行状况状态。                                                                                                                                                                                                                                                                                                                                                                        | 活动                                                                                                                                                                                                                                            |
| riskScore                                 | 设备的风险分数。                                                                                                                                                                                                                                                                                                                                                                       | 高                                                                                                                                                                                                                                              |
| 实体                                  | 已标识为给定警报的一部分或与之相关的所有实体。                                                                                                                                                                                                                                                                                | \[\] (查看以下实体字段的详细信息)                                                                                                                                                                                                          |
| **实体格式**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| entityType                                | 已标识为给定警报的一部分或与之相关的实体。<br>属性值为： *User*、 *Ip*、 *Url*、 *File*、 *Process*、 *邮箱*、 *MailMessage*、 *MailCluster*、 *Registry*                                                                                                                                                                                                     | User                                                                                                                                                                                                                                              |
| sha1                                      | 如果 entityType 是 *文件*，则可用。<br>与文件或进程相关联的警报的文件哈希。                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| sha256                                    | 如果 entityType 是 *文件*，则可用。<br>与文件或进程相关联的警报的文件哈希。                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| fileName                                  | 如果 entityType 是 *文件*，则可用。<br>与文件或进程相关联的警报的文件名                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| 路径                                  | 如果 entityType 是 *文件*，则可用。<br>与文件或进程相关联的警报的文件路径                                                                                                                                                                                                                                                                                    | C： \\ \\ 代理 \\ \\ \_ 工作 \\ \\ \_ 临时 \\ \\ 部署 \_ 系统 2020-09-06 12 \_ 14 \_ 54 \\ \\ 输出                                                                                                                                                                    |
| processId                                 | 如果 entityType 为 *进程*，则为可用。                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | 如果 entityType 为 *进程*，则为可用。                                                                                                                                                                                                                                                                                                                                                     | " \\ " 您的文件已准备好下载 \_1911150169.exe\\ ""                                                                                                                                                                                           |
| processCreationTime                       | 如果 entityType 为 *进程*，则为可用。                                                                                                                                                                                                                                                                                                                                                     | 2020-18T03：25： 38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | 如果 entityType 为 *进程*，则为可用。                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | 如果 entityType 为 *进程*，则为可用。                                                                                                                                                                                                                                                                                                                                                     | 2020-18T02：12： 32.8616797 Z                                                                                                                                                                                                                      |
| ipAddress                                 | 如果 entityType 为 *Ip*，则可用。 <br>与网络事件相关联的警报的 IP 地址，例如 *与恶意网络目标的通信*。                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| url                                       | 如果 entityType 为 *Url*，则可用。 <br>与网络事件相关联的警报的 Url，例如， *与恶意网络目标的通信*。                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| 帐户                               | 如果 entityType 是 *用户*，则可用。                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| domainName                                | 如果 entityType 是 *用户*，则可用。                                                                                                                                                                                                                                                                                                                                                        | 欧洲公司                                                                                                                                                                                                                              |
| userSid                                   | 如果 entityType 是 *用户*，则可用。                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | 如果 entityType 是 *用户*，则可用。                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | 如果 entityType 是*用户* / *邮箱* / *MailMessage*，则可用。                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | 如果 entityType 为 *邮箱*，则可用。                                                                                                                                                                                                                                                                                                                                                     | 测试的您                                                                                                                                                                                                                                        |
| mailboxAddress                            | 如果 entityType 是*用户* / *邮箱* / *MailMessage*，则可用。                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | 如果 entityType 为  *MailCluster*，则可用。                                                                                                                                                                                                                                                                                                                                                 | 遵照P2SenderDomain;ContentType                                                                                                                                                                                                                |
| sender                                    | 如果 entityType 是*用户* / *邮箱* / *MailMessage*，则可用。                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| recipient                                 | 如果 entityType 为 *MailMessage*，则可用。                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| subject                                   | 如果 entityType 为 *MailMessage*，则可用。                                                                                                                                                                                                                                                                                                                                                 | \[外部 \] 注意事项                                                                                                                                                                                                                            |
| deliveryAction                            | 如果 entityType 为 *MailMessage*，则可用。                                                                                                                                                                                                                                                                                                                                                 | 附带                                                                                                                                                                                                                                         |
| securityGroupId                           | 如果 entityType 为  *SecurityGroup*，则可用。                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-ab09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | 如果 entityType 为  *SecurityGroup*，则可用。                                                                                                                                                                                                                                                                                                                                               | 网络配置操作员                                                                                                                                                                                                                   |
| registryHive                              | 如果 entityType 为  *注册表*，则可用。                                                                                                                                                                                                                                                                                                                                                    | HKEY \_ 本地 \_ 计算机                                                                                                                                                                                                                              |
| registryKey                               | 如果 entityType 为  *注册表*，则可用。                                                                                                                                                                                                                                                                                                                                                     | 软件 \\ \\ MICROSOFT \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | 如果 entityType 为  *注册表*，则可用。                                                                                                                                                                                                                                                                                                                                                    | String                                                                                                                                                                                                                                            |
| registryValue                             | 如果 entityType 为  *注册表*，则可用。                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | 与实体相关的设备的 ID （如果有）。                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>示例

**请求**

```
GET https://api.security.microsoft.com/api/incidents
```

**响应**
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

## <a name="related-topic"></a>相关主题
- [事件 Api](api-incident.md)
- [更新事件](api-update-incidents.md)
