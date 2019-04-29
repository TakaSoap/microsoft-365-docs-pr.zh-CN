---
title: 为 Microsoft 365 企业版部署 SharePoint Online 和 OneDrive for Business
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 在你的组织中，逐步完成对 Microsoft 365 企业版中 SharePoint Online 的价值规划、推广和推动过程。
ms.openlocfilehash: 30fe3a971a869a4609d6b8ef2809692b4d4e5420
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400176"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a><span data-ttu-id="c0d68-103">为 Microsoft 365 企业版部署 SharePoint Online 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="c0d68-103">Deploy SharePoint Online and OneDrive for Business for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c0d68-104">*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="c0d68-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c0d68-105">SharePoint Online 和 Microsoft Teams 用于执行文件存储和共享、内容管理和协作，是 Microsoft 365 企业版的“专用于团队合作”价值的关键元素。</span><span class="sxs-lookup"><span data-stu-id="c0d68-105">SharePoint Online and Microsoft Teams is how you do file storage and sharing, content management, and collaboration and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="c0d68-p101">SharePoint Online 还有高级安全功能，包括访问控制、权限以及动态加密和静态加密。SharePoint Online 安全性是 Microsoft 365 企业版的“智能安全性”价值的关键元素。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p101">SharePoint Online also has advanced security capabilities including access control and permissions and encryption in flight and at rest. SharePoint Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="c0d68-108">如果完全不了解 SharePoint Online，请参阅 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 和 [SharePoint 入门](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)。</span><span class="sxs-lookup"><span data-stu-id="c0d68-108">If you are brand new to SharePoint Online, see [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) and [Get Started with SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).</span></span>

<span data-ttu-id="c0d68-109">下面分阶段逐步介绍了如何完成构想 SharePoint Online 在组织中的作用，通过一系列渐进式发布让组织上手使用，并提升对最终用户的使用价值。</span><span class="sxs-lookup"><span data-stu-id="c0d68-109">The following phases and steps guide you through the process of envisioning the role of SharePoint Online in your organization, onboarding your organization through a series of progressive rollouts, and driving usage its value to your end users.</span></span> <span data-ttu-id="c0d68-110">开始之前，请确保你配置了右侧的[基础结构](deploy-foundation-infrastructure.md)阶段，以便 SharePoint Online 网站具有所需的安全功能。</span><span class="sxs-lookup"><span data-stu-id="c0d68-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your SharePoint Online sites have the security capabilities you need.</span></span> 

