---
title: 通信合规性入门
description: 设置通信合规性策略以配置员工通信以供审阅。
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
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 928401f0c4b0fe479d993eba958ca1e109d4c05f
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43708391"
---
# <a name="get-started-with-communication-compliance"></a><span data-ttu-id="0caa9-103">通信合规性入门</span><span class="sxs-lookup"><span data-stu-id="0caa9-103">Get started with communication compliance</span></span>

>[!IMPORTANT]
><span data-ttu-id="0caa9-104">本主题适用于在 Microsoft 365 订阅中配置通信合规性。</span><span class="sxs-lookup"><span data-stu-id="0caa9-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="0caa9-105">如果要为 Microsoft 365 订阅配置监督策略，请参阅[配置针对 microsoft 365 的监督](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-105">If you want to configure Supervision policies for a Microsoft 365 subscription, see [Configure supervision for Microsoft 365](supervision-policies.md).</span></span>

<span data-ttu-id="0caa9-106">使用通信合规性策略，以捕获内部或外部审阅者进行检查的员工通信。</span><span class="sxs-lookup"><span data-stu-id="0caa9-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="0caa9-107">有关通信合规性策略如何帮助您监视组织中的通信的详细信息，请参阅[Microsoft 365 中的通信合规性策略](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span> <span data-ttu-id="0caa9-108">如果您想要查看 Contoso 如何快速将通信合规性策略配置为在 Microsoft 团队和 Exchange Online 通信中监视攻击性语言，请查看此[案例研究](communication-compliance-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-108">If you'd like to review how Contoso quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams and Exchange Online communications, check out this [case study](communication-compliance-case-study.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0caa9-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="0caa9-109">Before you begin</span></span>

