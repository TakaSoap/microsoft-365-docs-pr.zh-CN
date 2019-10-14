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
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a><span data-ttu-id="8c727-103">为 Microsoft 365 企业版部署 SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c727-103">Deploy SharePoint and OneDrive for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8c727-104">*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="8c727-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8c727-105">SharePoint 和 Microsoft Teams 用于执行文件存储和共享、内容管理和协作，是 Microsoft 365 企业版的“专用于团队合作”价值的关键元素。</span><span class="sxs-lookup"><span data-stu-id="8c727-105">SharePoint and Microsoft Teams are how you do file storage and sharing, content management, and collaboration and are key elements of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="8c727-p101">SharePoint 还有高级安全功能，包括访问控制、权限以及动态加密和静态加密。SharePoint 安全性是 Microsoft 365 企业版的“智能安全性”价值的关键元素。</span><span class="sxs-lookup"><span data-stu-id="8c727-p101">SharePoint also has advanced security capabilities including access control with permissions and encryption in flight and at rest. SharePoint security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="8c727-108">如果完全不了解 SharePoint，请参阅 [SharePoint](https://products.office.com/sharepoint/collaboration) 和 [SharePoint 入门](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121)。</span><span class="sxs-lookup"><span data-stu-id="8c727-108">If you are brand new to SharePoint, see [SharePoint](https://products.office.com/sharepoint/collaboration) and [Get Started with SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).</span></span>

<span data-ttu-id="8c727-109">下面分阶段逐步介绍了如何完成构想 SharePoint 在组织中的作用，通过一系列渐进式发布让组织上手使用，并提升对最终用户的使用价值。</span><span class="sxs-lookup"><span data-stu-id="8c727-109">The following phases and steps guide you through the process of envisioning the role of SharePoint in your organization, onboarding your organization through a series of progressive rollouts, and driving usage and its value to your end users.</span></span> <span data-ttu-id="8c727-110">开始之前，请确保你配置了正确的[底层基础结构](deploy-workloads.md#foundation-infrastructure-prerequisites)阶段，以便 SharePoint 网站具有所需的安全功能。</span><span class="sxs-lookup"><span data-stu-id="8c727-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-workloads.md#foundation-infrastructure-prerequisites) phases so that your SharePoint sites have the security capabilities you need.</span></span> 

<span data-ttu-id="8c727-111">若要为 Microsoft 365 企业版部署 OneDrive，请参阅[适用于企业的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="8c727-111">To deploy OneDrive for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="8c727-112">阶段 1：构想</span><span class="sxs-lookup"><span data-stu-id="8c727-112">Phase 1: Envision</span></span>
<span data-ttu-id="8c727-113">在这一阶段中，集合 SharePoint 部署的组织合作伙伴，并确定组织如何利用 SharePoint 满足自己的业务需求。</span><span class="sxs-lookup"><span data-stu-id="8c727-113">In this phase, you gather the organization partners for your SharePoint deployment and determine how your organization will use SharePoint to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-deployment-members"></a><span data-ttu-id="8c727-114">第 1 步：集合 SharePoint 部署成员</span><span class="sxs-lookup"><span data-stu-id="8c727-114">Step 1: Gather your SharePoint deployment members</span></span>

<span data-ttu-id="8c727-p103">必须找到合适的人员听取他们的建议和反馈，才能在 [Microsoft 365 企业版底层基础结构](deploy-foundation-infrastructure.md)之上成功部署 SharePoint。这些关键人员包括业务决策者、IT 人员（如架构师和实现者）以及向最终用户宣传的人员。</span><span class="sxs-lookup"><span data-stu-id="8c727-p103">For a successful deployment of SharePoint on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="8c727-117">这三组人员可确保部署考虑到满足业务需求、文件夹和文档迁移的技术和安全性，以及供典型用户使用的成果。</span><span class="sxs-lookup"><span data-stu-id="8c727-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="8c727-118">结果</span><span class="sxs-lookup"><span data-stu-id="8c727-118">Result</span></span>

<span data-ttu-id="8c727-119">负责组织的业务、技术和最终用户视角的人员名单。</span><span class="sxs-lookup"><span data-stu-id="8c727-119">A list of people that represent the business, technical, and end user perspectives of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a><span data-ttu-id="8c727-120">第 2 步：确定 SharePoint 业务应用场景并排定优先级</span><span class="sxs-lookup"><span data-stu-id="8c727-120">Step 2: Determine and prioritize your SharePoint business scenarios</span></span>

<span data-ttu-id="8c727-p104">SharePoint 可用于不同用途。需要确定哪些用途能够满足业务需求。应确定将 SharePoint 用于满足团队、部门或整个组织的文档存储和共享、内容管理和协作需求。</span><span class="sxs-lookup"><span data-stu-id="8c727-p104">SharePoint can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="8c727-124">有关应用场景和功能列表，请参阅 [SharePoint](https://products.office.com/sharepoint/collaboration )。</span><span class="sxs-lookup"><span data-stu-id="8c727-124">See the list of scenarios and capabilities at [SharePoint](https://products.office.com/sharepoint/collaboration ).</span></span>

<span data-ttu-id="8c727-125">下面的业务核心可满足组织需求：</span><span class="sxs-lookup"><span data-stu-id="8c727-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="8c727-126">共享和协作</span><span class="sxs-lookup"><span data-stu-id="8c727-126">Share and Work Together</span></span> | <span data-ttu-id="8c727-127">充分利用团队网站、通信网站和同步。</span><span class="sxs-lookup"><span data-stu-id="8c727-127">Take advantage of team sites, collaboration sites, and sync.</span></span> |
| <span data-ttu-id="8c727-128">通知和交互</span><span class="sxs-lookup"><span data-stu-id="8c727-128">Inform and Engage</span></span> | <span data-ttu-id="8c727-129">未来将发布的信息。</span><span class="sxs-lookup"><span data-stu-id="8c727-129">Information coming in the future.</span></span> |
| <span data-ttu-id="8c727-130">变革</span><span class="sxs-lookup"><span data-stu-id="8c727-130">Transform</span></span> | <span data-ttu-id="8c727-131">使用 Flow 在应用和服务之间创建自动化工作流。</span><span class="sxs-lookup"><span data-stu-id="8c727-131">Uses Flow to create automated workflows between apps and services.</span></span> |
| <span data-ttu-id="8c727-132">利用集体性知识</span><span class="sxs-lookup"><span data-stu-id="8c727-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="8c727-133">使用搜索功能在组织内获取所需结果。</span><span class="sxs-lookup"><span data-stu-id="8c727-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="8c727-134">保护</span><span class="sxs-lookup"><span data-stu-id="8c727-134">Protect</span></span> | <span data-ttu-id="8c727-135">确保组织受到保护且合规。</span><span class="sxs-lookup"><span data-stu-id="8c727-135">Ensures your organization is secured and has the correct compliance.</span></span> |
|||

<span data-ttu-id="8c727-136">请参阅 [SharePoint 管理](https://docs.microsoft.com/sharepoint/sharepoint-online)，获取根据需求配置 SharePoint 的帮助资源。</span><span class="sxs-lookup"><span data-stu-id="8c727-136">See [SharePoint admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint for your needs.</span></span>

<span data-ttu-id="8c727-p105">了解 SharePoint 优势的一种方法是，检查个人、团队、部门或整个组织现在如何交互，然后查找可便于更轻松存储和共享文件的相应应用场景。请注意，对于一些应用场景，[Microsoft Teams](teams-workload.md) 可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="8c727-p105">One way to see the benefits of SharePoint is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

#### <a name="sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="8c727-139">针对高度管控数据的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="8c727-139">SharePoint site for highly regulated data</span></span>

<span data-ttu-id="8c727-140">高度管控数据受地区法规约束，它是组织最有价值的数据，例如商业机密、财务或人力资源信息以及组织策略。</span><span class="sxs-lookup"><span data-stu-id="8c727-140">Highly regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span> <span data-ttu-id="8c727-141">你可以对某个 SharePoint 网站进行相应配置，从而实现针对此类数据的限制访问、数据分类、数据丢失防护和加密。</span><span class="sxs-lookup"><span data-stu-id="8c727-141">You can configure a SharePoint site for restricted access, data classification, data loss prevention, and encryption for this type of data.</span></span> <span data-ttu-id="8c727-142">有关详细信息，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint 网站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="8c727-142">For the details, see [Microsoft Teams and SharePoint sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="8c727-143">结果</span><span class="sxs-lookup"><span data-stu-id="8c727-143">Result</span></span>
<span data-ttu-id="8c727-144">满足组织的文档存储和共享、内容管理、协作和安全需求的 SharePoint 应用场景列表。</span><span class="sxs-lookup"><span data-stu-id="8c727-144">A list of SharePoint scenarios that address your organization’s needs for document storage and sharing, content management, collaboration, and security.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="8c727-145">阶段 2：载入</span><span class="sxs-lookup"><span data-stu-id="8c727-145">Phase 2: Onboard</span></span>

<span data-ttu-id="8c727-146">在这一阶段中，计划 SharePoint 部署的技术方面，并开始向选定用户组发布它们。</span><span class="sxs-lookup"><span data-stu-id="8c727-146">In this phase, you plan for the technical aspects of a SharePoint deployment and start rolling them out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="8c727-147">先决条件：标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="8c727-147">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="8c727-148">若要保护对 SharePoint 网站的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8c727-148">To protect access to SharePoint sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="8c727-149">第 1 步：完成技术计划</span><span class="sxs-lookup"><span data-stu-id="8c727-149">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="8c727-150">开始技术规划前，请确定是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="8c727-150">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="8c727-151">如果贵公司有 50 个以上的席位，并且参与了[合格计划](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，则可以使用 FastTrack 福利，该福利免费提供，可指导你进行计划、迁移、部署和服务采用。</span><span class="sxs-lookup"><span data-stu-id="8c727-151">If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use FastTrack benefits, available at no additional cost to guide you through planning, migration, deployment, and service adoption.</span></span> <span data-ttu-id="8c727-152">你也可以使用我们的 FastTrack 载入向导自行完成此工作，使用 Office 365 帐户登录后即可从 [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) 获取此向导。</span><span class="sxs-lookup"><span data-stu-id="8c727-152">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="8c727-153">若要自行计划（或结合使用 FastTrack），需要确定网络和组织是否都已具备使用 SharePoint 的条件。</span><span class="sxs-lookup"><span data-stu-id="8c727-153">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint.</span></span> <span data-ttu-id="8c727-154">在底层基础结构中满足[网络退出条件](networking-exit-criteria.md)尤其重要，需要特别注意 Internet 带宽、吞吐量和流量延迟，以最大限度地提升基于 SharePoint 文档的附加流量的性能。</span><span class="sxs-lookup"><span data-stu-id="8c727-154">It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint-based documents.</span></span>

<span data-ttu-id="8c727-155">使用 [迁移至 SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)，为 SharePoint 推出做好准备：</span><span class="sxs-lookup"><span data-stu-id="8c727-155">Use [Migrate to SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) to prepare for your SharePoint rollout:</span></span> 

<span data-ttu-id="8c727-156">若要更好地了解 SharePoint 安全性，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="8c727-156">For a better understanding of security in SharePoint, review the following resources:</span></span>

-   [<span data-ttu-id="8c727-157">SharePoint 和 OneDrive 如何保护云数据</span><span class="sxs-lookup"><span data-stu-id="8c727-157">How SharePoint and OneDrive safeguard your data in the cloud</span></span>](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [<span data-ttu-id="8c727-158">OneDrive 和 SharePoint 中的数据加密</span><span class="sxs-lookup"><span data-stu-id="8c727-158">Data Encryption in OneDrive and SharePoint</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a><span data-ttu-id="8c727-159">结果</span><span class="sxs-lookup"><span data-stu-id="8c727-159">Result</span></span>

<span data-ttu-id="8c727-160">了解 SharePoint 网站、本地文件夹以及文档迁移和安全性，并且准备好开始向组织中的选定组发布 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="8c727-160">You understand SharePoint sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="8c727-161">第 2 步：运行 IT 试点</span><span class="sxs-lookup"><span data-stu-id="8c727-161">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="8c727-162">在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。</span><span class="sxs-lookup"><span data-stu-id="8c727-162">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="8c727-163">在 IT 试点期间：</span><span class="sxs-lookup"><span data-stu-id="8c727-163">During the IT pilot:</span></span>

- <span data-ttu-id="8c727-164">选择 IT 试点参与者可以实践的 SharePoint 业务应用场景。</span><span class="sxs-lookup"><span data-stu-id="8c727-164">Choose a SharePoint business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="8c727-165">为你的试验参与者提供一组练习，以测试 SharePoint 文档的存储、共享、协作和其他功能。</span><span class="sxs-lookup"><span data-stu-id="8c727-165">Give your pilot participants a set of exercises to test SharePoint document storage, sharing, collaboration, team-based scheduling, and other capabilities.</span></span>
- <span data-ttu-id="8c727-166">确定变更管理策略并生成材料，以在组织范围内推动用户采用。</span><span class="sxs-lookup"><span data-stu-id="8c727-166">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint.</span></span> <span data-ttu-id="8c727-167">变更管理资料可以包括电子邮件公告文本、内部培训计划、走廊海报和演示文稿。</span><span class="sxs-lookup"><span data-stu-id="8c727-167">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="8c727-168">这些材料可将 SharePoint 及其优势，以及提高认知度和推动使用的目标告知你的组织。</span><span class="sxs-lookup"><span data-stu-id="8c727-168">These materials will inform your organization about SharePoint and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="8c727-169">请参阅 [SharePoint 采纳资源](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) 以开始使用。</span><span class="sxs-lookup"><span data-stu-id="8c727-169">See the [SharePoint adoption resources](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) to get started.</span></span>
- <span data-ttu-id="8c727-170">让 IT 试点参与者根据自己的体验审阅变更管理材料。</span><span class="sxs-lookup"><span data-stu-id="8c727-170">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="8c727-171">他们可以提供最佳做法提示，并建议如何最准确说明 SharePoint 的优势以及如何使用它。</span><span class="sxs-lookup"><span data-stu-id="8c727-171">They can provide tips on best practices and advice on how to best describe the benefits of SharePoint and how to use it.</span></span>

#### <a name="result"></a><span data-ttu-id="8c727-172">结果</span><span class="sxs-lookup"><span data-stu-id="8c727-172">Result</span></span>

<span data-ttu-id="8c727-173">已完成 SharePoint IT 试点，且已制定、审阅和优化初始变更管理材料。</span><span class="sxs-lookup"><span data-stu-id="8c727-173">Your SharePoint IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="8c727-174">第 3 步：向业务组发布</span><span class="sxs-lookup"><span data-stu-id="8c727-174">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="8c727-175">完成 IT 试点后，向组织中的业务组或部门发布 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="8c727-175">After completing your IT pilot, roll out SharePoint to a business group or department in your organization.</span></span> <span data-ttu-id="8c727-176">此发布应包括：</span><span class="sxs-lookup"><span data-stu-id="8c727-176">This rollout should include:</span></span>

- <span data-ttu-id="8c727-177">确定业务组中的 SharePoint 关键业务应用场景。</span><span class="sxs-lookup"><span data-stu-id="8c727-177">Identification of key business scenarios for SharePoint within the business group.</span></span>
- <span data-ttu-id="8c727-178">公告活动，用以通知用户将 SharePoint 用于部门、工作或项目团队的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="8c727-178">Announcement activities to inform users of the expectations and timelines for SharePoint usage for departments and for working or project teams.</span></span>
- <span data-ttu-id="8c727-179">将业务组成员的本地文件夹和文档迁移到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="8c727-179">Migration of on-premises folders and documents of your business group members to SharePoint.</span></span>
- <span data-ttu-id="8c727-180">提供用户培训或资源链接，以介绍 SharePoint 及其使用方法。</span><span class="sxs-lookup"><span data-stu-id="8c727-180">Delivering user training or links to resources to introduce SharePoint and how to use it.</span></span> <span data-ttu-id="8c727-181">请观看 [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 视频培训。</span><span class="sxs-lookup"><span data-stu-id="8c727-181">See [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="8c727-182">设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。</span><span class="sxs-lookup"><span data-stu-id="8c727-182">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="8c727-183">发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。</span><span class="sxs-lookup"><span data-stu-id="8c727-183">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="8c727-184">结果</span><span class="sxs-lookup"><span data-stu-id="8c727-184">Result</span></span>

<span data-ttu-id="8c727-185">业务组正常运行 SharePoint，且变更管理材料已经过测试和优化。</span><span class="sxs-lookup"><span data-stu-id="8c727-185">A business group is up and running with SharePoint and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="8c727-186">阶段 3：提升价值</span><span class="sxs-lookup"><span data-stu-id="8c727-186">Phase 3: Drive value</span></span>

<span data-ttu-id="8c727-187">在这一阶段中，完成发布 SharePoint，并帮助用户认识到它的优势。</span><span class="sxs-lookup"><span data-stu-id="8c727-187">In this phase, you complete the rollout of SharePoint and help your users realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="8c727-188">第 1 步：向组织中的其余人员发布</span><span class="sxs-lookup"><span data-stu-id="8c727-188">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="8c727-189">向组织中的其余人员发布应包括：</span><span class="sxs-lookup"><span data-stu-id="8c727-189">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="8c727-190">确定各个业务组中的 SharePoint Online 关键业务应用场景。</span><span class="sxs-lookup"><span data-stu-id="8c727-190">Identification of key business scenarios for SharePoint Online within separate business groups.</span></span>
- <span data-ttu-id="8c727-191">使用优化后的变更管理材料开展公告活动，以告知组织用户相关使用的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="8c727-191">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="8c727-192">将组织中其余人员的文件夹和文档迁移到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="8c727-192">Migration of folders and documents for the rest of your organization to SharePoint.</span></span>
- <span data-ttu-id="8c727-193">提供用户培训或资源链接，以介绍 SharePoint 及其使用方法。</span><span class="sxs-lookup"><span data-stu-id="8c727-193">Delivering user training or provide links to resources to introduce SharePoint and how to use it.</span></span>
- <span data-ttu-id="8c727-p114">设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。</span><span class="sxs-lookup"><span data-stu-id="8c727-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="8c727-197">结果</span><span class="sxs-lookup"><span data-stu-id="8c727-197">Result</span></span>
<span data-ttu-id="8c727-198">组织开始启动并运行，且变更管理策略就绪，可以通知、培训和允许用户使用 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="8c727-198">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="8c727-199">第 2 步：衡量使用情况、管理满意度和提高采用率</span><span class="sxs-lookup"><span data-stu-id="8c727-199">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="8c727-200">向整个组织发布后，必须继续使用变更管理策略：</span><span class="sxs-lookup"><span data-stu-id="8c727-200">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="8c727-201">让领导层将 SharePoint 提升为用于文档存储和共享的主要工具。</span><span class="sxs-lookup"><span data-stu-id="8c727-201">Have your leadership promote SharePoint as the primary tool for document storage and sharing.</span></span>
- <span data-ttu-id="8c727-202">鼓励个人使用该工具在业务组、部门和工作及项目团队之间进行文档存储和共享。</span><span class="sxs-lookup"><span data-stu-id="8c727-202">Encourage individuals to use it for document storage and sharing among business groups, departments, and working and project teams.</span></span>

<span data-ttu-id="8c727-203">建议的活动如下：</span><span class="sxs-lookup"><span data-stu-id="8c727-203">Here are some suggested activities:</span></span>

- <span data-ttu-id="8c727-204">请参阅 [Office 365 的成功因素](https://aka.ms/successfactors)，了解与云服务采用有关的常规最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8c727-204">See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="8c727-p115">请参阅 [Office 365 活动报告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，了解整个组织的 Office 365 服务使用情况。如果不是组织的 Office 365 全局管理员，请让全局管理员向你的用户帐户授予“报告读取者”权限，以便你能够访问活动报告。</span><span class="sxs-lookup"><span data-stu-id="8c727-p115">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="8c727-207">监视反馈地点（中心 Teams 团队或 Yammer 的公用频道），获取个人在体验 SharePoint 后提出的问题和反馈。</span><span class="sxs-lookup"><span data-stu-id="8c727-207">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint.</span></span> <span data-ttu-id="8c727-208">尽快解决他们的疑问和问题，以避免个人受挫，并证明我们是支持发布的。</span><span class="sxs-lookup"><span data-stu-id="8c727-208">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="8c727-209">确定并培养每个业务组中的佼佼者，并强调他们在使用 SharePoint 时的成就和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8c727-209">Identify and nurture champions in each business group and highlight their accomplishments and best practices when using SharePoint.</span></span> <span data-ttu-id="8c727-210">将他们的成功事迹反映给组织，以展示项目的成功和采用。</span><span class="sxs-lookup"><span data-stu-id="8c727-210">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="8c727-211">通过得到业务组中技术领导的认可，将会在领导和同事间产生强大的影响。</span><span class="sxs-lookup"><span data-stu-id="8c727-211">Endorsement by technical leaders within a business group can exert a powerful influence over leadership and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="8c727-212">结果</span><span class="sxs-lookup"><span data-stu-id="8c727-212">Result</span></span>

<span data-ttu-id="8c727-213">组织已将 Microsoft 365 企业版中的 SharePoint 用作支持文档存储和协作的服务。</span><span class="sxs-lookup"><span data-stu-id="8c727-213">Your organization has adopted SharePoint in Microsoft 365 Enterprise to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="8c727-214">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="8c727-214">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8c727-215">若要一窥 Microsoft，并了解我们是如何部署 SharePoint 的，请参阅 [SharePoint 到云：了解 Microsoft 如何运行自己的迁移](https://www.microsoft.com/zh-CN/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration)。</span><span class="sxs-lookup"><span data-stu-id="8c727-215">To peek inside Microsoft and learn how we deployed SharePoint, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/zh-CN/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8c727-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8c727-216">Next steps</span></span>

<span data-ttu-id="8c727-217">若要持续维护 SharePoint，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="8c727-217">See these resources for the ongoing maintenance of SharePoint:</span></span> 

- [<span data-ttu-id="8c727-218">了解 SharePoint 中的权限级别</span><span class="sxs-lookup"><span data-stu-id="8c727-218">Understanding permission levels in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [<span data-ttu-id="8c727-219">自定义 SharePoint 网站权限</span><span class="sxs-lookup"><span data-stu-id="8c727-219">Customize SharePoint site permissions</span></span>](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [<span data-ttu-id="8c727-220">对 SharePoint 启用或禁用外部共享</span><span class="sxs-lookup"><span data-stu-id="8c727-220">Turn external sharing on or off for SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [<span data-ttu-id="8c727-221">设置和管理访问请求</span><span class="sxs-lookup"><span data-stu-id="8c727-221">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