<span data-ttu-id="c0d68-111">若要为 Microsoft 365 企业版部署 OneDrive for Business ，请参阅[适用于企业的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="c0d68-111">To deploy OneDrive for Business for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="c0d68-112">阶段 1：构想</span><span class="sxs-lookup"><span data-stu-id="c0d68-112">Phase 1: Envision</span></span>
<span data-ttu-id="c0d68-113">在这一阶段中，集合 SharePoint Online 部署人员，并确定组织如何利用他们满足自己的业务需求。</span><span class="sxs-lookup"><span data-stu-id="c0d68-113">In this phase, you gather the people for your SharePoint Online deployment and determine how your organization will use them to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a><span data-ttu-id="c0d68-114">第 1 步：集合 SharePoint Online 部署成员</span><span class="sxs-lookup"><span data-stu-id="c0d68-114">Step 1: Gather your SharePoint Online deployment members</span></span>

<span data-ttu-id="c0d68-p103">必须找到合适的人员听取他们的建议和反馈，才能在 [Microsoft 365 企业版底层基础结构](deploy-foundation-infrastructure.md)之上成功部署 SharePoint Online。这些关键人员包括业务决策者、IT 人员（如架构师和实现者）以及向最终用户宣传的人员。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p103">For a successful deployment of SharePoint Online on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="c0d68-117">这三组人员可确保部署考虑到满足业务需求、文件夹和文档迁移的技术和安全性，以及供典型用户使用的成果。</span><span class="sxs-lookup"><span data-stu-id="c0d68-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="c0d68-118">结果</span><span class="sxs-lookup"><span data-stu-id="c0d68-118">Result</span></span>

<span data-ttu-id="c0d68-119">负责组织的业务、技术和最终用户方面的人员名单。</span><span class="sxs-lookup"><span data-stu-id="c0d68-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a><span data-ttu-id="c0d68-120">第 2 步：确定 SharePoint Online 业务应用场景并排定优先级</span><span class="sxs-lookup"><span data-stu-id="c0d68-120">Step 2: Determine and prioritize your SharePoint Online business scenarios</span></span>

<span data-ttu-id="c0d68-p104">SharePoint Online 可用于不同用途。需要确定哪些用途能够满足业务需求。应确定将 SharePoint Online 用于满足团队、部门或整个组织的文档存储和共享、内容管理和协作需求。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p104">SharePoint Online can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint Online to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="c0d68-124">有关应用场景和功能列表，请参阅 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software)。</span><span class="sxs-lookup"><span data-stu-id="c0d68-124">See the list of scenarios and capabilities at [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).</span></span>

<span data-ttu-id="c0d68-125">下面的业务核心可满足组织需求：</span><span class="sxs-lookup"><span data-stu-id="c0d68-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="c0d68-126">共享和协作</span><span class="sxs-lookup"><span data-stu-id="c0d68-126">Share and Work Together</span></span> | <span data-ttu-id="c0d68-127">利用团队网站、协作网站和同步。</span><span class="sxs-lookup"><span data-stu-id="c0d68-127">Take advantage of team sites, collaboration sites, and sync.</span></span> |
| <span data-ttu-id="c0d68-128">通知和交互</span><span class="sxs-lookup"><span data-stu-id="c0d68-128">Inform and Engage</span></span> | <span data-ttu-id="c0d68-129">未来将发布的信息。</span><span class="sxs-lookup"><span data-stu-id="c0d68-129">Information coming in the future.</span></span> |
| <span data-ttu-id="c0d68-130">变革</span><span class="sxs-lookup"><span data-stu-id="c0d68-130">Transform</span></span> | <span data-ttu-id="c0d68-131">使用流来创建存储或工作流。</span><span class="sxs-lookup"><span data-stu-id="c0d68-131">Uses Flow to create a store or workflow.</span></span> |
| <span data-ttu-id="c0d68-132">利用集体性知识</span><span class="sxs-lookup"><span data-stu-id="c0d68-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="c0d68-133">使用搜索功能在组织内获取所需结果。</span><span class="sxs-lookup"><span data-stu-id="c0d68-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="c0d68-134">保护</span><span class="sxs-lookup"><span data-stu-id="c0d68-134">Protect</span></span> | <span data-ttu-id="c0d68-135">确保组织受到保护且合规。</span><span class="sxs-lookup"><span data-stu-id="c0d68-135">Ensures your organization is secured and has the correct compliance.</span></span> |
| <span data-ttu-id="c0d68-136">外部/开发</span><span class="sxs-lookup"><span data-stu-id="c0d68-136">External/Develop</span></span> | <span data-ttu-id="c0d68-137">允许组织使用 SharePoint 框架来开发自定义解决方案和应用。</span><span class="sxs-lookup"><span data-stu-id="c0d68-137">Lets your organization develop customize solutions and apps by using the SharePoint Framework.</span></span> |
|||

<span data-ttu-id="c0d68-138">请参阅 [SharePoint Online 管理](https://docs.microsoft.com/sharepoint/sharepoint-online)页面，获取根据需求配置 SharePoint Online 的帮助资源。</span><span class="sxs-lookup"><span data-stu-id="c0d68-138">See [SharePoint Online admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint Online for your needs.</span></span>

<span data-ttu-id="c0d68-p105">了解 SharePoint Online 优势的一种方法是，检查个人、团队、部门或整个组织现在如何交互，然后查找可便于更轻松存储和共享文件及协作的相应应用场景。请注意，对于一些应用场景，[Microsoft Teams](teams-workload.md) 可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p105">One way to see the benefits of SharePoint Online is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

<span data-ttu-id="c0d68-141">SharePoint Online 为 Microsoft 365 企业版提供这些战略业务方案：</span><span class="sxs-lookup"><span data-stu-id="c0d68-141">SharePoint Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="c0d68-142">与团队沟通以了解最新情况，征求意见，打造凝聚力和建立共识</span><span class="sxs-lookup"><span data-stu-id="c0d68-142">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="c0d68-143">利用集体性知识</span><span class="sxs-lookup"><span data-stu-id="c0d68-143">Harness collective knowledge</span></span>
- <span data-ttu-id="c0d68-144">便于用户变革业务流程</span><span class="sxs-lookup"><span data-stu-id="c0d68-144">Empower users to transform business processes</span></span>
- <span data-ttu-id="c0d68-145">塑造公司文化</span><span class="sxs-lookup"><span data-stu-id="c0d68-145">Shape the company culture</span></span>
- <span data-ttu-id="c0d68-146">管理项目、任务和截止时间，以达到业务目标</span><span class="sxs-lookup"><span data-stu-id="c0d68-146">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="c0d68-147">让第一线员工推动数字化转型</span><span class="sxs-lookup"><span data-stu-id="c0d68-147">Engage your firstline workers to enable your Digital Transformation</span></span>
- <span data-ttu-id="c0d68-148">了解工作习惯，以提升影响力</span><span class="sxs-lookup"><span data-stu-id="c0d68-148">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="c0d68-149">与合作伙伴、同事和客户沟通</span><span class="sxs-lookup"><span data-stu-id="c0d68-149">Communicate with partners, colleagues, and customers</span></span>
- <span data-ttu-id="c0d68-150">在组织内外存储和共享文件，以跨组织边界无缝工作</span><span class="sxs-lookup"><span data-stu-id="c0d68-150">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="c0d68-151">随时随地跨设备安全工作，在保持灵活工作方式的同时完成更多任务</span><span class="sxs-lookup"><span data-stu-id="c0d68-151">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="c0d68-152">保护信息并降低数据丢失风险</span><span class="sxs-lookup"><span data-stu-id="c0d68-152">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="c0d68-153">帮助组织增强隐私和合规性以符合一般数据保护条例 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="c0d68-153">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="c0d68-154">有关详细信息，请参阅[使用 Microsoft 365 实现数字化转型](http://transform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c0d68-154">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a><span data-ttu-id="c0d68-155">针对高度管控数据的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="c0d68-155">SharePoint Online site for highly regulated data</span></span>

<span data-ttu-id="c0d68-p106">高度管控数据是受区域法规约束或组织的最有价值的数据，例如商业秘密、财务或人力资源信息以及组织战略。你可以对某个 SharePoint Online 网站进行相应配置，从而实现针对此类数据的限制访问、数据分类、数据丢失防护和加密。有关详细信息，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a SharePoint Online site for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="c0d68-159">结果</span><span class="sxs-lookup"><span data-stu-id="c0d68-159">Result</span></span>
<span data-ttu-id="c0d68-160">满足组织的文档存储和共享、内容管理及协作需求的 SharePoint Online 应用场景列表。</span><span class="sxs-lookup"><span data-stu-id="c0d68-160">A list of SharePoint Online scenarios that address your organization’s needs for document storage and sharing, content management, and collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="c0d68-161">阶段 2：载入</span><span class="sxs-lookup"><span data-stu-id="c0d68-161">Phase 2: Onboard</span></span>

<span data-ttu-id="c0d68-162">在这一阶段中，计划 SharePoint Online 部署的技术方面，并开始向选定用户组发布它们。</span><span class="sxs-lookup"><span data-stu-id="c0d68-162">In this phase, you plan for the technical aspects of a SharePoint Online deployment and start rolling then out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="c0d68-163">先决条件：标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="c0d68-163">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="c0d68-164">若要保护对 SharePoint Online 网站的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint Online 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c0d68-164">To protect access to SharePoint Online sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="c0d68-165">第 1 步：完成技术计划</span><span class="sxs-lookup"><span data-stu-id="c0d68-165">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="c0d68-p107">开始技术计划前，请先确定是否要使用 FastTrack。如果组织有超过 50 个席位，且要参与[符合条件的计划](https://technet.microsoft.com/library/dn783224.aspx)，无需额外付费即可使用 FastTrack 权益，它逐步介绍了如何完成计划、部署和服务采用。也可以使用 FastTrack 新手入门向导自行完成这项工作，使用 Office 365 帐户登录后即可从 [FastTrack](https://fasttrack.microsoft.com/) 中获取向导。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use FastTrack benefits, available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="c0d68-p108">若要自行计划（或结合使用 FastTrack），需要确定网络和组织是否都已具备使用 SharePoint Online 的条件。在底层基础结构中满足网络退出条件尤其重要，需要特别注意 Internet 带宽、吞吐量和流量延迟，以最大限度地提升性能，便于发生基于 SharePoint Online 的文档的其他通信。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p108">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint Online-based documents.</span></span>

<span data-ttu-id="c0d68-171">若要为发布 SharePoint Online 技术方面做准备，请参阅下面这些资源：</span><span class="sxs-lookup"><span data-stu-id="c0d68-171">Use these resources to prepare for the technical aspects of a SharePoint Online rollout:</span></span> 

- [<span data-ttu-id="c0d68-172">SharePoint Online 计划指南</span><span class="sxs-lookup"><span data-stu-id="c0d68-172">SharePoint Online Planning Guide</span></span>](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [<span data-ttu-id="c0d68-173">迁移到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c0d68-173">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

<span data-ttu-id="c0d68-174">若要更好地了解 SharePoint Online 安全性，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="c0d68-174">For a better understanding of security in SharePoint Online, review the following resources:</span></span>

-   [<span data-ttu-id="c0d68-175">SharePoint Online 和 OneDrive 如何保护云数据</span><span class="sxs-lookup"><span data-stu-id="c0d68-175">How SharePoint Online and OneDrive safeguard your data in the cloud</span></span>](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [<span data-ttu-id="c0d68-176">OneDrive for Business 和 SharePoint Online 中的数据加密</span><span class="sxs-lookup"><span data-stu-id="c0d68-176">Data Encryption in OneDrive for Business and SharePoint Online</span></span>](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)

#### <a name="result"></a><span data-ttu-id="c0d68-177">结果</span><span class="sxs-lookup"><span data-stu-id="c0d68-177">Result</span></span>

<span data-ttu-id="c0d68-178">了解 SharePoint Online 网站、本地文件夹以及文档迁移和安全性，并且准备好开始向组织中的选定组发布 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="c0d68-178">You understand SharePoint Online sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="c0d68-179">第 2 步：运行 IT 试点</span><span class="sxs-lookup"><span data-stu-id="c0d68-179">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="c0d68-p109">在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。在 IT 试点期间：</span><span class="sxs-lookup"><span data-stu-id="c0d68-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="c0d68-182">选择 IT 试点参与者可以实践的 SharePoint Online 业务应用场景。</span><span class="sxs-lookup"><span data-stu-id="c0d68-182">Choose a SharePoint Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="c0d68-183">向试点参与者提供一组练习，以测试 SharePoint Online 文档存储、共享、协作、团队计划和其他功能。</span><span class="sxs-lookup"><span data-stu-id="c0d68-183">Give your pilot participants a set of exercises to test SharePoint Online document storage, sharing, collaboration, team-based scheduling, and other capabilities.</span></span>
- <span data-ttu-id="c0d68-p110">确定变更管理策略并生成材料，以在整个组织范围内推动用户采用 SharePoint Online。变更管理材料可以包括电子邮件公告文本、内部培训计划、走廊海报和演示文稿。这些材料可便于组织了解 SharePoint Online 及其优势，以及提高认知度和使用率这些目标。请参阅 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 变更管理策略文章，以汲取一些想法。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p110">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about SharePoint Online and its benefits with the goals of raising awareness and driving usage. See the change management strategy for [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="c0d68-p111">让 IT 试点参与者根据自己的体验审阅变更管理材料。他们可以提供最佳做法提示，并建议如何最准确说明 SharePoint Online 优势，以及如何将 SharePoint Online 用于通信和计划用途。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p111">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of SharePoint Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="c0d68-190">结果</span><span class="sxs-lookup"><span data-stu-id="c0d68-190">Result</span></span>

<span data-ttu-id="c0d68-191">已完成 SharePoint Online IT 试点，且已制定、审阅和优化初始变更管理材料。</span><span class="sxs-lookup"><span data-stu-id="c0d68-191">Your SharePoint Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="c0d68-192">第 3 步：向业务组发布</span><span class="sxs-lookup"><span data-stu-id="c0d68-192">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="c0d68-p112">完成 IT 试点后，向组织中的业务组或部门发布 SharePoint Online。此发布应包括：</span><span class="sxs-lookup"><span data-stu-id="c0d68-p112">After completing your IT pilot, roll out SharePoint Online to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="c0d68-195">确定业务组中的 SharePoint Online 关键业务应用场景。</span><span class="sxs-lookup"><span data-stu-id="c0d68-195">Identification of key business scenarios for SharePoint Online within the business group.</span></span>
- <span data-ttu-id="c0d68-196">公告活动，用以通知用户将 SharePoint Online 用于部门、工作或项目团队的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="c0d68-196">Announcement activities to inform users of the expectations and timelines for SharePoint Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="c0d68-197">将业务组成员的本地文件夹和文档迁移到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="c0d68-197">Migration of on-premises folders and documents of your business group members to SharePoint Online.</span></span>
- <span data-ttu-id="c0d68-p113">提供用户培训或资源链接，以介绍 SharePoint Online 及其使用方法。请观看 [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 视频培训。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p113">Delivering user training or links to resources to introduce SharePoint Online and how to use it. See [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="c0d68-200">设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。</span><span class="sxs-lookup"><span data-stu-id="c0d68-200">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="c0d68-201">发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。</span><span class="sxs-lookup"><span data-stu-id="c0d68-201">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="c0d68-202">结果</span><span class="sxs-lookup"><span data-stu-id="c0d68-202">Result</span></span>

<span data-ttu-id="c0d68-203">业务组正常运行 SharePoint Online，且变更管理材料已经过测试和优化。</span><span class="sxs-lookup"><span data-stu-id="c0d68-203">A business group is up and running with SharePoint Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="c0d68-204">阶段 3：提升价值</span><span class="sxs-lookup"><span data-stu-id="c0d68-204">Phase 3: Drive value</span></span>

<span data-ttu-id="c0d68-205">在这一阶段中，完成发布 SharePoint Online，以支持为用户带来优势。</span><span class="sxs-lookup"><span data-stu-id="c0d68-205">In this phase, you complete the rollout of SharePoint Online support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="c0d68-206">第 1 步：向组织中的其余人员发布</span><span class="sxs-lookup"><span data-stu-id="c0d68-206">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="c0d68-207">向组织中的其余人员发布应包括：</span><span class="sxs-lookup"><span data-stu-id="c0d68-207">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="c0d68-208">确定各个业务组中的 SharePoint Online 关键业务应用场景。</span><span class="sxs-lookup"><span data-stu-id="c0d68-208">Identification of key business scenarios for SharePoint Online Online within separate business groups.</span></span>
- <span data-ttu-id="c0d68-209">使用优化后的变更管理材料开展公告活动，以告知组织用户相关使用的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="c0d68-209">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="c0d68-210">将组织中其余人员的文件夹和文档迁移到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="c0d68-210">Migration of folders and documents for the rest of your organization to SharePoint Online.</span></span>
- <span data-ttu-id="c0d68-211">提供用户培训或资源链接，以介绍 SharePoint Online 及其使用方法。</span><span class="sxs-lookup"><span data-stu-id="c0d68-211">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span>
- <span data-ttu-id="c0d68-p114">设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="c0d68-215">结果</span><span class="sxs-lookup"><span data-stu-id="c0d68-215">Result</span></span>
<span data-ttu-id="c0d68-216">组织开始启动并运行，且变更管理策略就绪，可以通知、培训和允许用户使用 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="c0d68-216">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="c0d68-217">第 2 步：衡量使用情况、管理满意度和提高采用率</span><span class="sxs-lookup"><span data-stu-id="c0d68-217">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="c0d68-218">向整个组织发布后，必须继续使用变更管理策略：</span><span class="sxs-lookup"><span data-stu-id="c0d68-218">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="c0d68-219">让领导层将 SharePoint Online 提升为，用于文档存储和共享以及团队、部门或整个组织范围内协作的主要工具。</span><span class="sxs-lookup"><span data-stu-id="c0d68-219">Have your leadership promote SharePoint Online as the primary tool for document storage and sharing and team, division, or organization-wide collaboration.</span></span>
- <span data-ttu-id="c0d68-220">鼓励个人将其用于业务组、部门、工作和项目团队协作和日历。</span><span class="sxs-lookup"><span data-stu-id="c0d68-220">Encourage individuals to use it for business group, departmental, work, and project team collaboration and calendaring.</span></span>

<span data-ttu-id="c0d68-221">建议的活动如下：</span><span class="sxs-lookup"><span data-stu-id="c0d68-221">Here are some suggested activities:</span></span>

- <span data-ttu-id="c0d68-222">参阅 [Office 365 采用指南](https://aka.ms/successfactors)，了解与云服务采用有关的常规最佳做法。</span><span class="sxs-lookup"><span data-stu-id="c0d68-222">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="c0d68-p115">请参阅 [Office 365 活动报告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，了解整个组织的 Office 365 服务使用情况。如果不是组织的 Office 365 全局管理员，请让全局管理员向你的用户帐户授予“报告读取者”权限，以便你能够访问活动报告。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p115">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="c0d68-p116">监视反馈地点（中心 Teams 团队或 Yammer 的公用频道），获取个人在体验 SharePoint Online 后提出的问题和反馈。尽快解决他们的疑问和问题，以避免个人受挫，并证明我们是支持发布的。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p116">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="c0d68-p117">确定并培养每个业务组中的佼佼者，并强调他们在使用 SharePoint Online 时的成就和最佳做法。将他们的成功事迹反映给组织，以展示项目的成功和采用。通过得到业务组中技术领导的认可，将会在领导和同事间产生强大的影响。</span><span class="sxs-lookup"><span data-stu-id="c0d68-p117">Identify and nurture champions in each business group and highlight their accomplishments and best practices by using SharePoint Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="c0d68-230">结果</span><span class="sxs-lookup"><span data-stu-id="c0d68-230">Result</span></span>

<span data-ttu-id="c0d68-231">组织已将 SharePoint Online 用作支持文档存储和协作的服务。</span><span class="sxs-lookup"><span data-stu-id="c0d68-231">Your organization has adopted SharePoint Online as a service to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c0d68-232">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="c0d68-232">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c0d68-233">若要一窥 Microsoft，并了解这家公司是如何部署 SharePoint Online 的，请参阅 [SharePoint 到云：了解 Microsoft 如何运行自己的迁移](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)。</span><span class="sxs-lookup"><span data-stu-id="c0d68-233">To peek inside Microsoft and learn how the company deployed SharePoint Online, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0d68-234">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c0d68-234">Next steps</span></span>

<span data-ttu-id="c0d68-235">若要持续维护 SharePoint Online，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="c0d68-235">See these resources for the ongoing maintenance of SharePoint Online:</span></span> 

- [<span data-ttu-id="c0d68-236">了解 SharePoint 中的权限级别</span><span class="sxs-lookup"><span data-stu-id="c0d68-236">Understanding permission levels in SharePoint</span></span>](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [<span data-ttu-id="c0d68-237">自定义 SharePoint 网站权限</span><span class="sxs-lookup"><span data-stu-id="c0d68-237">Customize SharePoint site permissions</span></span>](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)
- [<span data-ttu-id="c0d68-238">对 SharePoint Online 启用或禁用外部共享</span><span class="sxs-lookup"><span data-stu-id="c0d68-238">Turn external sharing on or off for SharePoint Online</span></span>](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)
- [<span data-ttu-id="c0d68-239">设置和管理访问请求</span><span class="sxs-lookup"><span data-stu-id="c0d68-239">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

