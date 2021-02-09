---
title: Microsoft Defender for Office 365 中的自动调查和响应的工作原理
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自动事件响应， 调查， 修正， 威胁防护
ms.date: 01/29/2021
description: 了解 Microsoft Defender for Office 365 中的自动调查和响应功能如何工作
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 97cc2f6bcb066ff2d6f64254add3a57eb27b8828
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142545"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的自动调查和响应的工作原理

当触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。 有时，安全运营团队可能会因触发的警报数量而感到不知所措。 Microsoft Defender for Office 365 (AIR) 功能的自动调查和响应可以提供帮助。

AIR 使安全运营团队可以更高效地运行。 AIR 功能包括自动调查流程，以响应当今存在的已知威胁。 适当的修正操作等待审批，使安全运营团队能够响应检测到的威胁。

本文介绍 AIR 如何通过几个示例工作。 当你准备好开始使用 AIR 时，请参阅"自动[调查和响应威胁"。](office-365-air.md)

- [示例 1：用户报告的网络钓鱼邮件启动调查手册](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [示例 2：安全管理员从威胁资源管理器触发调查](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [示例 3：安全运营团队使用 Office 365 管理活动 API 将 AIR 与 SIEM 集成](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>示例：用户报告的网络钓鱼邮件启动调查手册

假定您组织的用户收到一封认为是网络钓鱼尝试的电子邮件。 经过培训以报告此类邮件的用户使用"报告邮件"[](enable-the-report-message-add-in.md)加载项或"报告钓鱼"加载项[](enable-the-report-phish-add-in.md)将其发送给 Microsoft 进行分析。 提交也会发送到你的系统，并且显示在资源管理器中的"提交"视图中 (以前称为用户 **报告的视图**) 。 此外，用户报告的消息现在触发基于系统的信息警报，该警报将自动启动调查手册。

在根调查阶段，将评估电子邮件的各个方面。 这些方面包括：

- 确定它可能是哪种类型的威胁;
- 发送者;
- 电子邮件从邮箱发送 (发送) ;
- 电子邮件的其他实例是否已送达或阻止;
- 来自分析员的评估;
- 电子邮件是否与任何已知市场活动关联;
- 等。

根调查完成后，该操作手册会提供对原始电子邮件及其关联实体执行的建议操作的列表。

接下来，执行多个威胁调查和搜寻步骤：

- 类似的电子邮件通过电子邮件群集搜索进行标识。
- 信号与其他平台（如 Microsoft Defender [for Endpoint）共享](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。
- 确定任何用户是否点击了可疑电子邮件中任何恶意链接。
- 检查 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 (Microsoft Defender [for Office 365](office-365-atp.md)) 以查看用户是否报告了任何其他类似邮件。
- 检查用户是否遭到入侵。 此检查利用 Office 365、Microsoft [Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 Azure Active [Directory](https://docs.microsoft.com/azure/active-directory)中的信号，关联任何相关的用户活动异常。

在搜寻阶段，会向各种搜寻步骤分配风险和威胁。

修正是手册的最后阶段。 在此阶段，将基于调查和搜寻阶段执行修正步骤。

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>示例：安全管理员从威胁资源管理器触发调查

除了由警报触发的自动调查之外，组织的安全运营团队还可以从威胁资源管理器中的视图触发 [自动调查](threat-explorer.md)。  此调查还会创建警报，以便 Microsoft Defender 事件和外部 SIEM 工具可以看到此调查已触发。

例如，假设您使用的是资源管理器 **中的"恶意软件** "视图。 使用图表下方的选项卡，选择" **电子邮件"** 选项卡。如果在列表中选择一个或多个项目，则 **+ 操作** 按钮将激活。

![包含选定邮件的资源管理器](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

使用"**操作"** 菜单，可以选择"**触发调查"。**

![所选邮件的操作菜单](../../media/explorer-malwareview-selectedemails-actions.jpg)

与警报触发的手册类似，从资源管理器中的视图触发的自动调查包括根调查、识别和关联威胁的步骤，以及缓解这些威胁的建议操作。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>示例：安全运营团队使用 Office 365 管理活动 API 将 AIR 与 SIEM 集成

Microsoft Defender for Office 365[](air-view-investigation-results.md)中的 AIR 功能包括报告&安全操作团队可用于监视和解决威胁的详细信息。 但您也可以将 AIR 功能与其他解决方案集成。 示例包括 SIEM (、) 或自定义报告解决方案中的安全信息和事件管理。 可以使用 [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)管理活动 API 完成这些类型的集成。

例如，最近，组织为安全运营团队设置了查看 AIR 已处理的用户报告的网络钓鱼警报的方法。 他们的解决方案将相关警报与组织的 SIEM 服务器及其案例管理系统集成。 该解决方案可大大减少误报数量，以便其安全运营团队可以将时间和精力集中在实际威胁上。 若要详细了解此自定义解决方案，请参阅技术社区 [博客：使用 Microsoft Defender for Office 365 和 O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)管理 API 提高 SOC 的有效性。

## <a name="next-steps"></a>后续步骤

- [开始使用 AIR](office-365-air.md)
- [查看挂起或已完成的修正操作](air-review-approve-pending-completed-actions.md)
