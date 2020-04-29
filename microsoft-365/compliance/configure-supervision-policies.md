---
title: 配置监督策略
description: 为 Office 365 配置通信监督
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
titleSuffix: Office 365 Compliance
ms.openlocfilehash: c13e481cfc55e56d8cc1c0a772f2f661992f5353
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921454"
---
# <a name="configure-supervision-policies-in-office-365"></a><span data-ttu-id="7c5a9-103">在 Office 365 中配置监督策略</span><span class="sxs-lookup"><span data-stu-id="7c5a9-103">Configure supervision policies in Office 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="7c5a9-104">在 Microsoft 365 年 2 2020 月的兼容性符合通信合规性的情况下，将停用 Office 365 中的监督。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-104">Following the release of communication compliance in Microsoft 365 Compliance in February 2020, Supervision in Office 365 is being retired.</span></span> <span data-ttu-id="7c5a9-105">监督策略将不再可用于创建，并且最终会在一段较长的只读访问期后删除策略。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-105">Supervision policies will no longer be available for creation, and policies will eventually be removed, after an extended period of read only access.</span></span>
>
><span data-ttu-id="7c5a9-106">如果您使用监督，请注意：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-106">If you use Supervision, be aware that:</span></span>
>
>- <span data-ttu-id="7c5a9-107">从2020年6月15日起，租户将不能创建新的监察策略。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-107">Beginning June 15th, 2020, tenants will not have the ability to create new Supervision policies.</span></span>
>- <span data-ttu-id="7c5a9-108">2020年8月31日开始，现有策略将停止捕获新邮件。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-108">Beginning August 31st, 2020, existing policies will stop capturing new messages.</span></span>
>- <span data-ttu-id="7c5a9-109">在10月26日开始，2020，将删除现有策略。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-109">Beginning October 26th, 2020, existing policies will be deleted.</span></span>
>
><span data-ttu-id="7c5a9-110">我们积极鼓励当前正在探索或使用 Office 365 中的监督的客户使用新的[通信合规性](communication-compliance.md)解决方案，以通过一组更丰富的智能功能来满足您的通信监视或管理法规要求。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-110">We actively encourage customers who are currently exploring or using Supervision in Office 365 to use the new [communication compliance](communication-compliance.md) solution to address your communications monitoring or regulatory requirements with a much richer set of intelligent capabilities.</span></span>

<span data-ttu-id="7c5a9-111">使用监督策略来捕获由内部或外部审阅者进行检查的员工通信。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-111">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="7c5a9-112">有关监察策略如何帮助您监视组织中的通信的详细信息，请参阅[Office 365 中的监察策略](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-112">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

>[!NOTE]
><span data-ttu-id="7c5a9-113">监督策略监视的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或者包含在 Office 365 企业版 E5 订阅中，或者包含在 Microsoft 365 E5 订阅中。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-113">Users monitored by supervision policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription, or be included in a Microsoft 365 E5 subscription.</span></span>
><span data-ttu-id="7c5a9-114">如果你没有现有的企业版 E5 计划，并且想要尝试监督，则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-114">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="7c5a9-115">按照以下步骤在组织中设置和使用监督：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-115">Follow these steps to set up and use supervision in your organization:</span></span>
  
