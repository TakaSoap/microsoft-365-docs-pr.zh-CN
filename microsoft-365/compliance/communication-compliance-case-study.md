---
title: 案例研究-Contoso 为 Microsoft 团队和 Exchange 通信快速配置冒犯性语言策略
description: Contoso 的个案研究以及如何快速将通信合规性策略配置为在 Microsoft 团队和 Exchange Online 通信中监视攻击性语言
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 4a119e0ec082893d393d1b43af76b41dc93c76a1
ms.sourcegitcommit: 144c0f3c2c6112bffc5a9b04392a38123a979ebc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053069"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-and-exchange-communications"></a><span data-ttu-id="6109a-103">案例研究-Contoso 为 Microsoft 团队和 Exchange 通信快速配置冒犯性语言策略</span><span class="sxs-lookup"><span data-stu-id="6109a-103">Case study - Contoso quickly configures an offensive language policy for Microsoft Teams and Exchange communications</span></span>

<span data-ttu-id="6109a-104">Microsoft 365 中的通信合规性通过帮助您检测、捕获和采取补救措施对组织中不适当的邮件进行补救，来帮助最大限度地减少通信风险。</span><span class="sxs-lookup"><span data-stu-id="6109a-104">Communication compliance in Microsoft 365 helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="6109a-105">通过预定义和自定义策略，可以扫描策略匹配的内部和外部通信，以便指定的审阅者可以对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="6109a-105">Pre-defined and custom policies allow you to scan internal and external communications for policy matches so they can be examined by designated reviewers.</span></span> <span data-ttu-id="6109a-106">审阅者可以调查组织中扫描的电子邮件、Microsoft 团队或第三方通信，并采取适当的补救措施以确保它们符合组织的邮件标准。</span><span class="sxs-lookup"><span data-stu-id="6109a-106">Reviewers can investigate scanned email, Microsoft Teams, or third-party communications in your organization and take appropriate remediation actions to make sure they're compliant with your organization's message standards.</span></span>

<span data-ttu-id="6109a-107">Contoso Corporation 是一个虚构的组织，需要快速配置一个策略来监视冒犯性语言。</span><span class="sxs-lookup"><span data-stu-id="6109a-107">The Contoso Corporation is a fictional organization that needs to quickly configure a policy to monitor for offensive language.</span></span> <span data-ttu-id="6109a-108">他们一直使用 Microsoft 365，主要是为他们的员工提供电子邮件和 Microsoft 团队支持，但在工作场所骚扰方面有新的要求强制实施公司政策。</span><span class="sxs-lookup"><span data-stu-id="6109a-108">They have been using Microsoft 365 primarily for email and Microsoft Teams support for their employees but have new requirements to enforce company policy around workplace harassment.</span></span> <span data-ttu-id="6109a-109">Contoso IT 管理员和合规性专家对使用 Microsoft 365 的基础有一个基本的了解，并且正在寻找有关如何快速开始实现通信合规性的端到端指南。</span><span class="sxs-lookup"><span data-stu-id="6109a-109">Contoso IT administrators and compliance specialists have a basic understanding of the fundamentals of working with Microsoft 365 and are looking for end-to-end guidance for how to quickly get started with communication compliance.</span></span>

<span data-ttu-id="6109a-110">此案例研究将介绍快速配置通信合规性策略以监视攻击性语言通信的基础知识。</span><span class="sxs-lookup"><span data-stu-id="6109a-110">This case study will cover the basics for quickly configuring a communication compliance policy to monitor communications for offensive language.</span></span> <span data-ttu-id="6109a-111">本指南包括：</span><span class="sxs-lookup"><span data-stu-id="6109a-111">This guidance includes:</span></span>

- <span data-ttu-id="6109a-112">第1步-规划通信合规性</span><span class="sxs-lookup"><span data-stu-id="6109a-112">Step 1 - Planning for communication compliance</span></span>
- <span data-ttu-id="6109a-113">第2步-访问 Microsoft 365 中的通信合规性</span><span class="sxs-lookup"><span data-stu-id="6109a-113">Step 2 - Accessing communication compliance in Microsoft 365</span></span>
- <span data-ttu-id="6109a-114">步骤 3-配置系统必备组件和创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="6109a-114">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>
- <span data-ttu-id="6109a-115">第4步-调查和修正警报</span><span class="sxs-lookup"><span data-stu-id="6109a-115">Step 4 - Investigation and remediation of alerts</span></span>

