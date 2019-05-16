---
title: 部署适用于 Microsoft 365 企业版的 Exchange Online
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 逐步完成在组织内的 Microsoft 365 企业中规划、推出和驱动 Exchange Online 价值的过程。
ms.openlocfilehash: c54c80a955d86028ac473857cbdcb8b1a8f272d3
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072282"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="0e4ed-103">部署适用于 Microsoft 365 企业版的 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e4ed-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0e4ed-104">*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="0e4ed-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0e4ed-105">Exchange Online 是用于电子邮件和日历的主要云服务, 可帮助您的用户以不需要实时聊天或集中式文档存储的方式进行协作。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="0e4ed-106">Exchange Online 是您实现个人和小型组短期通信和计划的方式, 并且是 Microsoft 365 企业的团队合作价值的关键要素。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-106">Exchange Online is how you do individual and small group short-lived communication and scheduling and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="0e4ed-107">借助 Exchange Online, 无论您在使用什么设备, 都可以使用已知的 Outlook 应用程序更有效地完成更多和工作。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="0e4ed-108">Exchange Online 还具有高级安全功能, 包括反恶意软件和反垃圾邮件筛选, 以保护邮箱和数据丢失防护功能, 以防止用户错误地将敏感信息发送给未经授权的人员。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="0e4ed-109">Exchange Online security 是 Microsoft 365 企业版的智能安全价值的关键要素。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="0e4ed-110">如果你对 Exchange Online 全新品牌, 请参阅[Microsoft Exchange online](https://products.office.com/exchange/exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="0e4ed-111">下面的阶段和步骤将指导您完成在组织中对 Exchange Online 角色进行构想的过程, 通过一系列渐进式部署将组织加入 Exchange Online, 并推动 Exchange Online 和它的使用对最终用户的价值。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="0e4ed-112">仅在完成了[第2阶段](identity-infrastructure.md)后, 才应遵循以下部署说明: Microsoft 365 企业版基础结构的标识。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-112">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="0e4ed-113">阶段 1：构想</span><span class="sxs-lookup"><span data-stu-id="0e4ed-113">Phase 1: Envision</span></span>

<span data-ttu-id="0e4ed-114">在此阶段中, 您将为您的 Exchange Online 部署收集人员, 并确定组织如何使用 Exchange Online 来满足其业务需求。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="0e4ed-115">步骤 1: 收集 Exchange Online 部署成员</span><span class="sxs-lookup"><span data-stu-id="0e4ed-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="0e4ed-116">若要在 Microsoft 365 企业版基础结构的[第2阶段 (第2阶段](identity-infrastructure.md)) 上成功部署 Exchange Online, 您需要获取合适的人员进行输入和反馈。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to get the right people for input and feedback.</span></span> <span data-ttu-id="0e4ed-117">关键人员包括业务决策者、IT 人员 (如架构师和实施者), 并支持最终用户。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="0e4ed-118">这三个组确保您的 Exchange Online 部署包括满足业务需求的注意事项、邮箱迁移和安全性的技术方面以及结果将是典型用户将使用的内容。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="0e4ed-119">结果</span><span class="sxs-lookup"><span data-stu-id="0e4ed-119">Result</span></span>

<span data-ttu-id="0e4ed-120">代表组织业务、技术和最终用户方面的人员列表。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="0e4ed-121">步骤 2: 确定 Exchange Online 业务方案并确定其优先级</span><span class="sxs-lookup"><span data-stu-id="0e4ed-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="0e4ed-122">Exchange Online 可用于不同的用途。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="0e4ed-123">您需要根据您的组织、业务组、部门或个人工作和项目团队的不同级别的业务需求来确定哪种用途对应。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="0e4ed-124">应将 Exchange Online 设定为满足个人和小型组短期的通信和日程安排需求。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="0e4ed-125">了解 Exchange Online 优势的一种方法是, 先检查个人、团队或团队的交互方式, 然后查找提供更简单的方式来交流、安排会议和进行协作的适当方案。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="0e4ed-126">请记住, 对于某些协作方案, [Microsoft 团队](teams-workload.md)可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

