---
title: Microsoft 365 Defender 的新增功能
description: 列出新特性和功能Microsoft 365 Defender
keywords: what's new in Microsoft 365 Defender， ga， generally available， capabilities， available， new
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: af5efb669b1f73b4008ac2c3fae251a4d08511dd
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340980"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> 希望体验 Microsoft 365 Defender？ 你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

以下功能在最新版本的 (GA) 中通常Microsoft 365 Defender。

RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中：
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="july-2021"></a>2021 年 7 月
- [Professional服务目录](https://sip.security.microsoft.com/interoperability/professional_services)<br>通过受支持的合作伙伴连接增强平台的检测、调查和威胁智能功能。
    

## <a name="may-2021"></a>2021 年 5 月

- [门户中的新警报Microsoft 365 Defender页](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243) <br> 提供针对攻击的上下文的增强信息。 你可以看到其他触发的警报导致了当前警报，以及攻击中涉及的所有受影响的实体和活动，包括文件、用户和邮箱。 有关详细信息 [，请参阅](/microsoft-365/security/defender/investigate-alerts) 调查警报。
- [事件和警报趋势图Microsoft 365 Defender门户](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425) <br> 确定单个事件是否具有多个警报，或者您的组织是否受到多个不同事件的攻击。 有关详细信息 [，请参阅确定](/microsoft-365/security/defender/incident-queue) 事件的优先级。


## <a name="april-2021"></a>2021 年 4 月
- Microsoft 365 Defender<br> 改进的[Microsoft 365 Defender](https://security.microsoft.com)门户现已可用。 这一新体验将 Defender for Endpoint、defender for Office 365、Defender for Identity 等集成到单个门户中。 这是用于管理安全控制的新主页。 [了解新增功能](./overview-security-center.md)。

- [Microsoft 365 Defender威胁分析报告](threat-analytics.md)<br>
 威胁分析可帮助你响应活动攻击并最大限度地减少其影响。 还可以了解解决方案阻止的攻击尝试Microsoft 365 Defender采取预防措施，以缓解进一步暴露的风险并增加恢复能力。 作为统一安全体验的一部分，威胁分析现在适用于 Microsoft Defender for Endpoint 和 Microsoft Defender for Office E5 许可证持有者。

## <a name="march-2021"></a>2021 年 3 月
- [CloudAppEvents 表](advanced-hunting-cloudappevents-table.md) <br>查找有关应用程序涵盖的各种云应用和服务中的Microsoft Cloud App Security。 此表还包括之前在 中提供的信息 `AppFileEvents` 。
## <a name="february-2021"></a>2021 年 2 月
-  (预览) 增强Microsoft 365[安全 https://security.microsoft.com) ](https://security.microsoft.com) (现在适用于公共预览版。 这一新体验将 Defender for Endpoint 和 Defender for Office 365中心。 [了解有关更改的详细信息](./overview-security-center.md)。

## <a name="september-2020"></a>2020 年 9 月
- [IdentityDirectoryEvents 表](advanced-hunting-identitydirectoryevents-table.md) <br> 查找涉及本地域控制器的事件，该域控制器运行 Active Directory (AD) 。 此 [高级搜寻](advanced-hunting-overview.md) 架构表涵盖域控制器上一系列与标识相关的事件和系统事件。
- [AssignedIPAddresses () 函数](advanced-hunting-assignedipaddresses-function.md) <br> 在高级搜寻查询中使用此函数可快速获取分配给设备的最新 IP 地址或特定时间的最新 IP 地址。

## <a name="july-2020"></a>2020 年 7 月
- [FileProfile () 函数](advanced-hunting-fileprofile-function.md) <br> 在高级搜寻查询中使用此函数，通过综合文件信息丰富结果。
- [标识表和应用表](advanced-hunting-schema-tables.md)<br> 通过高级搜寻架构中的[IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)表，了解身份验证事件、Active [Directory](advanced-hunting-identityqueryevents-table.md)查询和与应用相关的活动。
- [转到查寻](advanced-hunting-go-hunt.md)<br> 快速透视从调查事件到检查特定事件、用户、设备或高级搜寻上的其他实体类型。

## <a name="june-2020"></a>2020 年 6 月
- Twitter 源 <br> 直接在仪表板内获取最新的安全研究、威胁情报、产品新闻等。
- [EmailPostDeliveryEvents 架构表](advanced-hunting-emailpostdeliveryevents-table.md) <br> 在高级搜寻查询中纳入有关对电子邮件执行传递后操作的信息。
- [检查高级搜寻中的记录](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 使用新的详细信息面板快速检查查询结果中的记录。

## <a name="may-2020"></a>2020 年 5 月
- [自定义检测](custom-detections-overview.md) <br> 使用高级搜寻查询创建自定义检测规则，以自动监视和响应安全事件和系统状态。

## <a name="february-2020"></a>2020 年 2 月
- [事件](incidents-overview.md) <br> 准确了解攻击的开始位置和其他详细信息，以帮助你查看攻击的范围。
- [自动调查和响应](m365d-autoir.md) <br> AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。
- [高级搜寻增强功能](advanced-hunting-overview.md) <br> 使用 Kusto 查询语言和安全优化架构，在新式工作区中主动搜寻威胁。

## <a name="march-2019"></a>2019 年 3 月
- 高级搜寻 <br> 各种搜寻功能的登陆页面，可让你主动查找影响电子邮件和数据、设备和标识的威胁。
- [Microsoft 安全功能分数](microsoft-secure-score.md) <br> 衡量组织的安全状态，较高的数字表示采取更多改进措施。 按照安全功能分数建议可保护你的组织免遭威胁。 
- [报表](overview-security-center.md) <br>  功能一系列卡片，涵盖安全分析师和管理员在日常操作中跟踪的一系列领域。
