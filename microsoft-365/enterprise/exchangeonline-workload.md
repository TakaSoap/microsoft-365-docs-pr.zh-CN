---
title: 部署适用于 Microsoft 365 企业版的 Exchange Online
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 逐步完成在组织内的 Microsoft 365 企业中规划、推出和驱动 Exchange Online 价值的过程。
ms.openlocfilehash: 9214796c37e9cb5ca9fcb07ced5db7efd8e0f7d0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634142"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>部署适用于 Microsoft 365 企业版的 Exchange Online

*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*

Exchange Online 是针对电子邮件和日历的主要云服务，可帮助你的用户以不需要实时聊天或集中存储文档的方式进行协作。 Exchange Online 是 Microsoft 365 企业的团队合作价值的关键元素。 借助 Exchange Online，无论您在使用什么设备，都可以使用已知的 Outlook 应用程序更有效地完成更多和工作。

Exchange Online 还拥有可保护邮箱的高级安全功能（包括反恶意软件和反垃圾邮件筛选），以及可防止用户错误地向未授权人员发送敏感信息的数据丢失预防功能。 Exchange Online security 是 Microsoft 365 企业版的智能安全价值的关键要素。

如果你是第一次使用 Exchange online，请参阅 [Microsoft Exchange online](https://products.office.com/exchange/exchange-online)。

以下阶段和步骤将指导您完成在组织中对 Exchange Online 角色进行构想的过程，通过一系列渐进式部署将组织加入 Exchange Online，并推动 Exchange Online 及其对最终用户的价值的使用。

>[!Note]
>仅在完成了第2阶段后，才应遵循以下部署说明[： Microsoft 365 企业版基础结构的标识](identity-infrastructure.md)。
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>第1阶段：构想 Exchange Online 部署

在此阶段中，您将为您的 Exchange Online 部署收集人员，并确定组织如何使用 Exchange Online 来满足其业务需求。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>步骤1：收集 Exchange Online 部署成员

若要在 Microsoft 365 企业版基础结构的[第2阶段（第2阶段](identity-infrastructure.md)）上成功部署 Exchange Online，您需要收集合适的人员进行输入和反馈。 关键人员包括业务决策者、IT 人员（如架构师和实施者），并支持最终用户。 

这三个组可确保您的 Exchange Online 部署包括满足业务需求的注意事项、邮箱迁移和安全性的技术方面以及结果是典型用户将使用的内容。

#### <a name="result"></a>结果

代表组织业务、技术和最终用户方面的人员列表。

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>步骤2：确定 Exchange Online 业务方案并确定其优先级

Exchange Online 可用于不同的用途。 您需要根据您的组织、业务组、部门或个人工作和项目团队的不同级别的业务需求来确定哪种用途对应。 应将 Exchange Online 设定为满足个人和小型组短期的通信和日程安排需求。 

了解 Exchange Online 优势的一种方法是，先检查个人、团队或团队的交互方式，然后查找提供更简单的方式来交流、安排会议和进行协作的适当方案。 请记住，对于某些协作方案， [Microsoft 团队](teams-workload.md)可能是更好的选择。

#### <a name="result"></a>结果
满足组织的通信、日程安排和短期协作需求的 Exchange Online 方案的列表。

## <a name="phase-2-onboard"></a>阶段 2：载入

在此阶段中，您将规划 Exchange Online 部署的技术方面，并开始将其推出给选定的用户组。

### <a name="prerequisites-identity-and-device-access-configuration"></a>先决条件：标识和设备访问配置

若要保护对 Exchange Online 邮箱的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 Exchange online 访问策略](secure-email-recommended-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>第 1 步：完成技术计划

开始技术规划前，请确定是否要使用 FastTrack。 如果您的组织有超过50的座位并且参与了[符合条件的计划](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，则可以使用[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365)，*无需额外成本*即可指导您完成规划、部署和服务采用。 你也可以使用我们的 FastTrack 载入向导自行完成此工作，使用 Office 365 帐户登录后即可从 [FastTrack](https://fasttrack.microsoft.com/) 获取此向导。

如果您正在进行自己的规划，或与 FastTrack 结合使用，则需要确定您的网络和组织是否已准备好进行 Exchange Online。 对于连接到组织网络的用户，在基础结构中满足[网络](networking-infrastructure.md)的退出条件尤其重要。 特别注意 Internet 带宽、吞吐量和流量延迟，以最大程度地提高基于 Exchange Online 的电子邮件和附件的额外流量的性能。

使用这些资源为 Exchange Online 部署的技术方面做准备： 

- [将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [将 Exchange Server 公用文件夹迁移到 Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [将 Exchange Server 公用文件夹迁移到 Microsoft 365 组](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Exchange Online 中的协作](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Exchange Online 中的收件人](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [iOS 和 Android 版 Outlook](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

若要更好地了解 Exchange Online 中的安全性，请查看以下资源：

- [Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Exchange Online 的安全性和合规性](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [反垃圾邮件和反恶意软件保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

接下来，请使用以下资源来了解 Exchange Online 邮箱管理：

- [在 Exchange Online 中创建用户邮箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [管理用户邮箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [创建和管理通讯组](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>结果

您了解邮箱迁移、安全性和管理，并准备好开始向组织中选定的组推出 Exchange Online。

### <a name="step-2-run-an-it-pilot"></a>第 2 步：运行 IT 试点

对于大多数中型和大型组织，应与您的利益干系人在第1阶段、早期采用者和技术爱好者之间运行 IT 试点。 在 IT 试点期间：

- 向你的试点参与者 Microsoft 365 许可证，并将其本地邮箱迁移到 Exchange Online。
- 为你的试点参与者提供一组练习来测试 Exchange Online 电子邮件、计划和其他功能。
- 确定您的更改管理策略并生成可促进组织范围内用户采用 Outlook 和 Exchange Online 的材料。 
 
  变更管理资料可以包括电子邮件公告文本、内部培训计划、走廊海报和演示文稿。 这些材料将告知组织有关 Exchange Online 及其优势的信息，以提高意识和促进使用的目标。 有关某些想法，请参阅[Microsoft 团队文章的更改管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)。

- 让 IT 试点参与者根据自己的体验审阅变更管理材料。 他们可以提供有关最佳做法的提示，并提供有关如何最大限度地说明 Outlook 和 Exchange Online 的优势以及如何使用它进行通信和日程安排的建议。

#### <a name="result"></a>结果

您的 Exchange Online IT 试点已完成，并且已开发、评审和优化初始变更管理材料。

### <a name="step-3-roll-out-to-a-business-group"></a>第 3 步：向业务组发布

完成 IT 试点后，将 Exchange Online 部署到组织中的业务组或部门。 如果您的组织使用的是本地电子邮件服务（如 Exchange Server），则此部署由邮箱迁移组成。 此发布应包括：

- 在业务组中确定 Exchange Online 的关键业务方案。
- 通知用户为部门、工作或项目团队的 Exchange Online 使用提供预期和日程表的通知活动。
- 将您的业务组成员的本地邮箱迁移到 Exchange Online。
- 在 Outlook 中提供[用户培训](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)或链接到介绍 outlook 和如何使用它的资源。
- 设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。

发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。

#### <a name="result"></a>结果

业务组已启动并在 Outlook 和 Exchange Online 中运行，并且已对更改管理资料进行了测试和改进。

## <a name="phase-3-drive-value"></a>阶段 3：提升价值

在这一阶段，您将完成 Exchange Online 的推出并支持您的用户帮助他们实现其优势。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>步骤1：将 Exchange Online 部署到组织的其余部分

向组织中的其余人员发布应包括：

- 在单独的业务组中标识 Exchange Online 的关键业务方案。
- 将精选的更改管理材料用于发布活动，以向组织提供 Exchange Online 使用的预期和日程表。
- 将组织其余部分的邮箱迁移到 Exchange Online。
- 在 Outlook 中提供[用户培训](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)，或提供指向介绍 outlook 和如何使用它的资源的链接。
- 设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。

#### <a name="result"></a>结果

您的组织已启动并在运行，并且您的更改管理策略已就绪，可以通知、培训和允许用户使用 Exchange Online。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>第 2 步：衡量使用情况、管理满意度和提高采用率

向整个组织推出 Exchange Online 后，必须继续使用您的更改管理策略执行以下操作：

- 让你的领导层将 Exchange Online 提升为用于个人和短期通信和日程安排的主要工具。
- 鼓励个人将其用于业务组、部门、工作和项目团队通信、日历和协作。

建议的活动如下：

- 请参阅[Microsoft 365 的成功因素](https://aka.ms/successfactors)，了解云服务采用的一般最佳实践。 
- 若要了解组织中的服务使用情况，请参阅[管理中心中的 Microsoft 365 报表](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)。 如果你不是组织的全局管理员，请让全局管理员的用户向你的用户帐户授予报告读者权限，以便你可以访问活动报告。
- 监视反馈场所（中心团队团队或 Yammer 中的公共渠道），了解个人是否遇到 Exchange Online 的问题和反馈。 尽快解决他们的疑问和问题，以避免个人受挫，并证明我们是支持发布的。
- 在每个业务组中找出并培养冠军，并使用 Outlook 突出显示其最佳实践。 将他们的成功事迹反映给组织，以展示项目的成功和采用。 由业务组内的技术领导者签署可对领导者和同行施加强大的影响。

#### <a name="result"></a>结果

您的组织已采用 Exchange Online 和 Outlook 作为其主要个人和小型组短寿命的通信和计划工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

若要查看并了解如何迁移到 Exchange Online 并了解如何使用 Exchange Online Protection 来防范网络攻击，请参阅：

- [Microsoft 将 150,000 个邮箱迁移到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft 使用威胁智能来保护、检测和响应威胁](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft 使用 Office 365 阻止网络钓鱼的尝试](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>后续步骤

有关日常维护 Exchange Online，请参阅以下资源：

- [Exchange Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Exchange Online 中的监视、报告和邮件跟踪](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [在 Exchange Online 中备份电子邮件](https://docs.microsoft.com/exchange/back-up-email) 