## <a name="step-1---planning-for-communication-compliance"></a><span data-ttu-id="6109a-116">第1步-规划通信合规性</span><span class="sxs-lookup"><span data-stu-id="6109a-116">Step 1 - Planning for communication compliance</span></span>

<span data-ttu-id="6109a-117">Contoso IT 管理员和合规性专家在 Microsoft 365 中参加了有关合规性解决方案的在线网络研讨会，并确定通信合规性策略将帮助他们满足更新的公司策略要求以减少工作区骚扰.</span><span class="sxs-lookup"><span data-stu-id="6109a-117">Contoso IT administrators and compliance specialists attended online webinars about compliance solutions in Microsoft 365 and decided that communication compliance policies will help them meet the updated corporate policy requirements for reducing workplace harassment.</span></span> <span data-ttu-id="6109a-118">它们共同开发了一个计划，用于创建和启用通信合规性策略，该策略将监视在 Exchange Online 中发送的电子邮件的 Microsoft 团队中发送的用于聊天的攻击性语言。</span><span class="sxs-lookup"><span data-stu-id="6109a-118">Working together, they've developed a plan to create and enable a communication compliance policy that will monitor for offensive language for chats sent in Microsoft Teams in email messages sent in Exchange Online.</span></span> <span data-ttu-id="6109a-119">其计划包括标识：</span><span class="sxs-lookup"><span data-stu-id="6109a-119">Their plan includes identifying:</span></span>

- <span data-ttu-id="6109a-120">需要访问通信合规性功能的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="6109a-120">The IT administrators that need access to communication compliance features.</span></span>
- <span data-ttu-id="6109a-121">需要创建和管理通信策略的合规性专家。</span><span class="sxs-lookup"><span data-stu-id="6109a-121">The compliance specialists that need to create and manage communication policies.</span></span>
- <span data-ttu-id="6109a-122">需要调查和修正通信合规性警报的合规性专家和其他部门（人力资源、法律等）中的其他同事。</span><span class="sxs-lookup"><span data-stu-id="6109a-122">The compliance specialists and other colleague in other departments (Human Resources, Legal, etc.) that need to investigate and remediate communication compliance alerts.</span></span>
- <span data-ttu-id="6109a-123">将为通信合规性攻击性语言策略的范围内的用户。</span><span class="sxs-lookup"><span data-stu-id="6109a-123">The users that will be in-scope for the communication compliance offensive language policy.</span></span>

### <a name="licensing"></a><span data-ttu-id="6109a-124">许可</span><span class="sxs-lookup"><span data-stu-id="6109a-124">Licensing</span></span>

<span data-ttu-id="6109a-125">第一步是确认 Contoso 的 Microsoft 365 许可包括对通信合规性解决方案的支持。</span><span class="sxs-lookup"><span data-stu-id="6109a-125">The first step is to confirm that Contoso's Microsoft 365 licensing includes support for the communication compliance solution.</span></span> <span data-ttu-id="6109a-126">若要访问和使用通信合规性，Contoso IT 管理员需要验证 Contoso 是否具有以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="6109a-126">To access and use communication compliance, Contoso IT administrators need to verify that Contoso has one of the following:</span></span>

- <span data-ttu-id="6109a-127">Microsoft 365 E5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="6109a-127">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="6109a-128">具有 "高级合规性" 加载项的 Office 365 企业版 E3 许可证</span><span class="sxs-lookup"><span data-stu-id="6109a-128">Office 365 Enterprise E3 license with the Advanced Compliance add-on</span></span>
- <span data-ttu-id="6109a-129">Office 365 企业版 E5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="6109a-129">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>

<span data-ttu-id="6109a-130">他们还必须确认必须将通信合规性策略中包含的用户分配给上面列出的许可证之一。</span><span class="sxs-lookup"><span data-stu-id="6109a-130">They must also confirm that users included in communication compliance policies must be assigned to one of the licenses listed above.</span></span>

<span data-ttu-id="6109a-131">Contoso IT 管理员需要执行以下步骤来验证 Contoso 的许可支持：</span><span class="sxs-lookup"><span data-stu-id="6109a-131">Contoso IT administrators take the following steps to verify the licensing support for Contoso:</span></span>

