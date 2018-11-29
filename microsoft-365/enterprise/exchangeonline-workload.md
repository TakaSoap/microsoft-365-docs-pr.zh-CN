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
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="1d304-103">部署 Microsoft 365 企业版的 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1d304-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1d304-p101">Exchange Online 是主要的云服务的电子邮件和日历，从而帮助您的用户协作不需要实时聊天或集中文档存储的方式。Exchange Online 是您如何单个和小型组短期通信和日程安排，并且是 Microsoft 365 enterprise 的团队协作值的内置的一个重要方面。Exchange Online 可以完成的详细信息和更有效地使用已知的 Outlook 应用程序，无论您是在何种设备。</span><span class="sxs-lookup"><span data-stu-id="1d304-p101">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage. Exchange Online is how you do individual and small group short-lived communication and scheduling and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise. Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="1d304-p102">Exchange Online 还具有高级安全功能包括反恶意软件和反垃圾邮件筛选保护邮箱和防止用户地将其发送到未经授权的人员的敏感信息的数据丢失防护功能。Exchange Online 的安全性是 Microsoft 365 enterprise 的智能安全值的一个重要方面。</span><span class="sxs-lookup"><span data-stu-id="1d304-p102">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people. Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="1d304-109">如果您是全新到 Exchange Online，请参阅[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="1d304-109">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="1d304-110">以下阶段和步骤指导您完成构想渐进式推出一系列到 Exchange Online 组织的 Exchange online 组织，入职培训中的角色和驱动的 Exchange Online 的使用情况的过程并将其向最终用户的值。</span><span class="sxs-lookup"><span data-stu-id="1d304-110">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="1d304-111">仅 Microsoft 365 enterprise 完成[foundation 基础](deploy-foundation-infrastructure.md)结构后，应遵循以下部署说明。</span><span class="sxs-lookup"><span data-stu-id="1d304-111">These deployment instructions should be followed only after you’ve completed your [foundation infrastructure](deploy-foundation-infrastructure.md) for Microsoft 365 Enterprise.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="1d304-112">阶段 1：构想</span><span class="sxs-lookup"><span data-stu-id="1d304-112">Phase 1: Envision</span></span>

<span data-ttu-id="1d304-113">在此阶段中，可以为 Exchange Online 部署收集人员和确定您的组织将如何使用 Exchange Online 以满足其业务需求。</span><span class="sxs-lookup"><span data-stu-id="1d304-113">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="1d304-114">步骤 1： 收集您的 Exchange Online 部署成员</span><span class="sxs-lookup"><span data-stu-id="1d304-114">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="1d304-p103">对于成功部署的 Exchange Online 在 Microsoft 365 [foundation 基础架构](deploy-foundation-infrastructure.md)，您需要获得输入和反馈的适当的人员。关键人员包括业务决策者、 IT 人员，如架构师和实施，以及为最终用户的拥护者。</span><span class="sxs-lookup"><span data-stu-id="1d304-p103">For a successful deployment of Exchange Online on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="1d304-117">这三个组确保 Exchange Online 部署包括满足业务需求和邮箱迁移和安全性的技术方面，结果将为紧迫的典型用户将使用的注意事项。</span><span class="sxs-lookup"><span data-stu-id="1d304-117">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="1d304-118">结果</span><span class="sxs-lookup"><span data-stu-id="1d304-118">Result</span></span>

<span data-ttu-id="1d304-119">代表组织业务、技术和最终用户方面的人员列表。</span><span class="sxs-lookup"><span data-stu-id="1d304-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="1d304-120">步骤 2： 确定并设置其优先级 Exchange Online 业务方案</span><span class="sxs-lookup"><span data-stu-id="1d304-120">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="1d304-p104">Exchange Online 可用于不同的用途。您需要决定哪些目的将映射到您的组织、 业务部门、 部门或各个工作和项目团队的不同级别上的业务需求。您应面向 Exchange Online 以满足您的个人和小型组短期通信和计划需求。</span><span class="sxs-lookup"><span data-stu-id="1d304-p104">Exchange Online can be used for different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams. You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="1d304-p105">请参阅 Exchange Online 的优点的一种方法是检查如何个人、 团队或 v 团队如今，交互，然后查找提供更轻松的方式进行通信，安排会议和协作的相应方案。请记住[的 Microsoft 团队](teams-workload.md)可能的协作方案的一些更好的选择。</span><span class="sxs-lookup"><span data-stu-id="1d304-p105">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

