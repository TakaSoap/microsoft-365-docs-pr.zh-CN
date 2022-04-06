---
title: 从Microsoft Defender for Endpoint迁移高级搜寻查询
description: 了解如何调整Microsoft Defender for Endpoint查询，以便可以在Microsoft 365 Defender中使用它们
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、Microsoft 365 Defender、microsoft 365、m365、Microsoft Defender for Endpoint、搜索、查询、遥测、自定义检测、架构、kusto、映射
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 9fd00df5e61d37e5133f23e5f06973ceb99c4636
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666165"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>从Microsoft Defender for Endpoint迁移高级搜寻查询

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

将高级搜寻工作流从Microsoft Defender for Endpoint移动到使用更广泛的数据集主动搜寻威胁。 在Microsoft 365 Defender中，可以从其他Microsoft 365安全解决方案访问数据，包括：

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

>[!NOTE]
>大多数Microsoft Defender for Endpoint客户可以在[没有其他许可证的情况下使用Microsoft 365 Defender](prerequisites.md#licensing-requirements)。 若要开始从 Defender for Endpoint 转换高级搜寻工作流，[请打开Microsoft 365 Defender](m365d-enable.md)。

可以在不影响现有 Defender for Endpoint 工作流的情况下进行转换。 保存的查询保持不变，自定义检测规则继续运行并生成警报。 但是，它们将在Microsoft 365 Defender中可见。

## <a name="schema-tables-in-microsoft-365-defender-only"></a>仅Microsoft 365 Defender中的架构表

[Microsoft 365 Defender高级搜寻架构](advanced-hunting-schema-tables.md)提供了包含各种Microsoft 365安全解决方案中的数据的其他表。 以下表仅在Microsoft 365 Defender中可用：

| 表名 | 说明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 与警报关联的文件、IP 地址、URL、用户或设备 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | 来自Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps和Microsoft Defender for Identity的警报，包括严重性信息和威胁类别  |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 有关电子邮件所附文件的信息 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 电子邮件事件，包括电子邮件送达和阻止事件 |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | 在传递后所发生的安全事件，即在 Microsoft 365 将电子邮件传递给收件人邮箱后所发生的安全事件 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 有关电子邮件上 URL 的信息 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | 涉及运行 Active Directory (AD) 的本地域控制器事件。 该表包含一系列身份相关的事件以及域控制器上的系统事件。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | 来自不同来源的账户信息，包括 Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 和 Microsoft 联机服务上的身份验证事件 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Active Directory 对象的查询，例如用户、组、设备和域 |

>[!IMPORTANT]
> 只能在Microsoft 365 Defender中查看使用仅在Microsoft 365 Defender中使用的架构表的查询和自定义检测。

## <a name="map-devicealertevents-table"></a>映射 DeviceAlertEvents 表

表`AlertInfo`和`AlertEvidence`表替换`DeviceAlertEvents`Microsoft Defender for Endpoint架构中的表。 除了有关设备警报的数据外，这两个表还包括有关标识、应用和电子邮件警报的数据。

使用下表检查列如何`DeviceAlertEvents`映射到列和`AlertEvidence`表中的`AlertInfo`列。

> [!TIP]
> 除了下表中的列外， `AlertEvidence` 该表还包括许多其他列，这些列提供来自各种源的警报的更全面的图片。 [查看所有 AlertEvidence 列](advanced-hunting-alertevidence-table.md)

| DeviceAlertEvents 列 | 在何处查找相同数据Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` 和  `AlertEvidence` 表 |
| `Timestamp` | `AlertInfo` 和  `AlertEvidence` 表 |
| `DeviceId` | `AlertEvidence` 表 |
| `DeviceName` | `AlertEvidence` 表 |
| `Severity` | `AlertInfo` 表 |
| `Category` | `AlertInfo` 表 |
| `Title` | `AlertInfo` 表 |
| `FileName` | `AlertEvidence` 表 |
| `SHA1` | `AlertEvidence` 表 |
| `RemoteUrl` | `AlertEvidence` 表 |
| `RemoteIP` | `AlertEvidence` 表 |
| `AttackTechniques` | `AlertInfo` 表 |
| `ReportId` | 此列通常用于在Microsoft Defender for Endpoint中查找其他表中的相关记录。 在Microsoft 365 Defender中，可以直接从`AlertEvidence`表中获取相关数据。 |
| `Table` | 此列通常用于Microsoft Defender for Endpoint中的其他表中的其他事件信息。 在Microsoft 365 Defender中，可以直接从`AlertEvidence`表中获取相关数据。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>调整现有Microsoft Defender for Endpoint查询

Microsoft Defender for Endpoint查询将按样工作，除非它们引用表`DeviceAlertEvents`。 若要在Microsoft 365 Defender中使用这些查询，请应用以下更改：

- 将 `DeviceAlertEvents` 替换为 `AlertInfo`。
- 联接 `AlertInfo` 表和 `AlertEvidence` 表 `AlertId` 以获取等效数据。

### <a name="original-query"></a>原始查询

以下查询在Microsoft Defender for Endpoint中用于`DeviceAlertEvents`获取涉及 _powershell.exe的_ 警报：

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d)
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```

### <a name="modified-query"></a>修改后的查询

已调整以下查询以供Microsoft 365 Defender使用。 它不直接从 `DeviceAlertEvents`中检查文件名，而是联接 `AlertEvidence` 并检查该表中的文件名。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where AttackTechniques has "PowerShell (T1086)"
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>迁移自定义检测规则

在Microsoft 365 Defender上编辑Microsoft Defender for Endpoint规则时，如果生成的查询仅查看设备表，它们将继续像以前一样运行。

例如，自定义检测规则生成的仅查询设备表的警报将继续传递到 SIEM 并生成电子邮件通知，具体取决于你在Microsoft Defender for Endpoint中配置这些通知的方式。 Defender for Endpoint 中的任何现有抑制规则也将继续应用。

编辑 Defender for Endpoint 规则以便查询仅在Microsoft 365 Defender中可用的标识和电子邮件表后，该规则会自动移动到Microsoft 365 Defender。

迁移规则生成的警报：

- 在 Defender for Endpoint 门户中不再可见 (Microsoft Defender 安全中心) 
- 停止传递到 SIEM 或生成电子邮件通知。 若要解决此更改，请通过Microsoft 365 Defender配置通知以获取警报。 可以使用[Microsoft 365 Defender API](api-incident.md) 接收客户检测警报或相关事件的通知。
- 不会被Microsoft Defender for Endpoint抑制规则所抑制。 若要防止为某些用户、设备或邮箱生成警报，请修改相应的查询以显式排除这些实体。

如果以这种方式编辑规则，系统会提示你在应用此类更改之前进行确认。

Microsoft 365 Defender中自定义检测规则生成的新警报显示在提供以下信息的警报页中：

- 警报标题和说明
- 受影响的资产
- 响应警报时采取的操作
- 触发警报的查询结果
- 有关自定义检测规则的信息

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/new-alert-page.png" alt-text="显示自定义检测规则在Microsoft 365 Defender门户中生成的新警报的警报页示例" lightbox="../../media/new-alert-page.png":::

## <a name="write-queries-without-devicealertevents"></a>在没有 DeviceAlertEvents 的情况下编写查询

在Microsoft 365 Defender架构中`AlertInfo`，提供了这些和`AlertEvidence`表，以适应各种源警报随附的各种信息集。

若要获取用于从`DeviceAlertEvents`Microsoft Defender for Endpoint架构中的表获取的相同警报信息，请筛选`AlertInfo`表，`ServiceSource`然后将每个唯一 ID 与表联接`AlertEvidence`，该表提供详细的事件和实体信息。

请参阅下面的示例查询：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

此查询生成的列数多于`DeviceAlertEvents`Microsoft Defender for Endpoint架构中的列数。 若要使结果可管理，请使用 `project` 它来仅获取感兴趣的列。 以下示例将投影调查检测到 PowerShell 活动时可能感兴趣的列：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine
```

如果要筛选警报中涉及的特定实体，可以通过指定要筛选的实体类型 `EntityType` 和值来执行此操作。 以下示例查找特定的 IP 地址：

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
- [Microsoft Defender for Endpoint中的高级搜寻](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
