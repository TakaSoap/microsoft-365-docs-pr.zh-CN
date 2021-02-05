---
title: 案例研究 - Contoso 为 Microsoft Teams、Exchange 和 Yammer 通信快速配置冒犯性语言策略
description: Contoso 的案例研究，以及他们如何快速配置通信合规性策略以监视 Microsoft Teams、Exchange Online 和 Yammer 通信中的冒犯性语言。
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
ms.openlocfilehash: 5925ad7641370b26d0a272968a13028b74b81ef4
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50109993"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>案例研究 - Contoso 为 Microsoft Teams、Exchange 和 Yammer 通信快速配置冒犯性语言策略

Microsoft 365 中的通信合规性可帮助你检测、捕获和操作组织中不适当的邮件，从而有助于最大限度地降低通信风险。 预定义和自定义策略允许你扫描内部和外部通信中的策略匹配项，以便指定的审阅者可以检查它们。 审阅者可以调查组织中扫描的电子邮件、Microsoft Teams、Yammer 或第三方通信，并采取适当的修正措施，以确保他们符合组织的邮件标准。

Contoso Corporation 是一个虚构组织，需要快速配置策略以监视冒犯性语言。 他们一直主要将 Microsoft 365 用于电子邮件、Microsoft Teams 和 Yammer 用户支持，但对于强制执行公司关于工作场所骚扰的策略有新的要求。 Contoso IT 管理员和合规性专家对使用 Microsoft 365 的基础知识有基本的了解，并正在寻找有关如何快速开始使用通信合规性的端到端指南。

此案例研究将介绍快速配置通信合规性策略以监视攻击性语言通信的基础知识。 本指南包括：

- 步骤 1 - 规划通信合规性
- 步骤 2 - 访问 Microsoft 365 中的通信合规性
- 步骤 3 - 配置先决条件并创建通信合规性策略
- 步骤 4 - 调查和修正警报

## <a name="step-1-planning-for-communication-compliance"></a>步骤 1：规划通信合规性

Contoso IT 管理员和合规性专家参加 Microsoft 365 中有关合规性解决方案的联机网络研讨会，并决定通信合规性策略帮助他们满足更新的公司策略要求，以减少工作场所的骚扰。 通过协同工作，他们制定了创建和启用通信合规性策略的计划，该策略将监视 Microsoft Teams 中发送的聊天、Yammer 中的私人消息和社区对话以及 Exchange Online 中发送的电子邮件中的冒犯性语言。 他们的计划包括确定：

- 需要访问通信合规性功能的 IT 管理员。
- 需要创建和管理通信策略的合规性专家。
- 合规专家和其他部门的其他同事 (人力资源、法律等) 需要调查和修正通信合规性警报。
- 将在通信合规性冒犯性语言策略范围内的用户。

### <a name="licensing"></a>授权

第一步是确认 Contoso 的 Microsoft 365 许可包括对通信合规性解决方案的支持。 若要访问和使用通信合规性，Contoso IT 管理员需要验证 Contoso 是否具有以下项之一：

- Microsoft 365 E5 订阅（付费或试用版本）
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 预览体验成员风险管理加载项
- Microsoft 365 A5 订阅（付费或试用版本）
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 预览体验成员风险管理加载项
- Microsoft 365 G5 订阅（付费或试用版本）
- Microsoft 365 G5 订阅 + Microsoft 365 G5 合规加载项
- Microsoft 365 G5 订阅 + Microsoft 365 G5 预览体验成员风险管理加载项
- Office 365 企业版 E5 订阅（付费或试用版本）
- Office 365 企业版 E3 订阅 + Office 365 高级合规版加载项（新订阅已不再可用，请参阅注释）

他们还必须确认必须为通信合规性策略中包含的用户分配上述许可证之一。

>[!IMPORTANT]
>Office 365 高级合规版已不再作为独立订阅销售。 当前订阅到期后，客户应过渡到以上订阅之一，其中包含了相同的或其它合规性功能。

Contoso IT 管理员执行以下步骤来验证 Contoso 的许可支持：