<span data-ttu-id="1d304-126">Exchange Online 为 Microsoft 365 企业版提供这些战略业务方案：</span><span class="sxs-lookup"><span data-stu-id="1d304-126">Exchange Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="1d304-127">实时或按你自己的时间协作文档以简化共创过程</span><span class="sxs-lookup"><span data-stu-id="1d304-127">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="1d304-128">管理项目、任务和截止时间以达到业务目标</span><span class="sxs-lookup"><span data-stu-id="1d304-128">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="1d304-129">了解工作习惯，以提升影响力</span><span class="sxs-lookup"><span data-stu-id="1d304-129">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="1d304-130">与你的团队进行沟通以了解情况，征求意见，建立凝聚力和共识</span><span class="sxs-lookup"><span data-stu-id="1d304-130">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="1d304-131">存储和共享组织内部和外部的文件，以跨组织边界无缝工作</span><span class="sxs-lookup"><span data-stu-id="1d304-131">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="1d304-132">随时随地跨设备安全工作，在保持灵活工作方式的同时完成更多任务</span><span class="sxs-lookup"><span data-stu-id="1d304-132">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="1d304-133">保护信息并降低数据丢失风险</span><span class="sxs-lookup"><span data-stu-id="1d304-133">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="1d304-134">检测和防范外部威胁</span><span class="sxs-lookup"><span data-stu-id="1d304-134">Detect and protect against external threats</span></span> 
- <span data-ttu-id="1d304-135">监视、 报告和分析活动迅速做出反应以提供组织的安全</span><span class="sxs-lookup"><span data-stu-id="1d304-135">Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="1d304-136">帮助组织增强隐私和合规性以符合一般数据保护条例 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="1d304-136">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="1d304-137">有关详细信息，请参阅[使用 Microsoft 365 实现数字化转型](http://transform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1d304-137">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="result"></a><span data-ttu-id="1d304-138">结果</span><span class="sxs-lookup"><span data-stu-id="1d304-138">Result</span></span>
<span data-ttu-id="1d304-139">通信、 日程安排和短期协作满足您组织的 Exchange Online 方案的列表。</span><span class="sxs-lookup"><span data-stu-id="1d304-139">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="1d304-140">阶段 2：上手使用</span><span class="sxs-lookup"><span data-stu-id="1d304-140">Phase 2: Onboard</span></span>

<span data-ttu-id="1d304-141">此阶段中，在您规划 Exchange Online 部署的技术方面，并开始实施所选用户组。</span><span class="sxs-lookup"><span data-stu-id="1d304-141">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="1d304-142">先决条件： 标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="1d304-142">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="1d304-143">若要保护 Exchange Online 邮箱的访问，请确保您已配置了[标识和设备访问策略](identity-access-policies.md)和[推荐 Exchange Online 的访问策略](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1d304-143">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="1d304-144">第 1 步：完成技术计划</span><span class="sxs-lookup"><span data-stu-id="1d304-144">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="1d304-p106">技术规划之前，确定您是否要使用 FastTrack。如果您的组织已超过 50 座位和参与[合格的计划](https://technet.microsoft.com/library/dn783224.aspx)，则可以使用[Microsoft 365 FastTrack](https://fasttrack.microsoft.com/microsoft365)，可在任何其他的成本，用于指导您规划、 部署和服务应用。或者，可以使用 FastTrack 入职培训向导，它们是可从[FastTrack](https://fasttrack.microsoft.com/)一旦登录 Office 365 帐户完成此项工作。</span><span class="sxs-lookup"><span data-stu-id="1d304-p106">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="1d304-p107">如果您正在执行自己的规划，或与 FastTrack 结合使用，您需要确定您的网络和组织可供 Exchange Online。尤其重要您中具有 Internet 带宽、 吞吐量和通信延迟最大限度地 exchange 性能额外的流量特别注意您 foundation 基础结构满足网络的退出条件联机基于电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="1d304-p107">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="1d304-150">使用这些资源准备 Exchange Online 推出的技术方面：</span><span class="sxs-lookup"><span data-stu-id="1d304-150">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="1d304-151">将多个电子邮件帐户迁移到 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="1d304-151">Ways to migrate multiple email accounts to Office 365</span></span>](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
- <span data-ttu-id="1d304-152">[Office 365 邮件迁移顾问](https://portal.office.com/onboarding/mailsetupadvisor#/)（必须登录到您的 Office 365 订阅）</span><span class="sxs-lookup"><span data-stu-id="1d304-152">[Office 365 mail migration advisor](https://portal.office.com/onboarding/mailsetupadvisor#/) (must be signed in to your Office 365 subscription)</span></span>
- <span data-ttu-id="1d304-153">[Exchange Online 中的协作](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-153">[Collaboration in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="1d304-154">[Exchange Online 中的收件人](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-154">[Recipients in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span></span>

<span data-ttu-id="1d304-155">有关更好地了解 Exchange Online 中的安全，查看以下资源：</span><span class="sxs-lookup"><span data-stu-id="1d304-155">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- <span data-ttu-id="1d304-156">[Exchange Online 中的权限](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-156">[Permissions in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="1d304-157">[Exchange Online 的安全性和合规性](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-157">[Security and compliance for Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="1d304-158">[反垃圾邮件和反恶意软件保护](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-158">[Anti-spam and anti-malware protection](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span></span>

<span data-ttu-id="1d304-159">接下来，使用这些资源了解管理 Exchange Online 邮箱：</span><span class="sxs-lookup"><span data-stu-id="1d304-159">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- <span data-ttu-id="1d304-160">[Exchange Online 中创建用户邮箱](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-160">[Create user mailboxes in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="1d304-161">[管理用户邮箱](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-161">[Manage user mailboxes](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span></span> 
- [<span data-ttu-id="1d304-162">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="1d304-162">Create and manage distribution groups</span></span>](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a><span data-ttu-id="1d304-163">结果</span><span class="sxs-lookup"><span data-stu-id="1d304-163">Result</span></span>

<span data-ttu-id="1d304-164">您了解邮箱迁移、 安全性和管理，并已准备好开始推出 Exchange Online 到您的组织中的所选组。</span><span class="sxs-lookup"><span data-stu-id="1d304-164">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="1d304-165">步骤 2：运行 IT 试点</span><span class="sxs-lookup"><span data-stu-id="1d304-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="1d304-p108">在大多数大中型组织中，应通过阶段 1 中的利益干系人以及早期采用者和技术爱好者运行一个 IT 试点。在 IT 试点期间：</span><span class="sxs-lookup"><span data-stu-id="1d304-p108">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="1d304-168">选择 Exchange Online 的业务方案，可以在其中实践 IT 试点参与者。</span><span class="sxs-lookup"><span data-stu-id="1d304-168">Choose an Exchange Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="1d304-169">为试点参与者提供 Office 365 许可证并将其内部部署邮箱迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1d304-169">Give your pilot participants Office 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="1d304-170">为试点参与者提供一练习测试 Exchange Online 电子邮件、 日程安排以及其他功能。</span><span class="sxs-lookup"><span data-stu-id="1d304-170">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="1d304-p109">确定您更改的管理策略，并生成到 Exchange online 的驱动器组织范围内用户应用资料。更改管理资料可以包括电子邮件通知文本、 内部培训计划、 走廊海报和演示文稿。有关 Exchange Online 和其优点与引发认知和驱动的使用情况的目标，这些资料将通知您的组织。请参阅的一些方法[更改 Microsoft 团队的管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)文章。</span><span class="sxs-lookup"><span data-stu-id="1d304-p109">Determine your change management strategy and produce materials to drive organization-wide user adoption of Exchange Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage. See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="1d304-p110">具有 IT 试点参与者查看基于其体验的更改管理材料。它们可以提供有关如何以最佳介绍 Exchange Online 的优点以及如何使用通信和日程安排的最佳做法的提示和建议。</span><span class="sxs-lookup"><span data-stu-id="1d304-p110">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="1d304-177">结果</span><span class="sxs-lookup"><span data-stu-id="1d304-177">Result</span></span>

<span data-ttu-id="1d304-178">Exchange Online IT 试点已完成，初始更改管理资料已开发，查看，并精简。</span><span class="sxs-lookup"><span data-stu-id="1d304-178">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="1d304-179">步骤 3：推广到业务组</span><span class="sxs-lookup"><span data-stu-id="1d304-179">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="1d304-p111">完成您的 IT 试生产之后, 推出 Exchange Online 到业务组或组织中的部门。如果您的组织使用如 Exchange 服务器的内部部署电子邮件服务，此推出包含邮箱迁移。此推出应包括：</span><span class="sxs-lookup"><span data-stu-id="1d304-p111">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization. If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration. This rollout should include:</span></span>

- <span data-ttu-id="1d304-183">标识关键业务方案的 Exchange Online 中的业务组。</span><span class="sxs-lookup"><span data-stu-id="1d304-183">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="1d304-184">要向用户告知期望和 Exchange Online 使用部门和工作或项目工作组的日程表的通知活动。</span><span class="sxs-lookup"><span data-stu-id="1d304-184">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="1d304-185">到 Exchange Online 您业务组成员的内部部署邮箱的迁移。</span><span class="sxs-lookup"><span data-stu-id="1d304-185">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="1d304-186">在 Exchange Online 或资源的链接介绍 Exchange Online 和如何使用它提供用户培训。</span><span class="sxs-lookup"><span data-stu-id="1d304-186">Delivering user training on Exchange Online or links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="1d304-187">设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。</span><span class="sxs-lookup"><span data-stu-id="1d304-187">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="1d304-188">发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。</span><span class="sxs-lookup"><span data-stu-id="1d304-188">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="1d304-189">结果</span><span class="sxs-lookup"><span data-stu-id="1d304-189">Result</span></span>

<span data-ttu-id="1d304-190">业务组已启动并运行与 Exchange Online 和更改管理资料已测试和精简。</span><span class="sxs-lookup"><span data-stu-id="1d304-190">A business group is up and running with Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="1d304-191">阶段 3：推动价值</span><span class="sxs-lookup"><span data-stu-id="1d304-191">Phase 3: Drive value</span></span>

<span data-ttu-id="1d304-192">在此阶段中，可以完成的 Exchange Online 推出和支持您的用户，以帮助他们实现其好处。</span><span class="sxs-lookup"><span data-stu-id="1d304-192">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="1d304-193">步骤 1： 推出 Exchange Online 到您的组织的其余部分</span><span class="sxs-lookup"><span data-stu-id="1d304-193">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="1d304-194">向组织中的其余人员发布应包括：</span><span class="sxs-lookup"><span data-stu-id="1d304-194">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="1d304-195">标识关键业务方案的 Exchange Online 的单独的业务组中。</span><span class="sxs-lookup"><span data-stu-id="1d304-195">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="1d304-196">使用您优化的更改管理资料的通知，告知您的组织的期望的活动和日程表 Exchange Online 的用法。</span><span class="sxs-lookup"><span data-stu-id="1d304-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="1d304-197">到 Exchange Online 组织的其余部分的邮箱的迁移。</span><span class="sxs-lookup"><span data-stu-id="1d304-197">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="1d304-198">提供用户培训在 Exchange Online 或提供介绍 Exchange Online 和如何使用它的资源的链接。</span><span class="sxs-lookup"><span data-stu-id="1d304-198">Delivering user training on Exchange Online or provide links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="1d304-p112">设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。</span><span class="sxs-lookup"><span data-stu-id="1d304-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="1d304-202">结果</span><span class="sxs-lookup"><span data-stu-id="1d304-202">Result</span></span>

<span data-ttu-id="1d304-203">您的组织已启动并开始运行，且您更改的管理策略是为了告知、 培训，并使用户能够使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1d304-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="1d304-204">步骤 2：衡量使用情况、管理满意度和推动采用</span><span class="sxs-lookup"><span data-stu-id="1d304-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="1d304-205">Exchange Online 向推出您的整个组织之后, 必须继续采用对您更改管理策略：</span><span class="sxs-lookup"><span data-stu-id="1d304-205">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="1d304-206">已将 Exchange Online 提升为单个和短期通信的主要工具您领导和计划。</span><span class="sxs-lookup"><span data-stu-id="1d304-206">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="1d304-207">鼓励个人用于业务组，部门、 工作，并且项目团队 communications、 日历和协作。</span><span class="sxs-lookup"><span data-stu-id="1d304-207">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="1d304-208">建议的活动如下：</span><span class="sxs-lookup"><span data-stu-id="1d304-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="1d304-209">参阅 [Office 365 采用指南](https://aka.ms/successfactors)，了解与云服务采用有关的常规最佳做法。</span><span class="sxs-lookup"><span data-stu-id="1d304-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="1d304-p113">请参阅 [Office 365 活动报告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，了解整个组织的 Office 365 服务使用情况。如果不是组织的 Office 365 全局管理员，请让全局管理员向你的用户帐户授予“报告读取者”权限，以便你能够访问活动报告。</span><span class="sxs-lookup"><span data-stu-id="1d304-p113">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="1d304-p114">监视您的反馈地点 （管理中心的团队团队或 Yammer 中的公共通道） 问题和有关其与 Exchange Online 体验的个人的反馈。快速可以可以防止失望的个人和演示推出支持解决问题和问题。</span><span class="sxs-lookup"><span data-stu-id="1d304-p114">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="1d304-p115">确定并培养拥护者每个业务组中的突出显示其成绩和使用 Exchange Online 的最佳实践。反映出到组织，以显示项目成功和采用其成功。认可业务组内的技术负责人可以施加通过负责人和对等方强大的影响。</span><span class="sxs-lookup"><span data-stu-id="1d304-p115">Identify and nurture champions in each business group and highlight their accomplishments and best practices using Exchange Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="1d304-217">结果</span><span class="sxs-lookup"><span data-stu-id="1d304-217">Result</span></span>

<span data-ttu-id="1d304-218">Exchange Online 组织采用作为其主要单个和小型组短期通信和计划工具。</span><span class="sxs-lookup"><span data-stu-id="1d304-218">Your organization has adopted Exchange Online as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="1d304-219">Microsoft 如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="1d304-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1d304-220">若要查看 Microsoft 内部并了解公司如何迁移到 Exchange Online 和使用 Exchange Online Protection 防御网络攻击，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1d304-220">To peek inside Microsoft and learn how the company migrated to Exchange Online and is using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="1d304-221">Microsoft 将 150,000 个邮箱迁移到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1d304-221">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="1d304-222">Microsoft 使用威胁智能来保护、检测和响应威胁</span><span class="sxs-lookup"><span data-stu-id="1d304-222">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="1d304-223">Microsoft 使用 Office 365 阻止网络钓鱼的尝试</span><span class="sxs-lookup"><span data-stu-id="1d304-223">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="1d304-224">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1d304-224">Next steps</span></span>

<span data-ttu-id="1d304-225">请参阅 Exchange online 的正在进行维护这些资源：</span><span class="sxs-lookup"><span data-stu-id="1d304-225">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- <span data-ttu-id="1d304-226">[Exchange Online 中的 Exchange 管理中心](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-226">[Exchange admin center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="1d304-227">[Exchange Online 中的监视、报告和邮件跟踪](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-227">[Monitoring, reporting, and message tracing in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="1d304-228">[在 Exchange Online 中备份电子邮件](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d304-228">[Backing up email in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span></span> 
