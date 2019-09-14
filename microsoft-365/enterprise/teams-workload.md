---
title: 部署 Microsoft 365 企业版的 Microsoft Teams
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/28/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 在你的组织中，对 Microsoft 365 企业版中 Microsoft Teams 的价值逐步完成规划、推广和推动过程。
ms.openlocfilehash: fd2e72ddb0dfbcc437d30dee16241fbccc81b05b
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982613"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>部署 Microsoft 365 企业版的 Microsoft Teams

*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*

Microsoft Teams 集聊天、会议、文档共享和按线索组织对话等多项功能于一体，可以轻松地跨组创建和共享内容。Teams 不仅是你针对 Microsoft 365 企业版进行团队合作和协作的方式，还是构建 Microsoft 365 的团队合作价值的关键要素。如果你是 Teams 的全新用户，请参阅 [Microsoft Teams 概述](https://docs.microsoft.com/MicrosoftTeams/teams-overview)。
 
如果你当前使用的是 Skype for Business，我们正在将 Skype for Business 功能植入 Teams 中。这一功能指日可待，并且 Teams 最终将成为单一客户端体验。作为我们 Skype for Business 重要的客户，Microsoft 将随时为你提供支持。有关更多信息，请参阅[从 Skype for Business 到 Microsoft Teams 的旅程](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams)。

以下阶段和步骤将引导你完成构想组织中 Teams 角色的过程，通过一系列渐进式的部署将组织载入到 Teams 中，并推动 Teams 的使用和提升对最终用户的价值。 

开始之前，请确保你配置了右侧的[基础结构](deploy-foundation-infrastructure.md)阶段，以便团队具有所需的安全功能。

## <a name="phase-1-envision"></a>阶段 1：构想

在这个阶段，请集合 Teams 部署的人员，并确定组织将如何使用 Teams 来解决其业务需要。

### <a name="step-1-gather-your-teams-deployment-members"></a>步骤 1：集合 Teams 部署成员
为了在 Microsoft 365 [底层基础结构](deploy-foundation-infrastructure.md)之上成功部署 Teams，你需要找到合适的人员听取他们的建议和反馈。这些关键人员包括业务决策者、架构师和实施者等方面的 IT 人员，以及最终用户中的提倡者。 

这三组人员可确保你的 Teams 部署涵盖在解决业务需要、许可和安全性的技术方面要考虑的事项，以及确保 Teams 会成为你的典型用户将使用的功能。

#### <a name="result"></a>结果

代表组织业务、技术和最终用户方面的人员列表。

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a>步骤 2：确定并设置 Teams 业务应用场景的优先级
Teams 可用于很多不同的目的。你需要将组织、业务组、部门和各个工作和项目小组的业务需求与相关目的进行对应。有关帮助你定义 Teams 应用场景的示例，请查阅 [Microsoft 365 生产力库](https://www.microsoft.com/microsoft-365/success/?rtc=1)。 

你应将 Teams 用于定向解决快速发展且需要密切高度协作的团队的需求，他们需要使用的设施远不是 Exchange Online 电子邮件所能够提供的。例如，带有记录历史信息的实时群聊，以及用于存储文件和备注的常见且易于查找的位置。 

一种了解 Teams 优势的方法就是：检查一个团队或 v-team 目前的交互方式，然后找到一种适当的可替代这种交互的 Teams 应用场景，并在提供更多附加功能的同时提供更简单的进行协作的方法。

#### <a name="microsoft-teams-for-highly-regulated-data"></a>针对高度管控数据的 Microsoft Teams

高度管控数据是受区域法规约束或组织的最有价值的数据，例如商业秘密、财务或人力资源信息以及组织战略。你可以对某个团队进行相应配置，从而实现针对此类数据的限制访问、数据分类、数据丢失防护和加密。有关详细信息，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站](teams-sharepoint-online-sites-highly-regulated-data.md)。

#### <a name="result"></a>结果

能满足组织协作和团队合作需求的 Teams 应用场景列表。

## <a name="phase-2-onboard"></a>阶段 2：载入

在这个阶段中，需要计划 Teams 部署的技术方面，并开始向选定的用户组推广 Teams。

### <a name="prerequisites-identity-and-device-access-configuration"></a>先决条件：标识和设备访问配置

若要保护对团队的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint Online 访问策略](sharepoint-file-access-policies.md)。

### <a name="step-1-complete-your-technical-planning"></a>第 1 步：完成技术计划

