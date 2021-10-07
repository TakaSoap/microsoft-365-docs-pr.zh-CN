---
title: 高级搜寻架构中的 EmailPostDeliveryEvents 表
description: 在高级搜寻架构的 EmailPostDeliveryEvents 表中了解Microsoft 365电子邮件的传递后操作
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， EmailPostDeliveryEvents， 网络消息 ID， 发件人， 收件人， 附件 ID， 附件名称， 恶意软件裁定， 网络钓鱼裁定， 附件计数， 链接计数， url 计数
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5de874a75763152422fb1cd84e90bc9fed716e6a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199557"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级 `EmailPostDeliveryEvents` 搜寻[架构中的](advanced-hunting-overview.md)表包含有关对邮件发送者处理的电子邮件执行传递后Microsoft 365。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持的事件 (值) ，请使用安全中心中提供的内置架构 `ActionType` 参考。

若要获取有关各个电子邮件的信息，您还可以使用 、 和 [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) 表。 有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `NetworkMessageId` | string | 由用户生成的电子邮件的唯一Microsoft 365 |
| `InternetMessageId` | string | 发送电子邮件系统设置的电子邮件的面向公众的标识符 |
| `Action` | string | 对实体采取的操作 |
| `ActionType` | string | 触发事件的活动类型：手动修正、钓鱼邮件 ZAP、恶意软件 ZAP |
| `ActionTrigger` | string | 指示操作是由管理员手动触发 (还是通过审批挂起的自动操作) 触发，还是由某些特殊机制（如 ZAP 或动态传递）触发 |
| `ActionResult` | string | 操作结果 |
| `RecipientEmailAddress` | string | 收件人的电子邮件地址，或通讯组列表扩展后收件人的电子邮件地址 |
| `DeliveryLocation` | string | 发送电子邮件的位置：收件箱/文件夹、本地/外部、垃圾箱、隔离区、已失败、已弃用、已删除的邮件 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用。 |
| `ThreatTypes` | string | 关于电子邮件是否包含恶意软件、网络钓鱼或其他威胁的电子邮件筛选堆栈裁定 |
| `DetectionMethods` | string | 用于检测电子邮件中的恶意软件、网络钓鱼或其他威胁的方法 |

## <a name="supported-event-types"></a>支持的事件类型
此表捕获具有以下值 `ActionType` 的事件：

- **手动修正** – 管理员在将电子邮件传递到用户邮箱后对电子邮件手动采取操作。 这包括通过威胁资源管理器手动 [采取的](../office-365-security/threat-explorer.md) 操作，或者 AIR ([自动](m365d-autoir-actions.md)调查和) 批准。
- **钓鱼邮件 ZAP** [– 零时差自动清除 (ZAP](../office-365-security/zero-hour-auto-purge.md)) 对发送后对网络钓鱼电子邮件采取操作。
- **恶意软件 ZAP** – 零时差自动清除 (ZAP) 对在传递后发现包含恶意软件的电子邮件采取操作。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
