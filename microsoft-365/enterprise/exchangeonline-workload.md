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
ms.openlocfilehash: 30ba71fbf2af684afbbffe0a2e2b1720a8eeec2c
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453858"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="c2833-103">部署适用于 Microsoft 365 企业版的 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c2833-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c2833-104">*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="c2833-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c2833-105">Exchange Online 是针对电子邮件和日历的主要云服务，可帮助你的用户以不需要实时聊天或集中存储文档的方式进行协作。</span><span class="sxs-lookup"><span data-stu-id="c2833-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="c2833-106">Exchange Online 是 Microsoft 365 企业的团队合作价值的关键元素。</span><span class="sxs-lookup"><span data-stu-id="c2833-106">Exchange Online is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="c2833-107">借助 Exchange Online，无论您在使用什么设备，都可以使用已知的 Outlook 应用程序更有效地完成更多和工作。</span><span class="sxs-lookup"><span data-stu-id="c2833-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="c2833-108">Exchange Online 还拥有可保护邮箱的高级安全功能（包括反恶意软件和反垃圾邮件筛选），以及可防止用户错误地向未授权人员发送敏感信息的数据丢失预防功能。</span><span class="sxs-lookup"><span data-stu-id="c2833-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="c2833-109">Exchange Online security 是 Microsoft 365 企业版的智能安全价值的关键要素。</span><span class="sxs-lookup"><span data-stu-id="c2833-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="c2833-110">如果你是第一次使用 Exchange online，请参阅 [Microsoft Exchange online](https://products.office.com/exchange/exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="c2833-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="c2833-111">下面的阶段和步骤将指导您完成在组织中对 Exchange Online 角色进行构想的过程，通过一系列渐进式部署将组织加入 Exchange Online，并推动 Exchange Online 和它的使用对最终用户的价值。</span><span class="sxs-lookup"><span data-stu-id="c2833-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="c2833-112">仅在完成了第2阶段后，才应遵循以下部署说明[： Microsoft 365 企业版基础结构的标识](identity-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="c2833-112">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity of the Microsoft 365 Enterprise foundation infrastructure](identity-infrastructure.md).</span></span>
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a><span data-ttu-id="c2833-113">第1阶段：构想 Exchange Online 部署</span><span class="sxs-lookup"><span data-stu-id="c2833-113">Phase 1: Envision your Exchange Online deployment</span></span>

<span data-ttu-id="c2833-114">在此阶段中，您将为您的 Exchange Online 部署收集人员，并确定组织如何使用 Exchange Online 来满足其业务需求。</span><span class="sxs-lookup"><span data-stu-id="c2833-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="c2833-115">步骤1：收集 Exchange Online 部署成员</span><span class="sxs-lookup"><span data-stu-id="c2833-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="c2833-116">若要在 Microsoft 365 企业版基础结构的[第2阶段（第2阶段](identity-infrastructure.md)）上成功部署 Exchange Online，您需要收集合适的人员进行输入和反馈。</span><span class="sxs-lookup"><span data-stu-id="c2833-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to gather the right people for input and feedback.</span></span> <span data-ttu-id="c2833-117">关键人员包括业务决策者、IT 人员（如架构师和实施者），并支持最终用户。</span><span class="sxs-lookup"><span data-stu-id="c2833-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="c2833-118">这三个组可确保您的 Exchange Online 部署包括满足业务需求的注意事项、邮箱迁移和安全性的技术方面以及结果是典型用户将使用的内容。</span><span class="sxs-lookup"><span data-stu-id="c2833-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result is something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="c2833-119">结果</span><span class="sxs-lookup"><span data-stu-id="c2833-119">Result</span></span>

<span data-ttu-id="c2833-120">代表组织业务、技术和最终用户方面的人员列表。</span><span class="sxs-lookup"><span data-stu-id="c2833-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="c2833-121">步骤2：确定 Exchange Online 业务方案并确定其优先级</span><span class="sxs-lookup"><span data-stu-id="c2833-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="c2833-122">Exchange Online 可用于不同的用途。</span><span class="sxs-lookup"><span data-stu-id="c2833-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="c2833-123">您需要根据您的组织、业务组、部门或个人工作和项目团队的不同级别的业务需求来确定哪种用途对应。</span><span class="sxs-lookup"><span data-stu-id="c2833-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="c2833-124">应将 Exchange Online 设定为满足个人和小型组短期的通信和日程安排需求。</span><span class="sxs-lookup"><span data-stu-id="c2833-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="c2833-125">了解 Exchange Online 优势的一种方法是，先检查个人、团队或团队的交互方式，然后查找提供更简单的方式来交流、安排会议和进行协作的适当方案。</span><span class="sxs-lookup"><span data-stu-id="c2833-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="c2833-126">请记住，对于某些协作方案， [Microsoft 团队](teams-workload.md)可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="c2833-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

#### <a name="result"></a><span data-ttu-id="c2833-127">结果</span><span class="sxs-lookup"><span data-stu-id="c2833-127">Result</span></span>
<span data-ttu-id="c2833-128">满足组织的通信、日程安排和短期协作需求的 Exchange Online 方案的列表。</span><span class="sxs-lookup"><span data-stu-id="c2833-128">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="c2833-129">阶段 2：载入</span><span class="sxs-lookup"><span data-stu-id="c2833-129">Phase 2: Onboard</span></span>

<span data-ttu-id="c2833-130">在此阶段中，您将规划 Exchange Online 部署的技术方面，并开始将其推出给选定的用户组。</span><span class="sxs-lookup"><span data-stu-id="c2833-130">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="c2833-131">先决条件：标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="c2833-131">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="c2833-132">若要保护对 Exchange Online 邮箱的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 Exchange online 访问策略](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c2833-132">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="c2833-133">第 1 步：完成技术计划</span><span class="sxs-lookup"><span data-stu-id="c2833-133">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="c2833-134">开始技术规划前，请确定是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="c2833-134">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="c2833-135">如果您的组织有超过50的座位并且参与了[符合条件的计划](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，则可以使用[FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365)，*无需额外成本*即可指导您完成规划、部署和服务采用。</span><span class="sxs-lookup"><span data-stu-id="c2833-135">If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *available at no additional cost* to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="c2833-136">你也可以使用我们的 FastTrack 载入向导自行完成此工作，使用 Office 365 帐户登录后即可从 [FastTrack](https://fasttrack.microsoft.com/) 获取此向导。</span><span class="sxs-lookup"><span data-stu-id="c2833-136">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="c2833-137">如果您正在进行自己的规划，或与 FastTrack 结合使用，则需要确定您的网络和组织是否已准备好进行 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c2833-137">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="c2833-138">对于连接到组织网络的用户，在基础结构中满足[网络](networking-infrastructure.md)的退出条件尤其重要。</span><span class="sxs-lookup"><span data-stu-id="c2833-138">It is especially important that you meet the exit criteria for [networking](networking-infrastructure.md) in your foundation infrastructure for users connected to your organization network.</span></span> <span data-ttu-id="c2833-139">特别注意 Internet 带宽、吞吐量和流量延迟，以最大程度地提高基于 Exchange Online 的电子邮件和附件的额外流量的性能。</span><span class="sxs-lookup"><span data-stu-id="c2833-139">Pay special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="c2833-140">使用这些资源为 Exchange Online 部署的技术方面做准备：</span><span class="sxs-lookup"><span data-stu-id="c2833-140">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="c2833-141">将多个电子邮件帐户迁移到 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="c2833-141">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [<span data-ttu-id="c2833-142">将 Exchange Server 公用文件夹迁移到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c2833-142">Migrate Exchange Server public folders to Exchange Online</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [<span data-ttu-id="c2833-143">将 Exchange Server 公用文件夹迁移到 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="c2833-143">Migrate Exchange Server public folders to Office 365 Groups</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [<span data-ttu-id="c2833-144">Exchange Online 中的协作</span><span class="sxs-lookup"><span data-stu-id="c2833-144">Collaboration in Exchange Online</span></span>](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [<span data-ttu-id="c2833-145">Exchange Online 中的收件人</span><span class="sxs-lookup"><span data-stu-id="c2833-145">Recipients in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [<span data-ttu-id="c2833-146">iOS 和 Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="c2833-146">Outlook for iOS and Android</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

<span data-ttu-id="c2833-147">若要更好地了解 Exchange Online 中的安全性，请查看以下资源：</span><span class="sxs-lookup"><span data-stu-id="c2833-147">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- [<span data-ttu-id="c2833-148">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="c2833-148">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [<span data-ttu-id="c2833-149">Exchange Online 的安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="c2833-149">Security and compliance for Exchange Online</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [<span data-ttu-id="c2833-150">反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="c2833-150">Anti-spam and anti-malware protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

<span data-ttu-id="c2833-151">接下来，请使用以下资源来了解 Exchange Online 邮箱管理：</span><span class="sxs-lookup"><span data-stu-id="c2833-151">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- [<span data-ttu-id="c2833-152">在 Exchange Online 中创建用户邮箱</span><span class="sxs-lookup"><span data-stu-id="c2833-152">Create user mailboxes in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [<span data-ttu-id="c2833-153">管理用户邮箱</span><span class="sxs-lookup"><span data-stu-id="c2833-153">Manage user mailboxes</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [<span data-ttu-id="c2833-154">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="c2833-154">Create and manage distribution groups</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a><span data-ttu-id="c2833-155">结果</span><span class="sxs-lookup"><span data-stu-id="c2833-155">Result</span></span>

<span data-ttu-id="c2833-156">您了解邮箱迁移、安全性和管理，并准备好开始向组织中选定的组推出 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c2833-156">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="c2833-157">第 2 步：运行 IT 试点</span><span class="sxs-lookup"><span data-stu-id="c2833-157">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="c2833-158">对于大多数中型和大型组织，应与您的利益干系人在第1阶段、早期采用者和技术爱好者之间运行 IT 试点。</span><span class="sxs-lookup"><span data-stu-id="c2833-158">For most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="c2833-159">在 IT 试点期间：</span><span class="sxs-lookup"><span data-stu-id="c2833-159">During the IT pilot:</span></span>

- <span data-ttu-id="c2833-160">向你的试点参与者 Microsoft 365 许可证，并将其本地邮箱迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c2833-160">Give your pilot participants Microsoft 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="c2833-161">为你的试点参与者提供一组练习来测试 Exchange Online 电子邮件、计划和其他功能。</span><span class="sxs-lookup"><span data-stu-id="c2833-161">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="c2833-162">确定您的更改管理策略并生成可促进组织范围内用户采用 Outlook 和 Exchange Online 的材料。</span><span class="sxs-lookup"><span data-stu-id="c2833-162">Determine your change management strategy and produce materials to drive organization-wide user adoption of Outlook and Exchange Online.</span></span> 
 
  <span data-ttu-id="c2833-163">变更管理资料可以包括电子邮件公告文本、内部培训计划、走廊海报和演示文稿。</span><span class="sxs-lookup"><span data-stu-id="c2833-163">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="c2833-164">这些材料将告知组织有关 Exchange Online 及其优势的信息，以提高意识和促进使用的目标。</span><span class="sxs-lookup"><span data-stu-id="c2833-164">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="c2833-165">有关某些想法，请参阅[Microsoft 团队文章的更改管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)。</span><span class="sxs-lookup"><span data-stu-id="c2833-165">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>

- <span data-ttu-id="c2833-166">让 IT 试点参与者根据自己的体验审阅变更管理材料。</span><span class="sxs-lookup"><span data-stu-id="c2833-166">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="c2833-167">他们可以提供有关最佳做法的提示，并提供有关如何最大限度地说明 Outlook 和 Exchange Online 的优势以及如何使用它进行通信和日程安排的建议。</span><span class="sxs-lookup"><span data-stu-id="c2833-167">They can provide tips on best practices and advice on how to best describe the benefits of Outlook and Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="c2833-168">结果</span><span class="sxs-lookup"><span data-stu-id="c2833-168">Result</span></span>

<span data-ttu-id="c2833-169">您的 Exchange Online IT 试点已完成，并且已开发、评审和优化初始变更管理材料。</span><span class="sxs-lookup"><span data-stu-id="c2833-169">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="c2833-170">第 3 步：向业务组发布</span><span class="sxs-lookup"><span data-stu-id="c2833-170">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="c2833-171">完成 IT 试点后，将 Exchange Online 部署到组织中的业务组或部门。</span><span class="sxs-lookup"><span data-stu-id="c2833-171">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="c2833-172">如果您的组织使用的是本地电子邮件服务（如 Exchange Server），则此部署由邮箱迁移组成。</span><span class="sxs-lookup"><span data-stu-id="c2833-172">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="c2833-173">此发布应包括：</span><span class="sxs-lookup"><span data-stu-id="c2833-173">This rollout should include:</span></span>

- <span data-ttu-id="c2833-174">在业务组中确定 Exchange Online 的关键业务方案。</span><span class="sxs-lookup"><span data-stu-id="c2833-174">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="c2833-175">通知用户为部门、工作或项目团队的 Exchange Online 使用提供预期和日程表的通知活动。</span><span class="sxs-lookup"><span data-stu-id="c2833-175">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="c2833-176">将您的业务组成员的本地邮箱迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c2833-176">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="c2833-177">在 Outlook 中提供[用户培训](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)或链接到介绍 outlook 和如何使用它的资源。</span><span class="sxs-lookup"><span data-stu-id="c2833-177">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="c2833-178">设立反馈机制（如包含业务组中所有成员的中心 Microsoft Teams 团队），以收集业务组中用户的评论，并采取措施来解决他们报告的问题。</span><span class="sxs-lookup"><span data-stu-id="c2833-178">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="c2833-179">发布期间，可以优化变更管理材料，为在整个组织范围内发布做好准备。</span><span class="sxs-lookup"><span data-stu-id="c2833-179">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="c2833-180">结果</span><span class="sxs-lookup"><span data-stu-id="c2833-180">Result</span></span>

<span data-ttu-id="c2833-181">业务组已启动并在 Outlook 和 Exchange Online 中运行，并且已对更改管理资料进行了测试和改进。</span><span class="sxs-lookup"><span data-stu-id="c2833-181">A business group is up and running with Outlook and Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="c2833-182">阶段 3：提升价值</span><span class="sxs-lookup"><span data-stu-id="c2833-182">Phase 3: Drive value</span></span>

<span data-ttu-id="c2833-183">在这一阶段，您将完成 Exchange Online 的推出并支持您的用户帮助他们实现其优势。</span><span class="sxs-lookup"><span data-stu-id="c2833-183">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="c2833-184">步骤1：将 Exchange Online 部署到组织的其余部分</span><span class="sxs-lookup"><span data-stu-id="c2833-184">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="c2833-185">向组织中的其余人员发布应包括：</span><span class="sxs-lookup"><span data-stu-id="c2833-185">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="c2833-186">在单独的业务组中标识 Exchange Online 的关键业务方案。</span><span class="sxs-lookup"><span data-stu-id="c2833-186">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="c2833-187">将精选的更改管理材料用于发布活动，以向组织提供 Exchange Online 使用的预期和日程表。</span><span class="sxs-lookup"><span data-stu-id="c2833-187">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="c2833-188">将组织其余部分的邮箱迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c2833-188">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="c2833-189">在 Outlook 中提供[用户培训](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)，或提供指向介绍 outlook 和如何使用它的资源的链接。</span><span class="sxs-lookup"><span data-stu-id="c2833-189">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or provide links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="c2833-p112">设立反馈机制（如包含所有用户的中心团队），以收集组织用户反馈的评论和问题。如果组织中的人数少于 2500 人，请使用 Teams 中的公用频道；否则，请使用 Yammer 中的公用组。</span><span class="sxs-lookup"><span data-stu-id="c2833-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="c2833-193">结果</span><span class="sxs-lookup"><span data-stu-id="c2833-193">Result</span></span>

<span data-ttu-id="c2833-194">您的组织已启动并在运行，并且您的更改管理策略已就绪，可以通知、培训和允许用户使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c2833-194">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="c2833-195">第 2 步：衡量使用情况、管理满意度和提高采用率</span><span class="sxs-lookup"><span data-stu-id="c2833-195">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="c2833-196">向整个组织推出 Exchange Online 后，必须继续使用您的更改管理策略执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c2833-196">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="c2833-197">让你的领导层将 Exchange Online 提升为用于个人和短期通信和日程安排的主要工具。</span><span class="sxs-lookup"><span data-stu-id="c2833-197">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="c2833-198">鼓励个人将其用于业务组、部门、工作和项目团队通信、日历和协作。</span><span class="sxs-lookup"><span data-stu-id="c2833-198">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="c2833-199">建议的活动如下：</span><span class="sxs-lookup"><span data-stu-id="c2833-199">Here are some suggested activities:</span></span>

- <span data-ttu-id="c2833-200">请参阅 [Office 365 的成功因素](https://aka.ms/successfactors)，了解与云服务采用有关的常规最佳做法。</span><span class="sxs-lookup"><span data-stu-id="c2833-200">See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="c2833-p113">请参阅 [Office 365 活动报告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，了解整个组织的 Office 365 服务使用情况。如果不是组织的 Office 365 全局管理员，请让全局管理员向你的用户帐户授予“报告读取者”权限，以便你能够访问活动报告。</span><span class="sxs-lookup"><span data-stu-id="c2833-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="c2833-203">监视反馈场所（中心团队团队或 Yammer 中的公共渠道），了解个人是否遇到 Exchange Online 的问题和反馈。</span><span class="sxs-lookup"><span data-stu-id="c2833-203">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="c2833-204">尽快解决他们的疑问和问题，以避免个人受挫，并证明我们是支持发布的。</span><span class="sxs-lookup"><span data-stu-id="c2833-204">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="c2833-205">在每个业务组中找出并培养冠军，并使用 Outlook 突出显示其最佳实践。</span><span class="sxs-lookup"><span data-stu-id="c2833-205">Identify and nurture champions in each business group and highlight their best practices using Outlook.</span></span> <span data-ttu-id="c2833-206">将他们的成功事迹反映给组织，以展示项目的成功和采用。</span><span class="sxs-lookup"><span data-stu-id="c2833-206">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="c2833-207">由业务组内的技术领导者签署可对领导者和同行施加强大的影响。</span><span class="sxs-lookup"><span data-stu-id="c2833-207">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="c2833-208">结果</span><span class="sxs-lookup"><span data-stu-id="c2833-208">Result</span></span>

<span data-ttu-id="c2833-209">您的组织已采用 Exchange Online 和 Outlook 作为其主要个人和小型组短寿命的通信和计划工具。</span><span class="sxs-lookup"><span data-stu-id="c2833-209">Your organization has adopted Exchange Online and Outlook as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c2833-210">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="c2833-210">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c2833-211">若要查看并了解如何迁移到 Exchange Online 并了解如何使用 Exchange Online Protection 来防范网络攻击，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c2833-211">To peek inside Microsoft and learn how we migrated to Exchange Online and are using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="c2833-212">Microsoft 将 150,000 个邮箱迁移到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c2833-212">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="c2833-213">Microsoft 使用威胁智能来保护、检测和响应威胁</span><span class="sxs-lookup"><span data-stu-id="c2833-213">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="c2833-214">Microsoft 使用 Office 365 阻止网络钓鱼的尝试</span><span class="sxs-lookup"><span data-stu-id="c2833-214">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="c2833-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c2833-215">Next steps</span></span>

<span data-ttu-id="c2833-216">有关日常维护 Exchange Online，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="c2833-216">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- [<span data-ttu-id="c2833-217">Exchange Online 中的 exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="c2833-217">Exchange admin center in Exchange Online</span></span>](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [<span data-ttu-id="c2833-218">Exchange Online 中的监视、报告和邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="c2833-218">Monitoring, reporting, and message tracing in Exchange Online</span></span>](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [<span data-ttu-id="c2833-219">在 Exchange Online 中备份电子邮件</span><span class="sxs-lookup"><span data-stu-id="c2833-219">Backing up email in Exchange Online</span></span>](https://docs.microsoft.com/exchange/back-up-email) 
