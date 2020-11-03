---
title: 高级搜寻架构中的 EmailEvents 表
description: 了解在高级搜寻架构的 EmailEvents 表中与 Microsoft 365 电子邮件相关联的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、EmailEvents、网络邮件 id、发件人、收件人、附件 id、附件名称、恶意软件结论、仿冒判定、附件计数、链接计数、url 计数
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
ms.openlocfilehash: 86cc32cf395f2216eb3e167e372d1225734c4c28
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842628"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender



`EmailEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关涉及 Microsoft Defender for Office 365 电子邮件处理的事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `EmailId` | string | 唯一的电子邮件和收件人标识符 |
| `NetworkMessageId` | string | 由 Microsoft 365 生成的电子邮件的唯一标识符 |
| `InternetMessageId` | string | 发送电子邮件系统设置的电子邮件的面向公众的标识符 |
| `SenderMailFromAddress` | string | “发件人”标题（又称为“信件发送方”或“返回路径地址”）中的发件人电子邮件地址 |
| `SenderFromAddress` | string | 发件人标题中的发件人电子邮件地址（电子邮件收件人在其电子邮件客户端上可以看到） |
| `SenderMailFromDomain` | string | “发件人”标题（又称为“信件发送方”或“返回路径地址”）中的发件人域 |
| `SenderFromDomain` | string | 发件人标题中的发件人域（电子邮件收件人在其电子邮件客户端上可以看到） |
| `SenderIPv4` | string | 最近检测到的中继邮件的邮件服务器的 IPv4 地址 |
| `SenderIPv6` | string | 最近检测到的中继邮件的邮件服务器的 IPv6 地址 |
| `RecipientEmailAddress` | string | 收件人的电子邮件地址，或通讯组列表扩展后收件人的电子邮件地址 |
| `Subject` | string | 电子邮件主题 |
| `EmailClusterId` | string | 基于对内容的启发式分析群集的相似电子邮件组的标识符 |
| `EmailDirection` | string | 电子邮件方向（相对于所在的网络）：入站、出站、组织内 |
| `DeliveryAction` | string | 电子邮件发送操作：已发送、已标记为垃圾邮件、已阻止或已替换 |
| `DeliveryLocation` | string | 发送电子邮件的位置：收件箱/文件夹、本地/外部、垃圾箱、隔离区、已失败、已弃用、已删除的邮件 |
| `PhishFilterVerdict` | string | 关于电子邮件是否是钓鱼邮件的电子邮件筛选堆栈裁定：钓鱼邮件或非钓鱼邮件 |
| `PhishDetectionMethod` | string | 用于将电子邮件检测为网络钓鱼的方法：恶意 URL 信誉、安全链接 URL 沙箱、高级网络钓鱼筛选器、常规网络钓鱼筛选器、反欺骗：组织内、反欺骗：外部域、域模拟、用户模拟、品牌模拟 |
| `MalwareFilterVerdict` | string | 关于电子邮件是否包含恶意软件的电子邮件筛选堆栈裁定：恶意软件，非恶意软件 |
| `MalwareDetectionMethod` | string | 用于检测电子邮件中的恶意软件的方法：反恶意软件引擎、文件信誉、安全附件 |
| `FinalEmailAction` | string | 基于筛选器裁定、策略和用户操作对电子邮件执行的最后操作：将邮件移到垃圾邮件文件夹、添加 X 标头、修改主题、重定向邮件、删除邮件、发送到隔离区、未执行任何操作、密件抄送邮件 |
| `FinalEmailActionPolicy` | string | 生效的操作策略：反垃圾邮件高可信度、反垃圾邮件、反垃圾邮件批量邮件、反垃圾邮件、反垃圾邮件钓鱼、防钓鱼域模拟、防钓鱼用户模拟、防钓鱼欺骗、防钓鱼图形模拟、反恶意软件、安全附件、企业传输规则 (ETR) |
| `FinalEmailActionPolicyGuid` | string | 确定最后邮件操作的策略的唯一标识符 |
| `AttachmentCount` | int | 电子邮件中的附件数目 |
| `UrlCount` | int | 电子邮件中的嵌入 URL 数目 |
| `EmailLanguage` | string | 检测到的电子邮件内容的语言 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
