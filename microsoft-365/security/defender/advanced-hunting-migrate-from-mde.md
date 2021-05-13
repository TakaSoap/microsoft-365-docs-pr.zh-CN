---
title: 从 Microsoft Defender for Endpoint 迁移高级搜寻查询
description: 了解如何调整适用于终结点的 Microsoft Defender 查询，以便可以在 Microsoft 365 Defender 中使用它们
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 适用于终结点的 Microsoft Defender， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， 映射
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470684"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>从 Microsoft Defender for Endpoint 迁移高级搜寻查询

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

从 Microsoft Defender for Endpoint 移动高级搜寻工作流，以使用更广泛的数据集主动搜寻威胁。 在 Microsoft 365 Defender 中，你可以访问来自其他安全Microsoft 365解决方案的数据，包括：

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>大多数 Microsoft Defender for Endpoint 客户可以使用[Microsoft 365 Defender，而无需额外的许可证](prerequisites.md#licensing-requirements)。 若要开始从 Defender for Endpoint 转换高级搜寻工作流，[请Microsoft 365 Defender。](m365d-enable.md)

你可以转换，而不影响现有的 Defender for Endpoint 工作流。 保存的查询保持不变，并且自定义检测规则将继续运行并生成警报。 但是，它们在 Defender 中Microsoft 365可见。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>仅 defender 中的Microsoft 365表
Microsoft 365 [Defender 高级搜寻架构](advanced-hunting-schema-tables.md)提供包含来自各种安全解决方案的数据Microsoft 365表。 下表仅适用于 Microsoft 365 Defender：

| 表名 | 说明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 与警报关联的文件、IP 地址、URL、用户或设备 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | 来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的警报，包括严重性信息和威胁类别  |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 有关附加到电子邮件的文件的信息 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365电子邮件事件，包括电子邮件传递和阻止事件 |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | 邮件送达后发生的安全事件Microsoft 365将电子邮件传递到收件人邮箱之后 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 有关电子邮件 URL 的信息 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | 涉及运行 Active Directory 和 AD (本地域控制器) 。 此表涵盖域控制器上一系列与标识相关的事件和系统事件。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | 来自各种源的帐户信息，包括Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 和 Microsoft 联机服务上的身份验证事件 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | 对 Active Directory 对象的查询，例如用户、组、设备和域 |

>[!IMPORTANT]
> 使用仅在 Microsoft 365 Defender 中可用的架构表的查询和自定义检测只能在 Microsoft 365 Defender 中查看。

## <a name="map-devicealertevents-table"></a>映射 DeviceAlertEvents 表
和 `AlertInfo` `AlertEvidence` 表替换 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的表。 除了有关设备警报的数据，这两个表还包括有关标识、应用和电子邮件警报的数据。

使用下表检查列 `DeviceAlertEvents` 如何映射到 和 表中的 `AlertInfo` `AlertEvidence` 列。

>[!TIP]
>除了下表中的列之外，该表还包含许多其他列，这些列提供来自各种源的警报的更全面的 `AlertEvidence` 图片。 [查看所有 AlertEvidence 列](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 列 | 在 Defender 中查找相同数据Microsoft 365位置 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` 和  `AlertEvidence` 表 |
| `Timestamp` | `AlertInfo` 和  `AlertEvidence` 表 |
| `DeviceId` | `AlertEvidence` table |
| `DeviceName` | `AlertEvidence` table |
| `Severity` | `AlertInfo` table |
| `Category` | `AlertInfo` table |
| `Title` | `AlertInfo` table |
| `FileName` | `AlertEvidence` table |
| `SHA1` | `AlertEvidence` table |
| `RemoteUrl` | `AlertEvidence` table |
| `RemoteIP` | `AlertEvidence` table |
| `AttackTechniques` | `AlertInfo` table |
| `ReportId` | 此列通常在 Microsoft Defender for Endpoint 中用于查找其他表中的相关记录。 在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 数据。 |
| `Table` | 此列通常在 Microsoft Defender for Endpoint 中用于其他表中的其他事件信息。 在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 数据。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>调整现有的 Microsoft Defender 终结点查询
Microsoft Defender for Endpoint 查询将像现在一样工作，除非它们引用 `DeviceAlertEvents` 表。 若要在 Defender 中使用这些Microsoft 365，请应用以下更改：

- 将 `DeviceAlertEvents` 替换为 `AlertInfo` 。
- 将 `AlertInfo` 和 表 `AlertEvidence` 联接在 一 `AlertId` 起可获取等效数据。

### <a name="original-query"></a>原始查询
以下查询使用 `DeviceAlertEvents` Microsoft Defender for Endpoint 获取涉及以下powershell.exe： __

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>修改后的查询
以下查询已调整为在 Microsoft 365 Defender 中使用。 它联接并检查该表中的文件名，而不是直接从 `DeviceAlertEvents` `AlertEvidence` 中检查文件名。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>迁移自定义检测规则

当 Microsoft Defender for Endpoint 规则在 Microsoft 365 Defender 上编辑时，它们将继续像以前一样运行，就像生成的查询仅查看设备表一样。 

例如，由仅查询设备表的自定义检测规则生成的警报将继续传递到 SIEM 并生成电子邮件通知，具体取决于你在 Microsoft Defender for Endpoint 中配置这些警报的方式。 Defender for Endpoint 中现有的抑制规则也将继续适用。

编辑 Defender for Endpoint 规则以便查询仅在 Microsoft 365 Defender 中可用的标识和电子邮件表后，该规则将自动移动到 Microsoft 365 Defender。 

由迁移的规则生成的警报：

- 在 Defender for Endpoint 门户门户中不再 (Microsoft Defender 安全中心) 
- 停止传递到 SIEM 或生成电子邮件通知。 若要解决此更改，请通过 Microsoft 365 Defender 配置通知，获取警报。 可以使用 Microsoft 365 [Defender API](api-incident.md)接收有关客户检测警报或相关事件的通知。
- Microsoft Defender 的终结点抑制规则不会抑制。 若要阻止为某些用户、设备或邮箱生成警报，请修改相应的查询以明确排除这些实体。

如果您这样编辑规则，则系统会在应用此类更改之前提示您进行确认。

Defender 门户中的自定义检测规则生成的新Microsoft 365显示在提供以下信息的警报页面中：

- 警报标题和说明 
- 影响的资产
- 为响应警报而采取的操作
- 触发警报的查询结果 
- 有关自定义检测规则的信息 
 
> [!div class="mx-imgBorder"]
> ![新警报页面的图像](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>编写不含 DeviceAlertEvents 的查询

在 Microsoft 365 Defender 架构中，提供 和 表以适应来自各种来源的警报附带的 `AlertInfo` `AlertEvidence` 各种信息集。 

若要获取用于从 Microsoft Defender for Endpoint 架构中的表获取的相同警报信息，请按筛选表，然后将每个唯一 ID 与表联接，该表提供详细的事件和 `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` 实体信息。 

请参阅下面的示例查询：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

此查询生成列数多于 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的列数。 若要使结果可管理，请使用 `project` 仅获取感兴趣的列。 下面的示例将规划调查检测到 PowerShell 活动时可能感兴趣的列：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

如果要筛选警报中涉及的特定实体，可以通过指定 中的实体类型和要筛选 `EntityType` 的值来这样做。 以下示例查找特定的 IP 地址：

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>另请参阅
- [打开 Microsoft 365 Defender](advanced-hunting-query-language.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [Microsoft Defender for Endpoint 中的高级搜寻](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)