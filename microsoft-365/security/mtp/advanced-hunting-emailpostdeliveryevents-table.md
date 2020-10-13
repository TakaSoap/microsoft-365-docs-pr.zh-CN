---
title: 高级搜寻架构中的 EmailPostDeliveryEvents 表
description: 了解在高级搜寻架构的 EmailPostDeliveryEvents 表中对 Microsoft 365 电子邮件执行的交付后操作
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、EmailPostDeliveryEvents、网络邮件 id、发件人、收件人、附件 id、附件名称、恶意软件结论、仿冒判定、附件计数、链接计数、url 计数
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
ms.openlocfilehash: ea54f6b312c473240dba07eae95733d2ea610fe5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430545"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

`EmailPostDeliveryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关在 Microsoft 365 处理的电子邮件上执行投递后操作的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

若要获取有关单个电子邮件的详细信息，您还可以使用 [`EmailEvents`](advanced-hunting-emailevents-table.md) 、 [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) 和 [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) 表。 有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `EventId` | string | 事件的唯一标识符 |
| `NetworkMessageId` | string | 由 Microsoft 365 生成的电子邮件的唯一标识符 |
| `InternetMessageId` | string | 发送电子邮件系统设置的电子邮件的面向公众的标识符 |
| `Action` | string | 对实体执行的操作 |
| `ActionType` | string | 触发事件的活动类型：手动修正、网络钓鱼 ZAP、恶意软件 ZAP |
| `ActionTrigger` | string | 指示管理员是由管理员触发操作 (手动触发，还是通过审批挂起的自动操作) 或通过某些特殊机制（如 ZAP 或动态传递）触发的操作 |
| `ActionResult` | string | 操作结果 |
| `RecipientEmailAddress` | string | 收件人的电子邮件地址，或通讯组列表扩展后收件人的电子邮件地址 |
| `DeliveryLocation` | string | 发送电子邮件的位置：收件箱/文件夹、本地/外部、垃圾箱、隔离区、已失败、已弃用、已删除的邮件 |

## <a name="supported-event-types"></a>支持的事件类型
此表捕获具有以下值的事件 `ActionType` ：

- **手动修正** –管理员在将电子邮件传递到用户邮箱后手动对其采取操作。 这包括通过 [威胁资源管理器](../office-365-security/threat-explorer.md) 手动执行的操作或对 [自动调查和响应 (AIR) 操作](mtp-autoir-actions.md)的审批。
- **网络钓鱼 ZAP** – [零小时自动清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md) 在传递后对网络钓鱼电子邮件采取操作。
- **恶意软件 ZAP** –零小时自动清除 (ZAP) 对在传递后包含恶意软件的电子邮件采取操作。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
