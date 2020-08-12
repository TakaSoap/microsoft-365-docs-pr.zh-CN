---
title: 案例研究-Contoso 为 Microsoft 团队、Exchange 和 Yammer 通信快速配置冒犯性语言策略
description: Contoso 的个案研究以及如何快速配置通信合规性策略以监视 Microsoft 团队、Exchange Online 和 Yammer 通信中的攻击性语言。
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
ms.openlocfilehash: 9e16e96989fd3e2312129f9633bd298181839cf0
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632083"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a><span data-ttu-id="178f6-103">案例研究-Contoso 为 Microsoft 团队、Exchange 和 Yammer 通信快速配置冒犯性语言策略</span><span class="sxs-lookup"><span data-stu-id="178f6-103">Case study - Contoso quickly configures an offensive language policy for Microsoft Teams, Exchange, and Yammer communications</span></span>

<span data-ttu-id="178f6-104">Microsoft 365 中的通信合规性可帮助您在组织中检测、捕获和处理不适当的邮件，从而帮助最大限度地减少通信风险。</span><span class="sxs-lookup"><span data-stu-id="178f6-104">Communication compliance in Microsoft 365 helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span> <span data-ttu-id="178f6-105">通过预定义和自定义策略，可以扫描策略匹配的内部和外部通信，以便指定的审阅者可以对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="178f6-105">Pre-defined and custom policies allow you to scan internal and external communications for policy matches so they can be examined by designated reviewers.</span></span> <span data-ttu-id="178f6-106">审阅者可以在组织中调查扫描的电子邮件、Microsoft 团队、Yammer 或第三方通信，并采取适当的补救措施以确保它们符合组织的邮件标准。</span><span class="sxs-lookup"><span data-stu-id="178f6-106">Reviewers can investigate scanned email, Microsoft Teams, Yammer, or third-party communications in your organization and take appropriate remediation actions to make sure they're compliant with your organization's message standards.</span></span>

<span data-ttu-id="178f6-107">Contoso Corporation 是一个虚构的组织，需要快速配置一个策略来监视冒犯性语言。</span><span class="sxs-lookup"><span data-stu-id="178f6-107">The Contoso Corporation is a fictional organization that needs to quickly configure a policy to monitor for offensive language.</span></span> <span data-ttu-id="178f6-108">他们一直使用 Microsoft 365，主要用于电子邮件、Microsoft 团队和 Yammer 对其用户的支持，但具有在工作区骚扰方面强制实施公司策略的新要求。</span><span class="sxs-lookup"><span data-stu-id="178f6-108">They have been using Microsoft 365 primarily for email, Microsoft Teams, and Yammer support for their users but have new requirements to enforce company policy around workplace harassment.</span></span> <span data-ttu-id="178f6-109">Contoso IT 管理员和合规性专家对使用 Microsoft 365 的基础有一个基本的了解，并且正在寻找有关如何快速开始实现通信合规性的端到端指南。</span><span class="sxs-lookup"><span data-stu-id="178f6-109">Contoso IT administrators and compliance specialists have a basic understanding of the fundamentals of working with Microsoft 365 and are looking for end-to-end guidance for how to quickly get started with communication compliance.</span></span>

<span data-ttu-id="178f6-110">此案例研究将介绍快速配置通信合规性策略以监视攻击性语言通信的基础知识。</span><span class="sxs-lookup"><span data-stu-id="178f6-110">This case study will cover the basics for quickly configuring a communication compliance policy to monitor communications for offensive language.</span></span> <span data-ttu-id="178f6-111">本指南包括：</span><span class="sxs-lookup"><span data-stu-id="178f6-111">This guidance includes:</span></span>

- <span data-ttu-id="178f6-112">第1步-规划通信合规性</span><span class="sxs-lookup"><span data-stu-id="178f6-112">Step 1 - Planning for communication compliance</span></span>
- <span data-ttu-id="178f6-113">第2步-访问 Microsoft 365 中的通信合规性</span><span class="sxs-lookup"><span data-stu-id="178f6-113">Step 2 - Accessing communication compliance in Microsoft 365</span></span>
- <span data-ttu-id="178f6-114">步骤 3-配置系统必备组件和创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="178f6-114">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>
- <span data-ttu-id="178f6-115">第4步-调查和修正警报</span><span class="sxs-lookup"><span data-stu-id="178f6-115">Step 4 - Investigation and remediation of alerts</span></span>

## <a name="step-1-planning-for-communication-compliance"></a><span data-ttu-id="178f6-116">步骤1：规划通信合规性</span><span class="sxs-lookup"><span data-stu-id="178f6-116">Step 1: Planning for communication compliance</span></span>

