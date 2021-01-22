---
title: Microsoft 365 Defender 的新增功能
description: 列出 Microsoft 365 Defender 中的新特性和功能
keywords: Microsoft 威胁防护的新增功能， ga， 通用， 功能， 可用， 新增
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8e66c734151e7476d7c54bd050891a1bffb17b3c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932018"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> 想要体验 Microsoft 365 Defender？ 可以在[实验室环境中对其进行评估或在](https://aka.ms/mtp-trial-lab)[生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。
>

Microsoft 365 Defender (GA) 中通常提供以下功能。

RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中：
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> 想要体验 Microsoft 365 Defender？ 可以在[实验室环境中对其进行评估或在](https://aka.ms/mtp-trial-lab)[生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)
>

## <a name="september-2020"></a>2020 年 9 月
- [IdentityDirectoryEvents 表](advanced-hunting-identitydirectoryevents-table.md) <br> 查找涉及运行 Active Directory 和 AD (本地域控制器) 。 此 [高级搜寻](advanced-hunting-overview.md) 架构表涵盖域控制器上的一系列与标识相关的事件和系统事件。
- [AssignedIPAddresses () 函数](advanced-hunting-assignedipaddresses-function.md) <br> 在高级搜寻查询中使用此函数可快速获取分配给设备的最新 IP 地址或特定时间的最新 IP 地址。

## <a name="july-2020"></a>2020 年 7 月
- [FileProfile () 函数](advanced-hunting-fileprofile-function.md) <br> 在高级搜寻查询中使用此函数，以使用全面的文件信息丰富结果。
- [标识表应用程序表](advanced-hunting-schema-tables.md)<br> 通过高级搜寻架构中的[IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)表了解身份验证事件、Active [Directory](advanced-hunting-identityqueryevents-table.md)查询和与应用相关的活动。
- [转到查寻](advanced-hunting-go-hunt.md)<br> 快速透视从调查事件到检查特定事件、用户、设备或高级搜寻的其他实体类型。

## <a name="june-2020"></a>2020 年 6 月
- Twitter 源 <br> 直接在仪表板内获取最新的安全研究、威胁情报、产品新闻等。
- [EmailPostDeliveryEvents 架构表](advanced-hunting-emailpostdeliveryevents-table.md) <br> 在高级搜寻查询中纳入有关对电子邮件执行传递后操作的信息。
- [检查高级搜寻中的记录](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 使用新的详细信息面板快速检查查询结果中的记录。

## <a name="may-2020"></a>2020 年 5 月
- [自定义检测](custom-detections-overview.md) <br> 使用高级搜寻查询可创建自定义检测规则，以自动监视和响应安全事件和系统状态。

## <a name="february-2020"></a>2020 年 2 月
- [事件](incidents-overview.md) <br> 准确了解攻击的开始位置和其他详细信息，以帮助你查看攻击的范围。
- [自动调查和响应](mtp-autoir.md) <br> AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。
- [高级搜寻增强功能](advanced-hunting-overview.md) <br> 使用 Kusto 查询语言和安全优化架构，在新式工作区中主动搜寻威胁。

## <a name="march-2019"></a>2019 年 3 月
- 高级搜寻 <br> 各种搜寻功能的登录页面，可让你主动查找影响电子邮件和数据、设备和标识的威胁。
- [Microsoft 安全功能分数](microsoft-secure-score.md) <br> 组织安全状况的度量，数字越高，表示采取的改进措施就越高。 遵循安全分数建议可保护组织免受威胁。 
- [报告](monitoring-and-reporting.md) <br>  功能丰富的卡片涵盖安全分析师和管理员在日常操作中跟踪的一系列领域。