1. <span data-ttu-id="6109a-132">IT 管理员登录到**microsoft 365 管理中心** [（https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 管理中心** > **帐单** > **许可证**。</span><span class="sxs-lookup"><span data-stu-id="6109a-132">IT administrators sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Billing** > **Licenses**.</span></span>

2. <span data-ttu-id="6109a-133">在这里，他们确认他们有一个[许可证选项](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin)，其中包括支持通信合规性。</span><span class="sxs-lookup"><span data-stu-id="6109a-133">Here they confirm that they have one of the [license options](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) that includes support for communication compliance.</span></span>

![通信合规性许可](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a><span data-ttu-id="6109a-135">通信合规性的权限</span><span class="sxs-lookup"><span data-stu-id="6109a-135">Permissions for communication compliance</span></span>

<span data-ttu-id="6109a-136">默认情况下，全局管理员不具有对通信合规性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6109a-136">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="6109a-137">[必须配置权限](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance)，以便 Contoso IT 管理员和合规性专家可以访问通信合规性。</span><span class="sxs-lookup"><span data-stu-id="6109a-137">[Permissions must be configured](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance) so that Contoso IT administrators and compliance specialists have access to communication compliance.</span></span>

1. <span data-ttu-id="6109a-138">Contoso IT 管理员登录到**office 365 安全与合规中心**权限页面[（https://protection.office.com/permissions) ](https://protection.office.com/permissions)使用全局管理员帐户的凭据，并选择用于查看和管理 Office 365 中的角色的链接。</span><span class="sxs-lookup"><span data-stu-id="6109a-138">Contoso IT administrators sign into the **Office 365 Security and Compliance center** permissions page [(https://protection.office.com/permissions)](https://protection.office.com/permissions) using credentials for a global administrator account and select the link to view and manage roles in Office 365.</span></span>
2. <span data-ttu-id="6109a-139">选择 "**创建**" 后，将新角色组命名为 "*通信合规性*" 的友好名称，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6109a-139">After selecting **Create**, they give the new role group a friendly name of "*Communication compliance*" and select **Next**.</span></span>
3. <span data-ttu-id="6109a-140">他们选择 "**选择角色**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6109a-140">They select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="6109a-141">他们通过选中*监管审核管理员*、*案例管理*、*合规性管理员*和*审阅*的复选框来添加所需的角色，然后选择 "**添加**"、 **"完成" 和 "** **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6109a-141">They add the required roles by selecting the checkbox for *Supervisory Review Administrator*, *Case Management*, *Compliance Administrator*, and *Review*, then they select **Add**, **Done,** and **Next**.</span></span>

![通信合规性角色](../media/communication-compliance-case-roles.png)

4. <span data-ttu-id="6109a-143">接下来，IT 管理员选择 "**选择成员**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6109a-143">Next, the IT administrators select **Choose members** then select **Add**.</span></span> <span data-ttu-id="6109a-144">选中要为其创建策略并管理策略匹配的邮件的所有用户和组的复选框。</span><span class="sxs-lookup"><span data-stu-id="6109a-144">The select the checkbox for all the users and groups that they want to create policies and manage messages with policy matches.</span></span> <span data-ttu-id="6109a-145">他们将 IT 管理员、合规性专家和其他同事添加到在初始规划中确定的人力资源和法律部门，然后选择 "**添加**"、"**完成**" 和 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6109a-145">They add the IT administrators, compliance specialists, and other colleagues in Human Resources and Legal departments that they identified in the initial planning, then select **Add**, **Done**, and **Next**.</span></span>
5. <span data-ttu-id="6109a-146">若要完成权限，IT 管理员选择 "**创建角色组**" 以完成。</span><span class="sxs-lookup"><span data-stu-id="6109a-146">To finalize the permissions, the IT administrators select **Create role group** to finish.</span></span> <span data-ttu-id="6109a-147">在 Contoso 的 Microsoft 365 服务中，角色将需要大约30分钟的时间才能生效。</span><span class="sxs-lookup"><span data-stu-id="6109a-147">It will take about 30 minutes for the roles to be effective in Contoso's Microsoft 365 service.</span></span>

![通信合规性检查](../media/communication-compliance-case-review.png)

## <a name="step-2---accessing-communication-compliance-in-microsoft-365"></a><span data-ttu-id="6109a-149">第2步-访问 Microsoft 365 中的通信合规性</span><span class="sxs-lookup"><span data-stu-id="6109a-149">Step 2 - Accessing communication compliance in Microsoft 365</span></span>

<span data-ttu-id="6109a-150">为通信合规性配置权限后，在新角色组中定义的 Contoso IT 管理员和合规性专家可以访问 Microsoft 365 中的通信合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="6109a-150">After configuring the permissions for communication compliance, Contoso IT administrators and compliance specialists defined in the new role group can access the communication compliance solution in Microsoft 365.</span></span> <span data-ttu-id="6109a-151">Contoso IT 管理员和合规性专家有几种方法可以访问通信合规性并开始创建新策略：</span><span class="sxs-lookup"><span data-stu-id="6109a-151">Contoso IT administrators and compliance specialists have several ways to access communication compliance and get started creating a new policy:</span></span>

- <span data-ttu-id="6109a-152">直接从通信合规性解决方案开始</span><span class="sxs-lookup"><span data-stu-id="6109a-152">Starting directly from the communication compliance solution</span></span>
- <span data-ttu-id="6109a-153">从 Microsoft 365 合规性中心开始</span><span class="sxs-lookup"><span data-stu-id="6109a-153">Starting from the Microsoft 365 compliance center</span></span>
- <span data-ttu-id="6109a-154">从 Microsoft 365 解决方案目录开始</span><span class="sxs-lookup"><span data-stu-id="6109a-154">Starting from the Microsoft 365 solution catalog</span></span>
- <span data-ttu-id="6109a-155">从 Microsoft 365 管理中心开始</span><span class="sxs-lookup"><span data-stu-id="6109a-155">Starting from the Microsoft 365 admin center</span></span>

### <a name="starting-directly-from-the-communication-compliance-solution"></a><span data-ttu-id="6109a-156">直接从通信合规性解决方案开始</span><span class="sxs-lookup"><span data-stu-id="6109a-156">Starting directly from the communication compliance solution</span></span>

<span data-ttu-id="6109a-157">访问解决方案的最快方法是直接登录到**通信合规性**（<https://compliance.microsoft.com/supervisoryreview>）解决方案。</span><span class="sxs-lookup"><span data-stu-id="6109a-157">The quickest way to access the solution is to sign in directly to the **Communication compliance** (<https://compliance.microsoft.com/supervisoryreview>) solution.</span></span> <span data-ttu-id="6109a-158">使用此链接，Contoso IT 管理员和合规性专家将转到通信合规性概述仪表板，您可以在其中快速查看通知的状态并从预定义的模板创建新策略。</span><span class="sxs-lookup"><span data-stu-id="6109a-158">Using this link, Contoso IT administrators and compliance specialists will be directed to the communication compliance Overview dashboard where you can quickly review the status of alerts and create new policies from the pre-defined templates.</span></span>

![通信合规性概述](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a><span data-ttu-id="6109a-160">从 Microsoft 365 合规性中心开始</span><span class="sxs-lookup"><span data-stu-id="6109a-160">Starting from the Microsoft 365 compliance center</span></span>

<span data-ttu-id="6109a-161">Contoso IT 管理员和合规性专家访问通信合规性解决方案的另一种简单方法是直接登录**Microsoft 365 合规中心** [（https://compliance.microsoft.com)](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6109a-161">Another easy way for Contoso IT administrators and compliance specialists to access the communication compliance solution is to sign in directly to the **Microsoft 365 compliance center** [(https://compliance.microsoft.com)](https://compliance.microsoft.com).</span></span> <span data-ttu-id="6109a-162">登录后，用户只需选择 "**全部显示**" 控制即可显示所有合规性解决方案，然后选择要开始的**通信合规性**解决方案。</span><span class="sxs-lookup"><span data-stu-id="6109a-162">After signing in, users simply need to select the **Show all** control to display all the compliance solutions and then select the **Communication compliance** solution to get started.</span></span>

![合规性中心](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a><span data-ttu-id="6109a-164">从 Microsoft 365 解决方案目录开始</span><span class="sxs-lookup"><span data-stu-id="6109a-164">Starting from the Microsoft 365 solution catalog</span></span>

<span data-ttu-id="6109a-165">Contoso IT 管理员和合规性专家也可以通过选择 Microsoft 365 解决方案目录来选择访问通信合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="6109a-165">Contoso IT administrators and compliance specialists could also choose to access the communication compliance solution by selecting the Microsoft 365 solution catalog.</span></span> <span data-ttu-id="6109a-166">通过在**Microsoft 365 合规性中心**中选择左侧导航的 "**解决方案**" 部分中的 "**目录**"，他们可以打开列出所有 Microsoft 365 合规性解决方案的解决方案目录。</span><span class="sxs-lookup"><span data-stu-id="6109a-166">By selecting **Catalog** in **Solutions** section of the left navigation while in the **Microsoft 365 compliance center**, they can open the solution catalog listing all Microsoft 365 compliance solutions.</span></span> <span data-ttu-id="6109a-167">向下滚动到 "**内幕风险管理**" 部分，Contoso IT 管理员可以选择通信合规性以开始。</span><span class="sxs-lookup"><span data-stu-id="6109a-167">Scrolling down to the **Insider risk management** section, Contoso IT administrators can select Communication compliance to get started.</span></span> <span data-ttu-id="6109a-168">Contoso IT 管理员还决定使用导航控件中的 "显示" 将通信合规性解决方案固定到左导航窗格中，以便在以后登录时更快地进行访问。</span><span class="sxs-lookup"><span data-stu-id="6109a-168">Contoso IT administrators also decide to use the Show in navigation control to pin the communication compliance solution to the left-navigation pane for quicker access when they sign in going forward.</span></span>

![解决方案目录](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a><span data-ttu-id="6109a-170">从 Microsoft 365 管理中心开始</span><span class="sxs-lookup"><span data-stu-id="6109a-170">Starting from the Microsoft 365 admin center</span></span>

<span data-ttu-id="6109a-171">若要在从 microsoft 365 管理中心开始时访问通信合规性，Contoso IT 管理员和合规性专家登录到 microsoft 365 管理中心[（https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 管理中心** > **合规性**。</span><span class="sxs-lookup"><span data-stu-id="6109a-171">To access communication compliance when starting from the Microsoft 365 admin center, Contoso IT administrators and compliance specialists sign in to the Microsoft 365 admin center [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Compliance**.</span></span>

![通信合规性链接](../media/communication-compliance-case-compliance-link.png)

<span data-ttu-id="6109a-173">这将打开**Office 365 安全与合规中心**，并且必须选择页面顶部的横幅中提供的**Microsoft 365 合规性中心**的链接。</span><span class="sxs-lookup"><span data-stu-id="6109a-173">This opens the **Office 365 Security and Compliance center**, and they must select the link to the **Microsoft 365 compliance center** provided in the banner at the top of the page.</span></span>

![Office 365 安全与合规中心](../media/communication-compliance-case-scc.png)

<span data-ttu-id="6109a-175">在**Microsoft 365 合规性中心**中，Contoso IT 管理员选择 "**全部显示**" 以显示完整的合规性解决方案列表。</span><span class="sxs-lookup"><span data-stu-id="6109a-175">Once in the **Microsoft 365 compliance center**, Contoso IT administrators select **Show all** to display the full list of compliance solutions.</span></span>

![通信合规性菜单](../media/communication-compliance-case-show-all.png)

<span data-ttu-id="6109a-177">选择 "**全部显示**" 后，Contoso IT 管理员可以访问通信合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="6109a-177">After selecting **Show all**, the Contoso IT administrators can access the communication compliance solution.</span></span>

![通信合规性概述](../media/communication-compliance-case-overview.png)

## <a name="step-3---configuring-prerequisites-and-creating-a-communication-compliance-policy"></a><span data-ttu-id="6109a-179">步骤 3-配置系统必备组件和创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="6109a-179">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>

<span data-ttu-id="6109a-180">若要开始使用通信合规性策略，Contoso IT 管理员需要先配置一些先决条件，然后再设置新策略来监视冒犯性语言。</span><span class="sxs-lookup"><span data-stu-id="6109a-180">To get started with a communication compliance policy, there are several prerequisites that Contoso IT administrators need to configure before setting up the new policy to monitor for offensive language.</span></span> <span data-ttu-id="6109a-181">完成这些先决条件后，Contoso IT 管理员和合规性专家可以配置新策略和合规性专家，以开始调查并修正任何生成的警报。</span><span class="sxs-lookup"><span data-stu-id="6109a-181">After these prerequisites have been completed, Contoso IT administrators and compliance specialists can configure the new policy and compliance specialists can start investigation and remediating any generated alerts.</span></span>

### <a name="enabling-auditing-in-office-365"></a><span data-ttu-id="6109a-182">在 Office 365 中启用审核</span><span class="sxs-lookup"><span data-stu-id="6109a-182">Enabling auditing in Office 365</span></span>

<span data-ttu-id="6109a-183">通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="6109a-183">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="6109a-184">审核日志汇总了与已定义的组织策略相关联的所有活动，或只要有对通信合规性策略的更改。</span><span class="sxs-lookup"><span data-stu-id="6109a-184">The audit logs are a summary of all activities associated with a defined organizational policy or anytime there is a change to a communication compliance policy.</span></span>

<span data-ttu-id="6109a-185">Contoso IT 管理员查看并完成有关启用审核的[分步说明](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="6109a-185">Contoso IT administrators review and complete the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) to turn on auditing.</span></span> <span data-ttu-id="6109a-186">在他们启用审核后，会显示一条消息，指出正在准备审核日志，并且在准备完成后，可以在几个小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="6109a-186">After they turn on auditing, a message is displayed that says the audit log is being prepared and that they can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="6109a-187">Contoso IT 管理员只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="6109a-187">The Contoso IT administrators only have to do this action once.</span></span>

### <a name="setting-up-a-group-for-in-scope-users"></a><span data-ttu-id="6109a-188">为范围内用户设置组</span><span class="sxs-lookup"><span data-stu-id="6109a-188">Setting up a group for in-scope users</span></span>

<span data-ttu-id="6109a-189">Contoso 合规性专家希望将所有员工添加到将监视攻击性语言的通信策略中。</span><span class="sxs-lookup"><span data-stu-id="6109a-189">Contoso compliance specialists want to add all employee to the communication policy that will monitor for offensive language.</span></span> <span data-ttu-id="6109a-190">他们可以决定单独将每个员工用户帐户添加到策略中，但他们已决定在使用此策略的用户的**所有员工**通讯组时，会轻松得多，并节省大量时间。</span><span class="sxs-lookup"><span data-stu-id="6109a-190">They could decide to add each employee user account to the policy separately, but they've decided it is much easier and saves a lot of time to use an **All Employees** distribution group for the users for this policy.</span></span>

<span data-ttu-id="6109a-191">他们需要创建一个新组来包含所有 Contoso 员工，因此他们需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6109a-191">They need to create a new group to include all Contoso employees, so they take the following steps:</span></span>

1. <span data-ttu-id="6109a-192">Contoso it 管理员：登录**microsoft 365 管理中心** [（https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 管理中心** > **组** > **组**。</span><span class="sxs-lookup"><span data-stu-id="6109a-192">Contoso IT administrators IT sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Groups** > **Groups**.</span></span>
2. <span data-ttu-id="6109a-193">他们选择 "**添加组**" 并完成向导，以创建新的*Office 365 组*或*通讯组*。</span><span class="sxs-lookup"><span data-stu-id="6109a-193">They select **Add a group** and complete the wizard to create a new *Office 365 group* or *Distribution group*.</span></span>

![组](../media/communication-compliance-case-all-employees.png)

3. <span data-ttu-id="6109a-195">创建新组之后，需要将所有 Contoso 用户添加到新组中。</span><span class="sxs-lookup"><span data-stu-id="6109a-195">After the new group is created, they need to add all Contoso users to the new group.</span></span> <span data-ttu-id="6109a-196">他们打开**exchange 管理中心** [（https://outlook.office365.com/ecp) ](https://outlook.office365.com/ecp)并导航到**exchange 管理中心** > "**收件人** > "**组**。</span><span class="sxs-lookup"><span data-stu-id="6109a-196">They open the **Exchange admin center** [(https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) and navigate to **Exchange admin center** > **recipients** > **groups**.</span></span> <span data-ttu-id="6109a-197">Contoso IT 管理员选择成员资格区域和他们创建的新的*所有员工*组，并在向导中选择 "**编辑**" 控件以将所有 Contoso 员工添加到新组中。</span><span class="sxs-lookup"><span data-stu-id="6109a-197">The Contoso IT administrators select the Membership area and the new *All Employees* group they created and select the **Edit** control to add all Contoso employees to the new group in the wizard.</span></span>

![Exchange 管理中心](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a><span data-ttu-id="6109a-199">创建用于监视冒犯性语言的策略</span><span class="sxs-lookup"><span data-stu-id="6109a-199">Creating the policy to monitor for offensive language</span></span>

<span data-ttu-id="6109a-200">在满足所有先决条件的前提下，Contoso 的 IT 管理员和合规性专家可以配置通信合规性策略以监视攻击性语言。</span><span class="sxs-lookup"><span data-stu-id="6109a-200">With all the prerequisites completed, the IT administrators and the compliance specialists for Contoso are ready to configure the communication compliance policy to monitor for offensive language.</span></span> <span data-ttu-id="6109a-201">使用新的冒犯性语言策略模板，配置此策略既简单又快速。</span><span class="sxs-lookup"><span data-stu-id="6109a-201">Using the new offensive language policy template, configuring this policy is simple and quick.</span></span>

1. <span data-ttu-id="6109a-202">Contoso IT 管理员和合规性专家登录**Microsoft 365 合规性中心**，并从左侧导航窗格中选择 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="6109a-202">The Contoso IT administrators and compliance specialists sign into the **Microsoft 365 compliance center** and select **Communication compliance** from the left navigation pane.</span></span> <span data-ttu-id="6109a-203">此操作将打开**概述**仪表板，其中包含有关通信合规性策略模板的快速链接。</span><span class="sxs-lookup"><span data-stu-id="6109a-203">This action opens the **Overview** dashboard that has quick links for communication compliance policy templates.</span></span> <span data-ttu-id="6109a-204">它们通过选择模板的 "**入门**" 来选择**用于攻击性语言**模板的监视器。</span><span class="sxs-lookup"><span data-stu-id="6109a-204">They choose the **Monitor for offensive language** template by selecting **Get started** for the template.</span></span>

![通信合规性攻击性语言模板](../media/communication-compliance-case-template.png)

2. <span data-ttu-id="6109a-206">在策略模板向导中，Contoso IT 管理员和合规性专家将共同完成以下三个必填字段：**策略名称**、**要监督的用户或组**以及**审阅者**。</span><span class="sxs-lookup"><span data-stu-id="6109a-206">On the policy template wizard, the Contoso IT administrators and compliance specialists work together to complete the three required fields: **Policy name**, **Users or groups to supervise**, and **Reviewers**.</span></span>
3. <span data-ttu-id="6109a-207">由于策略向导已经为策略建议了名称，IT 管理员和合规性专家决定保留建议的名称，并将重点放在其余字段上。</span><span class="sxs-lookup"><span data-stu-id="6109a-207">Since the policy wizard has already suggested a name for the policy, the IT administrators and compliance specialists decide to keep the suggested name and focus on the remaining fields.</span></span> <span data-ttu-id="6109a-208">他们选择 "要管理的**用户或组**的*所有雇员*" 组，然后选择应调查和修正 "**审阅者**" 字段的策略通知的合规性专家。</span><span class="sxs-lookup"><span data-stu-id="6109a-208">They select the *All employees* group for the **Users or groups to supervise** field and select the compliance specialists that should investigate and remediate policy alerts for the **Reviewers** field.</span></span> <span data-ttu-id="6109a-209">配置策略和开始收集警报信息的最后一步是选择 "**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="6109a-209">The last step to configure the policy and start gathering alert information is to select **Create policy**.</span></span>

![通信合规性冒犯性语言向导](../media/communication-compliance-case-wizard.png)

## <a name="step-4--investigate-and-remediate-alerts"></a><span data-ttu-id="6109a-211">第4步–调查和修正警报</span><span class="sxs-lookup"><span data-stu-id="6109a-211">Step 4 – Investigate and remediate alerts</span></span>

<span data-ttu-id="6109a-212">现在已配置用于监视攻击性语言的通信合规性策略，Contoso 合规性专家的下一步是调查并修正该策略生成的任何警报。</span><span class="sxs-lookup"><span data-stu-id="6109a-212">Now that the communication compliance policy to monitor for offensive language is configured, the next step for the Contoso compliance specialists will be to investigate and remediate any alerts generated by the policy.</span></span> <span data-ttu-id="6109a-213">该策略最长需要24小时才能完全处理所有通信源通道中的通信，并且警报**仪表板**中显示警报。</span><span class="sxs-lookup"><span data-stu-id="6109a-213">It will take up to 24 hours for the policy to fully process communications in all the communication source channels and for alerts to show up in the **Alert dashboard**.</span></span>

<span data-ttu-id="6109a-214">生成警报后，Contoso 合规性专家将遵循[工作流说明](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate)来调查和修正攻击性语言问题。</span><span class="sxs-lookup"><span data-stu-id="6109a-214">After alerts are generated, Contoso compliance specialists will follow the [workflow instructions](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) to investigate and remediate offensive language issues.</span></span>
