---
title: 从 Microsoft Defender for Endpoint 迁移高级搜寻查询
description: 了解如何调整适用于终结点查询的 Microsoft Defender，以便可以在 Microsoft 365 Defender 中使用它们
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， microsoft defender atp， mdatp， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， microsoft 365， 映射
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080732"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>从 Microsoft Defender for Endpoint 迁移高级搜寻查询

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

从 Microsoft Defender for Endpoint 移动高级搜寻工作流，以使用更广泛的数据集主动搜寻威胁。 在 Microsoft 365 Defender 中，你可以访问来自其他 Microsoft 365 安全解决方案的数据，包括：

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>大多数适用于终结点的 Microsoft Defender 客户可以使用 [Microsoft 365 Defender，而无需其他许可证](prerequisites.md#licensing-requirements)。 若要开始从 Defender for Endpoint 转换高级搜寻工作流，[请打开 Microsoft 365 Defender。](mtp-enable.md)

你可以转换，而不会影响现有的 Defender for Endpoint 工作流。 保存的查询保持不变，并且自定义检测规则将继续运行并生成警报。 但是，它们将在 Microsoft 365 Defender 中可见。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>仅适用于 Microsoft 365 Defender 中的架构表
[Microsoft 365 Defender 高级搜寻架构](advanced-hunting-schema-tables.md)提供包含各种 Microsoft 365 安全解决方案数据的其他表。 下表仅适用于 Microsoft 365 Defender：

| 表名 | 说明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 与警报关联的文件、IP 地址、URL、用户或设备 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | 来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的警报，包括严重性信息和威胁类别  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | 云应用和服务中的文件相关活动 |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 有关附加到电子邮件的文件的信息 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 电子邮件事件，包括电子邮件传递和阻止事件 |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | 在 Microsoft 365 将电子邮件传递到收件人邮箱后发生的安全事件 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 有关电子邮件 URL 的信息 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | 涉及运行 Active Directory 本地域控制器的事件 (AD) 。 此表涵盖域控制器上与标识相关的一系列事件和系统事件。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | 来自各种源的帐户信息，包括 Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 和 Microsoft 联机服务上的身份验证事件 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | 对 Active Directory 对象（如用户、组、设备和域）的查询 |

## <a name="map-devicealertevents-table"></a>映射 DeviceAlertEvents 表
和 `AlertInfo` `AlertEvidence` 表替换了 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的表。 除了有关设备警报的数据，这两个表还包括有关标识、应用和电子邮件警报的数据。

使用下表检查列 `DeviceAlertEvents` 如何映射到和表中的 `AlertInfo` `AlertEvidence` 列。

>[!TIP]
>除了下表中的列之外，该表还包含许多其他列，这些列提供来自各种源的警报的更全面的 `AlertEvidence` 图片。 [查看所有 AlertEvidence 列](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 列 | 在哪里可以找到 Microsoft 365 Defender 中的相同数据 |
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
| `ReportId` | 此列通常在 Microsoft Defender for Endpoint 中用于查找其他表中的相关记录。 在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。 |
| `Table` | 此列通常在 Microsoft Defender for Endpoint 中用于其他表中的其他事件信息。 在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>调整现有的 Microsoft Defender 终结点查询
Microsoft Defender for Endpoint 查询将正常工作，除非它们引用 `DeviceAlertEvents` 该表。 若要在 Microsoft 365 Defender 中使用这些查询，请应用这些更改：

- 替换为 `DeviceAlertEvents` `AlertInfo` 。
- 将 `AlertInfo` 和表 `AlertEvidence` 联接在一起 `AlertId` 可获取等效数据。

### <a name="original-query"></a>原始查询
以下查询在 `DeviceAlertEvents` Microsoft Defender for Endpoint 中用于获取涉及以下powershell.exe：

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>修改后的查询
以下查询已调整为在 Microsoft 365 Defender 中使用。 它联接并检查该表中的文件名，而不是直接 `DeviceAlertEvents` `AlertEvidence` 检查文件名。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>迁移自定义检测规则

在 Microsoft 365 Defender 上编辑 Microsoft Defender for Endpoint 规则时，它们将继续像以前一样运行，就像生成的查询仅查看设备表一样。 例如，由仅查询设备表的自定义检测规则生成的警报将继续传递到 SIEM 并生成电子邮件通知，具体取决于你在 Microsoft Defender for Endpoint 中配置它们的方式。 Defender for Endpoint 中的任何现有抑制规则也将继续适用。

编辑 Defender for Endpoint 规则以便查询仅在 Microsoft 365 Defender 中可用的标识和电子邮件表后，该规则将自动移动到 Microsoft 365 Defender。 

由迁移的规则生成的警报：

- 在 Microsoft Defender 安全中心 (Defender for Endpoint 门户中不再) 
- 停止传递到 SIEM 或生成电子邮件通知。 若要解决此更改，请通过 Microsoft 365 Defender 配置通知，获取警报。 可以使用 Microsoft [365 Defender API](api-incident.md) 接收客户检测警报或相关事件的通知。
- Microsoft Defender 不会针对终结点抑制规则进行抑制。 若要阻止为某些用户、设备或邮箱生成警报，请修改相应的查询以明确排除这些实体。

如果通过此方式编辑规则，将在应用此类更改之前提示您进行确认。

Microsoft 365 Defender 门户中的自定义检测规则生成的新警报显示在提供以下信息的警报页面中：

- 警报标题和说明 
- 受影响的资产
- 为响应警报而采取的操作
- 触发警报的查询结果 
- 有关自定义检测规则的信息 
 
![新警报页面的图像](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a>编写不含 DeviceAlertEvents 的查询

在 Microsoft 365 Defender 架构中，提供和表以适应各种来源的警报附带的 `AlertInfo` `AlertEvidence` 一组不同信息。 

若要获取用于从 Microsoft Defender for Endpoint 架构中的表获取的相同警报信息，请筛选该表，然后将每个唯一 ID 与表联接，该表提供详细的事件和 `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` 实体信息。 

请参阅下面的示例查询：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

此查询产生列数多于 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的列数。 若要使结果易于管理，请使用 `project` 仅获取感兴趣的列。 下面的示例对调查检测到 PowerShell 活动时您可能感兴趣的列进行规划：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

如果要筛选警报中涉及的特定实体，可以通过指定要筛选的实体类型和值 `EntityType` 来这样做。 以下示例查找特定的 IP 地址：

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
- [Microsoft Defender for Endpoint 中的高级搜寻](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)