- <span data-ttu-id="7c5a9-116">**步骤1（可选）**：[为监督设置组](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="7c5a9-116">**Step 1 (optional)**: [Set up groups for supervision](#step-1-set-up-groups-for-supervision-optional)</span></span>

    <span data-ttu-id="7c5a9-117">在开始使用监察策略之前，请确定哪些用户需要查看通信以及谁执行了检查。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-117">Before you start using supervision policies, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="7c5a9-118">如果您只想开始几个用户来了解监督工作的工作方式，则可以跳过 "立即" 设置组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-118">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="7c5a9-119">**步骤2（必需）**：[让监督在你的组织中可用](#step-2-make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="7c5a9-119">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="7c5a9-120">将自己添加到监管审核角色组，以便您可以设置策略。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-120">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="7c5a9-121">分配此角色的任何人都可以访问安全 & 合规性中心内的**监督**页面。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-121">Anyone who has this role assigned can access the **Supervision** page in the Security & Compliance Center.</span></span> <span data-ttu-id="7c5a9-122">如果 reviewable 电子邮件托管在 Exchange Online 中，则每个审阅者都必须具有[对 Exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-122">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7c5a9-123">**步骤3（可选）**：[创建自定义敏感信息类型和自定义关键字词典](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="7c5a9-123">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="7c5a9-124">如果您需要针对监督策略的自定义敏感信息类型或自定义关键字词典，则需要在启动监督向导之前创建它。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-124">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="7c5a9-125">**步骤4（必需）**：[设置监督策略](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="7c5a9-125">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="7c5a9-126">在安全 & 合规性中心创建监督策略。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-126">You create supervision policies in the Security & Compliance Center.</span></span> <span data-ttu-id="7c5a9-127">这些策略定义哪些通信将在组织中进行审核，并指定执行审阅的用户。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-127">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="7c5a9-128">通信包括电子邮件和 Microsoft 团队通信，以及第三方平台通信（如 Facebook、Twitter 等）。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-128">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.).</span></span> <span data-ttu-id="7c5a9-129">在 Microsoft 365 订阅的通信监督中不支持在组织中创建的监督策略。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-129">Supervision policies created in organizations are not supported in communication supervision in Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="7c5a9-130">**步骤5（可选）**：[测试通信监督策略](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="7c5a9-130">**Step 5 (optional)**: [Test your communication supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="7c5a9-131">测试您的监督策略以确保其按预期工作。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-131">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="7c5a9-132">一定要确保符合性策略满足您的标准。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-132">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="7c5a9-133">步骤1：设置组以进行监控（可选）</span><span class="sxs-lookup"><span data-stu-id="7c5a9-133">Step 1: Set up groups for supervision (optional)</span></span>

 <span data-ttu-id="7c5a9-134">在创建监督策略时，您需要定义哪些用户扫描了其通信，以及谁执行了审阅。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-134">When you create a supervision policy, you define who has their communications scanned and who performs reviews.</span></span> <span data-ttu-id="7c5a9-135">在策略中，您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-135">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="7c5a9-136">为简化您的设置，您可以为已扫描其通信的用户创建组，并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-136">To simplify your setup, you can create groups for people who have their communication scanned and groups for people who review those communications.</span></span> <span data-ttu-id="7c5a9-137">如果使用的是组，可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-137">If you're using groups, you may need several.</span></span> <span data-ttu-id="7c5a9-138">例如，您想要监视两个不同的人员组之间的通信，或者如果您想要指定一个不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-138">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="7c5a9-139">使用下图可帮助您为组织中的通信监督策略配置组：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-139">Use the following chart to help you configure groups in your organization for communication supervision policies:</span></span>

| <span data-ttu-id="7c5a9-140">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="7c5a9-140">**Policy Member**</span></span> | <span data-ttu-id="7c5a9-141">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="7c5a9-141">**Supported Groups**</span></span> | <span data-ttu-id="7c5a9-142">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="7c5a9-142">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="7c5a9-143">受监督用户</span><span class="sxs-lookup"><span data-stu-id="7c5a9-143">Supervised users</span></span> <br> <span data-ttu-id="7c5a9-144">非监督用户</span><span class="sxs-lookup"><span data-stu-id="7c5a9-144">Non-supervised users</span></span> | <span data-ttu-id="7c5a9-145">通讯组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-145">Distribution groups</span></span> <br> <span data-ttu-id="7c5a9-146">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-146">Microsoft 365 groups</span></span> | <span data-ttu-id="7c5a9-147">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-147">Dynamic distribution groups</span></span> |
| <span data-ttu-id="7c5a9-148">Reviewers</span><span class="sxs-lookup"><span data-stu-id="7c5a9-148">Reviewers</span></span> | <span data-ttu-id="7c5a9-149">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-149">Mail-enabled security groups</span></span>  | <span data-ttu-id="7c5a9-150">通讯组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-150">Distribution groups</span></span> <br> <span data-ttu-id="7c5a9-151">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-151">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="7c5a9-152">当您为受监督的用户选择 Microsoft 365 组时，该策略将监视共享邮箱的内容以及与该组关联的 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-152">When you select a Microsoft 365 group for supervised users, the policy monitors the content of the shared mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="7c5a9-153">当您选择通讯组列表时，该策略将监视单个用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-153">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="7c5a9-154">若要在大型企业组织中管理受监督的用户，您可能需要监视跨大型组的所有用户。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-154">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="7c5a9-155">您可以使用 PowerShell 为分配的组配置全局监督策略的通讯组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-155">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="7c5a9-156">这使您可以使用单个策略监视数千个用户，并在新员工加入您的组织时保持监督策略的更新。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-156">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="7c5a9-157">为具有以下属性的全局监督策略创建专用[通讯组](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)：确保此通讯组不用于其他目的或其他 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-157">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="7c5a9-158">**MemberDepartRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-158">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="7c5a9-159">确保用户无法将自己从通讯组中删除。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-159">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="7c5a9-160">**MemberJoinRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-160">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="7c5a9-161">确保用户无法将自己添加到通讯组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-161">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="7c5a9-162">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-162">**ModerationEnabled = True**.</span></span> <span data-ttu-id="7c5a9-163">确保发送到此组的所有邮件均可供审批，并且该组未用于在监督策略配置外部进行通信。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-163">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. <span data-ttu-id="7c5a9-164">选择一个未使用的[Exchange 自定义属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)来跟踪添加到组织中的监督策略的用户。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-164">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="7c5a9-165">定期对计划运行以下 PowerShell 脚本，以将用户添加到监督策略：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-165">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

<span data-ttu-id="7c5a9-166">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-166">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="7c5a9-167">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-167">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="7c5a9-168">管理启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-168">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="7c5a9-169">Microsoft 365 组概述</span><span class="sxs-lookup"><span data-stu-id="7c5a9-169">Overview of Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="7c5a9-170">步骤2：让监督在你的组织中可用（必需）</span><span class="sxs-lookup"><span data-stu-id="7c5a9-170">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="7c5a9-171">若要在安全 & 合规性中心中将**监察**功能作为菜单选项提供，您必须分配有监管审核管理员角色。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-171">To make **Supervision** available as a menu option in Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="7c5a9-172">若要执行此操作，您可以将自己添加为监管审核角色组的成员，也可以创建角色组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-172">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="7c5a9-173">将成员添加到监管审核角色组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-173">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="7c5a9-174">在组织[https://protection.office.com](https://protection.office.com)中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-174">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7c5a9-175">在安全 & 合规性中心中，转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-175">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="7c5a9-176">选择 "**监管审核**" 角色组，然后单击 "编辑" 图标。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-176">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="7c5a9-177">在 "**成员**" 部分，添加要为组织管理通信监督的人员。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-177">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="7c5a9-178">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="7c5a9-178">Create a new role group</span></span>

1. <span data-ttu-id="7c5a9-179">在组织[https://protection.office.com/permissions](https://protection.office.com/permissions)中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-179">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7c5a9-180">在安全 & 合规性中心中，转到 "**权限**"，然后**+** 单击 "添加" （）。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-180">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="7c5a9-181">在 "**角色**" 部分中，单击**+**"添加" （），然后向下滚动到 "**监察审核管理员**"。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-181">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="7c5a9-182">将此角色添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-182">Add this role to the role group.</span></span>

4. <span data-ttu-id="7c5a9-183">在 "**成员**" 部分，添加要为组织管理通信监督的人员。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-183">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

<span data-ttu-id="7c5a9-184">有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-184">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="7c5a9-185">为审阅者启用远程 PowerShell 访问（如果 Exchange Online 上托管电子邮件）</span><span class="sxs-lookup"><span data-stu-id="7c5a9-185">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="7c5a9-186">按照[启用或禁用对 Exchange Online PowerShell 的访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导进行操作。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-186">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="7c5a9-187">步骤3：创建自定义敏感信息类型和自定义关键字词典（可选）</span><span class="sxs-lookup"><span data-stu-id="7c5a9-187">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="7c5a9-188">若要从监督策略向导中的现有自定义敏感信息类型或自定义关键字词典中进行选择，需要先创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-188">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="7c5a9-189">创建自定义关键字词典/词典（可选）</span><span class="sxs-lookup"><span data-stu-id="7c5a9-189">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="7c5a9-190">使用文本编辑器（如记事本）创建一个文件，其中包含要在监督策略中监视的关键字术语。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-190">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="7c5a9-191">确保每个术语都位于单独的行中，并将文件保存为**Unicode/UTF-16 （小 Endian）** 格式。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-191">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="7c5a9-192">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="7c5a9-192">Create custom sensitive information types</span></span>

1. <span data-ttu-id="7c5a9-193">创建新的敏感信息类型，并将您的自定义词典添加到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-193">Create a new sensitive information type and add your custom dictionary in the Security & Compliance Center.</span></span> <span data-ttu-id="7c5a9-194">导航到 "**分类** \> " "**敏感信息**类型"，然后按照新的 "**敏感信息类型" 向导**中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-194">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="7c5a9-195">你将在此处执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-195">Here you will:</span></span>

    - <span data-ttu-id="7c5a9-196">定义敏感信息类型的名称和说明</span><span class="sxs-lookup"><span data-stu-id="7c5a9-196">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="7c5a9-197">定义邻近度、置信度和主要模式元素</span><span class="sxs-lookup"><span data-stu-id="7c5a9-197">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="7c5a9-198">将自定义词典作为匹配元素的要求导入</span><span class="sxs-lookup"><span data-stu-id="7c5a9-198">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="7c5a9-199">查看您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="7c5a9-199">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="7c5a9-200">有关更多详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)和[创建关键字词典](create-a-keyword-dictionary.md)</span><span class="sxs-lookup"><span data-stu-id="7c5a9-200">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="7c5a9-201">创建自定义词典/词典之后，可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 查看配置的关键字，也可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet 添加和删除术语。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-201">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="7c5a9-202">步骤4：设置监督策略（必需）</span><span class="sxs-lookup"><span data-stu-id="7c5a9-202">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="7c5a9-203">在组织[https://protection.office.com](https://protection.office.com)中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-203">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7c5a9-204">在安全 & 合规性中心中，选择 "**监督**"。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-204">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="7c5a9-205">选择 "**创建**"，然后按照向导设置策略配置。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-205">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="7c5a9-206">使用该向导，您将：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-206">Using the wizard, you will:</span></span>

    - <span data-ttu-id="7c5a9-207">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-207">Give the policy a name and description.</span></span>
    - <span data-ttu-id="7c5a9-208">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-208">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="7c5a9-209">定义监督策略[条件](supervision-policies.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-209">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="7c5a9-210">您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-210">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="7c5a9-211">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-211">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="7c5a9-212">你可以在此处选择默认和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-212">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="7c5a9-213">选择是否要启用冒犯性语言模型。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-213">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="7c5a9-214">这将检测在电子邮件正文中发送或接收的不正确的语言。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-214">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="7c5a9-215">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-215">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="7c5a9-216">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-216">Choose the reviewers for the policy.</span></span> <span data-ttu-id="7c5a9-217">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-217">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="7c5a9-218">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-218">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="7c5a9-219">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-219">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="7c5a9-220">步骤5：测试监督策略（可选）</span><span class="sxs-lookup"><span data-stu-id="7c5a9-220">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="7c5a9-221">创建通信监督策略后，最好进行测试以确保策略正确地实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-221">After you create a communication supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="7c5a9-222">如果监督策略中包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-222">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="7c5a9-223">按照以下步骤测试您的监督策略：</span><span class="sxs-lookup"><span data-stu-id="7c5a9-223">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="7c5a9-224">打开以您要测试的策略中定义的监督用户身份登录的电子邮件客户端或 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-224">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="7c5a9-225">发送符合您在监督策略中定义的条件的电子邮件或 Microsoft 团队聊天。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-225">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="7c5a9-226">它可以是关键字、附件大小、域等。确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-226">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7c5a9-227">已定义策略的电子邮件将在接近实时的情况中进行处理，并且可以在配置策略后立即进行测试。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-227">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="7c5a9-228">Microsoft 团队中的聊天可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-228">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="7c5a9-229">以通信监督策略中指定的审阅者的形式登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-229">Log into Microsoft 365 as a reviewer designated in the communication supervision policy.</span></span> <span data-ttu-id="7c5a9-230">导航到 "**监控** > "*您的自定义策略* > **打开**以查看该策略的报告。</span><span class="sxs-lookup"><span data-stu-id="7c5a9-230">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