<span data-ttu-id="0caa9-110">在开始进行通信合规性之前，应确认你的[Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。</span><span class="sxs-lookup"><span data-stu-id="0caa9-110">Before you get started with communication compliance, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="0caa9-111">若要访问和使用通信合规性，您的组织必须具有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="0caa9-111">To access and use communication compliance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="0caa9-112">Microsoft 365 E5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="0caa9-112">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="0caa9-113">Microsoft 365 E3 订阅 + Microsoft 365 E5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="0caa9-113">Microsoft 365 E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="0caa9-114">Microsoft 365 E3 订阅 + Microsoft 365 E5 内幕人士风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="0caa9-114">Microsoft 365 E3 subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="0caa9-115">Microsoft 365 A5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="0caa9-115">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="0caa9-116">Microsoft 365 A3 订阅 + Microsoft 365 A5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="0caa9-116">Microsoft 365 A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="0caa9-117">Microsoft 365 A3 订阅 + Microsoft 365 A5 内幕成员风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="0caa9-117">Microsoft 365 A3 subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="0caa9-118">Microsoft 365 G5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="0caa9-118">Microsoft 365 G5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="0caa9-119">Microsoft 365 G5 订阅 + Microsoft 365 G5 合规性附加</span><span class="sxs-lookup"><span data-stu-id="0caa9-119">Microsoft 365 G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="0caa9-120">Microsoft 365 G5 订阅 + Microsoft 365 G5 内幕版风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="0caa9-120">Microsoft 365 G5 subscription + the Microsoft 365 G5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="0caa9-121">Office 365 企业版 E5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="0caa9-121">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="0caa9-122">Office 365 企业版 E3 订阅 + Office 365 高级合规性外接程序（不再适用于新订阅，请参阅注意）</span><span class="sxs-lookup"><span data-stu-id="0caa9-122">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="0caa9-123">必须为通信合规性策略中包含的用户分配上述许可证之一。</span><span class="sxs-lookup"><span data-stu-id="0caa9-123">Users included in communication compliance policies must must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="0caa9-124">Office 365 高级合规性不再作为独立订阅销售。</span><span class="sxs-lookup"><span data-stu-id="0caa9-124">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="0caa9-125">当当前订阅过期时，客户应转换为上述订阅之一，其中包含相同或更多的合规性功能。</span><span class="sxs-lookup"><span data-stu-id="0caa9-125">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="0caa9-126">如果您没有现成的 Office 365 企业版 E5 计划，并且想要尝试使用内幕风险管理，则可以[将 Microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)到现有订阅或注册 Office 365 企业版 e5 的[试用版](https://www.microsoft.com/microsoft-365/enterprise)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-126">If you don't have an existing Office 365 Enterprise E5 plan and want to try insider risk management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Office 365 Enterprise E5.</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="0caa9-127">步骤1（必需）：启用通信合规性的权限</span><span class="sxs-lookup"><span data-stu-id="0caa9-127">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="0caa9-128">默认情况下，全局管理员不具有对通信合规性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0caa9-128">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="0caa9-129">在此步骤中分配的角色在所有通信合规性功能都可访问之前是必需的。</span><span class="sxs-lookup"><span data-stu-id="0caa9-129">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span>

<span data-ttu-id="0caa9-130">若要在 Microsoft 365 合规性中心中将**通信合规性**用作菜单选项，您必须分配有**监管审核管理员**角色。</span><span class="sxs-lookup"><span data-stu-id="0caa9-130">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="0caa9-131">您必须为具有**监管审核管理员**、**案例管理**、**合规性管理员**和**审阅**角色的审阅者创建新的角色组，以使用策略匹配来调查和修正邮件。</span><span class="sxs-lookup"><span data-stu-id="0caa9-131">You must create a new role group for reviewers with the **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="0caa9-132">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="0caa9-132">Create a new role group</span></span>

1. <span data-ttu-id="0caa9-133">在 Microsoft [https://protection.office.com/permissions](https://protection.office.com/permissions) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="0caa9-133">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="0caa9-134">在 "安全&amp;合规性中心" 中，转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-134">In the Security &amp; Compliance Center, go to **Permissions**.</span></span> <span data-ttu-id="0caa9-135">选择用于查看和管理 Office 365 中的角色的链接。</span><span class="sxs-lookup"><span data-stu-id="0caa9-135">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="0caa9-136">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0caa9-136">Select **Create**.</span></span>

4. <span data-ttu-id="0caa9-137">在 "**名称**" 字段中，为新角色组指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="0caa9-137">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="0caa9-138">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0caa9-138">Select **Next**.</span></span>

5. <span data-ttu-id="0caa9-139">选择 "**选择角色**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-139">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="0caa9-140">选中 "**监察审核管理员**、**案例管理**、**合规性管理员**和**审阅**" 复选框，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-140">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="0caa9-141">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0caa9-141">Select **Next**.</span></span>

    ![满足通信合规性角色组](../media/communication-compliance-role-groups-1.png)

6. <span data-ttu-id="0caa9-143">选择 "**选择成员**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-143">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="0caa9-144">选中您想要创建策略的所有用户和组的复选框，并使用策略匹配来管理邮件，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-144">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="0caa9-145">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0caa9-145">Select **Next**.</span></span>

7. <span data-ttu-id="0caa9-146">选择 "**创建角色组**" 以完成。</span><span class="sxs-lookup"><span data-stu-id="0caa9-146">Select **Create role group** to finish.</span></span>

<span data-ttu-id="0caa9-147">有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-147">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-audit-log"></a><span data-ttu-id="0caa9-148">步骤2（必需）：启用审核日志</span><span class="sxs-lookup"><span data-stu-id="0caa9-148">Step 2 (required): Enable the audit log</span></span>

<span data-ttu-id="0caa9-149">通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="0caa9-149">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="0caa9-150">审核日志是与定义的组织策略关联的所有活动的摘要，也是任何与通信合规性策略更改相关的活动。</span><span class="sxs-lookup"><span data-stu-id="0caa9-150">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="0caa9-151">有关启用审核的分步说明，请参阅[打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-151">For step-by-step instructions to turn on auditing, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="0caa9-152">启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="0caa9-152">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="0caa9-153">您只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="0caa9-153">You only have to do this action once.</span></span> <span data-ttu-id="0caa9-154">有关使用审核日志的详细信息，请参阅[Search the audit log](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-154">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="0caa9-155">步骤3（可选）：设置组以实现通信合规性</span><span class="sxs-lookup"><span data-stu-id="0caa9-155">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="0caa9-156">创建通信合规性策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。</span><span class="sxs-lookup"><span data-stu-id="0caa9-156">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="0caa9-157">在策略中，您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="0caa9-157">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="0caa9-158">为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="0caa9-158">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="0caa9-159">如果使用的是组，可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="0caa9-159">If you're using groups, you may need several.</span></span> <span data-ttu-id="0caa9-160">例如，如果要监视两个不同的人员组之间的通信，或者要指定不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="0caa9-160">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="0caa9-161">使用下图可帮助您为组织中的通信合规性策略配置组：</span><span class="sxs-lookup"><span data-stu-id="0caa9-161">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="0caa9-162">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="0caa9-162">**Policy Member**</span></span> | <span data-ttu-id="0caa9-163">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="0caa9-163">**Supported Groups**</span></span> | <span data-ttu-id="0caa9-164">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="0caa9-164">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="0caa9-165">受监督用户</span><span class="sxs-lookup"><span data-stu-id="0caa9-165">Supervised users</span></span> <br> <span data-ttu-id="0caa9-166">非监督用户</span><span class="sxs-lookup"><span data-stu-id="0caa9-166">Non-supervised users</span></span> | <span data-ttu-id="0caa9-167">通讯组</span><span class="sxs-lookup"><span data-stu-id="0caa9-167">Distribution groups</span></span> <br> <span data-ttu-id="0caa9-168">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="0caa9-168">Microsoft 365 Groups</span></span> | <span data-ttu-id="0caa9-169">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="0caa9-169">Dynamic distribution groups</span></span> |
| <span data-ttu-id="0caa9-170">Reviewers</span><span class="sxs-lookup"><span data-stu-id="0caa9-170">Reviewers</span></span> | <span data-ttu-id="0caa9-171">无</span><span class="sxs-lookup"><span data-stu-id="0caa9-171">None</span></span> | <span data-ttu-id="0caa9-172">通讯组</span><span class="sxs-lookup"><span data-stu-id="0caa9-172">Distribution groups</span></span> <br> <span data-ttu-id="0caa9-173">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="0caa9-173">Dynamic distribution groups</span></span> <br> <span data-ttu-id="0caa9-174">启用邮件功能的安全组</span><span class="sxs-lookup"><span data-stu-id="0caa9-174">Mail-enabled security groups</span></span> |
  
<span data-ttu-id="0caa9-175">当您为受监督的用户选择 Microsoft 365 组时，该策略将监视共享邮箱的内容以及与该组关联的 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="0caa9-175">When you select a Microsoft 365 group for supervised users, the policy monitors the content of the shared mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="0caa9-176">当您选择通讯组列表时，该策略将监视单个用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="0caa9-176">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="0caa9-177">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0caa9-177">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="0caa9-178">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="0caa9-178">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="0caa9-179">Microsoft 365 组概述</span><span class="sxs-lookup"><span data-stu-id="0caa9-179">Overview of Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-required-create-a-communication-compliance-policy"></a><span data-ttu-id="0caa9-180">步骤4（必需）：创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="0caa9-180">Step 4 (required): Create a communication compliance policy</span></span>
  
>[!Important]
><span data-ttu-id="0caa9-181">不支持使用 PowerShell 创建和管理通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="0caa9-181">Using PowerShell to create and manage communication compliance policies is not supported.</span></span> <span data-ttu-id="0caa9-182">若要创建和管理这些策略，必须使用[Microsoft 365 通信合规性解决方案](https://compliance.microsoft.com/supervisoryreview)中的策略管理控件。</span><span class="sxs-lookup"><span data-stu-id="0caa9-182">To create and manage these policies, you must use the policy management controls in the [Microsoft 365 communication compliance solution](https://compliance.microsoft.com/supervisoryreview).</span></span>

1. <span data-ttu-id="0caa9-183">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="0caa9-183">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="0caa9-184">在 Microsoft 365 合规性中心中，选择 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-184">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="0caa9-185">选择 "**策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0caa9-185">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="0caa9-186">选择 "**创建策略**"，从模板创建和配置新策略，或创建和配置自定义策略。</span><span class="sxs-lookup"><span data-stu-id="0caa9-186">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="0caa9-187">如果选择策略模板来创建策略，您将：</span><span class="sxs-lookup"><span data-stu-id="0caa9-187">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="0caa9-188">确认或更新策略名称。</span><span class="sxs-lookup"><span data-stu-id="0caa9-188">Confirm or update the policy name.</span></span> <span data-ttu-id="0caa9-189">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="0caa9-189">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="0caa9-190">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="0caa9-190">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="0caa9-191">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="0caa9-191">Choose the reviewers for the policy.</span></span> <span data-ttu-id="0caa9-192">审阅者是单个用户，并且所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="0caa9-192">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="0caa9-193">在这里添加的审阅者是在调查和修正工作流中上报通知时可供选择的审阅者。</span><span class="sxs-lookup"><span data-stu-id="0caa9-193">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span>
    - <span data-ttu-id="0caa9-194">选择 "受限条件" 字段，通常是要应用于策略的敏感信息类型或关键字词典。</span><span class="sxs-lookup"><span data-stu-id="0caa9-194">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="0caa9-195">如果您选择使用策略向导创建自定义策略，您将：</span><span class="sxs-lookup"><span data-stu-id="0caa9-195">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="0caa9-196">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="0caa9-196">Give the policy a name and description.</span></span> <span data-ttu-id="0caa9-197">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="0caa9-197">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="0caa9-198">选择要监督的用户或组，包括组织中的所有用户、特定用户和组，或者要排除的其他用户和组。</span><span class="sxs-lookup"><span data-stu-id="0caa9-198">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span>
    - <span data-ttu-id="0caa9-199">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="0caa9-199">Choose the reviewers for the policy.</span></span> <span data-ttu-id="0caa9-200">审阅者是单个用户，并且所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="0caa9-200">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="0caa9-201">选择要扫描的通信通道，包括 Exchange、Microsoft 团队或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="0caa9-201">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="0caa9-202">如果您在 Microsoft 365 中配置了连接器，您还将选择扫描第三方源。</span><span class="sxs-lookup"><span data-stu-id="0caa9-202">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="0caa9-203">选择要监视的通信方向，包括入站、出站或内部通信。</span><span class="sxs-lookup"><span data-stu-id="0caa9-203">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="0caa9-204">定义通信合规性策略[条件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-204">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="0caa9-205">您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0caa9-205">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="0caa9-206">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="0caa9-206">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="0caa9-207">在此步骤中，您可以选择默认和自定义的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="0caa9-207">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="0caa9-208">从 "通信合规性策略向导" 中的现有自定义敏感信息类型或自定义关键字词典中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0caa9-208">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="0caa9-209">如果需要，可以在运行向导之前创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="0caa9-209">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="0caa9-210">您还可以在 "通信合规性策略" 向导中创建新的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="0caa9-210">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="0caa9-211">选择是否要启用分类器。</span><span class="sxs-lookup"><span data-stu-id="0caa9-211">Choose if you'd like to enable classifiers.</span></span> <span data-ttu-id="0caa9-212">分类器可检测在电子邮件正文或其他类型的文本中发送或接收的不正确的语言。</span><span class="sxs-lookup"><span data-stu-id="0caa9-212">Classifiers can detect inappropriate language sent or received in the body of email messages or other types of text.</span></span>

    >[!CAUTION]
    ><span data-ttu-id="0caa9-213">我们正在弃用采用**冒犯性语言**的内置分类器，因为它生成了大量误报。</span><span class="sxs-lookup"><span data-stu-id="0caa9-213">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="0caa9-214">请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。</span><span class="sxs-lookup"><span data-stu-id="0caa9-214">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="0caa9-215">我们建议改为使用**威胁**、**猥亵**和**骚扰**内置分类符。</span><span class="sxs-lookup"><span data-stu-id="0caa9-215">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>
    
    - <span data-ttu-id="0caa9-216">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="0caa9-216">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="0caa9-217">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="0caa9-217">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="0caa9-218">使用 "自定义策略" 向导时，选择 "使用模板或**提交**时**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-218">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="0caa9-219">**您的策略已创建**页面将显示有关何时激活策略以及将捕获哪些通信的指南。</span><span class="sxs-lookup"><span data-stu-id="0caa9-219">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-5-optional-create-employee-notice-templates"></a><span data-ttu-id="0caa9-220">步骤5（可选）：创建员工通知模板</span><span class="sxs-lookup"><span data-stu-id="0caa9-220">Step 5 (optional): Create employee notice templates</span></span>

<span data-ttu-id="0caa9-221">如果希望通过向关联的员工发送提醒通知来选择对策略警报做出响应，您需要在您的组织中至少创建一个通知模板。</span><span class="sxs-lookup"><span data-stu-id="0caa9-221">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="0caa9-222">在将 "通知模板" 字段作为警报修正过程的一部分发送并为每个通信合规性策略创建自定义的通知模板之前，这些字段都是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="0caa9-222">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="0caa9-223">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="0caa9-223">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="0caa9-224">在 Microsoft 365 合规性中心中，转到 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-224">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="0caa9-225">选择 "**通知模板**" 选项卡，然后选择 "**创建通知模板**"。</span><span class="sxs-lookup"><span data-stu-id="0caa9-225">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="0caa9-226">在 "**修改通知模板**" 页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="0caa9-226">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="0caa9-227">通知模板名称（必需）</span><span class="sxs-lookup"><span data-stu-id="0caa9-227">Notice template name (required)</span></span>
    - <span data-ttu-id="0caa9-228">发件人（必需）</span><span class="sxs-lookup"><span data-stu-id="0caa9-228">Send from (required)</span></span>
    - <span data-ttu-id="0caa9-229">"抄送" 和 "密件抄送" （可选）</span><span class="sxs-lookup"><span data-stu-id="0caa9-229">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="0caa9-230">主题（必需）</span><span class="sxs-lookup"><span data-stu-id="0caa9-230">Subject (required)</span></span>
    - <span data-ttu-id="0caa9-231">邮件正文（必需）</span><span class="sxs-lookup"><span data-stu-id="0caa9-231">Message body (required)</span></span>

5. <span data-ttu-id="0caa9-232">选择 "**保存**" 以创建并保存 "通知" 模板。</span><span class="sxs-lookup"><span data-stu-id="0caa9-232">Select **Save** to create and save the notice template.</span></span>

## <a name="step-6-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="0caa9-233">步骤6（可选）：测试通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="0caa9-233">Step 6 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="0caa9-234">创建通信合规性策略后，最好对其进行测试，以确保策略正确地强制实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="0caa9-234">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="0caa9-235">如果通信合规性策略包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="0caa9-235">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="0caa9-236">请确保为策略激活时间，以便捕获要测试的通信。</span><span class="sxs-lookup"><span data-stu-id="0caa9-236">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="0caa9-237">按照以下步骤测试您的通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="0caa9-237">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="0caa9-238">打开电子邮件客户端或 Microsoft 团队，同时以您要测试的策略中定义的监督用户的身份登录。</span><span class="sxs-lookup"><span data-stu-id="0caa9-238">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="0caa9-239">发送符合通信合规性策略中定义的条件的电子邮件或 Microsoft 团队聊天。</span><span class="sxs-lookup"><span data-stu-id="0caa9-239">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="0caa9-240">此测试可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="0caa9-240">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0caa9-241">所有源通道中的通信可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="0caa9-241">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="0caa9-242">以通信合规性策略中指定的审阅者的资格登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0caa9-242">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="0caa9-243">导航到 "**通信合规性** > **警报**" 以查看策略的警报。</span><span class="sxs-lookup"><span data-stu-id="0caa9-243">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="0caa9-244">使用修正控件修正警报，并验证是否正确解决了警报。</span><span class="sxs-lookup"><span data-stu-id="0caa9-244">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>