<span data-ttu-id="0e4ed-127">Exchange Online 为 Microsoft 365 企业版启用这些战略业务方案:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-127">Exchange Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="0e4ed-128">实时或按自己的时间协作处理文档，以简化合著过程</span><span class="sxs-lookup"><span data-stu-id="0e4ed-128">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="0e4ed-129">管理项目、任务和截止时间以达到业务目标</span><span class="sxs-lookup"><span data-stu-id="0e4ed-129">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="0e4ed-130">了解工作习惯，以提升影响力</span><span class="sxs-lookup"><span data-stu-id="0e4ed-130">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="0e4ed-131">与你的团队进行沟通以了解情况，征求意见，建立凝聚力和共识</span><span class="sxs-lookup"><span data-stu-id="0e4ed-131">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="0e4ed-132">存储和共享组织内部和外部的文件，以跨组织边界无缝工作</span><span class="sxs-lookup"><span data-stu-id="0e4ed-132">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="0e4ed-133">随时随地跨设备安全工作，在保持灵活工作方式的同时完成更多任务</span><span class="sxs-lookup"><span data-stu-id="0e4ed-133">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="0e4ed-134">保护信息并降低数据丢失风险</span><span class="sxs-lookup"><span data-stu-id="0e4ed-134">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="0e4ed-135">检测和保护以防出现外部威胁</span><span class="sxs-lookup"><span data-stu-id="0e4ed-135">Detect and protect against external threats</span></span> 
- <span data-ttu-id="0e4ed-136">监控、报告和分析活动以及时响应以提供组织安全性</span><span class="sxs-lookup"><span data-stu-id="0e4ed-136">Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="0e4ed-137">帮助组织增强隐私和合规性以符合一般数据保护条例 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-137">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="0e4ed-138">有关详细信息，请参阅[使用 Microsoft 365 实现数字化转型](http://transform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-138">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="result"></a><span data-ttu-id="0e4ed-139">结果</span><span class="sxs-lookup"><span data-stu-id="0e4ed-139">Result</span></span>
<span data-ttu-id="0e4ed-140">满足组织的通信、日程安排和短期协作需求的 Exchange Online 方案的列表。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-140">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="0e4ed-141">阶段 2：载入</span><span class="sxs-lookup"><span data-stu-id="0e4ed-141">Phase 2: Onboard</span></span>

