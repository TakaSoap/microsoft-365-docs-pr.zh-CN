---
title: Microsoft 365 Defender 的新增功能
description: 列出Microsoft 365 Defender中的新功能
keywords: Microsoft 365 Defender、ga、正式发布、功能、可用、新功能中的新增功能
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
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 053326cacaeb2b4110f71edaa290ed10454aa720
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731639"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>以下功能以预览版或正式版 (正式版) 最新版本的Microsoft 365 Defender。

RSS 源: 通过将以下 URL 复制并粘贴到源阅读器中，可以在页面更新时收到通知: 

```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

有关其他 Microsoft Defender 安全产品的新增功能的详细信息，请参阅：

- [Microsoft Defender for Office 365 中的新增功能](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Microsoft Defender for Endpoint 中的新增功能](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Microsoft Defender for Identity中的新增功能](/defender-for-identity/whats-new)
- [Microsoft Defender for Cloud Apps中的新增功能](/cloud-app-security/release-notes)

还可以通过 [消息中心](https://admin.microsoft.com/Adminportal/Home#/MessageCenter)获取产品更新和重要通知。 



## <a name="march-2022"></a>2022 年 3 月

-  (预览版) 事件队列已增强，具有多个功能，旨在帮助调查。 增强功能包括按 ID 或名称搜索事件、指定自定义时间范围等功能。

## <a name="december-2021"></a>2021 年 12 月

-  (GA) `DeviceTvmSoftwareEvidenceBeta` 在高级搜寻中短期添加了该表，以便查看设备上检测到特定软件的证据。

## <a name="november-2021"></a>2021 年 11 月

-  (预览) Defender for Cloud应用的应用程序治理加载项功能现已在Microsoft 365 Defender中提供。 应用治理提供了一种安全性和策略管理功能，专为启用 OAuth 的应用而设计，这些应用通过 Microsoft Graph API 访问Microsoft 365数据。 应用治理通过可操作的见解和自动化的策略警报和操作，对这些应用及其用户如何访问、使用和共享存储在 Microsoft 365 中的敏感数据提供全面的可见性、修复和治理。 [详细了解应用程序治理](/cloud-app-security/app-governance-manage-app-governance)。
-  (预览) [高级搜寻](advanced-hunting-overview.md) 页面现在具有多重功能支持、智能滚动、简化架构选项卡、查询快速编辑选项、查询资源使用指示器和其他改进，使查询更流畅、更易于微调。
-  (预览) 现在可以使用 [事件功能链接](advanced-hunting-link-to-incident.md) 将高级搜寻查询结果中的事件或记录包含到你正在调查的新事件或现有事件中。

## <a name="october-2021"></a>2021 年 10 月

-  (GA) 高级搜寻中， [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 表中添加了更多列。 现在可以包括`AccountType`、`IsExternalUser`、`IsImpersonated`、`IPTags`和`IPCategory``UserAgentTags`查询。

## <a name="september-2021"></a>2021 年 9 月

-  (GA) Microsoft Defender for Office 365事件数据在Microsoft 365 Defender事件流式处理 API 中可用。 可以在[流式处理 API 中查看受支持的Microsoft 365 Defender事件类型中的事件类型的](supported-event-types.md)可用性和状态。
-  (高级搜寻中可用的 GA) Microsoft Defender for Office 365数据现已正式发布。
-  (GA) 向用户帐户分配事件和警报

  可以将事件及其关联的所有警报分配给用户帐户，从 **分配到：** 在事件的 **"管理事件** "窗格或 **警报的"管理警报** "窗格上。

## <a name="august-2021"></a>2021 年 8 月

-  (高级搜寻中提供的预览) Microsoft Defender for Office 365数据

  电子邮件表中的新列可以更深入地了解基于电子邮件的威胁，以便使用高级搜寻进行更彻底的调查。 现在，可以在 [EmailEvents](./advanced-hunting-emailevents-table.md)、 `FileSize` [EmailAttachmentInfo](./advanced-hunting-emailattachmentinfo-table.md) 和 `ThreatTypes` `DetectionMethods` [EmailPostDeliveryEvents](./advanced-hunting-emailpostdeliveryevents-table.md) 表中包含`AuthenticationDetails`该列。

-  (事件图) 预览版

  事件"**摘要**"选项卡上的新 **Graph** 选项卡显示攻击的完整范围、攻击如何随时间推移通过网络传播、开始的位置以及攻击者走了多远。

## <a name="july-2021"></a>2021 年 7 月

- [Professional服务目录](https://sip.security.microsoft.com/interoperability/professional_services)

  使用支持的合作伙伴连接增强平台的检测、调查和威胁情报功能。

## <a name="june-2021"></a>2021 年 6 月

-  (预览) [查看每个威胁标记的报告](threat-analytics.md#view-reports-per-threat-tags)

  威胁标记可帮助你专注于特定的威胁类别，并查看最相关的报告。

-  (预览) [流式处理 API](../defender-endpoint/raw-data-export.md)

  Microsoft 365 Defender支持通过高级搜寻将所有可用事件流式传输到事件中心和/或 Azure 存储帐户。

-  (预览版) [在高级搜寻中采取措施](advanced-hunting-take-action.md)

  快速包含威胁或解决在 [高级搜寻](advanced-hunting-overview.md)中找到的遭到入侵的资产。

-  (预览) [门户内架构参考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)

  直接在安全中心获取有关高级搜寻架构表的信息。 除了表和列说明，此引用还包括受支持的事件类型 (`ActionType` 值) 和示例查询。

-  (预览) [DeviceFromIP () 函数](advanced-hunting-devicefromip-function.md)

  获取有关在给定时间范围内为哪些设备分配了特定 IP 地址或地址的信息。

## <a name="may-2021"></a>2021 年 5 月

- [Microsoft 365 Defender门户中的新警报页](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243)

  为攻击中的上下文提供增强的信息。 可以看到哪些其他触发的警报导致了当前警报以及攻击中涉及的所有受影响实体和活动，包括文件、用户和邮箱。 有关详细信息，请参阅 ["调查警报](/microsoft-365/security/defender/investigate-alerts) "。

- [Microsoft 365 Defender门户中事件和警报的趋势图](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425)

  确定是否有多个针对单个事件的警报，或者你的组织受到多个不同事件的攻击。 有关详细信息，请参阅 [优先级事件](/microsoft-365/security/defender/incident-queue) 。

## <a name="april-2021"></a>2021 年 4 月

- Microsoft 365 Defender

  现已提供改进[的Microsoft 365 Defender](https://security.microsoft.com)门户。 这种新体验将 Defender for Endpoint、Defender for Office 365、Defender for Identity 等集成到单个门户中。 这是用于管理安全控制的新主页。 [了解新增功能](./microsoft-365-defender.md#the-microsoft-365-defender-portal)。

- [Microsoft 365 Defender威胁分析报告](threat-analytics.md)

  威胁分析可帮助你响应并最大程度地减少活动攻击的影响。 你还可以了解Microsoft 365 Defender解决方案阻止的攻击尝试，并采取预防措施来缓解进一步暴露和提高复原能力的风险。 作为统一安全体验的一部分，威胁分析现在可用于 Microsoft Defender for Endpoint 和 Microsoft Defender Office E5 许可证持有者。

## <a name="march-2021"></a>2021 年 3 月

- [CloudAppEvents 表](advanced-hunting-cloudappevents-table.md)

  查找有关Microsoft Cloud App Security涵盖的各种云应用和服务中的事件的信息。 此表还包括表中 `AppFileEvents` 以前可用的信息。

