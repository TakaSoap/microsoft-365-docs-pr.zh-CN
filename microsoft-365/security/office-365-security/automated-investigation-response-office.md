---
title: AIR R 自动调查和 () 概述
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 08/21/2020
description: 简要了解 Office 365 高级威胁防护计划 2 中的自动调查和响应功能。
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 27a2330d5f1ff339aabf6a0fccb94a15dec30852
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860717"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a>Microsoft 365 自动调查 (响应（在 Microsoft 365 (AIR) 概述

触发安全警报后，安全运营团队将根据这些警报来查看这些警报并采取措一步来保护你的组织。 有时，安全运营团队可能对触发的警报数量感到不一些。 Office 365 高级威胁防护 () Office 365 ATP) 中的自动调 (查和) 可能有所帮助。 

AIR 使你的安全运营团队可以更有效地运营。 AIR 功能包括自动调查流程以响应当今存在的已知威胁。 适当的修正操作等待审批，从而使安全操作团队能够响应检测到的威胁。 

本文概述 AIR。 准备好开始使用 AIR 后，请参阅["自动调查并响应威胁"。](office-365-air.md)

## <a name="at-a-high-level"></a>在高级别

触发警报后，安全手册将生效。 根据情况，可以 [开始自动调查流程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 。 在自动调查期间以及在执行自动调查之后， [建议采取修正](air-remediation-actions.md) 操作。 Office 365 高级威胁防护中不自动执行任何操作。 安全操作团队审阅，然后 [批准或拒绝每个修正操作](air-review-approve-pending-completed-actions.md)。 在批准或拒绝后的所有操作后，调查即完成。 所有这些活动都要在安全 & 合规中心内进行跟踪和 (请参阅" [查看调查服务监视监视](air-view-investigation-results.md#view-details-of-an-investigation)) "。

以下部分提供了关于警报、安全手册以及 AIR 的操作示例的更多详细信息。

## <a name="alerts"></a>警报

[警报](../../compliance/alert-policies.md#viewing-alerts) 表示针对事件响应的安全操作团队工作流的触发器。 确定合适警报组的调查优先级，确保未提供任何未解决的威胁是一大挑战性。 手动调查警报时，安全操作团队必须对实体 (如内容、设备和用户在风险中受威胁胁，并区) 分相关。 此类任务和工作流可能非常耗时，并且涉及多个工具和系统。 通过 AIR，通过使关键安全性和威胁管理警报可自动触发安全响应 Playbook 来自动调查和响应安全事件。 

目前对于 AIR，从以下类型的警报策略生成的警报是自动调查的：  

- 检测到可能存在的恶意 URL 单击
- 用户报告为钓鱼邮件的电子邮件`*`
- 送达后删除了恶意软件的电子邮件`*`
- 传递后删除了包含网络钓鱼 URL 的电子邮件`*`
- 检测到可疑电子邮件发送模式`#`
- 限制发送电子邮件的用户`#`

> [!NOTE]
> 标有星号 () 的警报会在安全 & 合规中心内各自警报策略 `*` 中为其分配信息严*Informational*重性，并关闭电子邮件通知。 电子邮件通知可以通过"提醒策略" [进行打开](../../compliance/alert-policies.md#alert-policy-settings)。 标有哈希事件 `#` () 发布与公共预览手册相关联的公用警报。

若要查看警报，请在安全&合规中心中，选择 **"警报**  >  **查看警报"。** 选择一个警报以查看其详细信息，然后从 **此处使用"** 查看调查"链接 [转到相应的调查](air-view-investigation-results.md#investigation-graph)。  

> [!NOTE]
> 默认情况下，信息通知在警报视图中是隐藏的。 若要查看它们，请更改警报筛选以包含信息性警报。

如果你的组织通过警报管理系统、服务管理系统或安全信息和事件管理 (SIEM) 系统管理安全警报，则可以通过电子邮件通知或通过 Office 365 管理活动 API 向 [该系统发送警报](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 调查警报通知是通过电子邮件或 API 发送的警报通知，其中包括指向安全 & 合规中心内访问警报的链接，这使分配的安全管理员能够快速导航至调查。

![链接到调查的警报](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>安全手册

安全手册是 Office 高级威胁防护和 Microsoft 威胁防护中的自动化的后端策略。 AIR 中提供的安全手册基于常见的实际安全方案，并根据安全运营团队反馈而制定。 在组织内触发特定警报时，会自动启动安全手册。 警报触发器触发器后，关联的手册将由自动调查和响应系统 (答) 运行。 调查根据该特定警报的手册分步分析警报，查看所有关联的元数据 (包括电子邮件、用户、主题、发件人等 ) 。 基于调查手册的查找，AIR 建议执行一组操作，组织安全团队可对这些操作控制和缓解威胁。 

通过 AIR 你将获取的安全手册旨在应对组织现在遇到电子邮件的最常见威胁。 它们基于来自安全运营和事件响应团队的输入，包括帮助推迟 Microsoft 的人员和我们的客户资产。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>安全手册分阶段推出

作为 AIR 的一部分，安全手册分阶段推出。 第 1 阶段现在正式发布，并包括几个对于安全管理员可查看和批准的操作建议的手册：

- 用户报告的网络钓鱼邮件
- URL 单击顶点更改
- 在恶意软件 ZAP 服务器后 (检测到) 
- 网络钓鱼检测到了钓鱼邮件 (的邮政) 

第 1 阶段还包括对使用威胁资源管理器管理控制台网站 (管理员触发 [的电子邮件](threat-explorer.md) 调查) 。

第 2 阶段现在正在开发公共预览版中的**public preview**以下手册，提供操作建议，并帮助安全管理员调查问题：

- 用户报告为已在 (预览版) 

完成后将发布更多的 Playbook。 请访问 [Microsoft 365 产品指南](https://www.microsoft.com/microsoft-365/roadmap) ，了解还有其他内容的计划和即将推出。

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbook 包括调查和建议

在 AIR 中，每个安全手册都包括： 

- 电子邮件实体的根调查 (，如文件、URL、收件人、IP 地址等) ，等等
- 进一步寻搜索组织收到的类似电子邮件 
- 识别和链接其他潜在威胁并进行共享的步骤，并且 
- 建议的威胁修正操作。

每个高级步骤都包括多个子步骤，执行它们可以对威胁提供深入、详细且十分详细的响应。

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>示例：用户报告的网络钓鱼邮件启动调查手册

假设您组织的用户会收到他们认为是网络钓鱼尝试的电子邮件。 用户有一些训适用于报告此类邮件的文档 [，使用"报告邮件"加载项](enable-the-report-message-add-in.md) 将邮件发送到 Microsoft 进行分析。 提交也会发送到你的系统，并且可在资源管理器 **的"提交"** 视图中 ("请求 **的视图** "中) 。 此外，用户报告的消息现在会触发基于系统的信息警报，这会自动启动调查手册。

在根调查阶段，会评估电子邮件的各个方面。 这些方面包括：

- 关于它可能是哪种威胁类型的确定;
- 它的发送对象;
- 电子邮件从应用程序发送 (时) ;
- 是否传递或阻止了电子邮件的其他实例;
- 我们的评估中的评估;
- 电子邮件是否与任何已知活动相关联;
- 等等。

根调查完成后，手册将提供对原始电子邮件及其关联实体执行的建议操作的列表。
  
接下来，执行几个威胁调查和搜索步骤：

- 通过电子邮件群集搜索标识类似的电子邮件。
- 信号可与其他平台（如 [Microsoft Defender ATP）共享](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。
- 确定是否有任何用户通过可疑电子邮件中的任何恶意链接进行了单击。
- 检查通过 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 Office 365 高级威胁防护 ([ATP](office-365-atp.md)) ，以查看是否有其他类似邮件由用户报告。
- 检查时是为了查看用户是否已被入入入是否被入入入。 此检查利用 Office 365、Microsoft [Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 Azure Active [Directory](https://docs.microsoft.com/azure/active-directory)中的信号来关联任何相关的用户活动异常。

在搜索阶段，将为各种智能寻线步骤分配风险和威胁。 

修正是 Playbook 的最后阶段。 在此阶段，将根据调查和搜索阶段采取修正步骤。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>示例：安全管理员通过威胁资源管理器触发调查

除了警报触发的自动调查，组织的安全运营团队还可以从威胁资源管理器中的视图触发自动 [调查](threat-explorer.md)。

例如，假设你在威胁资源管理器 **中使用** 恶意软件视图。 使用图表下方的选项卡，选择"电子邮件 **"** 选项卡。如果选择列表中的一个或多个项，将激活+ **操作** 按钮。 

![包含选定邮件的资源管理器](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

使用 **"操作**"菜单，**可以选择"触发器调查"。**

![选定邮件的操作菜单](../../media/explorer-malwareview-selectedemails-actions.jpg)

与警报触发的手册、从资源管理器的视图触发的自动调查包括根调查、标识并相关威胁的步骤以及建议采取的操作以缓解这些威胁。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>示例：安全操作团队使用 Office 365 管理活动 API 将 AIR 与其 SIEM 集成

Office 365 ATP 中的 AIR 功能包括 [的报告&安全](air-view-investigation-results.md) 运营团队可以用其监视和解决威胁的详细信息。 但是，你也可以将 AIR 功能与其他解决方案集成。 示例包括安全信息和事件管理 (SIEM) 、事例管理系统或自定义报告解决方案。 这些类型的集成可以通过使用 [Office 365 管理活动 API 来完成](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

例如，组织为安全运营团队制定了一种查看已由 AIR 处理的用户报告的网络钓鱼警报的方式。 其解决方案将相关警报与组织的 SIEM 服务器及其案例管理系统集成。 该解决方案大大减少误报数，以便安全运营团队可以专注于真实威胁的时间和精力。 若要了解有关此自定义解决方案的详细信息，请参阅 [技术社区博客：通过 Office 365 ATP 和 O365 管理 API 提高 SOC 的效力](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

## <a name="next-step"></a>后续步骤

- [AIR 使用入门](office-365-air.md)

## <a name="see-also"></a>另请参阅

- [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Microsoft 威胁防护中的自动调查和响应功能](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)