<span data-ttu-id="178f6-117">Contoso IT 管理员和合规性专家在 Microsoft 365 中参加了有关合规性解决方案的在线网络研讨会，并确定通信合规性策略将帮助他们满足针对减少工作区骚扰的更新的公司策略要求。</span><span class="sxs-lookup"><span data-stu-id="178f6-117">Contoso IT administrators and compliance specialists attended online webinars about compliance solutions in Microsoft 365 and decided that communication compliance policies will help them meet the updated corporate policy requirements for reducing workplace harassment.</span></span> <span data-ttu-id="178f6-118">它们共同开发了一个计划，用于创建和启用通信合规性策略，该策略将监视在 Microsoft 团队中发送的攻击性语言、Yammer 中的私人邮件和社区对话以及在 Exchange Online 中发送的电子邮件中的聊天。</span><span class="sxs-lookup"><span data-stu-id="178f6-118">Working together, they've developed a plan to create and enable a communication compliance policy that will monitor for offensive language for chats sent in Microsoft Teams, private messages and community conversations in Yammer, and in email messages sent in Exchange Online.</span></span> <span data-ttu-id="178f6-119">其计划包括标识：</span><span class="sxs-lookup"><span data-stu-id="178f6-119">Their plan includes identifying:</span></span>

- <span data-ttu-id="178f6-120">需要访问通信合规性功能的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="178f6-120">The IT administrators that need access to communication compliance features.</span></span>
- <span data-ttu-id="178f6-121">需要创建和管理通信策略的合规性专家。</span><span class="sxs-lookup"><span data-stu-id="178f6-121">The compliance specialists that need to create and manage communication policies.</span></span>
- <span data-ttu-id="178f6-122">其他部门的合规性专家和其他同事 (人力资源、法律等需要调查和修正通信合规性警报的 ) 。</span><span class="sxs-lookup"><span data-stu-id="178f6-122">The compliance specialists and other colleague in other departments (Human Resources, Legal, etc.) that need to investigate and remediate communication compliance alerts.</span></span>
- <span data-ttu-id="178f6-123">将为通信合规性攻击性语言策略的范围内的用户。</span><span class="sxs-lookup"><span data-stu-id="178f6-123">The users that will be in-scope for the communication compliance offensive language policy.</span></span>

### <a name="licensing"></a><span data-ttu-id="178f6-124">许可</span><span class="sxs-lookup"><span data-stu-id="178f6-124">Licensing</span></span>

<span data-ttu-id="178f6-125">第一步是确认 Contoso 的 Microsoft 365 许可包括对通信合规性解决方案的支持。</span><span class="sxs-lookup"><span data-stu-id="178f6-125">The first step is to confirm that Contoso's Microsoft 365 licensing includes support for the communication compliance solution.</span></span> <span data-ttu-id="178f6-126">若要访问和使用通信合规性，Contoso IT 管理员需要验证 Contoso 是否具有以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="178f6-126">To access and use communication compliance, Contoso IT administrators need to verify that Contoso has one of the following:</span></span>

- <span data-ttu-id="178f6-127">Microsoft 365 E5 订阅 (付费或试用版) </span><span class="sxs-lookup"><span data-stu-id="178f6-127">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="178f6-128">Microsoft 365 E3 订阅 + Microsoft 365 E5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="178f6-128">Microsoft 365 E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="178f6-129">Microsoft 365 E3 订阅 + Microsoft 365 E5 内幕人士风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="178f6-129">Microsoft 365 E3 subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="178f6-130">Microsoft 365 A5 订阅 (付费版或试用版) </span><span class="sxs-lookup"><span data-stu-id="178f6-130">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="178f6-131">Microsoft 365 A3 订阅 + Microsoft 365 A5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="178f6-131">Microsoft 365 A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="178f6-132">Microsoft 365 A3 订阅 + Microsoft 365 A5 内幕成员风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="178f6-132">Microsoft 365 A3 subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="178f6-133">Microsoft 365 G5 订阅 (付费版或试用版) </span><span class="sxs-lookup"><span data-stu-id="178f6-133">Microsoft 365 G5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="178f6-134">Microsoft 365 G5 订阅 + Microsoft 365 G5 合规性附加</span><span class="sxs-lookup"><span data-stu-id="178f6-134">Microsoft 365 G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="178f6-135">Microsoft 365 G5 订阅 + Microsoft 365 G5 内幕版风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="178f6-135">Microsoft 365 G5 subscription + the Microsoft 365 G5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="178f6-136">Office 365 企业版 E5 订阅 (付费或试用版) </span><span class="sxs-lookup"><span data-stu-id="178f6-136">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="178f6-137">Office 365 企业版 E3 订阅 + Office 365 高级合规性外接程序 (不再可用于新订阅，请参阅 note) </span><span class="sxs-lookup"><span data-stu-id="178f6-137">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="178f6-138">他们还必须确认必须为通信合规性策略中包括的用户分配上述许可证之一。</span><span class="sxs-lookup"><span data-stu-id="178f6-138">They must also confirm that users included in communication compliance policies must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="178f6-139">Office 365 高级合规性不再作为独立订阅销售。</span><span class="sxs-lookup"><span data-stu-id="178f6-139">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="178f6-140">当当前订阅过期时，客户应转换为上述订阅之一，其中包含相同或更多的合规性功能。</span><span class="sxs-lookup"><span data-stu-id="178f6-140">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="178f6-141">Contoso IT 管理员需要执行以下步骤来验证 Contoso 的许可支持：</span><span class="sxs-lookup"><span data-stu-id="178f6-141">Contoso IT administrators take the following steps to verify the licensing support for Contoso:</span></span>