1. IT 管理员登录到 Microsoft **365**[ https://admin.microsoft.com)](https://admin.microsoft.com)管理中心 (导航到 **Microsoft 365 管理中心**  >  **帐单**  >  **许可证**。

2. 在这里，他们确认他们具有一个 [许可证选项](communication-compliance-configure.md#subscriptions-and-licensing) ，其中包括对通信合规性的支持。

![通信合规性许可](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>通信合规性权限

共有 5 个角色组，用于配置权限以管理通信合规性功能。 为了将通信 **合规性** 作为 Microsoft 365 合规中心中的菜单选项提供，并继续执行这些配置步骤，Contoso 管理员分配有 *通信合规性管理员* 角色。

Contoso 决定使用 *通信* 合规性角色组，向该组分配所有通信合规性管理员、分析员、调查人员和查看者。 这样，Contoso 可以更轻松地快速入门，并最好地满足其合规性管理要求。

|**角色**|**角色权限**|
|:-----|:-----|
| **通信合规性** | 使用此角色组在单个组中管理组织的通信合规性。 通过添加指定管理员、分析者、调查者和查看者的所有用户账户，可以在单个组中配置通信合规性权限。 此角色组包含所有通信合规性权限角色。 这一配置是通信合规性快速入门的最简单方式，非常适合不需要为单独用户组定义单独权限的组织。 |
| **通信合规性管理员** | 使用此角色组进行通信合规性初始配置，后期可将通信合规性管理员隔离到已定义组中。 分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。 分配到此角色组的用户无法查看消息警报。 |
| **通信合规性分析者** | 使用此组向执行通信合规性分析者操作的用户分配权限。 分配到此角色组的用户可以查看分配其为审阅者的策略，查看消息元数据（而不是消息内容）、升级到其他审阅者，或向用户发送通知。 分析者不能解决挂起的警报。 |
| **通信合规性调查者** | 使用此组向执行通信合规性调查者操作的用户分配权限。 分配到此角色组的用户可以查看消息元数据和内容、升级到其他审阅者、升级到高级 eDiscovery 案例、向用户发送通知、以及解决警报。 |
| **通信合规性查看者** | 使用此组向管理通信报告的用户分配权限。 分配到此角色组的用户可以访问通信合规性主页上的所有报告小组件，并且可以查看所有通信合规性报告。 |

1. Contoso IT 管理员使用全局管理员帐户的凭据登录到 **Office 36 & 5** 安全与合规中心权限页面 [ (， https://protection.office.com/permissions)](https://protection.office.com/permissions)并选择该链接以查看和管理 Microsoft 365 中的角色。
2. 在 **安全&合规** 中心，他们转到"权限"并选择链接以查看和管理 Office 365 中的角色。
3. 管理员选择通信 *合规性角色组*，然后选择"编辑 **角色组"。**
4. 管理员 **从左侧导航** 窗格中选择"选择成员"，然后选择"编辑 **"。**
5. 他们选择 **"** 添加"，然后选中将管理通信合规性、调查和查看警报的所有 Contoso 用户的复选框。
6. 管理员选择"**添加"，** 然后选择"**完成"。**
7. 他们选择 **"保存** "将 Contoso 用户添加到角色组。 他们选择 **"关闭** "以完成这些步骤。

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>步骤 2：访问 Microsoft 365 中的通信合规性

配置通信合规性权限后，分配给通信合规性角色组的 Contoso IT 管理员和合规性专家可以访问 Microsoft 365 中的通信合规性解决方案。 Contoso IT 管理员和合规性专家通过多种方式访问通信合规性并开始创建新策略：

- 直接从通信合规性解决方案开始
- 从 Microsoft 365 合规中心开始
- 从 Microsoft 365 解决方案目录开始
- 从 Microsoft 365 管理中心开始

### <a name="starting-directly-from-the-communication-compliance-solution"></a>直接从通信合规性解决方案开始

访问解决方案的最快方法就是直接登录通信合规性 <https://compliance.microsoft.com/supervisoryreview> () 解决方案。 使用此链接，Contoso IT 管理员和合规性专家将被定向到通信合规性概述仪表板，您可以在其中快速查看警报的状态，并基于预定义的模板创建新策略。

![通信合规性概述](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>从 Microsoft 365 合规中心开始

Contoso IT 管理员和合规性专家访问通信合规性解决方案的另一种简单方法就是直接登录到 **Microsoft 365**[ https://compliance.microsoft.com)](https://compliance.microsoft.com)合规中心 (。 登录后，用户只需选择"显示所有控件"以显示所有合规性解决方案，然后选择通信 **合规性** 解决方案以开始操作。

![合规中心](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>从 Microsoft 365 解决方案目录开始

Contoso IT 管理员和合规性专家还可以选择 Microsoft 365 解决方案目录来访问通信合规性解决方案。 通过在Microsoft  **365** 合规中心内选择左侧导航的"解决方案"部分中的目录，他们可以打开列出所有 Microsoft 365 合规性解决方案的解决方案目录。 向下滚动到 **"内部风险管理** "部分，Contoso IT 管理员可以选择通信合规性以开始使用。 Contoso IT 管理员还决定使用导航中的"显示"控件将通信合规性解决方案固定到左侧导航窗格，以便他们今后登录时更快地访问。

![解决方案目录](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>从 Microsoft 365 管理中心开始

若要从 Microsoft 365 管理中心开始访问通信合规性，Contoso IT 管理员和合规性专家登录到 Microsoft 365 管理中心 [ (并 https://admin.microsoft.com)](https://admin.microsoft.com)导航到 **Microsoft 365** 管理中心合规性  >  。

![通信合规性链接](../media/communication-compliance-case-compliance-link.png)

此操作将打开 **Office 365** 安全与合规中心，他们必须选择页面顶部的横幅中提供的 **Microsoft 365** 合规中心链接。

![Office 365 安全与合规中心](../media/communication-compliance-case-scc.png)

进入 **Microsoft 365 合规** 中心后，Contoso IT管理员选择"全部显示"以显示合规性解决方案的完整列表。

![通信合规性菜单](../media/communication-compliance-case-show-all.png)

选择" **全部显示**"后，Contoso IT 管理员可以访问通信合规性解决方案。

![通信合规性概述](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>步骤 3：配置先决条件并创建通信合规性策略

若要开始使用通信合规性策略，Contoso IT 管理员需要在设置新策略以监视冒犯性语言之前配置几个先决条件。 完成这些先决条件后，Contoso IT 管理员和合规性专家可以配置新策略，合规性专家可以开始调查和修正任何生成的警报。

### <a name="enabling-auditing-in-microsoft-365"></a>在 Microsoft 365 中启用审核

通信合规性需要审核日志显示警报和跟踪审阅者采取的修正操作。 审核日志是与定义的组织策略关联的所有活动的摘要，或每当通信合规性策略发生变化时。

Contoso IT 管理员查看并完成[](turn-audit-log-search-on-or-off.md)启用审核的分步说明。 在启用审核后，将显示一条消息，指出审核日志准备，并且他们可以在准备完成后的几个小时内运行搜索。 Contoso IT 管理员只需执行一次此操作。

### <a name="configuring-yammer-tenant-for-native-mode"></a>为本机模式配置 Yammer 租户

通信合规性要求组织的 Yammer 租户在本机模式下监视私人消息和公共社区对话中的冒犯性语言。

Contoso IT 管理员确保他们查看 [Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) 中的 Yammer 本机模式概述文章中的信息，并按照 Microsoft [365](/yammer/configure-your-yammer-network/native-mode) 的本机模式配置 Yammer 网络文章中有关运行迁移工具的步骤操作。

### <a name="setting-up-a-group-for-in-scope-users"></a>为作用域内用户设置组

Contoso 合规性专家希望将所有用户添加到将监视冒犯性语言的通信策略中。 他们可以决定将每个用户帐户分别添加到策略中，但已决定要简单得多，并节省为此策略的用户使用"所有用户"通讯组的时间。

他们需要创建一个新组以包括所有 Contoso 用户，以便他们执行以下步骤：

1. Contoso IT 管理员 IT 登录到 **Microsoft 365**[ https://admin.microsoft.com)](https://admin.microsoft.com)管理中心 (并导航到 **Microsoft 365 管理中心**  >  **组**  >  **组**。
2. 他们选择 **"添加组"** 并完成向导以创建新的 *Microsoft 365 组* 或 *通讯组*。

    ![组](../media/communication-compliance-case-all-employees.png)

3. 创建新组后，他们需要将所有 Contoso 用户添加到新组。 他们打开 **Exchange 管理中心 (**[ https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp)导航到 Exchange **管理中心**  >  **收件人**  >  **组**。 Contoso IT 管理员选择"成员身份"区域及其创建的新"所有员工"组，然后选择"编辑"控件以将所有 Contoso 用户添加到向导中的新组。

    ![Exchange 管理中心](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>创建用于监视冒犯性语言的策略

完成所有先决条件后，CONtoso 的 IT 管理员和合规性专家已准备好配置通信合规性策略以监视冒犯性语言。 使用新的冒犯性语言策略模板，配置此策略非常简单和快速。

1. Contoso IT 管理员和合规性专家登录到 Microsoft **365** 合规中心，然后从左侧导航窗格中选择通信合规性。 此操作将打开 **"概述** "仪表板，该仪表板具有通信合规性策略模板的快速链接。 他们通过选择 **模板的** "入门 **"来选择** 攻击性语言模板的监视器。

    ![通信合规性冒犯性语言模板](../media/communication-compliance-case-template.png)

2. 在策略模板向导中，Contoso IT 管理员和合规性专家共同完成三个必填字段：策略名称、要监督的用户或组以及 **审阅者**。
3. 由于策略向导已建议策略的名称，因此 IT 管理员和合规性专家决定保留建议的名称，并重点关注其余字段。 他们为 *"用户"* 或组选择"所有用户"组来监督字段，并选择应调查和修正"审阅者"字段的策略警报的 **合规性专家。** 配置策略并开始收集警报信息的最后一步是选择"**创建策略"。**

    ![通信合规性冒犯性语言向导](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>步骤 4：调查和修正警报

现在已配置用于监视冒犯性语言的通信合规性策略，Contoso 合规专家的下一步是调查和修正策略生成的任何警报。 策略最多需要 24 小时才能完全处理所有通信源通道中的通信，警报会显示在 **警报仪表板中**。

生成警报后，Contoso 合规性专家将按照 [工作流](communication-compliance-investigate-remediate.md) 说明调查和修正冒犯性语言问题。