在开始进行技术规划之前，请确定是否要使用 FastTrack。如果你的组织有超过 50 个座位且参与了[符合条件的计划](https://technet.microsoft.com/library/dn783224.aspx)，则可以使用[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，无需额外费用即可指导你完成规划、部署和服务采用。或者，你也可以使用我们的 FastTrack 载入向导自行完成这项工作，相关向导可在登录 Office 365 帐户后在 [FastTrack](https://fasttrack.microsoft.com/) 中找到。

如果你正在自己进行规划（或结合使用 FastTrack），则需要确定网络和组织是否都已具备使用 Teams 的条件。在[底层基础结构](deploy-foundation-infrastructure.md)中满足网络的退出条件尤其重要，需要特别注意带宽、吞吐量和流量延迟，以最大限度地使通过 Teams 安排的会议达到最佳性能。

使用这些资源准备在组织中进行 Teams 推广的技术方面： 

- [检查 Teams 的环境准备情况](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [准备用于 Teams 的网络](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

为了更好地理解 Teams 中的安全性，请查阅以下附加资源：

- [Teams 中的安全性和合规性概述](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Office 365 组和团队](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Teams 中的来宾访问](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

接下来，使用这些资源了解 Teams 许可，并为组织执行 Teams 设置：

- [Teams 的 Office 365 授权](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [管理 Microsoft Teams 的用户访问](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [获取 Microsoft Teams 客户端](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [打开 Office 365 组织中的 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [管理 Office 365 组织中的 Microsoft Teams 功能](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a>结果

已完成网络、安全性和 Office 365 许可规划，并准备好向组织中选定的组推广 Teams。

### <a name="step-2-run-an-it-pilot"></a>步骤 2：运行 IT 试点

在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。在 IT 试点期间：

- 选择 IT 试点参与者可以实践的 Teams 业务应用场景。请参阅 [Microsoft Teams 入门工具包](http://microsoft.com/download/56505)汲取更多想法。
- 为试点参与者提供一组练习来测试基于 Teams 的聊天、文件存储、会议和其他功能。
- 确定变更管理策略并生成材料，以在组织范围内推动用户采用。变更管理资料可以包括电子邮件公告文本、内部培训计划、走廊海报和演示文稿。这些材料可将 Teams 及其优势，以及提高认知度和推动使用的目标告知你的组织。请参阅 [Microsoft Teams 的变更管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)汲取更多想法。
- 让 IT 试点参与者基于他们的体验审查变更管理策略。他们可以提供关于最佳做法的提示和如何充分描述 Teams 优势，以及如何将其用于协作和团队合作的建议。

#### <a name="result"></a>结果

已完成 Teams IT 试点，并已开发、审查和优化初始变更管理材料。

### <a name="step-3-roll-out-to-a-business-group"></a>步骤 3：推广到业务组

完成 IT 试点后，将 Teams 推广到组织中的业务组或部门。此推广应包括：

- 确定在业务组中 Teams 的关键业务场景。
- 公告活动，用以通知用户将 Teams 用于部门、工作或项目团队的预期和日程表。
- 提供关于 Teams 的用户培训或指向介绍 Teams 及其使用方法的资源的链接。
- 设立反馈机制（如包含业务组任何用户的中心小组），收集业务组中用户的评论和问题。

推广期间，你可以优化变更管理材料，为组织范围内的推广做准备。

#### <a name="result"></a>结果

业务组开始运行 Teams，且变更管理材料经过测试和优化。

## <a name="phase-3-drive-value"></a>阶段 3：推动价值

在这个阶段，需要完成 Teams 在组织内的推广并对用户提供支持，以便其了解 Teams 的优势。

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a>步骤 1：向组织中的其余人员推广 Teams

对目标业务组完成推广后，需要继续向组织中的其余人员推广 Teams。此推广应该包括：

- 确定各个独立业务组使用 Teams 的关键业务场景。
- 使用优化后的变更管理材料开展公告活动，通知组织用户将 Teams 用于部门、工作或项目团队的预期和日程表。
- 提供关于 Teams 的用户培训或介绍 Teams 及其使用方法的资源的链接。请在 [Microsoft Teams 最终用户培训](https://docs.microsoft.com/microsoftteams/enduser-training)中查看培训资源。
- 设立反馈机制（如包含所有用户的中心小组），收集组织用户的评论并就问题采取行动。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道，否则，请使用 Yammer 中的公用组。

#### <a name="result"></a>结果

组织开始启动并运行，且变更管理策略就绪，可以通知、培训和允许用户开始使用 Teams。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>步骤 2：衡量使用情况、管理满意度和推动采用

向整个组织推广 Teams 后，必须继续使用变更管理策略进行以下推动：

- 让领导层将 Teams 提升为组织的团队合作和协作工具。
- 鼓励个人将其用于业务组、部门、工作和项目团队通信和协作。

建议的活动如下：

- 请参阅 [Office 365 采用指南](https://aka.ms/successfactors)，了解云服务采用的常规最佳做法。 
- 请参阅 [Office 365 活动报表](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，了解整个组织的 Office 365 服务使用情况。如果你不是组织的 Office 365 全局管理员，请让全局管理员授予你用户帐户“报表读取者”权限，以便访问活动报表。
- 监控你的反馈地点（中心小组或 Yammer 的公用频道），获取个人在体验 Teams 时的问题和反馈。尽快解决他们的疑问和问题，避免个人在使用 Teams 时因受挫而放弃。
- 确定并培养每个业务组中的佼佼者，突出他们在使用 Teams 中的成就和最佳做法，并将他们的成功事迹反映给组织，以展示项目的成功和采用。通过得到业务组中技术领导的认可，将会在领导和同事间产生强大的影响。

#### <a name="result"></a>结果

组织已采用 Teams 作为其协作和团队合作工具。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

若要深入了解 Microsoft，了解公司如何进行部署以及如何使用 Microsoft Teams 进行协作，请参阅：

- [部署 Microsoft Teams 可简化协作流程并增强团队合作](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [Microsoft Teams 可增强 Microsoft 现代工作场所中的协作](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a>后续步骤

- [管理 Office 365 组织中的 Microsoft Teams 功能](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Microsoft Teams 的管理员培训](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