1. <span data-ttu-id="178f6-142">IT 管理员登录到**microsoft 365 管理中心** [ (https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 管理中心**  >  **帐单**  >  **许可证**。</span><span class="sxs-lookup"><span data-stu-id="178f6-142">IT administrators sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Billing** > **Licenses**.</span></span>

2. <span data-ttu-id="178f6-143">在这里，他们确认他们有一个[许可证选项](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin)，其中包括支持通信合规性。</span><span class="sxs-lookup"><span data-stu-id="178f6-143">Here they confirm that they have one of the [license options](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) that includes support for communication compliance.</span></span>

![通信合规性许可](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a><span data-ttu-id="178f6-145">通信合规性的权限</span><span class="sxs-lookup"><span data-stu-id="178f6-145">Permissions for communication compliance</span></span>

<span data-ttu-id="178f6-146">有五个角色用于配置管理通信合规性功能的权限。</span><span class="sxs-lookup"><span data-stu-id="178f6-146">There are five roles used to configure permissions to manage communication compliance features.</span></span> <span data-ttu-id="178f6-147">为了使通信合规性在 Microsoft 365 合规性中心中可用作菜单选项，若要继续执行这些配置步骤，则会为 Contoso 管理员分配*通信合规性管理员*角色。</span><span class="sxs-lookup"><span data-stu-id="178f6-147">To make Communication compliance available as a menu option in Microsoft 365 compliance center and to continue with these configuration steps, Contoso administrators are assigned the *Communication Compliance Admin* role.</span></span>

<span data-ttu-id="178f6-148">Contoso 决定创建一个自定义角色组，并将所有通信合规性角色分配给该组。</span><span class="sxs-lookup"><span data-stu-id="178f6-148">Contoso decides to create one custom role group and assign all the communication compliance roles to the group.</span></span> <span data-ttu-id="178f6-149">这使 Contoso 能够更轻松地快速入门，并最大限度地满足合规性管理要求。</span><span class="sxs-lookup"><span data-stu-id="178f6-149">This makes it easier for Contoso to get started quickly and best fits their compliance management requirements.</span></span>

<span data-ttu-id="178f6-150">Contoso 将创建一个包含所有以下通信合规性角色的角色组：</span><span class="sxs-lookup"><span data-stu-id="178f6-150">Contoso will create one role group that contains all the following communication compliance roles:</span></span>

|<span data-ttu-id="178f6-151">**角色**</span><span class="sxs-lookup"><span data-stu-id="178f6-151">**Role**</span></span>|<span data-ttu-id="178f6-152">**角色权限**</span><span class="sxs-lookup"><span data-stu-id="178f6-152">**Role permissions**</span></span>|
|:-----|:-----|
| <span data-ttu-id="178f6-153">**通信合规性管理员**</span><span class="sxs-lookup"><span data-stu-id="178f6-153">**Communication Compliance Admin**</span></span> | <span data-ttu-id="178f6-154">分配了此角色的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。</span><span class="sxs-lookup"><span data-stu-id="178f6-154">Users assigned this role can create, read, update, and delete communication compliance policies, global settings, and role group assignments.</span></span> <span data-ttu-id="178f6-155">分配了此角色的用户无法查看邮件警报。</span><span class="sxs-lookup"><span data-stu-id="178f6-155">Users assigned this role cannot view message alerts.</span></span> |
| <span data-ttu-id="178f6-156">**通信合规性分析**</span><span class="sxs-lookup"><span data-stu-id="178f6-156">**Communication Compliance Analysis**</span></span> | <span data-ttu-id="178f6-157">分配了此角色的用户可以查看将其分配为审阅者的策略、查看邮件元数据 (不是邮件内容) 、升级到其他审阅者或向用户发送通知。</span><span class="sxs-lookup"><span data-stu-id="178f6-157">Users assigned this role can view policies where they are assigned as Reviewers, view message metadata (not message content), escalate to additional reviewers, or send notifications to users.</span></span> <span data-ttu-id="178f6-158">分析师无法解决待处理的警报。</span><span class="sxs-lookup"><span data-stu-id="178f6-158">Analysts cannot resolve pending alerts.</span></span> |
| <span data-ttu-id="178f6-159">**通信合规性调查**</span><span class="sxs-lookup"><span data-stu-id="178f6-159">**Communication Compliance Investigation**</span></span> | <span data-ttu-id="178f6-160">分配了此角色的用户可以查看邮件元数据和内容、升级到其他审阅者、升级到高级电子数据展示事例、向用户发送通知以及解决警报。</span><span class="sxs-lookup"><span data-stu-id="178f6-160">Users assigned this role can view message metadata and content, escalate to additional reviewers, escalate to an Advanced eDiscovery case, send notifications to users, and resolve the alert.</span></span> |
| <span data-ttu-id="178f6-161">**通信合规性查看器**</span><span class="sxs-lookup"><span data-stu-id="178f6-161">**Communication Compliance Viewer**</span></span> | <span data-ttu-id="178f6-162">分配了此角色的用户可以访问通信合规性主页上的所有报告小部件，并且可以查看所有通信合规性报告。</span><span class="sxs-lookup"><span data-stu-id="178f6-162">Users assigned this role can access all reporting widgets on the communication compliance home page and can view all communication compliance reports.</span></span> |
| <span data-ttu-id="178f6-163">**通信合规性案例管理**</span><span class="sxs-lookup"><span data-stu-id="178f6-163">**Communication Compliance Case Management**</span></span> | <span data-ttu-id="178f6-164">分配了此角色的用户可以管理案例并对通知进行操作。</span><span class="sxs-lookup"><span data-stu-id="178f6-164">Users assigned this role can manage cases and act on alerts.</span></span> <span data-ttu-id="178f6-165">为管理员、分析师和调查人员创建自定义角色组时，需要此角色。</span><span class="sxs-lookup"><span data-stu-id="178f6-165">This role is required for when creating custom role groups for administrators, analysts, and investigators.</span></span> <span data-ttu-id="178f6-166">查看器的自定义组不需要分配此角色。</span><span class="sxs-lookup"><span data-stu-id="178f6-166">Custom groups for viewers do not need this role assigned.</span></span> |

1. <span data-ttu-id="178f6-167">Contoso IT 管理员使用全局管理员帐户的凭据登录到**Office 365 安全与合规中心**权限[ (https://protection.office.com/permissions) ](https://protection.office.com/permissions)页面，并选择在 Microsoft 365 中查看和管理角色的链接。</span><span class="sxs-lookup"><span data-stu-id="178f6-167">Contoso IT administrators sign into the **Office 365 Security and Compliance center** permissions page [(https://protection.office.com/permissions)](https://protection.office.com/permissions) using credentials for a global administrator account and select the link to view and manage roles in Microsoft 365.</span></span>
2. <span data-ttu-id="178f6-168">选择 "**创建**" 后，将新角色组命名为 "*通信合规性*" 的友好名称，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="178f6-168">After selecting **Create**, they give the new role group a friendly name of "*Communication Compliance*" and select **Next**.</span></span>
3. <span data-ttu-id="178f6-169">他们选择 "**选择角色**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="178f6-169">They select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="178f6-170">它们通过选中*通信合规性管理*、*通信合规性分析*、*通信合规性调查*、*通信合规性查看器*和*通信合规*性调查的复选框来添加所需的角色，然后选择 "**添加**"、 **"完成" 和 "** **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="178f6-170">They add the required roles by selecting the checkbox for *Communication Compliance Admin*, *Communication Compliance Analysis*, *Communication Compliance Investigation*, *Communication Compliance Viewer*, and *Communication Compliance Case Management*, then they select **Add**, **Done,** and **Next**.</span></span>

    ![通信合规性角色](../media/communication-compliance-case-roles.png)

4. <span data-ttu-id="178f6-172">接下来，IT 管理员选择 "**选择成员**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="178f6-172">Next, the IT administrators select **Choose members** then select **Add**.</span></span> <span data-ttu-id="178f6-173">选中要为其创建策略并管理策略匹配的邮件的所有用户和组的复选框。</span><span class="sxs-lookup"><span data-stu-id="178f6-173">The select the checkbox for all the users and groups that they want to create policies and manage messages with policy matches.</span></span> <span data-ttu-id="178f6-174">他们将 IT 管理员、合规性专家和其他同事添加到在初始规划中确定的人力资源和法律部门，然后选择 "**添加**"、"**完成**" 和 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="178f6-174">They add the IT administrators, compliance specialists, and other colleagues in Human Resources and Legal departments that they identified in the initial planning, then select **Add**, **Done**, and **Next**.</span></span>
5. <span data-ttu-id="178f6-175">若要完成权限，IT 管理员选择 "**创建角色组**" 以完成。</span><span class="sxs-lookup"><span data-stu-id="178f6-175">To finalize the permissions, the IT administrators select **Create role group** to finish.</span></span> <span data-ttu-id="178f6-176">在 Contoso 的 Microsoft 365 服务中，角色将需要大约30分钟的时间才能生效。</span><span class="sxs-lookup"><span data-stu-id="178f6-176">It will take about 30 minutes for the roles to be effective in Contoso's Microsoft 365 service.</span></span>

    ![通信合规性检查](../media/communication-compliance-case-review.png)

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a><span data-ttu-id="178f6-178">步骤2：访问 Microsoft 365 中的通信合规性</span><span class="sxs-lookup"><span data-stu-id="178f6-178">Step 2: Accessing communication compliance in Microsoft 365</span></span>

<span data-ttu-id="178f6-179">为通信合规性配置权限后，在新角色组中定义的 Contoso IT 管理员和合规性专家可以访问 Microsoft 365 中的通信合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="178f6-179">After configuring the permissions for communication compliance, Contoso IT administrators and compliance specialists defined in the new role group can access the communication compliance solution in Microsoft 365.</span></span> <span data-ttu-id="178f6-180">Contoso IT 管理员和合规性专家有几种方法可以访问通信合规性并开始创建新策略：</span><span class="sxs-lookup"><span data-stu-id="178f6-180">Contoso IT administrators and compliance specialists have several ways to access communication compliance and get started creating a new policy:</span></span>

- <span data-ttu-id="178f6-181">直接从通信合规性解决方案开始</span><span class="sxs-lookup"><span data-stu-id="178f6-181">Starting directly from the communication compliance solution</span></span>
- <span data-ttu-id="178f6-182">从 Microsoft 365 合规性中心开始</span><span class="sxs-lookup"><span data-stu-id="178f6-182">Starting from the Microsoft 365 compliance center</span></span>
- <span data-ttu-id="178f6-183">从 Microsoft 365 解决方案目录开始</span><span class="sxs-lookup"><span data-stu-id="178f6-183">Starting from the Microsoft 365 solution catalog</span></span>
- <span data-ttu-id="178f6-184">从 Microsoft 365 管理中心开始</span><span class="sxs-lookup"><span data-stu-id="178f6-184">Starting from the Microsoft 365 admin center</span></span>

### <a name="starting-directly-from-the-communication-compliance-solution"></a><span data-ttu-id="178f6-185">直接从通信合规性解决方案开始</span><span class="sxs-lookup"><span data-stu-id="178f6-185">Starting directly from the communication compliance solution</span></span>

<span data-ttu-id="178f6-186">访问解决方案的最快方法是直接登录到**通信合规性** (<https://compliance.microsoft.com/supervisoryreview>) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="178f6-186">The quickest way to access the solution is to sign in directly to the **Communication compliance** (<https://compliance.microsoft.com/supervisoryreview>) solution.</span></span> <span data-ttu-id="178f6-187">使用此链接，Contoso IT 管理员和合规性专家将转到通信合规性概述仪表板，您可以在其中快速查看通知的状态并从预定义的模板创建新策略。</span><span class="sxs-lookup"><span data-stu-id="178f6-187">Using this link, Contoso IT administrators and compliance specialists will be directed to the communication compliance Overview dashboard where you can quickly review the status of alerts and create new policies from the pre-defined templates.</span></span>

![通信合规性概述](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a><span data-ttu-id="178f6-189">从 Microsoft 365 合规性中心开始</span><span class="sxs-lookup"><span data-stu-id="178f6-189">Starting from the Microsoft 365 compliance center</span></span>

<span data-ttu-id="178f6-190">Contoso IT 管理员和合规性专家访问通信合规性解决方案的另一种简单方法是直接登录到**Microsoft 365 合规中心** [ (https://compliance.microsoft.com) ](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="178f6-190">Another easy way for Contoso IT administrators and compliance specialists to access the communication compliance solution is to sign in directly to the **Microsoft 365 compliance center** [(https://compliance.microsoft.com)](https://compliance.microsoft.com).</span></span> <span data-ttu-id="178f6-191">登录后，用户只需选择 "**全部显示**" 控制即可显示所有合规性解决方案，然后选择要开始的**通信合规性**解决方案。</span><span class="sxs-lookup"><span data-stu-id="178f6-191">After signing in, users simply need to select the **Show all** control to display all the compliance solutions and then select the **Communication compliance** solution to get started.</span></span>

![合规性中心](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a><span data-ttu-id="178f6-193">从 Microsoft 365 解决方案目录开始</span><span class="sxs-lookup"><span data-stu-id="178f6-193">Starting from the Microsoft 365 solution catalog</span></span>

<span data-ttu-id="178f6-194">Contoso IT 管理员和合规性专家也可以通过选择 Microsoft 365 解决方案目录来选择访问通信合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="178f6-194">Contoso IT administrators and compliance specialists could also choose to access the communication compliance solution by selecting the Microsoft 365 solution catalog.</span></span> <span data-ttu-id="178f6-195">通过在**Microsoft 365 合规性中心**中选择左侧导航的 "**解决方案**" 部分中的 "**目录**"，他们可以打开列出所有 Microsoft 365 合规性解决方案的解决方案目录。</span><span class="sxs-lookup"><span data-stu-id="178f6-195">By selecting **Catalog** in **Solutions** section of the left navigation while in the **Microsoft 365 compliance center**, they can open the solution catalog listing all Microsoft 365 compliance solutions.</span></span> <span data-ttu-id="178f6-196">向下滚动到 "**内幕风险管理**" 部分，Contoso IT 管理员可以选择通信合规性以开始。</span><span class="sxs-lookup"><span data-stu-id="178f6-196">Scrolling down to the **Insider risk management** section, Contoso IT administrators can select Communication compliance to get started.</span></span> <span data-ttu-id="178f6-197">Contoso IT 管理员还决定使用导航控件中的 "显示" 将通信合规性解决方案固定到左导航窗格中，以便在以后登录时更快地进行访问。</span><span class="sxs-lookup"><span data-stu-id="178f6-197">Contoso IT administrators also decide to use the Show in navigation control to pin the communication compliance solution to the left-navigation pane for quicker access when they sign in going forward.</span></span>

![解决方案目录](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a><span data-ttu-id="178f6-199">从 Microsoft 365 管理中心开始</span><span class="sxs-lookup"><span data-stu-id="178f6-199">Starting from the Microsoft 365 admin center</span></span>

<span data-ttu-id="178f6-200">若要在从 microsoft 365 管理中心开始时访问通信合规性，Contoso IT 管理员和合规性专家登录到 microsoft 365 管理中心[ (https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 admin center**  >  **合规性**。</span><span class="sxs-lookup"><span data-stu-id="178f6-200">To access communication compliance when starting from the Microsoft 365 admin center, Contoso IT administrators and compliance specialists sign in to the Microsoft 365 admin center [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Compliance**.</span></span>

![通信合规性链接](../media/communication-compliance-case-compliance-link.png)

<span data-ttu-id="178f6-202">此操作将打开**Office 365 安全与合规中心**，并且必须选择页面顶部的横幅中提供的**Microsoft 365 合规性中心**的链接。</span><span class="sxs-lookup"><span data-stu-id="178f6-202">This action opens the **Office 365 Security and Compliance center**, and they must select the link to the **Microsoft 365 compliance center** provided in the banner at the top of the page.</span></span>

![Office 365 安全与合规中心](../media/communication-compliance-case-scc.png)

<span data-ttu-id="178f6-204">在**Microsoft 365 合规性中心**中，Contoso IT 管理员选择 "**全部显示**" 以显示完整的合规性解决方案列表。</span><span class="sxs-lookup"><span data-stu-id="178f6-204">Once in the **Microsoft 365 compliance center**, Contoso IT administrators select **Show all** to display the full list of compliance solutions.</span></span>

![通信合规性菜单](../media/communication-compliance-case-show-all.png)

<span data-ttu-id="178f6-206">选择 "**全部显示**" 后，Contoso IT 管理员可以访问通信合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="178f6-206">After selecting **Show all**, the Contoso IT administrators can access the communication compliance solution.</span></span>

![通信合规性概述](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a><span data-ttu-id="178f6-208">步骤3：配置系统必备组件和创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="178f6-208">Step 3: Configuring prerequisites and creating a communication compliance policy</span></span>

<span data-ttu-id="178f6-209">若要开始使用通信合规性策略，Contoso IT 管理员需要先配置一些先决条件，然后再设置新策略来监视冒犯性语言。</span><span class="sxs-lookup"><span data-stu-id="178f6-209">To get started with a communication compliance policy, there are several prerequisites that Contoso IT administrators need to configure before setting up the new policy to monitor for offensive language.</span></span> <span data-ttu-id="178f6-210">完成这些先决条件后，Contoso IT 管理员和合规性专家可以配置新策略和合规性专家，以开始调查并修正任何生成的警报。</span><span class="sxs-lookup"><span data-stu-id="178f6-210">After these prerequisites have been completed, Contoso IT administrators and compliance specialists can configure the new policy and compliance specialists can start investigation and remediating any generated alerts.</span></span>

### <a name="enabling-auditing-in-microsoft-365"></a><span data-ttu-id="178f6-211">在 Microsoft 365 中启用审核</span><span class="sxs-lookup"><span data-stu-id="178f6-211">Enabling auditing in Microsoft 365</span></span>

<span data-ttu-id="178f6-212">通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="178f6-212">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="178f6-213">审核日志汇总了与已定义的组织策略相关联的所有活动，或只要有对通信合规性策略的更改。</span><span class="sxs-lookup"><span data-stu-id="178f6-213">The audit logs are a summary of all activities associated with a defined organizational policy or anytime there is a change to a communication compliance policy.</span></span>

<span data-ttu-id="178f6-214">Contoso IT 管理员查看并完成有关启用审核的[分步说明](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="178f6-214">Contoso IT administrators review and complete the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) to turn on auditing.</span></span> <span data-ttu-id="178f6-215">在他们启用审核后，会显示一条消息，指出正在准备审核日志，并且在准备完成后，可以在几个小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="178f6-215">After they turn on auditing, a message is displayed that says the audit log is being prepared and that they can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="178f6-216">Contoso IT 管理员只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="178f6-216">The Contoso IT administrators only have to do this action once.</span></span>

### <a name="configuring-yammer-tenant-for-native-mode"></a><span data-ttu-id="178f6-217">为本机模式配置 Yammer 租户</span><span class="sxs-lookup"><span data-stu-id="178f6-217">Configuring Yammer tenant for Native Mode</span></span>

<span data-ttu-id="178f6-218">通信合规性要求组织的 Yammer 租户处于本机模式，以监视私人邮件和公共社区对话中的冒犯性语言。</span><span class="sxs-lookup"><span data-stu-id="178f6-218">Communication compliance requires that the Yammer tenant for an organization is in Native Mode to monitor for offensive language in private messages and public community conversations.</span></span>

<span data-ttu-id="178f6-219">Contoso IT 管理员确保他们在[microsoft 365 文章中查看 Yammer 本机模式概述](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)中的信息，并按照在[为 Microsoft 365 的本机模式配置 Yammer 网络](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)主题中运行迁移工具的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="178f6-219">Contoso IT administrators make sure they review the information in the [Overview of Yammer Native Mode in Microsoft 365 article](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) and follow the steps for running the migration tool in the [Configure your Yammer network for Native Mode for Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode) topic.</span></span>

### <a name="setting-up-a-group-for-in-scope-users"></a><span data-ttu-id="178f6-220">为范围内用户设置组</span><span class="sxs-lookup"><span data-stu-id="178f6-220">Setting up a group for in-scope users</span></span>

<span data-ttu-id="178f6-221">Contoso 合规性专家希望将所有用户添加到将监视攻击性语言的通信策略中。</span><span class="sxs-lookup"><span data-stu-id="178f6-221">Contoso compliance specialists want to add all users to the communication policy that will monitor for offensive language.</span></span> <span data-ttu-id="178f6-222">他们可以决定单独将每个用户帐户添加到策略中，但他们已决定使用此策略的用户的**所有用户**通讯组的时间更简单，并节省时间。</span><span class="sxs-lookup"><span data-stu-id="178f6-222">They could decide to add each user account to the policy separately, but they've decided it is much easier and saves time to use an **All Users** distribution group for the users for this policy.</span></span>

<span data-ttu-id="178f6-223">他们需要创建一个新组，以包含所有 Contoso 用户，因此他们需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="178f6-223">They need to create a new group to include all Contoso users, so they take the following steps:</span></span>

1. <span data-ttu-id="178f6-224">Contoso it 管理员：登录**microsoft 365 管理中心** [ (https://admin.microsoft.com) ](https://admin.microsoft.com)并导航到**microsoft 365 管理中心**  >  **组**  >  **组**。</span><span class="sxs-lookup"><span data-stu-id="178f6-224">Contoso IT administrators IT sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Groups** > **Groups**.</span></span>
2. <span data-ttu-id="178f6-225">他们选择 "**添加组**" 并完成向导，以创建新的*Microsoft 365 组*或*通讯组*。</span><span class="sxs-lookup"><span data-stu-id="178f6-225">They select **Add a group** and complete the wizard to create a new *Microsoft 365 group* or *Distribution group*.</span></span>

    ![组](../media/communication-compliance-case-all-employees.png)

3. <span data-ttu-id="178f6-227">创建新组之后，需要将所有 Contoso 用户添加到新组中。</span><span class="sxs-lookup"><span data-stu-id="178f6-227">After the new group is created, they need to add all Contoso users to the new group.</span></span> <span data-ttu-id="178f6-228">他们打开**exchange 管理中心** [ (https://outlook.office365.com/ecp) ](https://outlook.office365.com/ecp)并导航到**Exchange 管理中心**  >  **收件人**  >  **组**。</span><span class="sxs-lookup"><span data-stu-id="178f6-228">They open the **Exchange admin center** [(https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) and navigate to **Exchange admin center** > **recipients** > **groups**.</span></span> <span data-ttu-id="178f6-229">Contoso IT 管理员选择成员资格区域和他们创建的新的*所有员工*组，并在向导中选择 "**编辑**" 控件以将所有 Contoso 用户添加到新组中。</span><span class="sxs-lookup"><span data-stu-id="178f6-229">The Contoso IT administrators select the Membership area and the new *All Employees* group they created and select the **Edit** control to add all Contoso users to the new group in the wizard.</span></span>

    ![Exchange 管理中心](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a><span data-ttu-id="178f6-231">创建用于监视冒犯性语言的策略</span><span class="sxs-lookup"><span data-stu-id="178f6-231">Creating the policy to monitor for offensive language</span></span>

<span data-ttu-id="178f6-232">在满足所有先决条件的前提下，Contoso 的 IT 管理员和合规性专家可以配置通信合规性策略以监视攻击性语言。</span><span class="sxs-lookup"><span data-stu-id="178f6-232">With all the prerequisites completed, the IT administrators and the compliance specialists for Contoso are ready to configure the communication compliance policy to monitor for offensive language.</span></span> <span data-ttu-id="178f6-233">使用新的冒犯性语言策略模板，配置此策略既简单又快速。</span><span class="sxs-lookup"><span data-stu-id="178f6-233">Using the new offensive language policy template, configuring this policy is simple and quick.</span></span>

1. <span data-ttu-id="178f6-234">Contoso IT 管理员和合规性专家登录**Microsoft 365 合规性中心**，并从左侧导航窗格中选择 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="178f6-234">The Contoso IT administrators and compliance specialists sign into the **Microsoft 365 compliance center** and select **Communication compliance** from the left navigation pane.</span></span> <span data-ttu-id="178f6-235">此操作将打开**概述**仪表板，其中包含有关通信合规性策略模板的快速链接。</span><span class="sxs-lookup"><span data-stu-id="178f6-235">This action opens the **Overview** dashboard that has quick links for communication compliance policy templates.</span></span> <span data-ttu-id="178f6-236">它们通过选择模板的 "**入门**" 来选择**用于攻击性语言**模板的监视器。</span><span class="sxs-lookup"><span data-stu-id="178f6-236">They choose the **Monitor for offensive language** template by selecting **Get started** for the template.</span></span>

    ![通信合规性攻击性语言模板](../media/communication-compliance-case-template.png)

2. <span data-ttu-id="178f6-238">在策略模板向导中，Contoso IT 管理员和合规性专家将共同完成以下三个必填字段：**策略名称**、**要监督的用户或组**以及**审阅者**。</span><span class="sxs-lookup"><span data-stu-id="178f6-238">On the policy template wizard, the Contoso IT administrators and compliance specialists work together to complete the three required fields: **Policy name**, **Users or groups to supervise**, and **Reviewers**.</span></span>
3. <span data-ttu-id="178f6-239">由于策略向导已经为策略建议了名称，IT 管理员和合规性专家决定保留建议的名称，并将重点放在其余字段上。</span><span class="sxs-lookup"><span data-stu-id="178f6-239">Since the policy wizard has already suggested a name for the policy, the IT administrators and compliance specialists decide to keep the suggested name and focus on the remaining fields.</span></span> <span data-ttu-id="178f6-240">他们选择 "要管理的**用户或组**" 字段的 "*所有用户*" 组，然后选择应调查和修正**审阅者**字段策略通知的合规性专家。</span><span class="sxs-lookup"><span data-stu-id="178f6-240">They select the *All users* group for the **Users or groups to supervise** field and select the compliance specialists that should investigate and remediate policy alerts for the **Reviewers** field.</span></span> <span data-ttu-id="178f6-241">配置策略和开始收集警报信息的最后一步是选择 "**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="178f6-241">The last step to configure the policy and start gathering alert information is to select **Create policy**.</span></span>

    ![通信合规性冒犯性语言向导](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a><span data-ttu-id="178f6-243">步骤4：调查并修正警报</span><span class="sxs-lookup"><span data-stu-id="178f6-243">Step 4: Investigate and remediate alerts</span></span>

<span data-ttu-id="178f6-244">现在已配置用于监视攻击性语言的通信合规性策略，Contoso 合规性专家的下一步是调查并修正该策略生成的任何警报。</span><span class="sxs-lookup"><span data-stu-id="178f6-244">Now that the communication compliance policy to monitor for offensive language is configured, the next step for the Contoso compliance specialists will be to investigate and remediate any alerts generated by the policy.</span></span> <span data-ttu-id="178f6-245">该策略最长需要24小时才能完全处理所有通信源通道中的通信，并且警报**仪表板**中显示警报。</span><span class="sxs-lookup"><span data-stu-id="178f6-245">It will take up to 24 hours for the policy to fully process communications in all the communication source channels and for alerts to show up in the **Alert dashboard**.</span></span>

<span data-ttu-id="178f6-246">生成警报后，Contoso 合规性专家将遵循[工作流说明](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate)来调查和修正攻击性语言问题。</span><span class="sxs-lookup"><span data-stu-id="178f6-246">After alerts are generated, Contoso compliance specialists will follow the [workflow instructions](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) to investigate and remediate offensive language issues.</span></span>