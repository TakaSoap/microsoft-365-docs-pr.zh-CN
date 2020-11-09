---
title: Microsoft Defender for Office 365 中的自动化调查和响应的工作原理
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自动事件响应、调查、修正和威胁防护
ms.date: 11/05/2020
description: 请参阅 Microsoft Defender for Office 365 中的自动化调查和响应功能的工作原理
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 039cca2f6f61d7c82f8c3e85f1fd147a68f84b68
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948429"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的自动化调查和响应的工作原理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。 有时，安全操作团队可能会受到触发的警报量的感觉的不知所措。 Microsoft Defender for Office 365 中的自动调查和响应 (空中) 功能可提供帮助。

通过 AIR，您的安全操作团队可以更高效地运行。 空中功能包括自动调查过程，以响应目前存在的已知威胁。 适当的补救措施等待批准，使安全操作团队能够响应检测到的威胁。

本文介绍了 AIR 如何通过几个示例运行。 当您准备好开始使用 AIR 时，请参阅 [自动调查和响应威胁](office-365-air.md)。

- [示例1：用户报告的网络钓鱼邮件启动调查行动手册](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [示例2：安全管理员触发来自威胁资源管理器的调查](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [示例3：安全操作团队使用 Office 365 管理活动 API 将空中与其 SIEM 集成](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)


## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>示例：用户报告的网络钓鱼邮件启动调查行动手册

假定组织中的某个用户收到电子邮件，而他们认为是网络钓鱼尝试。 经过培训的用户报告此类邮件，使用 [报告邮件加载项](enable-the-report-message-add-in.md) 将其发送到 Microsoft 进行分析。 提交也会发送到您的系统，并在 " **提交** " 视图中显示 (以前称为 **用户报告** 的视图) 。 此外，用户报告的消息现在会触发基于系统的信息警报，这将自动启动调查行动手册。

在根调查阶段，会评估电子邮件的各个方面。 这些方面包括：

- 确定它可能属于哪种类型的威胁;
- 发件人数;
- 电子邮件的发送位置 (发送基础结构) ;
- 是否已传递或阻止电子邮件的其他实例;
- 我们分析家中的一种评估;
- 电子邮件是否与任何已知的市场活动相关联;
- 等等。

根调查完成后，行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。
  
接下来，执行以下几个威胁调查和搜寻步骤：

- 类似的电子邮件通过电子邮件群集搜索进行标识。
- 该信号与其他平台（如 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共享。
- 确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。
- 在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 ([Microsoft Defender for Office 365](office-365-atp.md)) 中进行检查，以查看用户是否报告了其他类似的邮件。
- 将执行检查以查看是否已泄露用户。 此检查跨 Office 365、 [Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)之间的信号，关联任何相关的用户活动异常。

在搜寻阶段，会为各种搜寻步骤分配风险和威胁。 

修正是行动手册的最后阶段。 在此阶段中，将根据调查和搜寻阶段采取补救措施。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>示例：安全管理员触发来自威胁资源管理器的调查

除了由警报触发的自动调查之外，组织的安全操作团队还可以通过 [威胁资源管理器](threat-explorer.md)中的视图触发自动调查。  此调查还会创建一个警报，以便 Microsoft Defender 事件和外部 SIEM 工具可以查看是否触发了此调查。 

例如，假设您正在使用资源管理器中的 **恶意软件** 视图。 使用图表下方的选项卡，选择 " **电子邮件** " 选项卡。如果选择列表中的一个或多个项目，则 " **+ 动作** " 按钮将激活。 

![包含所选邮件的资源管理器](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

使用 " **操作** " 菜单，可以选择 **触发调查** 。

![选定邮件的 "操作" 菜单](../../media/explorer-malwareview-selectedemails-actions.jpg)

与由警报触发的行动手册类似，通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>示例：安全操作团队使用 Office 365 管理活动 API 将空中与其 SIEM 集成

Microsoft Defender for Office 365 中的空中功能包括 [报告 & 详细信息](air-view-investigation-results.md) ，安全操作团队可以使用这些信息来监视和解决威胁。 但您也可以将空中功能与其他解决方案集成。 示例包括安全信息和事件管理 (SIEM) 系统、案例管理系统或自定义报告解决方案。 这些类型的集成可以通过使用 [Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)来实现。 

例如，最近，一个组织为其安全操作团队设置了一种方法，以查看用户报告的已由 AIR 处理的网络钓鱼警报。 其解决方案将相关警报与组织的 SIEM 服务器及其事例管理系统集成在一起。 该解决方案大大减少了误报的数量，使其安全操作团队能够将他们的时间和精力集中在真正的威胁上。 若要了解有关此自定义解决方案的详细信息，请参阅 [技术社区博客：使用 Microsoft Defender For Office 365 和 O365 管理 API 提高 SOC 的有效性](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

## <a name="next-steps"></a>后续步骤

- [开始使用空中](office-365-air.md)

- [访问 Microsoft 365 路线图以查看已计划和即将发布的内容](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [了解 Microsoft 365 Defender 中的自动化调查和响应功能](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
