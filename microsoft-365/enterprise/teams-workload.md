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
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="58681-103">部署 Microsoft 365 企业版的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58681-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="58681-104">*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="58681-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="58681-p101">Microsoft Teams 集聊天、会议、文档共享和按线索组织对话等多项功能于一体，可以轻松地跨组创建和共享内容。Teams 不仅是你针对 Microsoft 365 企业版进行团队合作和协作的方式，还是构建 Microsoft 365 的团队合作价值的关键要素。如果你是 Teams 的全新用户，请参阅 [Microsoft Teams 概述](https://docs.microsoft.com/MicrosoftTeams/teams-overview)。</span><span class="sxs-lookup"><span data-stu-id="58681-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365. If you are brand new to Teams, see [Overview of Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span>
 
<span data-ttu-id="58681-p102">如果你当前使用的是 Skype for Business，我们正在将 Skype for Business 功能植入 Teams 中。这一功能指日可待，并且 Teams 最终将成为单一客户端体验。作为我们 Skype for Business 重要的客户，Microsoft 将随时为你提供支持。有关更多信息，请参阅[从 Skype for Business 到 Microsoft Teams 的旅程](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="58681-p102">If you’re currently using Skype for Business, we’re building Skype for Business capabilities into Teams. This will happen over time, and ultimately Teams will become the single client experience. As a valued Skype for Business customer, Microsoft is here to support you. See the [Journey from Skype for Business to Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams) for more information.</span></span>

<span data-ttu-id="58681-112">以下阶段和步骤将引导你完成构想组织中 Teams 角色的过程，通过一系列渐进式的部署将组织载入到 Teams 中，并推动 Teams 的使用和提升对最终用户的价值。</span><span class="sxs-lookup"><span data-stu-id="58681-112">The following phases and steps guide you through the process of envisioning the role of Teams in your organization, onboarding your organization to Teams through a series of progressive rollouts, and driving usage of Teams and its value to your end users.</span></span> 

<span data-ttu-id="58681-113">开始之前，请确保你配置了右侧的[基础结构](deploy-foundation-infrastructure.md)阶段，以便团队具有所需的安全功能。</span><span class="sxs-lookup"><span data-stu-id="58681-113">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the security capabilities you need.</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="58681-114">阶段 1：构想</span><span class="sxs-lookup"><span data-stu-id="58681-114">Phase 1: Envision</span></span>

<span data-ttu-id="58681-115">在这个阶段，请集合 Teams 部署的人员，并确定组织将如何使用 Teams 来解决其业务需要。</span><span class="sxs-lookup"><span data-stu-id="58681-115">In this phase, you gather the people for your Teams deployment and determine how your organization will use Teams to address its business needs.</span></span>

### <a name="step-1-gather-your-teams-deployment-members"></a><span data-ttu-id="58681-116">步骤 1：集合 Teams 部署成员</span><span class="sxs-lookup"><span data-stu-id="58681-116">Step 1: Gather your Teams deployment members</span></span>
<span data-ttu-id="58681-p103">为了在 Microsoft 365 [底层基础结构](deploy-foundation-infrastructure.md)之上成功部署 Teams，你需要找到合适的人员听取他们的建议和反馈。这些关键人员包括业务决策者、架构师和实施者等方面的 IT 人员，以及最终用户中的提倡者。</span><span class="sxs-lookup"><span data-stu-id="58681-p103">For a successful deployment of Teams on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="58681-119">这三组人员可确保你的 Teams 部署涵盖在解决业务需要、许可和安全性的技术方面要考虑的事项，以及确保 Teams 会成为你的典型用户将使用的功能。</span><span class="sxs-lookup"><span data-stu-id="58681-119">These three groups ensure that your Teams deployment includes considerations that address business needs, technical aspects of licensing and security, and that Teams will be something that your typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="58681-120">结果</span><span class="sxs-lookup"><span data-stu-id="58681-120">Result</span></span>

<span data-ttu-id="58681-121">代表组织业务、技术和最终用户方面的人员列表。</span><span class="sxs-lookup"><span data-stu-id="58681-121">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a><span data-ttu-id="58681-122">步骤 2：确定并设置 Teams 业务应用场景的优先级</span><span class="sxs-lookup"><span data-stu-id="58681-122">Step 2: Determine and prioritize your Teams business scenarios</span></span>
<span data-ttu-id="58681-p104">Teams 可用于很多不同的目的。你需要将组织、业务组、部门和各个工作和项目小组的业务需求与相关目的进行对应。有关帮助你定义 Teams 应用场景的示例，请查阅 [Microsoft 365 生产力库](https://www.microsoft.com/microsoft-365/success/?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="58681-p104">Teams can be used for many different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, and individual working and project teams. Take a look at the [Microsoft 365 Productivity Library](https://www.microsoft.com/microsoft-365/success/?rtc=1) for examples to help you define Teams scenarios.</span></span> 

<span data-ttu-id="58681-p105">你应将 Teams 用于定向解决快速发展且需要密切高度协作的团队的需求，他们需要使用的设施远不是 Exchange Online 电子邮件所能够提供的。例如，带有记录历史信息的实时群聊，以及用于存储文件和备注的常见且易于查找的位置。</span><span class="sxs-lookup"><span data-stu-id="58681-p105">You should target Teams to address fast-moving and highly collaborative teams that work closely together and require many more facilities than just email with Exchange Online can provide. Examples are live group chats with a recorded history and a common and easy-to-find place to store files and notes.</span></span> 

<span data-ttu-id="58681-128">一种了解 Teams 优势的方法就是：检查一个团队或 v-team 目前的交互方式，然后找到一种适当的可替代这种交互的 Teams 应用场景，并在提供更多附加功能的同时提供更简单的进行协作的方法。</span><span class="sxs-lookup"><span data-stu-id="58681-128">One way to see the benefits of Teams is to examine how a team or v-team interacts today, and then find an appropriate Teams scenario that replaces the interaction and provides easier ways to collaborate and provide additional capabilities.</span></span>

#### <a name="microsoft-teams-for-highly-regulated-data"></a><span data-ttu-id="58681-129">针对高度管控数据的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58681-129">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="58681-p106">高度管控数据是受区域法规约束或组织的最有价值的数据，例如商业秘密、财务或人力资源信息以及组织战略。你可以对某个团队进行相应配置，从而实现针对此类数据的限制访问、数据分类、数据丢失防护和加密。有关详细信息，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="58681-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="58681-133">结果</span><span class="sxs-lookup"><span data-stu-id="58681-133">Result</span></span>

<span data-ttu-id="58681-134">能满足组织协作和团队合作需求的 Teams 应用场景列表。</span><span class="sxs-lookup"><span data-stu-id="58681-134">A list of Teams scenarios that address your organization’s needs for collaboration and teamwork.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="58681-135">阶段 2：载入</span><span class="sxs-lookup"><span data-stu-id="58681-135">Phase 2: Onboard</span></span>

<span data-ttu-id="58681-136">在这个阶段中，需要计划 Teams 部署的技术方面，并开始向选定的用户组推广 Teams。</span><span class="sxs-lookup"><span data-stu-id="58681-136">In this phase, you plan for the technical aspects of a Teams deployment and start rolling out Teams to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="58681-137">先决条件：标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="58681-137">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="58681-138">若要保护对团队的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint Online 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="58681-138">To protect access to teams, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="58681-139">第 1 步：完成技术计划</span><span class="sxs-lookup"><span data-stu-id="58681-139">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="58681-p107">在开始进行技术规划之前，请确定是否要使用 FastTrack。如果你的组织有超过 50 个座位且参与了[符合条件的计划](https://technet.microsoft.com/library/dn783224.aspx)，则可以使用[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，无需额外费用即可指导你完成规划、部署和服务采用。或者，你也可以使用我们的 FastTrack 载入向导自行完成这项工作，相关向导可在登录 Office 365 帐户后在 [FastTrack](https://fasttrack.microsoft.com/) 中找到。</span><span class="sxs-lookup"><span data-stu-id="58681-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment and service adoption. Or, you can complete this work yourself using our FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="58681-p108">如果你正在自己进行规划（或结合使用 FastTrack），则需要确定网络和组织是否都已具备使用 Teams 的条件。在[底层基础结构](deploy-foundation-infrastructure.md)中满足网络的退出条件尤其重要，需要特别注意带宽、吞吐量和流量延迟，以最大限度地使通过 Teams 安排的会议达到最佳性能。</span><span class="sxs-lookup"><span data-stu-id="58681-p108">If you are doing your own planning (or in conjunction with FastTrack), you need to determine if your network and organization are ready for Teams. It is especially important that you meet the exit criteria for networking in your [foundation infrastructure](deploy-foundation-infrastructure.md), with special attention to bandwidth, throughput, and traffic delays to maximize performance for Teams-based meetings.</span></span>

<span data-ttu-id="58681-145">使用这些资源准备在组织中进行 Teams 推广的技术方面：</span><span class="sxs-lookup"><span data-stu-id="58681-145">Use these resources to prepare the technical aspects of your organization for a Teams rollout:</span></span> 

- [<span data-ttu-id="58681-146">检查 Teams 的环境准备情况</span><span class="sxs-lookup"><span data-stu-id="58681-146">Check your environment's readiness for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [<span data-ttu-id="58681-147">准备用于 Teams 的网络</span><span class="sxs-lookup"><span data-stu-id="58681-147">Prepare your network for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [<span data-ttu-id="58681-148">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="58681-148">Office 365 URLs and IP address ranges</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

<span data-ttu-id="58681-149">为了更好地理解 Teams 中的安全性，请查阅以下附加资源：</span><span class="sxs-lookup"><span data-stu-id="58681-149">For a better understanding of security in Teams, review the following additional resources:</span></span>

- [<span data-ttu-id="58681-150">Teams 中的安全性和合规性概述</span><span class="sxs-lookup"><span data-stu-id="58681-150">Overview of security and compliance in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [<span data-ttu-id="58681-151">Office 365 组和团队</span><span class="sxs-lookup"><span data-stu-id="58681-151">Office 365 groups and Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [<span data-ttu-id="58681-152">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="58681-152">Guest access in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

<span data-ttu-id="58681-153">接下来，使用这些资源了解 Teams 许可，并为组织执行 Teams 设置：</span><span class="sxs-lookup"><span data-stu-id="58681-153">Next, use these resources to understand Teams licensing and to perform the setup of Teams for your organization:</span></span>

- [<span data-ttu-id="58681-154">Teams 的 Office 365 授权</span><span class="sxs-lookup"><span data-stu-id="58681-154">Office 365 licensing for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [<span data-ttu-id="58681-155">管理 Microsoft Teams 的用户访问</span><span class="sxs-lookup"><span data-stu-id="58681-155">Manage user access to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [<span data-ttu-id="58681-156">获取 Microsoft Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="58681-156">Get clients for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [<span data-ttu-id="58681-157">打开 Office 365 组织中的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58681-157">Turn on Microsoft Teams in your Office 365 organization</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [<span data-ttu-id="58681-158">管理 Office 365 组织中的 Microsoft Teams 功能</span><span class="sxs-lookup"><span data-stu-id="58681-158">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a><span data-ttu-id="58681-159">结果</span><span class="sxs-lookup"><span data-stu-id="58681-159">Result</span></span>

<span data-ttu-id="58681-160">已完成网络、安全性和 Office 365 许可规划，并准备好向组织中选定的组推广 Teams。</span><span class="sxs-lookup"><span data-stu-id="58681-160">Your network, security, and Office 365 licensing planning is done and you are ready to begin rolling out Teams to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="58681-161">步骤 2：运行 IT 试点</span><span class="sxs-lookup"><span data-stu-id="58681-161">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="58681-p109">在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。在 IT 试点期间：</span><span class="sxs-lookup"><span data-stu-id="58681-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="58681-p110">选择 IT 试点参与者可以实践的 Teams 业务应用场景。请参阅 [Microsoft Teams 入门工具包](http://microsoft.com/download/56505)汲取更多想法。</span><span class="sxs-lookup"><span data-stu-id="58681-p110">Choose a Teams business scenario in which your IT pilot participants can practice. See the [Microsoft Teams getting started kit](http://microsoft.com/download/56505) for ideas.</span></span>
- <span data-ttu-id="58681-166">为试点参与者提供一组练习来测试基于 Teams 的聊天、文件存储、会议和其他功能。</span><span class="sxs-lookup"><span data-stu-id="58681-166">Give your pilot participants a set of exercises to test Teams-based chats, file storage, meetings, and other capabilities.</span></span>
- <span data-ttu-id="58681-p111">确定变更管理策略并生成材料，以在组织范围内推动用户采用。变更管理资料可以包括电子邮件公告文本、内部培训计划、走廊海报和演示文稿。这些材料可将 Teams 及其优势，以及提高认知度和推动使用的目标告知你的组织。请参阅 [Microsoft Teams 的变更管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)汲取更多想法。</span><span class="sxs-lookup"><span data-stu-id="58681-p111">Determine your change management strategy and produce materials to drive organization-wide user adoption. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Teams and its benefits with the goals of raising awareness and driving usage. See [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) for some ideas.</span></span>
- <span data-ttu-id="58681-p112">让 IT 试点参与者基于他们的体验审查变更管理策略。他们可以提供关于最佳做法的提示和如何充分描述 Teams 优势，以及如何将其用于协作和团队合作的建议。</span><span class="sxs-lookup"><span data-stu-id="58681-p112">Have your IT pilot participants review the change management strategy materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Teams and how to use it for collaboration and teamwork.</span></span>

#### <a name="result"></a><span data-ttu-id="58681-173">结果</span><span class="sxs-lookup"><span data-stu-id="58681-173">Result</span></span>

<span data-ttu-id="58681-174">已完成 Teams IT 试点，并已开发、审查和优化初始变更管理材料。</span><span class="sxs-lookup"><span data-stu-id="58681-174">Your Teams IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="58681-175">步骤 3：推广到业务组</span><span class="sxs-lookup"><span data-stu-id="58681-175">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="58681-p113">完成 IT 试点后，将 Teams 推广到组织中的业务组或部门。此推广应包括：</span><span class="sxs-lookup"><span data-stu-id="58681-p113">After completing your IT pilot, roll out Teams to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="58681-178">确定在业务组中 Teams 的关键业务场景。</span><span class="sxs-lookup"><span data-stu-id="58681-178">Identification of key business scenarios for Teams within the business group.</span></span>
- <span data-ttu-id="58681-179">公告活动，用以通知用户将 Teams 用于部门、工作或项目团队的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="58681-179">Announcement activities to inform users of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="58681-180">提供关于 Teams 的用户培训或指向介绍 Teams 及其使用方法的资源的链接。</span><span class="sxs-lookup"><span data-stu-id="58681-180">Direct user training on Teams or links to resources to introduce Teams and how to use it.</span></span>
- <span data-ttu-id="58681-181">设立反馈机制（如包含业务组任何用户的中心小组），收集业务组中用户的评论和问题。</span><span class="sxs-lookup"><span data-stu-id="58681-181">A feedback mechanism, such as a central team containing everyone in the business group, to collect comments and issues from users in the business group.</span></span>

<span data-ttu-id="58681-182">推广期间，你可以优化变更管理材料，为组织范围内的推广做准备。</span><span class="sxs-lookup"><span data-stu-id="58681-182">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="58681-183">结果</span><span class="sxs-lookup"><span data-stu-id="58681-183">Result</span></span>

<span data-ttu-id="58681-184">业务组开始运行 Teams，且变更管理材料经过测试和优化。</span><span class="sxs-lookup"><span data-stu-id="58681-184">A business group is up and running with Teams and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="58681-185">阶段 3：推动价值</span><span class="sxs-lookup"><span data-stu-id="58681-185">Phase 3: Drive value</span></span>

<span data-ttu-id="58681-186">在这个阶段，需要完成 Teams 在组织内的推广并对用户提供支持，以便其了解 Teams 的优势。</span><span class="sxs-lookup"><span data-stu-id="58681-186">In this phase, you complete the rollout of Teams to your organization and support your users so that they are realizing its benefits.</span></span>

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a><span data-ttu-id="58681-187">步骤 1：向组织中的其余人员推广 Teams</span><span class="sxs-lookup"><span data-stu-id="58681-187">Step 1: Roll out Teams to the rest of your organization</span></span>

<span data-ttu-id="58681-p114">对目标业务组完成推广后，需要继续向组织中的其余人员推广 Teams。此推广应该包括：</span><span class="sxs-lookup"><span data-stu-id="58681-p114">After completing your rollout to a targeted business group, roll out Teams to the rest of your organization. This rollout should include:</span></span>

- <span data-ttu-id="58681-190">确定各个独立业务组使用 Teams 的关键业务场景。</span><span class="sxs-lookup"><span data-stu-id="58681-190">Identification of key business scenarios for Teams within your separate business groups.</span></span>
- <span data-ttu-id="58681-191">使用优化后的变更管理材料开展公告活动，通知组织用户将 Teams 用于部门、工作或项目团队的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="58681-191">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="58681-p115">提供关于 Teams 的用户培训或介绍 Teams 及其使用方法的资源的链接。请在 [Microsoft Teams 最终用户培训](https://docs.microsoft.com/microsoftteams/enduser-training)中查看培训资源。</span><span class="sxs-lookup"><span data-stu-id="58681-p115">Delivering user training on Teams or links to resources to introduce Teams and how to use it. See the training resources at [End user training for Microsoft Teams](https://docs.microsoft.com/microsoftteams/enduser-training).</span></span>
- <span data-ttu-id="58681-p116">设立反馈机制（如包含所有用户的中心小组），收集组织用户的评论并就问题采取行动。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道，否则，请使用 Yammer 中的公用组。</span><span class="sxs-lookup"><span data-stu-id="58681-p116">A feedback mechanism, such as a central team containing everyone, to collect comments and act on issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="58681-197">结果</span><span class="sxs-lookup"><span data-stu-id="58681-197">Result</span></span>

<span data-ttu-id="58681-198">组织开始启动并运行，且变更管理策略就绪，可以通知、培训和允许用户开始使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="58681-198">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to begin using Teams.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="58681-199">步骤 2：衡量使用情况、管理满意度和推动采用</span><span class="sxs-lookup"><span data-stu-id="58681-199">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="58681-200">向整个组织推广 Teams 后，必须继续使用变更管理策略进行以下推动：</span><span class="sxs-lookup"><span data-stu-id="58681-200">After rolling out Teams to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="58681-201">让领导层将 Teams 提升为组织的团队合作和协作工具。</span><span class="sxs-lookup"><span data-stu-id="58681-201">Have your leadership promote Teams as the teamwork and collaboration tool for the organization.</span></span>
- <span data-ttu-id="58681-202">鼓励个人将其用于业务组、部门、工作和项目团队通信和协作。</span><span class="sxs-lookup"><span data-stu-id="58681-202">Encourage individuals to use it for business group, departmental, work, and project team communications and collaboration.</span></span>

<span data-ttu-id="58681-203">建议的活动如下：</span><span class="sxs-lookup"><span data-stu-id="58681-203">Here are some suggested activities:</span></span>

- <span data-ttu-id="58681-204">请参阅 [Office 365 采用指南](https://aka.ms/successfactors)，了解云服务采用的常规最佳做法。</span><span class="sxs-lookup"><span data-stu-id="58681-204">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="58681-p117">请参阅 [Office 365 活动报表](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，了解整个组织的 Office 365 服务使用情况。如果你不是组织的 Office 365 全局管理员，请让全局管理员授予你用户帐户“报表读取者”权限，以便访问活动报表。</span><span class="sxs-lookup"><span data-stu-id="58681-p117">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is to grant your user account Reports Reader permissions so you can access activity reports.</span></span>
- <span data-ttu-id="58681-p118">监控你的反馈地点（中心小组或 Yammer 的公用频道），获取个人在体验 Teams 时的问题和反馈。尽快解决他们的疑问和问题，避免个人在使用 Teams 时因受挫而放弃。</span><span class="sxs-lookup"><span data-stu-id="58681-p118">Monitor your feedback venue (a public channel in a central team or Yammer) for issues and feedback from individuals about their experiences with Teams. Address questions and issues as quickly as you can to prevent frustration and abandonment of Teams by individuals.</span></span>
- <span data-ttu-id="58681-p119">确定并培养每个业务组中的佼佼者，突出他们在使用 Teams 中的成就和最佳做法，并将他们的成功事迹反映给组织，以展示项目的成功和采用。通过得到业务组中技术领导的认可，将会在领导和同事间产生强大的影响。</span><span class="sxs-lookup"><span data-stu-id="58681-p119">Identify and nurture your champions in each business group and highlight their accomplishments and best practices using Teams. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="58681-212">结果</span><span class="sxs-lookup"><span data-stu-id="58681-212">Result</span></span>

<span data-ttu-id="58681-213">组织已采用 Teams 作为其协作和团队合作工具。</span><span class="sxs-lookup"><span data-stu-id="58681-213">Your organization has adopted Teams as its collaboration and teamwork tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="58681-214">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="58681-214">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="58681-215">若要深入了解 Microsoft，了解公司如何进行部署以及如何使用 Microsoft Teams 进行协作，请参阅：</span><span class="sxs-lookup"><span data-stu-id="58681-215">To peek inside Microsoft and learn how the company deployed and is using Microsoft Teams for collaboration, see:</span></span>

- [<span data-ttu-id="58681-216">部署 Microsoft Teams 可简化协作流程并增强团队合作</span><span class="sxs-lookup"><span data-stu-id="58681-216">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="58681-217">Microsoft Teams 可增强 Microsoft 现代工作场所中的协作</span><span class="sxs-lookup"><span data-stu-id="58681-217">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a><span data-ttu-id="58681-218">后续步骤</span><span class="sxs-lookup"><span data-stu-id="58681-218">Next steps</span></span>

- [<span data-ttu-id="58681-219">管理 Office 365 组织中的 Microsoft Teams 功能</span><span class="sxs-lookup"><span data-stu-id="58681-219">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="58681-220">Microsoft Teams 的管理员培训</span><span class="sxs-lookup"><span data-stu-id="58681-220">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
