---
title: 部署 Microsoft 365 企业版的 Exchange Online
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: 逐步完成规划、 推出，并在整个组织中 Microsoft 365 企业版驱动的 Exchange Online 值的过程。
ms.openlocfilehash: 36b24290acd4467400eab86b4c2760ccad65deab
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866021"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>部署 Microsoft 365 企业版的 Exchange Online

Exchange Online 是主要的云服务的电子邮件和日历，从而帮助您的用户协作不需要实时聊天或集中文档存储的方式。Exchange Online 是您如何单个和小型组短期通信和日程安排，并且是 Microsoft 365 enterprise 的团队协作值的内置的一个重要方面。Exchange Online 可以完成的详细信息和更有效地使用已知的 Outlook 应用程序，无论您是在何种设备。

Exchange Online 还具有高级安全功能包括反恶意软件和反垃圾邮件筛选保护邮箱和防止用户地将其发送到未经授权的人员的敏感信息的数据丢失防护功能。Exchange Online 的安全性是 Microsoft 365 enterprise 的智能安全值的一个重要方面。

如果您是全新到 Exchange Online，请参阅[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。

以下阶段和步骤指导您完成构想渐进式推出一系列到 Exchange Online 组织的 Exchange online 组织，入职培训中的角色和驱动的 Exchange Online 的使用情况的过程并将其向最终用户的值。

>[!Note]
>仅 Microsoft 365 enterprise 完成[foundation 基础](deploy-foundation-infrastructure.md)结构后，应遵循以下部署说明。
>

## <a name="phase-1-envision"></a>阶段 1：构想

在此阶段中，可以为 Exchange Online 部署收集人员和确定您的组织将如何使用 Exchange Online 以满足其业务需求。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>步骤 1： 收集您的 Exchange Online 部署成员

对于成功部署的 Exchange Online 在 Microsoft 365 [foundation 基础架构](deploy-foundation-infrastructure.md)，您需要获得输入和反馈的适当的人员。关键人员包括业务决策者、 IT 人员，如架构师和实施，以及为最终用户的拥护者。 

这三个组确保 Exchange Online 部署包括满足业务需求和邮箱迁移和安全性的技术方面，结果将为紧迫的典型用户将使用的注意事项。

#### <a name="result"></a>结果

代表组织业务、技术和最终用户方面的人员列表。

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>步骤 2： 确定并设置其优先级 Exchange Online 业务方案

Exchange Online 可用于不同的用途。您需要决定哪些目的将映射到您的组织、 业务部门、 部门或各个工作和项目团队的不同级别上的业务需求。您应面向 Exchange Online 以满足您的个人和小型组短期通信和计划需求。 

请参阅 Exchange Online 的优点的一种方法是检查如何个人、 团队或 v 团队如今，交互，然后查找提供更轻松的方式进行通信，安排会议和协作的相应方案。请记住[的 Microsoft 团队](teams-workload.md)可能的协作方案的一些更好的选择。

Exchange Online 为 Microsoft 365 企业版提供这些战略业务方案：

- 实时或按你自己的时间协作文档以简化共创过程
- 管理项目、任务和截止时间以达到业务目标
- 了解工作习惯，以提升影响力
- 与你的团队进行沟通以了解情况，征求意见，建立凝聚力和共识
- 存储和共享组织内部和外部的文件，以跨组织边界无缝工作
- 随时随地跨设备安全工作，在保持灵活工作方式的同时完成更多任务
- 保护信息并降低数据丢失风险
- 检测和防范外部威胁 
- 监视、 报告和分析活动迅速做出反应以提供组织的安全
- 帮助组织增强隐私和合规性以符合一般数据保护条例 (GDPR)

有关详细信息，请参阅[使用 Microsoft 365 实现数字化转型](http://transform.microsoft.com)。 

#### <a name="result"></a>结果
通信、 日程安排和短期协作满足您组织的 Exchange Online 方案的列表。

## <a name="phase-2-onboard"></a>阶段 2：上手使用

此阶段中，在您规划 Exchange Online 部署的技术方面，并开始实施所选用户组。

### <a name="prerequisites-identity-and-device-access-configuration"></a>先决条件： 标识和设备访问配置

若要保护 Exchange Online 邮箱的访问，请确保您已配置了[标识和设备访问策略](identity-access-policies.md)和[推荐 Exchange Online 的访问策略](secure-email-recommended-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>第 1 步：完成技术计划

技术规划之前，确定您是否要使用 FastTrack。如果您的组织已超过 50 座位和参与[合格的计划](https://technet.microsoft.com/library/dn783224.aspx)，则可以使用[Microsoft 365 FastTrack](https://fasttrack.microsoft.com/microsoft365)，可在任何其他的成本，用于指导您规划、 部署和服务应用。或者，可以使用 FastTrack 入职培训向导，它们是可从[FastTrack](https://fasttrack.microsoft.com/)一旦登录 Office 365 帐户完成此项工作。

如果您正在执行自己的规划，或与 FastTrack 结合使用，您需要确定您的网络和组织可供 Exchange Online。尤其重要您中具有 Internet 带宽、 吞吐量和通信延迟最大限度地 exchange 性能额外的流量特别注意您 foundation 基础结构满足网络的退出条件联机基于电子邮件和附件。

使用这些资源准备 Exchange Online 推出的技术方面： 

- [将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
- [Office 365 邮件迁移顾问](https://portal.office.com/onboarding/mailsetupadvisor#/)（必须登录到您的 Office 365 订阅）
- [Exchange Online 中的协作](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Exchange Online 中的收件人](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

有关更好地了解 Exchange Online 中的安全，查看以下资源：

- [Exchange Online 中的权限](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Exchange Online 的安全性和合规性](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [反垃圾邮件和反恶意软件保护](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

接下来，使用这些资源了解管理 Exchange Online 邮箱：

- [Exchange Online 中创建用户邮箱](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [管理用户邮箱](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [创建和管理通讯组](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>结果

您了解邮箱迁移、 安全性和管理，并已准备好开始推出 Exchange Online 到您的组织中的所选组。

### <a name="step-2-run-an-it-pilot"></a>步骤 2：运行 IT 试点

在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。在 IT 试点期间：

- 选择 Exchange Online 的业务方案，可以在其中实践 IT 试点参与者。
- 为试点参与者提供 Office 365 许可证并将其内部部署邮箱迁移到 Exchange Online。
- 为试点参与者提供一练习测试 Exchange Online 电子邮件、 日程安排以及其他功能。
- 确定您更改的管理策略，并生成到 Exchange online 的驱动器组织范围内用户应用资料。更改管理资料可以包括电子邮件通知文本、 内部培训计划、 走廊海报和演示文稿。有关 Exchange Online 和其优点与引发认知和驱动的使用情况的目标，这些资料将通知您的组织。请参阅的一些方法[更改 Microsoft 团队的管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)文章。
- 具有 IT 试点参与者查看基于其体验的更改管理材料。它们可以提供有关如何以最佳介绍 Exchange Online 的优点以及如何使用通信和日程安排的最佳做法的提示和建议。

#### <a name="result"></a>结果

Exchange Online IT 试点已完成，初始更改管理资料已开发，查看，并精简。

### <a name="step-3-roll-out-to-a-business-group"></a>步骤 3：推广到业务组

完成您的 IT 试生产之后, 推出 Exchange Online 到业务组或组织中的部门。如果您的组织使用如 Exchange 服务器的内部部署电子邮件服务，此推出包含邮箱迁移。此推出应包括：

- 标识关键业务方案的 Exchange Online 中的业务组。
- 要向用户告知期望和 Exchange Online 使用部门和工作或项目工作组的日程表的通知活动。
- 到 Exchange Online 您业务组成员的内部部署邮箱的迁移。
- 在 Exchange Online 或资源的链接介绍 Exchange Online 和如何使用它提供用户培训。
- 设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。

发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。

#### <a name="result"></a>结果

业务组已启动并运行与 Exchange Online 和更改管理资料已测试和精简。

## <a name="phase-3-drive-value"></a>阶段 3：推动价值

在此阶段中，可以完成的 Exchange Online 推出和支持您的用户，以帮助他们实现其好处。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>步骤 1： 推出 Exchange Online 到您的组织的其余部分

向组织中的其余人员发布应包括：

- 标识关键业务方案的 Exchange Online 的单独的业务组中。
- 使用您优化的更改管理资料的通知，告知您的组织的期望的活动和日程表 Exchange Online 的用法。
- 到 Exchange Online 组织的其余部分的邮箱的迁移。
- 提供用户培训在 Exchange Online 或提供介绍 Exchange Online 和如何使用它的资源的链接。
- 设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。

#### <a name="result"></a>结果

您的组织已启动并开始运行，且您更改的管理策略是为了告知、 培训，并使用户能够使用 Exchange Online。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步骤 2：衡量使用情况、管理满意度和推动采用

Exchange Online 向推出您的整个组织之后, 必须继续采用对您更改管理策略：

- 已将 Exchange Online 提升为单个和短期通信的主要工具您领导和计划。
- 鼓励个人用于业务组，部门、 工作，并且项目团队 communications、 日历和协作。

建议的活动如下：

- 参阅 [Office 365 采用指南](https://aka.ms/successfactors)，了解与云服务采用有关的常规最佳做法。 
- 请参阅 [Office 365 活动报告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，了解整个组织的 Office 365 服务使用情况。如果不是组织的 Office 365 全局管理员，请让全局管理员向你的用户帐户授予“报告读取者”权限，以便你能够访问活动报告。
- 监视您的反馈地点 （管理中心的团队团队或 Yammer 中的公共通道） 问题和有关其与 Exchange Online 体验的个人的反馈。快速可以可以防止失望的个人和演示推出支持解决问题和问题。
- 确定并培养拥护者每个业务组中的突出显示其成绩和使用 Exchange Online 的最佳实践。反映出到组织，以显示项目成功和采用其成功。认可业务组内的技术负责人可以施加通过负责人和对等方强大的影响。

#### <a name="result"></a>结果

Exchange Online 组织采用作为其主要单个和小型组短期通信和计划工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何使用 Microsoft 365 企业版

若要查看 Microsoft 内部并了解公司如何迁移到 Exchange Online 和使用 Exchange Online Protection 防御网络攻击，请参阅：

- [Microsoft 将 150,000 个邮箱迁移到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft 使用威胁智能来保护、检测和响应威胁](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft 使用 Office 365 阻止网络钓鱼的尝试](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>后续步骤

请参阅 Exchange online 的正在进行维护这些资源：

- [Exchange Online 中的 Exchange 管理中心](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Exchange Online 中的监视、报告和邮件跟踪](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [在 Exchange Online 中备份电子邮件](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
