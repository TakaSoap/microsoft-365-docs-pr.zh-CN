---
title: Microsoft 威胁防护的新增功能
description: 列出 Microsoft 威胁防护中的新特性和功能
keywords: microsoft 威胁防护中的新增功能、ga、正式发布、功能、可用、新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: d5a7cc491b0a8547848f4e341a605ae0c4b87cc9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201275"
---
# <a name="whats-new-in-microsoft-threat-protection"></a>Microsoft 威胁防护的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


以下功能在最新版本的 Microsoft 威胁防护中 () 正式提供。

RSS 源：通过将以下 URL 复制并粘贴到订阅源阅读器中来更新此页面时收到通知：
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a>2020 年 9 月
- [AssignedIPAddresses ( # A1 函数](advanced-hunting-assignedipaddresses-function.md) <br> 在 [高级搜寻](advanced-hunting-overview.md) 查询中使用此函数可以快速获取从指定时间点分配给设备或最近的 ip 地址的最新 ip 地址。

## <a name="july-2020"></a>2020 年 7 月
- [FileProfile ( # A1 函数](advanced-hunting-fileprofile-function.md) <br> 在高级搜寻查询中使用此功能，通过全面的文件信息丰富结果。
- [标识和应用程序表](advanced-hunting-schema-tables.md)<br> 在高级搜寻架构中获取对 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和 [AppFileEvents](advanced-hunting-appfileevents-table.md) 表的身份验证事件、Active Directory 查询和应用程序相关活动的可见性。
- [转到查寻](advanced-hunting-go-hunt.md)<br> 通过使用基于查询的高级搜寻功能，快速透视调查事件以检查特定事件、用户、设备或其他实体类型。

## <a name="june-2020"></a>2020 年 6 月
- Twitter 源 <br> 在仪表板中获取最新的安全研究、威胁智能、产品新闻和更多权限。
- [EmailPostDeliveryEvents 架构表](advanced-hunting-emailpostdeliveryevents-table.md) <br> 将有关在您的高级搜寻查询中对电子邮件执行的送达操作的信息合并在一起。
- [检查高级搜寻中的记录](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 使用新的详细信息面板快速检查查询结果中的记录。

## <a name="may-2020"></a>2020 年 5 月
- [自定义检测](custom-detections-overview.md) <br> 使用高级搜寻查询创建可自动监视和响应安全事件和系统状态的自定义检测规则。

## <a name="february-2020"></a>2020 年 2 月
- [事件](incidents-overview.md) <br> 确切知道攻击的启动位置和其他详细信息，以帮助您了解攻击的程度。
- [自动调查和响应](mtp-autoir.md) <br> AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。
- [高级搜寻增强功能](advanced-hunting-overview.md) <br> 使用 Kusto 查询语言和安全优化架构主动查找整个新式工作区中的威胁。

## <a name="march-2019"></a>2019 年 3 月
- 高级搜寻 <br> 登录页面到各种搜索功能，使您能够主动找到影响电子邮件和数据、设备和标识的威胁。
- [Microsoft 安全功能分数](microsoft-secure-score.md) <br> 组织的安全状态的度量值，其数字越高表示执行了更多改进操作。 按照安全得分建议，可以保护您的组织免受威胁。 
- [报表](monitoring-and-reporting.md) <br>  提供一系列涵盖安全分析员和管理员在日常运营中进行跟踪的各种领域的卡片主机。
