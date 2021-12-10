---
title: 开始使用 Microsoft Defender for Business
description: 了解如何开始使用 Microsoft Defender for Business，包括导航门户和查看状态和建议
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: b49d4da46153597a00f9e6bbdd00ebf6bd2e26cc
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374994"
---
# <a name="get-started-using-microsoft-defender-for-business"></a>开始使用 Microsoft Defender for Business

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向可能介绍 Microsoft Defender for Business 预览版中未包含的一些 (内容) 。

为公司完成安装和配置过程后，开始使用 Microsoft Defender for Business 的最佳方法就是访问 Microsoft 365 Defender 门户 () ，然后使用 Microsoft 365 的用户帐户 [https://security.microsoft.com](https://security.microsoft.com) 登录。 

## <a name="navigate-the-microsoft-365-defender-portal"></a>导航Microsoft 365 Defender门户

Microsoft 365 Defender门户 () 是使用和管理 Microsoft Defender for Business 的一站式 [https://security.microsoft.com](https://security.microsoft.com) 商店。 它包括欢迎横幅和标注来帮助你入门、显示相关信息的卡片和导航栏，让你可以轻松访问各种特性和功能。
 
花一点时间熟悉你的Microsoft 365 Defender门户。

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Microsoft 365 Defender 门户":::

## <a name="use-the-navigation-bar"></a>使用导航栏

使用屏幕左侧的导航栏访问事件、查看报告和管理安全策略和设置。 下表介绍了您将在导航栏中看到的项目。

| Item | 说明 |
|:---|:---|
| **主页** | 在主页上查看Microsoft 365 Defender。 主页包括突出显示检测到的任何活动威胁的卡片，以及可帮助保护公司数据和设备的安全的建议。 <br/><br/>推荐包含在 Defender for Business 中可以节省安全团队的时间和精力。 推荐基于行业最佳做法。 若要详细了解建议，请参阅安全建议[- 危险和漏洞管理。](../defender-endpoint/tvm-security-recommendation.md) |
| **事件** | 将你带去最近的事件列表。 触发警报时，将创建事件。 一个事件可以包含多个警报。 请务必定期查看事件。 <br/><br/>若要详细了解事件，请参阅在 Microsoft Defender for Business 中 [查看和管理事件](mdb-view-manage-incidents.md)。|
| **操作中心** | 将您带至响应操作列表，包括已完成或挂起的操作。 <br/>- 选择 **"历史记录** "选项卡以查看已采取的操作。 自动执行某些操作;其他人在获得批准后手动或完成。 <br/>- 选择" **挂起** "选项卡以查看需要审批的操作以继续。 <br/><br/>若要详细了解操作中心，请参阅在操作中心查看 [修正操作](mdb-review-remediation-actions.md)。 |
| **威胁分析** | 将你带去当前威胁的视图，并提供你威胁形势的概览视图。 威胁分析还包括来自 Microsoft 安全研究人员的报告和信息。 <br/><br/>若要了解有关威胁分析的更多信息，请参阅通过威胁分析跟踪和响应 [新出现的威胁](../defender-endpoint/threat-analytics.md)。 |
| **安全分数** | 为您提供公司安全位置的表示形式，并提供改进建议。<br/><br/>若要了解有关安全分数的信息，请参阅 [适用于设备的 Microsoft 安全分数](../defender-endpoint/tvm-microsoft-secure-score-devices.md)。 |
| **Learning中心** | 通过订阅中包含的学习路径提供对安全培训和其他资源的访问权限。 你可以按产品、技能级别、角色等进行筛选。 Learning中心可以帮助你的安全团队在 Defender for Business & 功能以及更多 Microsoft 产品（如[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)和 Microsoft Defender [for Office 365）上提升](../office-365-security/defender-for-office-365.md)安全功能。  |
| **终结点**  > **搜索** | 使你能够搜索已载入 Microsoft Defender for Business 的一个或多个设备。 |
| **终结点**  > **设备清单** | 使你能够搜索已载入 Microsoft Defender for Business 的一个或多个设备。 |
| **终结点**  > **漏洞管理** | 为您提供仪表板、建议、修正活动、软件清单和公司内的潜在弱点列表。 |
| **终结点**  > **教程** | 提供对演练和模拟的访问权限，以帮助你了解有关威胁防护功能如何工作更多信息。 <br/><br/>选择" **在尝试获取** 每个教程的模拟文件之前阅读演练"链接。 一些模拟Office应用（如 Microsoft Word）来阅读演练。 |
| **终结点**  > **设备配置** | 按操作系统和类型列出安全策略。 <br/><br/>若要了解有关安全策略和设置的信息，请参阅在 Microsoft Defender for Business 中 [查看或编辑策略](mdb-view-edit-policies.md)。 |
| **报表** | 列出可用的安全报告。 这些报告使你可以查看安全趋势、查看有关威胁检测和警报的详细信息，并了解有关公司易受攻击的设备的详细信息。 |
| **运行状况** | 使您可以查看服务运行状况状态并规划即将进行的更改。 <br/>-**选择"服务** 运行状况"以查看Microsoft 365包含在公司订阅中的服务运行状况。 <br/>- 选择 **消息中心** 以了解计划更改和预期内容。  |
| **角色&权限** | 使您可以将权限分配给公司中将管理安全并查看事件和报告的用户，Microsoft 365 Defender门户。 此外，还可以设置和管理设备组，以载入公司的设备并分配威胁防护策略。  |
| **设置** | 使你能够编辑 Microsoft 365 Defender 门户和 Microsoft Defender for Business 的设置。 例如，你可以将 (或) 上线，公司设备 (也称为终结点) 。 还可以定义规则（如警报抑制规则）并设置指示器以阻止或允许某些文件或进程。  |
| **更多资源** | 导航到其他门户，如Azure Active Directory。 请记住，Microsoft 365 Defender门户应满足您的需求，而无需导航到其他门户。 |

## <a name="complete-a-learning-module-about-incidents-and-response-actions"></a>完成有关事件和响应操作的学习模块

请参阅学习模块 [检测和响应安全问题](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/)，以大致了解事件和响应操作。 您将了解可以采取的事件队列、警报和响应操作。 本课程将帮助你开始在 Defender for Business 中处理事件。

> [!NOTE]
> 尽管学习模块 (检测和响应安全问题 [) ](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/) 实际上适用于 Microsoft Defender for Endpoint，但基本概念和整体流程与在 Defender for Business 中将看到的内容类似。

## <a name="next-steps"></a>后续步骤

现在，你已大致了解 Defender for Business，请尝试以下一个或多个任务：

- [尝试 Microsoft Defender for Business 中的教程和模拟](mdb-tutorials.md)

- [在 Microsoft Defender for Business 中管理设备](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解 Microsoft Defender for Business 中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [在 Microsoft Defender for Business 中查看或编辑策略](mdb-view-edit-policies.md)