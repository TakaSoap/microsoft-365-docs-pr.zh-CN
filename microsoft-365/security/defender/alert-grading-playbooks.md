---
title: 警报评分手册
description: 查看已知攻击的警报，并采取建议操作来修正攻击并保护你的网络。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fe0beb88cf613a5a966fc0534dfa4def715e81d2
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62355086"
---
# <a name="alert-grading-playbooks"></a>警报评分手册

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

警报评分手册允许你有条不紊地查看已知攻击警报并快速分类警报，并采取建议操作来修正攻击和保护你的网络。 警报评分还有助于对整体事件进行正确分类。

作为 SOC (安全研究) 安全操作中心，您必须有权访问 Microsoft 365 Defender 门户，以便可以：

- 评估和查看生成的警报和相关事件。 请参阅 [调查警报](investigate-alerts.md)。
- 搜索租户的安全信号数据并检查潜在威胁和可疑活动。 请参阅 [高级搜寻](advanced-hunting-overview.md)。

>[!Note]
>你可以向 Microsoft 提供有关真实误报和误报警报的反馈，不仅可在调查结束时提供，还可以在调查过程中提供。 这可以帮助 Microsoft 对安全事件进行未来的分析和分类。
>

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)保护你的组织免受电子邮件、链接和 URL (和协作) 造成的恶意威胁。 Defender for Office 365 包括：

- 威胁防护策略

   定义威胁防护策略，为组织设置适当级别的保护。

- 报表

  查看实时报告以监视 Defender Office 365组织的性能。

- 威胁调查和响应功能

  使用领先工具调查、了解、模拟和防止威胁。

- 自动调查和响应功能

  节省调查和缓解威胁的时间和精力。

Defender for Office 365 警报可分类为： 

- 真 正 (TP) 确认的恶意活动。 
- 误报 (FP) 确认的非恶意活动。

>[!Note]
>Microsoft 365 Defender门户[https://security.microsoft.com](https://security.microsoft.com)将现有 Microsoft 安全门户中的功能汇集在一起。 该Microsoft 365 Defender强调快速访问信息、简化布局以及将相关信息汇集在一起以便于使用。
>

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

[Microsoft Defender for Cloud Apps](/defender-cloud-apps) 是 CASB (云访问安全代理) ，支持各种部署模式，包括日志收集、API 连接器和反向代理。 它提供对数据移动的丰富可见性和控制以及完善的分析，以识别和对抗所有 Microsoft 和第三方云服务中的网络威胁。

云应用的 Defender 在本机与领先的 Microsoft 解决方案集成，在设计时牢记安全专业人员。 它提供了简单的部署、集中管理和创新的自动化功能。

Defender for Cloud Apps 框架包括保护你的网络免受网络威胁和异常、跨云应用检测异常行为以识别勒索软件、受到威胁的用户或未授权应用程序的功能。 它可分析高风险使用情况，并可以自动修正以限制组织的风险。

云应用 Defender 警报可分类为： 

- 已确认恶意活动的 TP。 
- 恶意的正 (B-TP) 可疑但并非恶意活动，例如渗透测试或其他授权可疑操作。 
- 确认的非恶意活动的 FP。

## <a name="alert-grading-playbooks"></a>警报评分手册

有关更快速地对以下威胁发出警报的步骤，请参阅这些手册：

- [可疑电子邮件转发活动](alert-grading-playbook-email-forwarding.md)
- [可疑的收件箱操作规则](alert-grading-playbook-inbox-manipulation-rules.md)
- [可疑收件箱转发规则](alert-grading-playbook-inbox-forwarding-rules.md)

请参阅[调查警报，](investigate-alerts.md)了解如何使用报告门户Microsoft 365 Defender警报。
