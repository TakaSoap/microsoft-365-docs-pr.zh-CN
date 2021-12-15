---
title: 高级搜寻架构中的 EmailEvents 表
description: 在高级搜寻架构的 EmailEvents 表中了解Microsoft 365电子邮件关联的事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， EmailEvents， 网络消息 ID， 发件人， 收件人， 附件 ID， 附件名称， 恶意软件裁定， 网络钓鱼裁定， 附件计数， 链接计数， url 计数
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: baf6e8d6d896e31b5092f7d2b8948bb7771382bd
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531515"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

高级 `EmailEvents` 搜寻[架构中的](advanced-hunting-overview.md)表包含有关在 Microsoft Defender for Office 365 上处理电子邮件的事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持的事件 (值) ，请使用 Defender for Cloud 中提供的内置 `ActionType` 架构参考。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | 记录事件的日期和时间 |
| `NetworkMessageId` | `string` | 由用户生成的电子邮件的唯一Microsoft 365 |
| `InternetMessageId` | `string` | 发送电子邮件系统设置的电子邮件的面向公众的标识符 |
| `SenderMailFromAddress` | `string` | “发件人”标题（又称为“信件发送方”或“返回路径地址”）中的发件人电子邮件地址 |
| `SenderFromAddress` | `string` | 发件人标题中的发件人电子邮件地址（电子邮件收件人在其电子邮件客户端上可以看到） |
| `SenderDisplayName` | `string` | 通讯簿中显示的发件人姓名，通常是给定或名字、中间名首字母和姓氏或姓氏的组合 |
| `SenderObjectId` | `string` |发件人帐户在邮件中的唯一Azure AD |
| `SenderMailFromDomain` | `string` | “发件人”标题（又称为“信件发送方”或“返回路径地址”）中的发件人域 |
| `SenderFromDomain` | `string` | 发件人标题中的发件人域（电子邮件收件人在其电子邮件客户端上可以看到） |
| `SenderIPv4` | `string` | 最近检测到的中继邮件的邮件服务器的 IPv4 地址 |
| `SenderIPv6` | `string` | 最近检测到的中继邮件的邮件服务器的 IPv6 地址 |
| `RecipientEmailAddress` | `string` | 收件人的电子邮件地址，或通讯组列表扩展后收件人的电子邮件地址 |
| `RecipientObjectId` | `string` | 电子邮件收件人的唯一标识符Azure AD |
| `Subject` | `string` | 电子邮件主题 |
| `EmailClusterId` | `string` | 基于对内容的启发式分析群集的相似电子邮件组的标识符 |
| `EmailDirection` | `string` | 电子邮件方向（相对于所在的网络）：入站、出站、组织内 |
| `DeliveryAction` | `string` | 电子邮件发送操作：已发送、已标记为垃圾邮件、已阻止或已替换 |
| `DeliveryLocation` | `string` | 发送电子邮件的位置：收件箱/文件夹、本地/外部、垃圾箱、隔离区、已失败、已弃用、已删除的邮件 |
| `ThreatTypes` | `string` | 关于电子邮件是否包含恶意软件、网络钓鱼或其他威胁的电子邮件筛选堆栈裁定 |
| `ThreatNames` | `string` |找到的恶意软件或其他威胁的检测名称 |
| `DetectionMethods` | `string` | 用于检测电子邮件中的恶意软件、网络钓鱼或其他威胁的方法 |
| `ConfidenceLevel` | `string` | 任何垃圾邮件或网络钓鱼裁定的可信度列表。 对于垃圾邮件，此列显示垃圾邮件可信度 (SCL) ，指示电子邮件是否被跳过 (-1) 、发现不是垃圾邮件 (0，1) 、被识别为可信度中等的垃圾邮件 (5，6) ，或发现为高可信度 (9) 的垃圾邮件。 对于网络钓鱼，此列显示可信度是"高"还是"低"。 |
| `EmailAction` | `string` | 基于筛选器裁定、策略和用户操作对电子邮件执行的最后操作：将邮件移到垃圾邮件文件夹、添加 X 标头、修改主题、重定向邮件、删除邮件、发送到隔离区、未执行任何操作、密件抄送邮件 |
| `EmailActionPolicy` | `string` | 生效的操作策略：反垃圾邮件高可信度、反垃圾邮件、反垃圾邮件批量邮件、反垃圾邮件、反垃圾邮件钓鱼、防钓鱼域模拟、防钓鱼用户模拟、防钓鱼欺骗、防钓鱼图形模拟、反恶意软件、安全附件、企业传输规则 (ETR) |
| `EmailActionPolicyGuid` | `string` | 确定最后邮件操作的策略的唯一标识符 |
| `AttachmentCount` | `int` | 电子邮件中的附件数目 |
| `UrlCount` | `int` | 电子邮件中的嵌入 URL 数目 |
| `EmailLanguage` | `string` | 检测到的电子邮件内容的语言 |
| `Connectors` | `string` | 定义组织邮件流和电子邮件路由方式的自定义说明 |
| `OrgLevelAction` | `string` | 为响应与组织级别定义的策略匹配而对电子邮件采取的操作 |
| `OrgLevelPolicy` | `string` | 触发对电子邮件采取的操作的组织策略 |
| `UserLevelAction` | `string` | 对电子邮件采取的操作，以响应与收件人定义的邮箱策略的匹配 |
| `UserLevelPolicy` | `string` | 触发对电子邮件采取的操作最终用户邮箱策略 |
| `ReportId` | `long` | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用。 |
| `AuthenticationDetails` | `string` | 按电子邮件身份验证协议（如 DMARC、DKIM、SPF 或 CompAuth (组合）的通过或失败裁定)  |

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
