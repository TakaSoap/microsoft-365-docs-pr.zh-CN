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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e22a237a5e8369093a83063f784fdba3ed75401c
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300810"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

以下功能在最新版本的 (GA) 预览版或Microsoft 365 Defender。

RSS 源: 通过将以下 URL 复制并粘贴到源阅读器中，可以在页面更新时收到通知: 
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

有关其他 Microsoft Defender 安全产品的新增功能详细信息，请参阅：

- [Microsoft Defender for Office 365](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Microsoft Defender for Endpoint 中的新增功能](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Microsoft Defender 标识的新增功能](/defender-for-identity/whats-new)
- [Microsoft Cloud App Security](/cloud-app-security/release-notes)

## <a name="november-2021"></a>2021 年 11 月

-  (预览) 适用于云应用的 Defender 的应用程序管理加载项功能现已在 Microsoft 365 Defender 中提供。 应用治理提供了一个安全和策略管理功能，该功能专为启用 OAuth 的应用设计，这些应用Microsoft 365 Microsoft Graph API 访问数据。 应用治理通过可操作的见解和自动化的策略警报和操作，对这些应用及其用户如何访问、使用和共享存储在 Microsoft 365 中的敏感数据提供全面的可见性、修复和治理。 [详细了解应用程序治理](/cloud-app-security/app-governance-manage-app-governance)。
-  (Preview) 高级搜寻页面[](advanced-hunting-overview.md)现在具有多任务支持、智能滚动、简化的架构选项卡、查询的快速编辑选项、查询资源使用率指示器和其他改进，使查询更流畅且更易于微调。
-  (预览版) 现在可以使用事件功能链接将高级[](advanced-hunting-link-to-incident.md)搜寻查询结果中的事件或记录直接包含到正在调查的新事件或现有事件中。 
## <a name="october-2021"></a>2021 年 10 月
-  (GA) 在高级搜寻中 [，CloudAppEvents](advanced-hunting-cloudappevents-table.md) 表中添加了更多列。 现在可以在 `AccountType` 查询中包括 `IsExternalUser` 、 `IsImpersonated` 、 、 `IPTags` `IPCategory` 、 `UserAgentTags` 和 。 

## <a name="september-2021"></a>2021 年 9 月
-  (事件) API Office 365 Microsoft Defender for Microsoft 365 Defender 事件数据。 你可以查看流式 API 中受支持的事件类型Microsoft 365 Defender[事件类型的可用性和状态](supported-event-types.md)。
-  (通用) Microsoft Defender Office 365高级搜寻中提供的数据现已普遍可用。
-  (预览) 向用户帐户分配事件和警报 <br> 您可以将事件及其关联的所有警报分配给用户帐户，该用户帐户位于事件的"管理事件"窗格或警报的"管理警报"窗格中。 


## <a name="august-2021"></a>2021 年 8 月
-  (预览) Microsoft Defender Office 365高级搜寻中提供的数据
<br>电子邮件表中的新列可以更深入地了解基于电子邮件的威胁，以便使用高级搜寻进行更全面的调查。 现在可以在 `AuthenticationDetails` EmailEvents、EmailAttachmentInfo 和[](./advanced-hunting-emailevents-table.md) `FileSize` [](./advanced-hunting-emailattachmentinfo-table.md) `ThreatTypes` `DetectionMethods` [EmailPostDeliveryEvents](./advanced-hunting-emailpostdeliveryevents-table.md)表中包含该列。 

-  (预览) 事件图 <br>  事件 **Graph"** 摘要"选项卡上的新"列表"选项卡显示攻击的完整范围、攻击如何随着时间的推移网络分布、开始位置以及攻击者已攻击多远。

## <a name="july-2021"></a>2021 年 7 月
- [Professional服务目录](https://sip.security.microsoft.com/interoperability/professional_services)<br>通过受支持的合作伙伴连接增强平台的检测、调查和威胁智能功能。

## <a name="june-2021"></a>2021 年 6 月
-  (预览) [每个威胁标记查看报告](threat-analytics.md#view-reports-per-threat-tags)<br> 威胁标记可帮助你专注于特定威胁类别并查看最相关的报告。
-  (预览) [流式处理 API](../defender-endpoint/raw-data-export.md)<br> Microsoft 365 Defender通过高级搜寻提供的所有事件流式处理到事件中心和/或 Azure 存储帐户。
-  (预览) [高级搜寻中采取措施](advanced-hunting-take-action.md)<br> 快速包含威胁或解决你在高级搜寻中发现的威胁 [资产](advanced-hunting-overview.md)。
-  (预览) [门户内架构参考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)<br> 直接在安全中心获取有关高级搜寻架构表的信息。 除了表和列说明之外，此参考还包括受支持的事件类型 (`ActionType` 查询) 查询的值。
-  (Preview) [DeviceFromIP () 函数](advanced-hunting-devicefromip-function.md)<br> 获取有关在给定时间范围内为哪些设备分配了特定 IP 地址或地址的信息。
    

## <a name="may-2021"></a>2021 年 5 月

- [门户中的新警报Microsoft 365 Defender页](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243) <br> 提供针对攻击的上下文的增强信息。 你可以看到其他触发的警报导致了当前警报，以及攻击中涉及的所有受影响的实体和活动，包括文件、用户和邮箱。 有关详细信息 [，请参阅](/microsoft-365/security/defender/investigate-alerts) 调查警报。
- [事件和警报趋势图Microsoft 365 Defender门户](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425) <br> 确定单个事件是否具有多个警报，或者您的组织是否受到多个不同事件的攻击。 有关详细信息 [，请参阅确定](/microsoft-365/security/defender/incident-queue) 事件的优先级。


## <a name="april-2021"></a>2021 年 4 月
- Microsoft 365 Defender<br> 改进的[Microsoft 365 Defender](https://security.microsoft.com)门户现已可用。 此新体验将 Defender for Endpoint、Defender for Office 365、Defender for Identity 等集成到单个门户中。 这是用于管理安全控制的新主页。 [了解新增功能](./microsoft-365-defender.md#the-microsoft-365-defender-portal)。

- [Microsoft 365 Defender威胁分析报告](threat-analytics.md)<br>
 威胁分析可帮助你响应活动攻击并最大限度地减少其影响。 还可以了解解决方案阻止的攻击尝试Microsoft 365 Defender采取预防性措施，以降低进一步暴露的风险并增加复原能力。 作为统一安全体验的一部分，威胁分析现在适用于 Microsoft Defender for Endpoint 和 Microsoft Defender for Office E5 许可证持有者。

## <a name="march-2021"></a>2021 年 3 月
- [CloudAppEvents 表](advanced-hunting-cloudappevents-table.md) <br>查找有关活动涵盖的各种云应用和服务中Microsoft Cloud App Security。 此表还包括以前在表中可用的 `AppFileEvents` 信息。
## <a name="february-2021"></a>2021 年 2 月
-  (预览) 增强[Microsoft 365 Defender门户 (https://security.microsoft.com) ](https://security.microsoft.com)现在适用于公共预览版。 此新体验将 Defender for Endpoint 和 Defender for Office 365中心。 [了解有关更改的详细信息](microsoft-365-defender.md#the-microsoft-365-defender-portal)。
- **[ (预览) Microsoft 365 Defender](api-overview.md)** API - 顶级 Microsoft 365 Defender API 将使您能够基于共享事件和高级搜寻表自动执行工作流。 