<span data-ttu-id="0e4ed-142">在此阶段中, 您将规划 Exchange Online 部署的技术方面, 并开始将其推出给选定的用户组。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-142">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="0e4ed-143">先决条件：标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="0e4ed-143">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="0e4ed-144">若要保护对 Exchange Online 邮箱的访问, 请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 Exchange online 访问策略](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-144">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="0e4ed-145">第 1 步：完成技术计划</span><span class="sxs-lookup"><span data-stu-id="0e4ed-145">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="0e4ed-146">在开始技术规划之前, 请确定是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-146">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="0e4ed-147">如果您的组织有超过50的座位并且参与了[符合条件的计划](https://technet.microsoft.com/library/dn783224.aspx), 则可以使用[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), 无需额外成本即可指导您完成规划、部署和服务采用。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-147">If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="0e4ed-148">或者, 您可以使用 FastTrack 载入向导完成此工作, 在使用 Office 365 帐户登录后, 即可在[FastTrack](https://fasttrack.microsoft.com/)中使用这些向导。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-148">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="0e4ed-149">如果您正在进行自己的规划, 或与 FastTrack 结合使用, 则需要确定您的网络和组织是否已准备好进行 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-149">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="0e4ed-150">尤其重要的是, 在基础结构中满足网络退出条件的需要, 特别关注 Internet 带宽、吞吐量和流量延迟, 以最大限度地提高 Exchange 的其他流量的性能基于联机的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-150">It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="0e4ed-151">使用这些资源为 Exchange Online 部署的技术方面做准备:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-151">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="0e4ed-152">将多个电子邮件帐户迁移到 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="0e4ed-152">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- <span data-ttu-id="0e4ed-153">[Exchange Online 中的协作](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-153">[Collaboration in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="0e4ed-154">[Exchange Online 中的收件人](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-154">[Recipients in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span></span>

<span data-ttu-id="0e4ed-155">若要更好地了解 Exchange Online 中的安全性, 请查看以下资源:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-155">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- <span data-ttu-id="0e4ed-156">[Exchange Online 中的权限](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-156">[Permissions in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="0e4ed-157">[Exchange Online 的安全性和合规性](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-157">[Security and compliance for Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="0e4ed-158">[反垃圾邮件和反恶意软件保护](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-158">[Anti-spam and anti-malware protection](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span></span>

<span data-ttu-id="0e4ed-159">接下来, 请使用以下资源来了解 Exchange Online 邮箱管理:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-159">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- <span data-ttu-id="0e4ed-160">[在 Exchange Online 中创建用户邮箱](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-160">[Create user mailboxes in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="0e4ed-161">[管理用户邮箱](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-161">[Manage user mailboxes](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span></span> 
- [<span data-ttu-id="0e4ed-162">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="0e4ed-162">Create and manage distribution groups</span></span>](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a><span data-ttu-id="0e4ed-163">结果</span><span class="sxs-lookup"><span data-stu-id="0e4ed-163">Result</span></span>

<span data-ttu-id="0e4ed-164">您了解邮箱迁移、安全性和管理, 并准备好开始向组织中选定的组推出 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-164">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="0e4ed-165">步骤 2：运行 IT 试点</span><span class="sxs-lookup"><span data-stu-id="0e4ed-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="0e4ed-p108">在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。在 IT 试点期间：</span><span class="sxs-lookup"><span data-stu-id="0e4ed-p108">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="0e4ed-168">选择你的 IT 试点参与者可以实践的 Exchange Online 业务方案。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-168">Choose an Exchange Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="0e4ed-169">向你的试点参与者 Office 365 许可证, 并将其本地邮箱迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-169">Give your pilot participants Office 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="0e4ed-170">为你的试点参与者提供一组练习来测试 Exchange Online 电子邮件、计划和其他功能。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-170">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="0e4ed-171">确定更改管理策略并生成可促进组织范围内用户采用 Exchange Online 的材料。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-171">Determine your change management strategy and produce materials to drive organization-wide user adoption of Exchange Online.</span></span> <span data-ttu-id="0e4ed-172">变更管理材料可包括电子邮件通知文本、内部培训计划、hallway 海报和演示文稿。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-172">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="0e4ed-173">这些材料将告知组织有关 Exchange Online 及其优势的信息, 以提高意识和促进使用的目标。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-173">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="0e4ed-174">有关某些想法, 请参阅[Microsoft 团队文章的更改管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-174">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="0e4ed-175">让 IT 试点参与者根据他们的经验查看更改管理材料。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-175">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="0e4ed-176">他们可以提供有关最佳做法的提示, 并提供有关如何最大限度地说明 Exchange Online 的优势以及如何将其用于通信和日程安排的建议。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-176">They can provide tips on best practices and advice on how to best describe the benefits of Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="0e4ed-177">结果</span><span class="sxs-lookup"><span data-stu-id="0e4ed-177">Result</span></span>

<span data-ttu-id="0e4ed-178">您的 Exchange Online IT 试点已完成, 并且已开发、评审和优化初始变更管理材料。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-178">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="0e4ed-179">步骤 3：推广到业务组</span><span class="sxs-lookup"><span data-stu-id="0e4ed-179">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="0e4ed-180">完成 IT 试点后, 将 Exchange Online 部署到组织中的业务组或部门。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-180">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="0e4ed-181">如果您的组织使用的是本地电子邮件服务 (如 Exchange Server), 则此部署由邮箱迁移组成。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-181">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="0e4ed-182">此首展应包括:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-182">This rollout should include:</span></span>

- <span data-ttu-id="0e4ed-183">在业务组中确定 Exchange Online 的关键业务方案。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-183">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="0e4ed-184">通知用户为部门、工作或项目团队的 Exchange Online 使用提供预期和日程表的通知活动。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-184">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="0e4ed-185">将您的业务组成员的本地邮箱迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-185">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="0e4ed-186">在 Exchange Online 上提供用户培训, 或链接到介绍 Exchange Online 和如何使用 Exchange Online 的资源。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-186">Delivering user training on Exchange Online or links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="0e4ed-187">设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-187">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="0e4ed-188">发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-188">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="0e4ed-189">结果</span><span class="sxs-lookup"><span data-stu-id="0e4ed-189">Result</span></span>

<span data-ttu-id="0e4ed-190">业务组已启动并在 Exchange Online 中运行, 并且已对更改管理资料进行了测试和改进。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-190">A business group is up and running with Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="0e4ed-191">阶段 3：推动价值</span><span class="sxs-lookup"><span data-stu-id="0e4ed-191">Phase 3: Drive value</span></span>

<span data-ttu-id="0e4ed-192">在这一阶段, 您将完成 Exchange Online 的推出并支持您的用户帮助他们实现其优势。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-192">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="0e4ed-193">步骤 1: 将 Exchange Online 部署到组织的其余部分</span><span class="sxs-lookup"><span data-stu-id="0e4ed-193">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="0e4ed-194">向组织中的其余人员发布应包括：</span><span class="sxs-lookup"><span data-stu-id="0e4ed-194">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="0e4ed-195">在单独的业务组中标识 Exchange Online 的关键业务方案。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-195">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="0e4ed-196">将精选的更改管理材料用于发布活动, 以向组织提供 Exchange Online 使用的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="0e4ed-197">将组织其余部分的邮箱迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-197">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="0e4ed-198">在 Exchange Online 上提供用户培训, 或提供指向介绍 Exchange Online 和如何使用 Exchange Online 的资源的链接。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-198">Delivering user training on Exchange Online or provide links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="0e4ed-p112">设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="0e4ed-202">结果</span><span class="sxs-lookup"><span data-stu-id="0e4ed-202">Result</span></span>

<span data-ttu-id="0e4ed-203">您的组织已启动并在运行, 并且您的更改管理策略已就绪, 可以通知、培训和允许用户使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="0e4ed-204">步骤 2：衡量使用情况、管理满意度和推动采用</span><span class="sxs-lookup"><span data-stu-id="0e4ed-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="0e4ed-205">向整个组织推出 Exchange Online 后, 必须继续使用您的更改管理策略执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-205">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="0e4ed-206">让你的领导层将 Exchange Online 提升为用于个人和短期通信和日程安排的主要工具。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-206">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="0e4ed-207">鼓励个人将其用于业务组、部门、工作和项目团队通信、日历和协作。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-207">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="0e4ed-208">建议的活动如下：</span><span class="sxs-lookup"><span data-stu-id="0e4ed-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="0e4ed-209">参阅 [Office 365 采用指南](https://aka.ms/successfactors)，了解与云服务采用有关的常规最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="0e4ed-p113">请参阅 [Office 365 活动报告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，了解整个组织的 Office 365 服务使用情况。如果不是组织的 Office 365 全局管理员，请让全局管理员向你的用户帐户授予“报告读取者”权限，以便你能够访问活动报告。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="0e4ed-212">监视反馈场所 (中心团队团队或 Yammer 中的公共渠道), 了解个人是否遇到 Exchange Online 的问题和反馈。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-212">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="0e4ed-213">尽快解决问题和问题, 以防止他人感到失望并演示对部署的支持。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-213">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="0e4ed-214">在每个业务组中确定并培养拥护者, 并使用 Exchange Online 突出显示其成果和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-214">Identify and nurture champions in each business group and highlight their accomplishments and best practices using Exchange Online.</span></span> <span data-ttu-id="0e4ed-215">反映它们对组织的成功, 以显示项目成功和采用情况。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-215">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="0e4ed-216">由业务组内的技术领导者签署可对领导者和同行施加强大的影响。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-216">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="0e4ed-217">结果</span><span class="sxs-lookup"><span data-stu-id="0e4ed-217">Result</span></span>

<span data-ttu-id="0e4ed-218">您的组织已采用 Exchange Online 作为其主要个人和小型组短期限的通信和计划工具。</span><span class="sxs-lookup"><span data-stu-id="0e4ed-218">Your organization has adopted Exchange Online as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="0e4ed-219">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="0e4ed-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0e4ed-220">若要查看并了解公司如何迁移到 Exchange Online 并了解如何使用 Exchange Online Protection 来防范网络攻击, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-220">To peek inside Microsoft and learn how the company migrated to Exchange Online and is using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="0e4ed-221">Microsoft 将 150,000 个邮箱迁移到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e4ed-221">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="0e4ed-222">Microsoft 使用威胁智能来保护、检测和响应威胁</span><span class="sxs-lookup"><span data-stu-id="0e4ed-222">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="0e4ed-223">Microsoft 使用 Office 365 阻止网络钓鱼的尝试</span><span class="sxs-lookup"><span data-stu-id="0e4ed-223">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="0e4ed-224">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0e4ed-224">Next steps</span></span>

<span data-ttu-id="0e4ed-225">有关日常维护 Exchange Online, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="0e4ed-225">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- <span data-ttu-id="0e4ed-226">[Exchange Online 中的 Exchange 管理中心](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-226">[Exchange admin center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="0e4ed-227">[Exchange Online 中的监视、报告和邮件跟踪](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-227">[Monitoring, reporting, and message tracing in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="0e4ed-228">[在 Exchange Online 中备份电子邮件](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4ed-228">[Backing up email in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span></span> 
