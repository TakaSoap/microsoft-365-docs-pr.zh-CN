---
title: 为 Microsoft 365 企业版部署 SharePoint 和 OneDrive
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 在你的组织中，逐步完成对 SharePoint 的价值规划、推广和推动过程。
ms.openlocfilehash: 0cad129cdca5f5dcc072f583b2b651a2547fc5fd
ms.sourcegitcommit: 68c54a45dd663027528b99f883c6ef04b04b19b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2019
ms.locfileid: "37469144"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>为 Microsoft 365 企业版部署 SharePoint 和 OneDrive

*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*

SharePoint 和 Microsoft Teams 用于执行文件存储和共享、内容管理和协作，是 Microsoft 365 企业版的“专用于团队合作”价值的关键元素。 

SharePoint 还有高级安全功能，包括访问控制、权限以及动态加密和静态加密。SharePoint 安全性是 Microsoft 365 企业版的“智能安全性”价值的关键元素。

如果完全不了解 SharePoint，请参阅 [SharePoint](https://products.office.com/sharepoint/collaboration) 和 [SharePoint 入门](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121)。

下面分阶段逐步介绍了如何完成构想 SharePoint 在组织中的作用，通过一系列渐进式发布让组织上手使用，并提升对最终用户的使用价值。 开始之前，请确保你配置了正确的[底层基础结构](deploy-workloads.md#foundation-infrastructure-prerequisites)阶段，以便 SharePoint 网站具有所需的安全功能。 

若要为 Microsoft 365 企业版部署 OneDrive，请参阅[适用于企业的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。

## <a name="phase-1-envision"></a>阶段 1：构想
在这一阶段中，集合 SharePoint 部署的组织合作伙伴，并确定组织如何利用 SharePoint 满足自己的业务需求。

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>第 1 步：集合 SharePoint 部署成员

必须找到合适的人员听取他们的建议和反馈，才能在 [Microsoft 365 企业版底层基础结构](deploy-foundation-infrastructure.md)之上成功部署 SharePoint。这些关键人员包括业务决策者、IT 人员（如架构师和实现者）以及向最终用户宣传的人员。 

这三组人员可确保部署考虑到满足业务需求、文件夹和文档迁移的技术和安全性，以及供典型用户使用的成果。

#### <a name="result"></a>结果

负责组织的业务、技术和最终用户视角的人员名单。

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>第 2 步：确定 SharePoint 业务应用场景并排定优先级

SharePoint 可用于不同用途。需要确定哪些用途能够满足业务需求。应确定将 SharePoint 用于满足团队、部门或整个组织的文档存储和共享、内容管理和协作需求。 

有关应用场景和功能列表，请参阅 [SharePoint](https://products.office.com/sharepoint/collaboration )。

下面的业务核心可满足组织需求：

|||
|:-----|:-----|
| 共享和协作 | 充分利用团队网站、通信网站和同步。 |
| 通知和交互 | 未来将发布的信息。 |
| 变革 | 使用 Flow 在应用和服务之间创建自动化工作流。 |
| 利用集体性知识 | 使用搜索功能在组织内获取所需结果。 |
| 保护 | 确保组织受到保护且合规。 |
|||

请参阅 [SharePoint 管理](https://docs.microsoft.com/sharepoint/sharepoint-online)，获取根据需求配置 SharePoint 的帮助资源。

了解 SharePoint 优势的一种方法是，检查个人、团队、部门或整个组织现在如何交互，然后查找可便于更轻松存储和共享文件的相应应用场景。请注意，对于一些应用场景，[Microsoft Teams](teams-workload.md) 可能是更好的选择。

#### <a name="sharepoint-site-for-highly-regulated-data"></a>针对高度管控数据的 SharePoint 网站

高度管控数据受地区法规约束，它是组织最有价值的数据，例如商业机密、财务或人力资源信息以及组织策略。 你可以对某个 SharePoint 网站进行相应配置，从而实现针对此类数据的限制访问、数据分类、数据丢失防护和加密。 有关详细信息，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint 网站](teams-sharepoint-online-sites-highly-regulated-data.md)。

#### <a name="result"></a>结果
满足组织的文档存储和共享、内容管理、协作和安全需求的 SharePoint 应用场景列表。

## <a name="phase-2-onboard"></a>阶段 2：载入

在这一阶段中，计划 SharePoint 部署的技术方面，并开始向选定用户组发布它们。

### <a name="prerequisites-identity-and-device-access-configuration"></a>先决条件：标识和设备访问配置

若要保护对 SharePoint 网站的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>第 1 步：完成技术计划

开始技术规划前，请确定是否要使用 FastTrack。 如果贵公司有 50 个以上的席位，并且参与了[合格计划](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，则可以使用 FastTrack 福利，该福利免费提供，可指导你进行计划、迁移、部署和服务采用。 你也可以使用我们的 FastTrack 载入向导自行完成此工作，使用 Office 365 帐户登录后即可从 [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) 获取此向导。

若要自行计划（或结合使用 FastTrack），需要确定网络和组织是否都已具备使用 SharePoint 的条件。 在底层基础结构中满足[网络退出条件](networking-exit-criteria.md)尤其重要，需要特别注意 Internet 带宽、吞吐量和流量延迟，以最大限度地提升基于 SharePoint 文档的附加流量的性能。

使用 [迁移至 SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)，为 SharePoint 推出做好准备： 

若要更好地了解 SharePoint 安全性，请参阅以下资源：

-   [SharePoint 和 OneDrive 如何保护云数据](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [OneDrive 和 SharePoint 中的数据加密](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>结果

了解 SharePoint 网站、本地文件夹以及文档迁移和安全性，并且准备好开始向组织中的选定组发布 SharePoint。

### <a name="step-2-run-an-it-pilot"></a>第 2 步：运行 IT 试点

在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。 在 IT 试点期间：

- 选择 IT 试点参与者可以实践的 SharePoint 业务应用场景。
- 为你的试验参与者提供一组练习，以测试 SharePoint 文档的存储、共享、协作和其他功能。
- 确定变更管理策略并生成材料，以在组织范围内推动用户采用。 变更管理资料可以包括电子邮件公告文本、内部培训计划、走廊海报和演示文稿。 这些材料可将 SharePoint 及其优势，以及提高认知度和推动使用的目标告知你的组织。 请参阅 [SharePoint 采纳资源](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) 以开始使用。
- 让 IT 试点参与者根据自己的体验审阅变更管理材料。 他们可以提供最佳做法提示，并建议如何最准确说明 SharePoint 的优势以及如何使用它。

#### <a name="result"></a>结果

已完成 SharePoint IT 试点，且已制定、审阅和优化初始变更管理材料。

### <a name="step-3-roll-out-to-a-business-group"></a>第 3 步：向业务组发布

完成 IT 试点后，向组织中的业务组或部门发布 SharePoint。 此发布应包括：

- 确定业务组中的 SharePoint 关键业务应用场景。
- 公告活动，用以通知用户将 SharePoint 用于部门、工作或项目团队的预期和日程表。
- 将业务组成员的本地文件夹和文档迁移到 SharePoint。
- 提供用户培训或资源链接，以介绍 SharePoint 及其使用方法。 请观看 [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 视频培训。
- 设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。
 
发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。

#### <a name="result"></a>结果

业务组正常运行 SharePoint，且变更管理材料已经过测试和优化。

## <a name="phase-3-drive-value"></a>阶段 3：提升价值

在这一阶段中，完成发布 SharePoint，并帮助用户认识到它的优势。

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>第 1 步：向组织中的其余人员发布

向组织中的其余人员发布应包括：

- 确定各个业务组中的 SharePoint Online 关键业务应用场景。
- 使用优化后的变更管理材料开展公告活动，以告知组织用户相关使用的预期和日程表。
- 将组织中其余人员的文件夹和文档迁移到 SharePoint。
- 提供用户培训或资源链接，以介绍 SharePoint 及其使用方法。
- 设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。

#### <a name="result"></a>结果
组织开始启动并运行，且变更管理策略就绪，可以通知、培训和允许用户使用 SharePoint。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>第 2 步：衡量使用情况、管理满意度和提高采用率

向整个组织发布后，必须继续使用变更管理策略：

- 让领导层将 SharePoint 提升为用于文档存储和共享的主要工具。
- 鼓励个人使用该工具在业务组、部门和工作及项目团队之间进行文档存储和共享。

建议的活动如下：

- 请参阅 [Office 365 的成功因素](https://aka.ms/successfactors)，了解与云服务采用有关的常规最佳做法。 
- 请参阅 [Office 365 活动报告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，了解整个组织的 Office 365 服务使用情况。如果不是组织的 Office 365 全局管理员，请让全局管理员向你的用户帐户授予“报告读取者”权限，以便你能够访问活动报告。
- 监视反馈地点（中心 Teams 团队或 Yammer 的公用频道），获取个人在体验 SharePoint 后提出的问题和反馈。 尽快解决他们的疑问和问题，以避免个人受挫，并证明我们是支持发布的。
- 确定并培养每个业务组中的佼佼者，并强调他们在使用 SharePoint 时的成就和最佳做法。 将他们的成功事迹反映给组织，以展示项目的成功和采用。 通过得到业务组中技术领导的认可，将会在领导和同事间产生强大的影响。

#### <a name="result"></a>结果

组织已将 Microsoft 365 企业版中的 SharePoint 用作支持文档存储和协作的服务。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

若要一窥 Microsoft，并了解我们是如何部署 SharePoint 的，请参阅 [SharePoint 到云：了解 Microsoft 如何运行自己的迁移](https://www.microsoft.com/zh-CN/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration)。

## <a name="next-steps"></a>后续步骤

若要持续维护 SharePoint，请参阅以下资源： 

- [了解 SharePoint 中的权限级别](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [自定义 SharePoint 网站权限](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [对 SharePoint 启用或禁用外部共享](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [设置和管理访问请求](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
