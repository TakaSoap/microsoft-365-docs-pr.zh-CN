---
title: 使用Microsoft 365 Defender门户开始
description: 了解如何开始使用Microsoft 365 Defender门户。 了解如何在门户中导航，并查看当前的安全状态和建议
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: c5a940676eab6ae3a07c526ecb1bd910ed8751fe
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667133"
---
# <a name="get-started-using-the-microsoft-365-defender-portal"></a>使用Microsoft 365 Defender门户开始

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

注册Microsoft Defender 商业版后，需要熟悉Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 。 本文包括以下几节：

- [如何导航Microsoft 365 Defender门户](#navigate-the-microsoft-365-defender-portal)

- [Learning有关事件和响应操作的模块](#complete-a-learning-module-about-incidents-and-response-actions) 

- [后续步骤](#next-steps)

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="navigate-the-microsoft-365-defender-portal"></a>导航Microsoft 365 Defender门户

Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 是用于使用和管理Microsoft Defender 商业版的一站式商店。 它包括可帮助你入门的欢迎横幅和标注、显示相关信息的卡片和导航栏，以便轻松访问各种功能。
 
花点时间熟悉Microsoft 365 Defender门户。

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Microsoft 365 Defender 门户":::

### <a name="use-the-navigation-bar"></a>使用导航栏

使用屏幕左侧的导航栏访问事件、查看报表和管理安全策略。 下表描述了将在导航栏中看到的项。

| Item | 说明 |
|:---|:---|
| **主页** | 在Microsoft 365 Defender中转到主页。 主页包含突出显示检测到的任何活动威胁的卡片，以及帮助保护公司数据和设备的建议。 <br/><br/>推荐包含在 Defender for Business 中，可以节省安全团队的时间和精力。 推荐基于行业最佳做法。 若要详细了解建议，请参阅[安全建议 - 危险和漏洞管理](../defender-endpoint/tvm-security-recommendation.md)。 |
| **事件** | 转到最近发生的事件列表。 触发警报时，会创建事件。 事件可以包含多个警报。 请务必定期查看事件。 <br/><br/>若要了解有关事件的详细信息，请参[阅Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)。|
| **操作中心** | 转到响应操作列表，包括已完成或挂起的操作。 <br/>- 选择 **"历史记录** "选项卡以查看已执行的操作。 某些操作会自动执行;其他人在获得批准后手动或完成。 <br/>- 选择 **"挂起"** 选项卡以查看需要审批才能继续的操作。 <br/><br/>若要了解有关操作中心的详细信息，请参 [阅操作中心中的"查看修正操作](mdb-review-remediation-actions.md)"。 |
| **威胁分析** | 带您查看当前威胁，并提供威胁环境的一览视图。 威胁分析还包括来自 Microsoft 安全研究人员的报告和信息。 <br/><br/>若要了解有关威胁分析的详细信息，请 [参阅通过威胁分析跟踪和应对新出现的威胁](../defender-endpoint/threat-analytics.md)。 |
| **安全分数** | 提供公司安全地位的表示形式，并提供改进建议。<br/><br/>若要了解有关安全分数的详细信息，请参阅 [Microsoft Secure Score for Devices](../defender-endpoint/tvm-microsoft-secure-score-devices.md)。 |
| **Learning中心** | 通过订阅中包含的学习路径提供对安全培训和其他资源的访问权限。 可以按产品、技能级别、角色等进行筛选。 Learning中心可帮助安全团队在 Defender for Business 和更多 Microsoft 产品/服务（如 [Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365）中](../defender-endpoint/microsoft-defender-endpoint.md)增强安全功能[&](../office-365-security/defender-for-office-365.md)功能。  |
| **端点** > **搜索** | 允许搜索载入到Microsoft Defender 商业版的一个或多个设备。 |
| **端点** > **设备清单** | 允许搜索载入到Microsoft Defender 商业版的一个或多个设备。 |
| **端点** > **漏洞管理** | 提供仪表板、建议、修正活动、软件清单和公司内潜在弱点列表。 |
| **端点** > **教程** | 提供对演练和模拟的访问权限，以帮助你详细了解威胁防护功能的工作原理。 <br/><br/>在尝试获取每个教程的模拟文件之前，请选择" **读取演练** "链接。 某些模拟需要Office应用（如Microsoft Word）来读取演练。 |
| **端点** > **设备配置** | 按操作系统和类型列出安全策略。 <br/><br/>若要了解有关安全策略的详细信息，请参阅[Microsoft Defender 商业版中的视图或编辑策略](mdb-view-edit-policies.md)。 |
| **报表** | 列出可用的安全报告。 通过这些报告，可以查看安全趋势、查看有关威胁检测和警报的详细信息，并详细了解公司易受攻击的设备。 |
| **运行状况** | 使你能够查看服务运行状况状态并规划即将发生的更改。 <br/>- 选择 **服务运行状况** 以查看公司订阅中包含的Microsoft 365服务的运行状况。 <br/>- 选择 **消息中心** ，了解计划内更改和预期内容。  |
| **&角色的权限** | 允许你向公司中负责管理安全性以及在Microsoft 365 Defender门户中查看事件和报表的人员分配权限。 此外，还可以设置和管理设备组以载入公司的设备并分配威胁防护策略。  |
| **设置** | 使你能够编辑Microsoft 365 Defender门户和Microsoft Defender 商业版的设置。 例如，可以载入 (或卸载) 和公司的设备 (也称为终结点) 。 还可以定义规则，例如警报抑制规则，并设置指示器来阻止或允许某些文件或进程。  |
| **更多资源** | 导航到其他门户，例如Azure Active Directory。 请记住，Microsoft 365 Defender门户应满足你的需求，而无需导航到其他门户。 |

## <a name="complete-a-learning-module-about-incidents-and-response-actions"></a>完成有关事件和响应操作的学习模块

请参阅学习模块， [检测和响应安全问题](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/)，以获取事件和响应操作的概述。 你将了解可执行的事件队列、警报和响应操作。 本课程将帮助你开始在 Defender for Business 中处理事件。

> [!NOTE]
> 尽管学习模块 ([检测和响应安全问题](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/)，) 实际上适用于Microsoft Defender for Endpoint，但基本概念和总体流与在 Defender for Business 中看到的类似。

## <a name="next-steps"></a>后续步骤

现在，你已大致了解 Defender for Business，请尝试以下一个或多个任务：

- [尝试Microsoft Defender 商业版教程和模拟](mdb-tutorials.md)

- [在Microsoft Defender 商业版中管理设备](mdb-manage-devices.md)

- [在Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解Microsoft Defender 商业版中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [在Microsoft Defender 商业版中查看或编辑策略](mdb-view-edit-policies.md)