---
title: 案例研究-Contoso 为 Microsoft 团队、Exchange 和 Yammer 通信快速配置冒犯性语言策略
description: Contoso 的个案研究以及如何快速配置通信合规性策略以监视 Microsoft 团队、Exchange Online 和 Yammer 通信中的攻击性语言。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 9c20b322d4da0339d7c8711abcee38f19f556423
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289385"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>案例研究-Contoso 为 Microsoft 团队、Exchange 和 Yammer 通信快速配置冒犯性语言策略

Microsoft 365 中的通信合规性可帮助您在组织中检测、捕获和处理不适当的邮件，从而帮助最大限度地减少通信风险。 通过预定义和自定义策略，可以扫描策略匹配的内部和外部通信，以便指定的审阅者可以对其进行检查。 审阅者可以在组织中调查扫描的电子邮件、Microsoft 团队、Yammer 或第三方通信，并采取适当的补救措施以确保它们符合组织的邮件标准。

Contoso Corporation 是一个虚构的组织，需要快速配置一个策略来监视冒犯性语言。 他们一直使用 Microsoft 365，主要用于电子邮件、Microsoft 团队和 Yammer 对其用户的支持，但具有在工作区骚扰方面强制实施公司策略的新要求。 Contoso IT 管理员和合规性专家对使用 Microsoft 365 的基础有一个基本的了解，并且正在寻找有关如何快速开始实现通信合规性的端到端指南。

此案例研究将介绍快速配置通信合规性策略以监视攻击性语言通信的基础知识。 本指南包括：

- 第1步-规划通信合规性
- 第2步-访问 Microsoft 365 中的通信合规性
- 步骤 3-配置系统必备组件和创建通信合规性策略
- 第4步-调查和修正警报

## <a name="step-1-planning-for-communication-compliance"></a>步骤1：规划通信合规性

Contoso IT 管理员和合规性专家在 Microsoft 365 中参加了有关合规性解决方案的在线网络研讨会，并确定通信合规性策略将帮助他们满足针对减少工作区骚扰的更新的公司策略要求。 它们共同开发了一个计划，用于创建和启用通信合规性策略，该策略将监视在 Microsoft 团队中发送的攻击性语言、Yammer 中的私人邮件和社区对话以及在 Exchange Online 中发送的电子邮件中的聊天。 其计划包括标识：

- 需要访问通信合规性功能的 IT 管理员。
- 需要创建和管理通信策略的合规性专家。
- 其他部门的合规性专家和其他同事 (人力资源、法律等需要调查和修正通信合规性警报的 ) 。
- 将为通信合规性攻击性语言策略的范围内的用户。

### <a name="licensing"></a>许可

第一步是确认 Contoso 的 Microsoft 365 许可包括对通信合规性解决方案的支持。 若要访问和使用通信合规性，Contoso IT 管理员需要验证 Contoso 是否具有以下各项之一：

- Microsoft 365 E5 订阅 (付费或试用版) 
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规性加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 内幕人士风险管理加载项
- Microsoft 365 A5 订阅 (付费版或试用版) 
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规性加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 内幕成员风险管理加载项
- Microsoft 365 G5 订阅 (付费版或试用版) 
- Microsoft 365 G5 订阅 + Microsoft 365 G5 合规性附加
- Microsoft 365 G5 订阅 + Microsoft 365 G5 内幕版风险管理加载项
- Office 365 企业版 E5 订阅 (付费或试用版) 
- Office 365 企业版 E3 订阅 + Office 365 高级合规性外接程序 (不再可用于新订阅，请参阅 note) 

他们还必须确认必须为通信合规性策略中包括的用户分配上述许可证之一。

>[!IMPORTANT]
>Office 365 高级合规性不再作为独立订阅销售。 当当前订阅过期时，客户应转换为上述订阅之一，其中包含相同或更多的合规性功能。

Contoso IT 管理员需要执行以下步骤来验证 Contoso 的许可支持：

