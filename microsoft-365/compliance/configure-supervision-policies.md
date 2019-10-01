---
title: 配置组织的监督策略
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
description: 设置监管审核策略以捕获员工通信以供审阅。
ms.openlocfilehash: dae8969598f5a71814c1b61db83341f30c0cb9d7
ms.sourcegitcommit: 8e5b799efd3ddd0eae9dd2835c3783103817fb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2019
ms.locfileid: "37317614"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="2d68d-103">配置组织的监督策略</span><span class="sxs-lookup"><span data-stu-id="2d68d-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="2d68d-104">使用监督策略来捕获由内部或外部审阅者进行检查的员工通信。</span><span class="sxs-lookup"><span data-stu-id="2d68d-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="2d68d-105">有关监察策略如何帮助您监视组织中的通信的详细信息，请参阅[Office 365 中的监察策略](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2d68d-105">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2d68d-106">监督策略监视的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或包含在 Office 365 企业版 E5 订阅中。</span><span class="sxs-lookup"><span data-stu-id="2d68d-106">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
> <span data-ttu-id="2d68d-107">如果你没有现有的企业版 E5 计划，并且想要尝试监督，则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="2d68d-107">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="2d68d-108">按照以下步骤在 Office 365 组织中设置和使用监督：</span><span class="sxs-lookup"><span data-stu-id="2d68d-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="2d68d-109">**步骤1（可选）**：[为监督设置组](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="2d68d-109">**Step 1 (optional)**: [Set up groups for Supervision](#step-1-set-up-groups-for-supervision-optional)</span></span> 

    <span data-ttu-id="2d68d-110">在开始使用监督之前，请确定哪些用户需要查看通信以及谁执行了检查。</span><span class="sxs-lookup"><span data-stu-id="2d68d-110">Before you start using supervision, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="2d68d-111">如果您只想开始几个用户来了解监督工作的工作方式，则可以跳过 "立即" 设置组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-111">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="2d68d-112">**步骤2（必需）**：[让监督在你的组织中可用](#step-2-make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="2d68d-112">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="2d68d-113">将自己添加到监管审核角色组，以便您可以设置策略。</span><span class="sxs-lookup"><span data-stu-id="2d68d-113">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="2d68d-114">分配此角色的任何人都可以访问合规中心中的**监督**页面。</span><span class="sxs-lookup"><span data-stu-id="2d68d-114">Anyone who has this role assigned can access the **Supervision** page in the Compliance Center.</span></span> <span data-ttu-id="2d68d-115">如果 reviewable 电子邮件托管在 Exchange Online 中，则每个审阅者都必须具有[对 Exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2d68d-115">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2d68d-116">**步骤3（可选）**：[创建自定义敏感信息类型和自定义关键字词典](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="2d68d-116">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="2d68d-117">如果您需要针对监督策略的自定义敏感信息类型或自定义关键字词典，则需要在启动监督向导之前创建它。</span><span class="sxs-lookup"><span data-stu-id="2d68d-117">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="2d68d-118">**步骤4（必需）**：[设置监督策略](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="2d68d-118">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="2d68d-119">在合规中心中创建监督策略。</span><span class="sxs-lookup"><span data-stu-id="2d68d-119">You create supervision policies in the Compliance Center.</span></span> <span data-ttu-id="2d68d-120">这些策略定义哪些通信将在组织中进行审核，并指定执行审阅的用户。</span><span class="sxs-lookup"><span data-stu-id="2d68d-120">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="2d68d-121">通信包括电子邮件和 Microsoft 团队通信，以及第三方平台通信（如 Facebook、Twitter 等）</span><span class="sxs-lookup"><span data-stu-id="2d68d-121">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="2d68d-122">**步骤5（可选）**：[测试监督策略](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="2d68d-122">**Step 5 (optional)**: [Test your supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="2d68d-123">测试您的监督策略以确保其按预期工作。</span><span class="sxs-lookup"><span data-stu-id="2d68d-123">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="2d68d-124">一定要确保符合性策略满足您的标准。</span><span class="sxs-lookup"><span data-stu-id="2d68d-124">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="2d68d-125">步骤1：设置组以进行监控（可选）</span><span class="sxs-lookup"><span data-stu-id="2d68d-125">Step 1: Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="2d68d-126">在创建监督策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。</span><span class="sxs-lookup"><span data-stu-id="2d68d-126">When you create a supervision policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="2d68d-127">在策略中，您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-127">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="2d68d-128">为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-128">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="2d68d-129">如果使用的是组，可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="2d68d-129">If you're using groups, you may need several.</span></span> <span data-ttu-id="2d68d-130">例如，您想要监视两个不同的人员组之间的通信，或者如果您想要指定一个不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-130">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="2d68d-131">使用以下图表可帮助您在组织中配置监督策略的组：</span><span class="sxs-lookup"><span data-stu-id="2d68d-131">Use the following chart to help you configure groups in your organization for supervision policies:</span></span>

| <span data-ttu-id="2d68d-132">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="2d68d-132">**Policy Member**</span></span> | <span data-ttu-id="2d68d-133">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="2d68d-133">**Supported Groups**</span></span> | <span data-ttu-id="2d68d-134">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="2d68d-134">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="2d68d-135">受监督用户</span><span class="sxs-lookup"><span data-stu-id="2d68d-135">Supervised users</span></span> <br> <span data-ttu-id="2d68d-136">非监督用户</span><span class="sxs-lookup"><span data-stu-id="2d68d-136">Non-supervised users</span></span> | <span data-ttu-id="2d68d-137">通讯组</span><span class="sxs-lookup"><span data-stu-id="2d68d-137">Distribution groups</span></span> <br> <span data-ttu-id="2d68d-138">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="2d68d-138">Office 365 groups</span></span> | <span data-ttu-id="2d68d-139">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="2d68d-139">Dynamic distribution groups</span></span> |
| <span data-ttu-id="2d68d-140">Reviewers</span><span class="sxs-lookup"><span data-stu-id="2d68d-140">Reviewers</span></span> | <span data-ttu-id="2d68d-141">启用邮件功能的安全组</span><span class="sxs-lookup"><span data-stu-id="2d68d-141">Mail-enabled security groups</span></span>  | <span data-ttu-id="2d68d-142">通讯组</span><span class="sxs-lookup"><span data-stu-id="2d68d-142">Distribution groups</span></span> <br> <span data-ttu-id="2d68d-143">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="2d68d-143">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="2d68d-144">当您为受监督的用户选择 Office 365 组时，该策略将监视共享 Office 365 邮箱的内容以及与该组关联的 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="2d68d-144">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="2d68d-145">当您选择通讯组列表时，该策略将监视单个用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="2d68d-145">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="2d68d-146">若要在大型企业组织中管理受监督的用户，您可能需要监视跨大型组的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2d68d-146">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="2d68d-147">您可以使用 PowerShell 为分配的组配置全局监督策略的通讯组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-147">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="2d68d-148">这使您可以使用单个策略监视数千个用户，并在新员工加入您的组织时保持监督策略的更新。</span><span class="sxs-lookup"><span data-stu-id="2d68d-148">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="2d68d-149">为具有以下属性的全局监督策略创建专用[通讯组](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)：确保此通讯组不用于其他目的或其他 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="2d68d-149">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="2d68d-150">**MemberDepartRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="2d68d-150">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="2d68d-151">确保用户无法将自己从通讯组中删除。</span><span class="sxs-lookup"><span data-stu-id="2d68d-151">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="2d68d-152">**MemberJoinRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="2d68d-152">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="2d68d-153">确保用户无法将自己添加到通讯组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-153">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="2d68d-154">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="2d68d-154">**ModerationEnabled = True**.</span></span> <span data-ttu-id="2d68d-155">确保发送到此组的所有邮件均可供审批，并且该组未用于在监督策略配置外部进行通信。</span><span class="sxs-lookup"><span data-stu-id="2d68d-155">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. <span data-ttu-id="2d68d-156">选择一个未使用的[Exchange 自定义属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)来跟踪添加到组织中的监督策略的用户。</span><span class="sxs-lookup"><span data-stu-id="2d68d-156">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="2d68d-157">定期对计划运行以下 PowerShell 脚本，以将用户添加到监督策略：</span><span class="sxs-lookup"><span data-stu-id="2d68d-157">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```
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

<span data-ttu-id="2d68d-158">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2d68d-158">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="2d68d-159">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="2d68d-159">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="2d68d-160">管理启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="2d68d-160">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="2d68d-161">Office 365 组概述</span><span class="sxs-lookup"><span data-stu-id="2d68d-161">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="2d68d-162">步骤2：让监督在你的组织中可用（必需）</span><span class="sxs-lookup"><span data-stu-id="2d68d-162">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="2d68d-163">若要使**监督**成为合规中心中的菜单选项，您必须分配有监管审核管理员角色。</span><span class="sxs-lookup"><span data-stu-id="2d68d-163">To make **Supervision** available as a menu option in the Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="2d68d-164">若要执行此操作，您可以将自己添加为监管审核角色组的成员，也可以创建角色组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-164">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="2d68d-165">将成员添加到监管审核角色组</span><span class="sxs-lookup"><span data-stu-id="2d68d-165">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="2d68d-166">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="2d68d-166">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2d68d-167">在 "合规性中心" 中，转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="2d68d-167">In the Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="2d68d-168">选择 "**监管审核**" 角色组，然后单击 "编辑" 图标。</span><span class="sxs-lookup"><span data-stu-id="2d68d-168">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="2d68d-169">在 "**成员**" 部分，添加要为组织管理监督的人员。</span><span class="sxs-lookup"><span data-stu-id="2d68d-169">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="2d68d-170">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="2d68d-170">Create a new role group</span></span>

1. <span data-ttu-id="2d68d-171">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="2d68d-171">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2d68d-172">在 "合规性中心" 中，转到 "**权限**"**+**，然后单击 "添加" （）。</span><span class="sxs-lookup"><span data-stu-id="2d68d-172">In the Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="2d68d-173">在 "**角色**" 部分中，单击**+**"添加" （），然后向下滚动到 "**监察审核管理员**"。</span><span class="sxs-lookup"><span data-stu-id="2d68d-173">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="2d68d-174">将此角色添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-174">Add this role to the role group.</span></span>

4. <span data-ttu-id="2d68d-175">在 "**成员**" 部分，添加要为组织管理监督的人员。</span><span class="sxs-lookup"><span data-stu-id="2d68d-175">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="2d68d-176">有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="2d68d-176">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="2d68d-177">为审阅者启用远程 PowerShell 访问（如果 Exchange Online 上托管电子邮件）</span><span class="sxs-lookup"><span data-stu-id="2d68d-177">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="2d68d-178">按照[启用或禁用对 Exchange Online PowerShell 的访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导进行操作。</span><span class="sxs-lookup"><span data-stu-id="2d68d-178">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="2d68d-179">步骤3：创建自定义敏感信息类型和自定义关键字词典（可选）</span><span class="sxs-lookup"><span data-stu-id="2d68d-179">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="2d68d-180">若要从监督策略向导中的现有自定义敏感信息类型或自定义关键字词典中进行选择，需要先创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="2d68d-180">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="2d68d-181">创建自定义关键字词典/词典（可选）</span><span class="sxs-lookup"><span data-stu-id="2d68d-181">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="2d68d-182">使用文本编辑器（如记事本）创建一个文件，其中包含要在监督策略中监视的关键字术语。</span><span class="sxs-lookup"><span data-stu-id="2d68d-182">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="2d68d-183">确保每个术语都位于单独的行中，并将文件保存为**Unicode/UTF-16 （小 Endian）** 格式。</span><span class="sxs-lookup"><span data-stu-id="2d68d-183">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="2d68d-184">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="2d68d-184">Create custom sensitive information types</span></span>

1. <span data-ttu-id="2d68d-185">创建新的敏感信息类型，并将您的自定义词典添加到 Office 365 安全 & 合规性中心中。</span><span class="sxs-lookup"><span data-stu-id="2d68d-185">Create a new sensitive information type and add your custom dictionary in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="2d68d-186">导航到 "**分类** \> " "**敏感信息**类型"，然后按照新的 "**敏感信息类型" 向导**中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="2d68d-186">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="2d68d-187">你将在此处执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2d68d-187">Here you will:</span></span>

    - <span data-ttu-id="2d68d-188">定义敏感信息类型的名称和说明</span><span class="sxs-lookup"><span data-stu-id="2d68d-188">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="2d68d-189">定义邻近度、置信度和主要模式元素</span><span class="sxs-lookup"><span data-stu-id="2d68d-189">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="2d68d-190">将自定义词典作为匹配元素的要求导入</span><span class="sxs-lookup"><span data-stu-id="2d68d-190">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="2d68d-191">查看您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="2d68d-191">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="2d68d-192">有关更多详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)和[创建关键字词典](create-a-keyword-dictionary.md)</span><span class="sxs-lookup"><span data-stu-id="2d68d-192">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="2d68d-193">创建自定义词典/词典之后，可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 查看配置的关键字，也可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet 添加和删除术语。</span><span class="sxs-lookup"><span data-stu-id="2d68d-193">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="2d68d-194">步骤4：设置监督策略（必需）</span><span class="sxs-lookup"><span data-stu-id="2d68d-194">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="2d68d-195">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="2d68d-195">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2d68d-196">在 "合规性中心" 中，选择 "**监督**"。</span><span class="sxs-lookup"><span data-stu-id="2d68d-196">In the Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="2d68d-197">选择 "**创建**"，然后按照向导设置策略配置。</span><span class="sxs-lookup"><span data-stu-id="2d68d-197">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="2d68d-198">使用该向导，您将：</span><span class="sxs-lookup"><span data-stu-id="2d68d-198">Using the wizard, you will:</span></span>

    - <span data-ttu-id="2d68d-199">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2d68d-199">Give the policy a name and description.</span></span>
    - <span data-ttu-id="2d68d-200">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="2d68d-200">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="2d68d-201">定义监督策略[条件](supervision-policies.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="2d68d-201">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="2d68d-202">您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="2d68d-202">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="2d68d-203">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="2d68d-203">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="2d68d-204">你可以在此处选择默认和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="2d68d-204">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="2d68d-205">选择是否要启用冒犯性语言模型。</span><span class="sxs-lookup"><span data-stu-id="2d68d-205">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="2d68d-206">这将检测在电子邮件正文中发送或接收的不正确的语言。</span><span class="sxs-lookup"><span data-stu-id="2d68d-206">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="2d68d-207">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="2d68d-207">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="2d68d-208">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="2d68d-208">Choose the reviewers for the policy.</span></span> <span data-ttu-id="2d68d-209">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="2d68d-209">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="2d68d-210">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="2d68d-210">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="2d68d-211">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="2d68d-211">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="2d68d-212">步骤5：测试监督策略（可选）</span><span class="sxs-lookup"><span data-stu-id="2d68d-212">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="2d68d-213">创建监督策略后，最好进行测试以确保策略正确地强制实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="2d68d-213">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="2d68d-214">如果监督策略中包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="2d68d-214">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="2d68d-215">按照以下步骤测试您的监督策略：</span><span class="sxs-lookup"><span data-stu-id="2d68d-215">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="2d68d-216">打开以您要测试的策略中定义的监督用户身份登录的电子邮件客户端或 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="2d68d-216">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="2d68d-217">发送符合您在监督策略中定义的条件的电子邮件或 Microsoft 团队聊天。</span><span class="sxs-lookup"><span data-stu-id="2d68d-217">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="2d68d-218">它可以是关键字、附件大小、域等。确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="2d68d-218">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d68d-219">已定义策略的电子邮件将在接近实时的情况中进行处理，并且可以在配置策略后立即进行测试。</span><span class="sxs-lookup"><span data-stu-id="2d68d-219">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="2d68d-220">Microsoft 团队中的聊天可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="2d68d-220">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="2d68d-221">以监督策略中指定的审阅者的形式登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="2d68d-221">Log into your Office 365 tenant as a reviewer designated in the supervision policy.</span></span> <span data-ttu-id="2d68d-222">导航到 "**监控** > "*您的自定义策略* > **打开**以查看该策略的报告。</span><span class="sxs-lookup"><span data-stu-id="2d68d-222">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="2d68d-223">PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="2d68d-223">PowerShell reference</span></span>

<span data-ttu-id="2d68d-224">如果需要，可以使用以下 PowerShell cmdlet 创建和管理监督策略：</span><span class="sxs-lookup"><span data-stu-id="2d68d-224">If needed, you can create and manage supervision policies with the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="2d68d-225">新 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2d68d-225">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2d68d-226">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2d68d-226">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2d68d-227">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2d68d-227">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2d68d-228">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2d68d-228">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2d68d-229">新 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="2d68d-229">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="2d68d-230">SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="2d68d-230">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="2d68d-231">SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="2d68d-231">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="2d68d-232">SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="2d68d-232">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="2d68d-233">SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="2d68d-233">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
