---
title: 从 Microsoft Defender for Endpoint 迁移高级搜寻查询
description: 了解如何调整 Microsoft Defender for Endpoint 查询，以便你可以在 Microsoft 365 Defender 中使用它们
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、microsoft defender atp、mdatp、search、query、遥测、自定义检测、架构、kusto、microsoft 365、映射
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846852"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>从 Microsoft Defender for Endpoint 迁移高级搜寻查询

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

通过 Microsoft Defender for Endpoint 移动高级的求职工作流，以使用更广泛的数据集主动查找威胁。 在 Microsoft 365 Defender 中，你可以访问其他 Microsoft 365 安全解决方案中的数据，包括：

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>大多数 Microsoft Defender for Endpoint 客户可以 [使用 Microsoft 365 Defender，而无需其他许可证](prerequisites.md#licensing-requirements)。 若要开始从 Defender for Endpoint 转换你的高级求职工作流，请 [打开 Microsoft 365 Defender](mtp-enable.md)。

你可以在不影响现有 Defender 的终结点工作流的情况下进行转换。 保存的查询保持不变，自定义检测规则将继续运行并生成警报。 但是，它们将在 Microsoft 365 Defender 中可见。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>仅限 Microsoft 365 Defender 中的架构表
[Microsoft 365 Defender 高级搜寻架构](advanced-hunting-schema-tables.md)提供了其他表格，其中包含来自各种 Microsoft 365 安全解决方案的数据。 以下表格仅适用于 Microsoft 365 Defender：

| 表名 | 说明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 与警报关联的文件、IP 地址、Url、用户或设备 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | 来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft 云应用安全性和 Microsoft Defender for Identity 的警报，包括严重信息和威胁类别  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | 云应用和服务中与文件相关的活动 |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 有关附加到电子邮件的文件的信息 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 电子邮件事件，包括电子邮件传递和阻止事件 |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | 在 Microsoft 365 将电子邮件传递给收件人邮箱之后，在送达后发生的安全事件 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 有关电子邮件上的 Url 的信息 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | 涉及运行 Active Directory (AD) 的本地域控制器的事件。 此表涵盖了域控制器上与标识相关的事件和系统事件的范围。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | 来自各种源（包括 Azure Active Directory）的帐户信息 |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 和 Microsoft online services 上的身份验证事件 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | 对 Active Directory 对象（如用户、组、设备和域）的查询 |

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents 表
`AlertInfo`和 `AlertEvidence` 表将替换 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的表。 除了有关设备警报的数据之外，这两个表还包括有关标识、应用和电子邮件的警报的数据。

使用下表可检查列如何 `DeviceAlertEvents` 映射到和表中的 `AlertInfo` 列 `AlertEvidence` 。

>[!TIP]
>除了下表中的列， `AlertEvidence` 该表还包含许多其他列，这些列提供了来自各种源的更全面的警报。 [查看所有 AlertEvidence 列](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 列 | 在 Microsoft 365 Defender 中查找相同数据的位置 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` 和  `AlertEvidence` 表 |
| `Timestamp` | `AlertInfo` 和  `AlertEvidence` 表 |
| `DeviceId` | `AlertEvidence` 型 |
| `DeviceName` | `AlertEvidence` 型 |
| `Severity` | `AlertInfo` 型 |
| `Category` | `AlertInfo` 型 |
| `Title` | `AlertInfo` 型 |
| `FileName` | `AlertEvidence` 型 |
| `SHA1` | `AlertEvidence` 型 |
| `RemoteUrl` | `AlertEvidence` 型 |
| `RemoteIP` | `AlertEvidence` 型 |
| `AttackTechniques` | `AlertInfo` 型 |
| `ReportId` | 此列通常用于在 Microsoft Defender for Endpoint 中查找其他表中的相关记录。 在 Microsoft 365 Defender 中，可以直接从表中获取相关数据 `AlertEvidence` 。 |
| `Table` | 此列通常在 Microsoft Defender for Endpoint 中用于其他表中的其他事件信息。 在 Microsoft 365 Defender 中，可以直接从表中获取相关数据 `AlertEvidence` 。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>调整现有 Microsoft Defender for Endpoint 查询
Microsoft Defender for Endpoint 查询将正常工作，除非它们引用 `DeviceAlertEvents` 表。 若要在 Microsoft 365 Defender 中使用这些查询，请应用以下更改：

- 替换 `DeviceAlertEvents` 为 `AlertInfo` 。
- 联接 `AlertInfo` 和上的 `AlertEvidence` 表 `AlertId` 以获取等效数据。

### <a name="original-query"></a>原始查询
以下查询 `DeviceAlertEvents` 在 Microsoft Defender For Endpoint 中使用，以获取涉及 _powershell.exe_ 的警报：

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>修改的查询
以下查询已调整为在 Microsoft 365 Defender 中使用。 `DeviceAlertEvents`它将加入 `AlertEvidence` 并检查该表中的文件名，而不是直接从文件名签。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>相关主题
- [启用 Microsoft 365 Defender](advanced-hunting-query-language.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [Microsoft Defender for Endpoint 中的高级搜寻](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)