1. IT 管理员登录到**microsoft 365 管理中心** [ (https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 管理中心**  >  **帐单**  >  **许可证**。

2. 在这里，他们确认他们有一个 [许可证选项](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) ，其中包括支持通信合规性。

![通信合规性许可](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>通信合规性的权限

有五个角色组用于配置管理通信合规性功能的权限。 为了使 **通信合规性** 在 Microsoft 365 合规性中心中可用作菜单选项，若要继续执行这些配置步骤，则会为 Contoso 管理员分配 *通信合规性管理员* 角色。

Contoso 决定使用 *通信合规性* 角色组将所有通信合规性管理员、分析师、调查人员和查看者分配给组。 这使 Contoso 能够更轻松地快速入门，并最大限度地满足合规性管理要求。

|**角色**|**角色权限**|
|:-----|:-----|
| **通信合规性** | 使用此角色组管理单个组中的组织的通信合规性。 通过添加指定管理员、分析师、调查人员和查看者的所有用户帐户，您可以在单个组中配置通信合规性权限。 此角色组包含所有通信合规性权限角色。 此配置是快速开始使用通信合规性的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。 |
| **通信合规性管理员** | 使用此角色组最初配置通信合规性和更高版本，以将通信合规性管理员与定义的组隔离。 分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。 分配到此角色组的用户无法查看邮件通知。 |
| **通信合规性分析师** | 使用此组可将权限分配给将充当通信合规性分析员的用户。 分配到此角色组的用户可以查看将其分配为审阅者的策略、查看邮件元数据 (不是邮件内容) 、升级到其他审阅者或向用户发送通知。 分析师无法解决待处理的警报。 |
| **通信合规调查人员** | 使用此组将权限分配给将充当通信合规性调查人员的用户。 分配到此角色组的用户可以查看邮件元数据和内容、升级到其他审阅者、升级到高级电子数据展示事例、向用户发送通知以及解决警报。 |
| **通信合规性查看器** | 使用此组可为将管理通信报告的用户分配权限。 分配到此角色组的用户可以访问通信合规性主页上的所有报告小部件，并且可以查看所有通信合规性报告。 |

1. Contoso IT 管理员使用全局管理员帐户的凭据登录到**Office 365 安全 & 合规性中心**权限[ (https://protection.office.com/permissions) ](https://protection.office.com/permissions)页面，并选择在 Microsoft 365 中查看和管理角色的链接。
2. 在 **安全 & 合规性中心**中，它们转到 " **权限** "，然后选择要在 Office 365 中查看和管理角色的链接。
3. 管理员选择 " *通信合规性* " 角色组，然后选择 " **编辑角色组**"。
4. 管理员选择左侧导航窗格中的 " **选择成员** "，然后选择 " **编辑**"。
5. 选择 " **添加** "，然后选中将管理通信合规性、调查和查看警报的所有 Contoso 用户的复选框。
6. 管理员选择 " **添加**"，然后选择 " **完成**"。
7. 他们选择 " **保存** " 将 Contoso 用户添加到角色组。 选择 " **关闭** " 完成这些步骤。

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>步骤2：访问 Microsoft 365 中的通信合规性

在配置了通信合规性的权限之后，分配给通信合规性角色组的 Contoso IT 管理员和合规性专家可以访问 Microsoft 365 中的通信合规性解决方案。 Contoso IT 管理员和合规性专家有几种方法可以访问通信合规性并开始创建新策略：

- 直接从通信合规性解决方案开始
- 从 Microsoft 365 合规性中心开始
- 从 Microsoft 365 解决方案目录开始
- 从 Microsoft 365 管理中心开始

### <a name="starting-directly-from-the-communication-compliance-solution"></a>直接从通信合规性解决方案开始

访问解决方案的最快方法是直接登录到 **通信合规性** (<https://compliance.microsoft.com/supervisoryreview>) 解决方案。 使用此链接，Contoso IT 管理员和合规性专家将转到通信合规性概述仪表板，您可以在其中快速查看通知的状态并从预定义的模板创建新策略。

![通信合规性概述](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>从 Microsoft 365 合规性中心开始

Contoso IT 管理员和合规性专家访问通信合规性解决方案的另一种简单方法是直接登录到**Microsoft 365 合规中心** [ (https://compliance.microsoft.com) ](https://compliance.microsoft.com)。 登录后，用户只需选择 " **全部显示** " 控制即可显示所有合规性解决方案，然后选择要开始的 **通信合规性** 解决方案。

![合规性中心](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>从 Microsoft 365 解决方案目录开始

Contoso IT 管理员和合规性专家也可以通过选择 Microsoft 365 解决方案目录来选择访问通信合规性解决方案。 通过在**Microsoft 365 合规性中心**中选择左侧导航的 "**解决方案**" 部分中的 "**目录**"，他们可以打开列出所有 Microsoft 365 合规性解决方案的解决方案目录。 向下滚动到 " **内幕风险管理** " 部分，Contoso IT 管理员可以选择通信合规性以开始。 Contoso IT 管理员还决定使用导航控件中的 "显示" 将通信合规性解决方案固定到左导航窗格中，以便在以后登录时更快地进行访问。

![解决方案目录](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>从 Microsoft 365 管理中心开始

若要在从 microsoft 365 管理中心开始时访问通信合规性，Contoso IT 管理员和合规性专家登录到 microsoft 365 管理中心[ (https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 admin center**  >  **合规性**。

![通信合规性链接](../media/communication-compliance-case-compliance-link.png)

此操作将打开 **Office 365 安全与合规中心**，并且必须选择页面顶部的横幅中提供的 **Microsoft 365 合规性中心** 的链接。

![Office 365 安全与合规中心](../media/communication-compliance-case-scc.png)

在 **Microsoft 365 合规性中心**中，Contoso IT 管理员选择 " **全部显示** " 以显示完整的合规性解决方案列表。

![通信合规性菜单](../media/communication-compliance-case-show-all.png)

选择 " **全部显示**" 后，Contoso IT 管理员可以访问通信合规性解决方案。

![通信合规性概述](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>步骤3：配置系统必备组件和创建通信合规性策略

若要开始使用通信合规性策略，Contoso IT 管理员需要先配置一些先决条件，然后再设置新策略来监视冒犯性语言。 完成这些先决条件后，Contoso IT 管理员和合规性专家可以配置新策略和合规性专家，以开始调查并修正任何生成的警报。

### <a name="enabling-auditing-in-microsoft-365"></a>在 Microsoft 365 中启用审核

通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。 审核日志汇总了与已定义的组织策略相关联的所有活动，或只要有对通信合规性策略的更改。

Contoso IT 管理员查看并完成有关启用审核的 [分步说明](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) 。 在他们启用审核后，会显示一条消息，指出正在准备审核日志，并且在准备完成后，可以在几个小时内运行搜索。 Contoso IT 管理员只需执行一次此操作。

### <a name="configuring-yammer-tenant-for-native-mode"></a>为本机模式配置 Yammer 租户

通信合规性要求组织的 Yammer 租户处于本机模式，以监视私人邮件和公共社区对话中的冒犯性语言。

Contoso IT 管理员确保他们在 [microsoft 365 文章中查看 Yammer 本机模式概述](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) 中的信息，并按照在 [microsoft 365 文章的本机模式中配置 yammer 网络](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode) 中运行迁移工具的步骤进行操作。

### <a name="setting-up-a-group-for-in-scope-users"></a>为范围内用户设置组

Contoso 合规性专家希望将所有用户添加到将监视攻击性语言的通信策略中。 他们可以决定单独将每个用户帐户添加到策略中，但他们已决定使用此策略的用户的 **所有用户** 通讯组的时间更简单，并节省时间。

他们需要创建一个新组，以包含所有 Contoso 用户，因此他们需要执行以下步骤：

1. Contoso it 管理员：登录**microsoft 365 管理中心** [ (https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 管理中心**  >  **组**  >  **组**。
2. 他们选择 " **添加组** " 并完成向导，以创建新的 *Microsoft 365 组* 或 *通讯组*。

    ![组](../media/communication-compliance-case-all-employees.png)

3. 创建新组之后，需要将所有 Contoso 用户添加到新组中。 他们打开**exchange 管理中心** [ (https://outlook.office365.com/ecp) ](https://outlook.office365.com/ecp)并导航到**Exchange 管理中心**  >  **收件人**  >  **组**。 Contoso IT 管理员选择成员资格区域和他们创建的新的 *所有员工* 组，并在向导中选择 " **编辑** " 控件以将所有 Contoso 用户添加到新组中。

    ![Exchange 管理中心](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>创建用于监视冒犯性语言的策略

在满足所有先决条件的前提下，Contoso 的 IT 管理员和合规性专家可以配置通信合规性策略以监视攻击性语言。 使用新的冒犯性语言策略模板，配置此策略既简单又快速。

1. Contoso IT 管理员和合规性专家登录 **Microsoft 365 合规性中心** ，并从左侧导航窗格中选择 " **通信合规性** "。 此操作将打开 **概述** 仪表板，其中包含有关通信合规性策略模板的快速链接。 它们通过选择模板的 "**入门**" 来选择**用于攻击性语言**模板的监视器。

    ![通信合规性攻击性语言模板](../media/communication-compliance-case-template.png)

2. 在策略模板向导中，Contoso IT 管理员和合规性专家将共同完成以下三个必填字段： **策略名称**、 **要监督的用户或组**以及 **审阅者**。
3. 由于策略向导已经为策略建议了名称，IT 管理员和合规性专家决定保留建议的名称，并将重点放在其余字段上。 他们选择 "要管理的**用户或组**" 字段的 "*所有用户*" 组，然后选择应调查和修正**审阅者**字段策略通知的合规性专家。 配置策略和开始收集警报信息的最后一步是选择 " **创建策略**"。

    ![通信合规性冒犯性语言向导](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>步骤4：调查并修正警报

现在已配置用于监视攻击性语言的通信合规性策略，Contoso 合规性专家的下一步是调查并修正该策略生成的任何警报。 该策略最长需要24小时才能完全处理所有通信源通道中的通信，并且警报 **仪表板**中显示警报。

生成警报后，Contoso 合规性专家将遵循 [工作流说明](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) 来调查和修正攻击性语言问题。