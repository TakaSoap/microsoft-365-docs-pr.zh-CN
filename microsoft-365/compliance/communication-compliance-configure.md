---
title: 配置通信合规性（预览）
description: 设置通信合规性策略以配置员工通信以供审阅。
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
ms.openlocfilehash: 8627a46ee861751799e1175c7e030e1b28c6d935
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111877"
---
# <a name="configure-communication-compliance-in-microsoft-365-preview"></a><span data-ttu-id="e9f06-103">在 Microsoft 365 中配置通信合规性（预览版）</span><span class="sxs-lookup"><span data-stu-id="e9f06-103">Configure communication compliance in Microsoft 365 (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9f06-104">本主题适用于在 Microsoft 365 订阅中配置通信合规性。</span><span class="sxs-lookup"><span data-stu-id="e9f06-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="e9f06-105">如果要为 Office 365 订阅配置监督策略，请参阅[configure 监督 For office 365](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="e9f06-106">使用通信合规性策略，以捕获内部或外部审阅者进行检查的员工通信。</span><span class="sxs-lookup"><span data-stu-id="e9f06-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="e9f06-107">有关通信合规性策略如何帮助您监视组织中的通信的详细信息，请参阅[Microsoft 365 中的通信合规性策略](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e9f06-108">通过通信合规性策略监控的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或包含在 Office 365 企业版 E5 订阅中。</span><span class="sxs-lookup"><span data-stu-id="e9f06-108">Users monitored by communication compliance policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
> <span data-ttu-id="e9f06-109">如果你没有现有的企业版 E5 计划，并且想要尝试进行通信合规性，则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-109">If you don't have an existing Enterprise E5 plan and want to try communication compliance, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="e9f06-110">按照以下步骤在 Microsoft 365 组织中设置和使用通信合规性：</span><span class="sxs-lookup"><span data-stu-id="e9f06-110">Follow these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>
  
- <span data-ttu-id="e9f06-111">**步骤1（可选）**：[设置组以实现通信合规性](#step-1-set-up-groups-for-communication-compliance-optional)</span><span class="sxs-lookup"><span data-stu-id="e9f06-111">**Step 1 (optional)**: [Set up groups for communication compliance](#step-1-set-up-groups-for-communication-compliance-optional)</span></span> 

    <span data-ttu-id="e9f06-112">在开始使用通信合规性之前，请确定哪些用户需要查看通信以及谁执行了检查。</span><span class="sxs-lookup"><span data-stu-id="e9f06-112">Before you start using communication compliance, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="e9f06-113">如果要开始使用几个用户查看通信合规性的工作方式，则可以跳过 "立即" 设置组。</span><span class="sxs-lookup"><span data-stu-id="e9f06-113">If you want to get started with just a few users to see how communication compliance works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="e9f06-114">**步骤2（必需）**：[在组织中提供通信合规性](#step-2-make-communication-compliance-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="e9f06-114">**Step 2 (required)**: [Make communication compliance available in your organization](#step-2-make-communication-compliance-available-in-your-organization-required)</span></span>

    <span data-ttu-id="e9f06-115">将自己添加到**监管审核管理员**角色，以便您可以设置策略。</span><span class="sxs-lookup"><span data-stu-id="e9f06-115">Add yourself to the **Supervisory Review Administrator** role so you can set up policies.</span></span> <span data-ttu-id="e9f06-116">您还需要创建一个具有**监管审核管理员**、**案例管理**和**审阅**角色的新组，以便对具有策略匹配的邮件进行调查和修正操作的人员或组的角色。</span><span class="sxs-lookup"><span data-stu-id="e9f06-116">You'll also need to create a new group with the **Supervisory Review Administrator**, **Case Management**, and **Review** roles to people or groups that will take investigative and remediation action on messages with policy matches.</span></span> <span data-ttu-id="e9f06-117">分配了这些角色的任何人都可以访问 Microsoft 365 合规性中心中的**通信合规性**页面。</span><span class="sxs-lookup"><span data-stu-id="e9f06-117">Anyone who has these roles assigned can access the **Communication compliance** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e9f06-118">如果 reviewable 电子邮件托管在 Exchange Online 中，则每个审阅者都必须具有[对 Exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-118">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e9f06-119">**步骤3（必需）**：[设置通信合规性策略](#step-3-create-a-communication-compliance-policy-required)</span><span class="sxs-lookup"><span data-stu-id="e9f06-119">**Step 3 (required)**: [Set up a communication compliance policy](#step-3-create-a-communication-compliance-policy-required)</span></span>

    <span data-ttu-id="e9f06-120">在 Microsoft 365 合规性中心创建通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="e9f06-120">You create communication compliance policies in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e9f06-121">这些策略定义哪些通信将在组织中进行审核，并指定执行审阅的用户。</span><span class="sxs-lookup"><span data-stu-id="e9f06-121">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="e9f06-122">通信包括电子邮件、Microsoft 团队、Skype for Business 和第三方平台通信（如 Facebook、Twitter 等）。</span><span class="sxs-lookup"><span data-stu-id="e9f06-122">Communications include email, Microsoft Teams, Skype for Business, and third-party platform communications (such as Facebook, Twitter, etc.).</span></span>

- <span data-ttu-id="e9f06-123">**步骤4（可选）**：[创建员工通知模板](#step-4-create-employee-notice-templates-optional)</span><span class="sxs-lookup"><span data-stu-id="e9f06-123">**Step 4 (optional)**: [Create employee notice templates](#step-4-create-employee-notice-templates-optional)</span></span>

    <span data-ttu-id="e9f06-124">创建自定义通知模板以向员工发送电子邮件通知，作为策略匹配项的修正选项。</span><span class="sxs-lookup"><span data-stu-id="e9f06-124">Create custom notice templates to send email notifications to employees as a remediation option for policy matches.</span></span>

- <span data-ttu-id="e9f06-125">**步骤5（可选）**：[测试通信合规性策略](#step-5-test-your-communication-compliance-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="e9f06-125">**Step 5 (optional)**: [Test your communication compliance policy](#step-5-test-your-communication-compliance-policy-optional)</span></span>

    <span data-ttu-id="e9f06-126">测试通信合规性策略以确保其按预期工作。</span><span class="sxs-lookup"><span data-stu-id="e9f06-126">Test your communication compliance policy to make sure it functions as desired.</span></span> <span data-ttu-id="e9f06-127">务必确保合规性策略满足标准。</span><span class="sxs-lookup"><span data-stu-id="e9f06-127">It's important to ensure that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="e9f06-128">**步骤6（可选）**：[为您的通信合规性策略启用审核](#step-6-enable-auditing-for-your-communication-compliance-policies-optional)</span><span class="sxs-lookup"><span data-stu-id="e9f06-128">**Step 6 (optional)**: [Enable auditing for your communication compliance policies](#step-6-enable-auditing-for-your-communication-compliance-policies-optional)</span></span>

    <span data-ttu-id="e9f06-129">为您的组织启用审核，以记录通信合规性策略的管理活动。</span><span class="sxs-lookup"><span data-stu-id="e9f06-129">Enable auditing for your organization to record managment activities for communication compliance policies.</span></span>

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a><span data-ttu-id="e9f06-130">步骤1：为通信合规性设置组（可选）</span><span class="sxs-lookup"><span data-stu-id="e9f06-130">Step 1: Set up groups for communication compliance (optional)</span></span>

 <span data-ttu-id="e9f06-131">创建通信合规性策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。</span><span class="sxs-lookup"><span data-stu-id="e9f06-131">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="e9f06-132">在策略中，您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="e9f06-132">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="e9f06-133">为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="e9f06-133">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="e9f06-134">如果使用的是组，可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="e9f06-134">If you're using groups, you may need several.</span></span> <span data-ttu-id="e9f06-135">例如，如果要监视两个不同的人员组之间的通信，或者要指定不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="e9f06-135">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="e9f06-136">使用下图可帮助您为组织中的通信合规性策略配置组：</span><span class="sxs-lookup"><span data-stu-id="e9f06-136">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="e9f06-137">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="e9f06-137">**Policy Member**</span></span> | <span data-ttu-id="e9f06-138">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="e9f06-138">**Supported Groups**</span></span> | <span data-ttu-id="e9f06-139">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="e9f06-139">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="e9f06-140">受监督用户</span><span class="sxs-lookup"><span data-stu-id="e9f06-140">Supervised users</span></span> <br> <span data-ttu-id="e9f06-141">非监督用户</span><span class="sxs-lookup"><span data-stu-id="e9f06-141">Non-supervised users</span></span> | <span data-ttu-id="e9f06-142">通讯组</span><span class="sxs-lookup"><span data-stu-id="e9f06-142">Distribution groups</span></span> <br> <span data-ttu-id="e9f06-143">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="e9f06-143">Office 365 groups</span></span> | <span data-ttu-id="e9f06-144">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="e9f06-144">Dynamic distribution groups</span></span> |
| <span data-ttu-id="e9f06-145">Reviewers</span><span class="sxs-lookup"><span data-stu-id="e9f06-145">Reviewers</span></span> | <span data-ttu-id="e9f06-146">启用邮件功能的安全组</span><span class="sxs-lookup"><span data-stu-id="e9f06-146">Mail-enabled security groups</span></span>  | <span data-ttu-id="e9f06-147">通讯组</span><span class="sxs-lookup"><span data-stu-id="e9f06-147">Distribution groups</span></span> <br> <span data-ttu-id="e9f06-148">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="e9f06-148">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="e9f06-149">当您为受监督的用户选择 Office 365 组时，该策略将监视共享 Office 365 邮箱的内容以及与该组关联的 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="e9f06-149">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="e9f06-150">当您选择通讯组列表时，该策略将监视单个用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="e9f06-150">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="e9f06-151">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="e9f06-151">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="e9f06-152">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="e9f06-152">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="e9f06-153">管理启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="e9f06-153">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="e9f06-154">Office 365 组概述</span><span class="sxs-lookup"><span data-stu-id="e9f06-154">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a><span data-ttu-id="e9f06-155">步骤2：在您的组织中提供通信合规性（必需）</span><span class="sxs-lookup"><span data-stu-id="e9f06-155">Step 2: Make communication compliance available in your organization (required)</span></span>

> [!Important]
> <span data-ttu-id="e9f06-156">默认情况下，全局管理员不具有对通信合规性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e9f06-156">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="e9f06-157">在此步骤中分配的角色在所有通信合规性功能都可访问之前是必需的。</span><span class="sxs-lookup"><span data-stu-id="e9f06-157">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span>

<span data-ttu-id="e9f06-158">若要在 Microsoft 365 合规性中心中将**通信合规性**用作菜单选项，您必须分配有**监管审核管理员**角色。</span><span class="sxs-lookup"><span data-stu-id="e9f06-158">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="e9f06-159">此外，若要使用策略匹配来调查和修正邮件，您必须为具有**监管审核管理员**、**案例管理**和**审阅**角色的审阅者创建一个组。</span><span class="sxs-lookup"><span data-stu-id="e9f06-159">Additionally, to investigate and remediate messages with policy matches, you must create a group for reviewers with the **Supervisory Review Administrator**, **Case Management**, and **Review** roles.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="e9f06-160">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="e9f06-160">Create a new role group</span></span>

1. <span data-ttu-id="e9f06-161">在 Microsoft [https://protection.office.com/permissions](https://protection.office.com/permissions) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="e9f06-161">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="e9f06-162">在 Microsoft Office 365 安全与合规中心中，转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-162">In the Microsoft Office 365 security and compliance center, go to **Permissions**.</span></span> <span data-ttu-id="e9f06-163">选择用于查看和管理 Office 365 中的角色的链接。</span><span class="sxs-lookup"><span data-stu-id="e9f06-163">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="e9f06-164">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="e9f06-164">Select **Create**.</span></span>

4. <span data-ttu-id="e9f06-165">在 "**名称**" 字段中，为新角色组指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="e9f06-165">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="e9f06-166">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9f06-166">Select **Next**.</span></span>

5. <span data-ttu-id="e9f06-167">选择 "**选择角色**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-167">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="e9f06-168">选中 "**监察审核管理员**、**案例管理**和**审阅**" 复选框，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-168">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="e9f06-169">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9f06-169">Select **Next**.</span></span>

    ![满足通信合规性角色组](media/communication-compliance-role-groups.png)

6. <span data-ttu-id="e9f06-171">选择 "**选择成员**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-171">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="e9f06-172">选中您想要创建策略的所有用户和组的复选框，并使用策略匹配来管理邮件，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-172">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="e9f06-173">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9f06-173">Select **Next**.</span></span>

7. <span data-ttu-id="e9f06-174">选择 "**创建角色组**" 以完成。</span><span class="sxs-lookup"><span data-stu-id="e9f06-174">Select **Create role group** to finish.</span></span>

<span data-ttu-id="e9f06-175">有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-175">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-3-create-a-communication-compliance-policy-required"></a><span data-ttu-id="e9f06-176">步骤3：创建通信合规性策略（必需）</span><span class="sxs-lookup"><span data-stu-id="e9f06-176">Step 3: Create a communication compliance policy (required)</span></span>
  
1. <span data-ttu-id="e9f06-177">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="e9f06-177">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="e9f06-178">在 Microsoft 365 合规性中心中，选择 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-178">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="e9f06-179">选择 "**策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e9f06-179">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="e9f06-180">选择 "**创建策略**"，从模板创建和配置新策略，或创建和配置自定义策略。</span><span class="sxs-lookup"><span data-stu-id="e9f06-180">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="e9f06-181">如果选择策略模板来创建策略，您将：</span><span class="sxs-lookup"><span data-stu-id="e9f06-181">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="e9f06-182">确认或更新策略名称。</span><span class="sxs-lookup"><span data-stu-id="e9f06-182">Confirm or update the policy name.</span></span> <span data-ttu-id="e9f06-183">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="e9f06-183">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="e9f06-184">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="e9f06-184">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="e9f06-185">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="e9f06-185">Choose the reviewers for the policy.</span></span> <span data-ttu-id="e9f06-186">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-186">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="e9f06-187">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="e9f06-187">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="e9f06-188">选择 "受限条件" 字段，通常是要应用于策略的敏感信息类型或关键字词典。</span><span class="sxs-lookup"><span data-stu-id="e9f06-188">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="e9f06-189">如果您选择使用策略向导创建自定义策略，您将：</span><span class="sxs-lookup"><span data-stu-id="e9f06-189">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="e9f06-190">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e9f06-190">Give the policy a name and description.</span></span> <span data-ttu-id="e9f06-191">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="e9f06-191">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="e9f06-192">选择要监督的用户或组，包括组织中的所有用户、特定用户和组，或者要排除的其他用户和组。</span><span class="sxs-lookup"><span data-stu-id="e9f06-192">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span> -
    - <span data-ttu-id="e9f06-193">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="e9f06-193">Choose the reviewers for the policy.</span></span> <span data-ttu-id="e9f06-194">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-194">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="e9f06-195">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="e9f06-195">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="e9f06-196">选择要扫描的通信通道，包括 Exchange、Microsoft 团队或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="e9f06-196">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="e9f06-197">如果您在 Microsoft 365 中配置了连接器，您还将选择扫描第三方源。</span><span class="sxs-lookup"><span data-stu-id="e9f06-197">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="e9f06-198">选择要监视的通信方向，包括入站、出站或内部通信。</span><span class="sxs-lookup"><span data-stu-id="e9f06-198">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="e9f06-199">定义通信合规性策略[条件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-199">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="e9f06-200">您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e9f06-200">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="e9f06-201">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e9f06-201">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="e9f06-202">在此步骤中，您可以选择默认和自定义的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e9f06-202">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="e9f06-203">从 "通信合规性策略向导" 中的现有自定义敏感信息类型或自定义关键字词典中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e9f06-203">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="e9f06-204">如果需要，可以在运行向导之前创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="e9f06-204">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="e9f06-205">您还可以在 "通信合规性策略" 向导中创建新的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e9f06-205">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="e9f06-206">选择是否要启用冒犯性语言分类器。</span><span class="sxs-lookup"><span data-stu-id="e9f06-206">Choose if you'd like to enable the offensive language classifier.</span></span> <span data-ttu-id="e9f06-207">此分类器检测在电子邮件正文中发送或接收的不正确语言。</span><span class="sxs-lookup"><span data-stu-id="e9f06-207">This  classifier detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="e9f06-208">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="e9f06-208">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="e9f06-209">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="e9f06-209">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="e9f06-210">使用 "自定义策略" 向导时，选择 "使用模板或**提交**时**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-210">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="e9f06-211">**您的策略已创建**页面将显示有关何时激活策略以及将捕获哪些通信的指南。</span><span class="sxs-lookup"><span data-stu-id="e9f06-211">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-4-create-employee-notice-templates-optional"></a><span data-ttu-id="e9f06-212">步骤4：创建员工通知模板（可选）</span><span class="sxs-lookup"><span data-stu-id="e9f06-212">Step 4: Create employee notice templates (optional)</span></span>

<span data-ttu-id="e9f06-213">如果希望通过向关联的员工发送提醒通知来选择对策略警报做出响应，您需要在您的组织中至少创建一个通知模板。</span><span class="sxs-lookup"><span data-stu-id="e9f06-213">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="e9f06-214">在将 "通知模板" 字段作为警报修正过程的一部分发送并为每个通信合规性策略创建自定义的通知模板之前，这些字段都是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="e9f06-214">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="e9f06-215">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="e9f06-215">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="e9f06-216">在 Microsoft 365 合规性中心中，转到 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-216">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="e9f06-217">选择 "**通知模板**" 选项卡，然后选择 "**创建通知模板**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-217">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="e9f06-218">在 "**修改通知模板**" 页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="e9f06-218">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="e9f06-219">通知模板名称（必需）</span><span class="sxs-lookup"><span data-stu-id="e9f06-219">Notice template name (required)</span></span>
    - <span data-ttu-id="e9f06-220">发件人（必需）</span><span class="sxs-lookup"><span data-stu-id="e9f06-220">Send from (required)</span></span>
    - <span data-ttu-id="e9f06-221">"抄送" 和 "密件抄送" （可选）</span><span class="sxs-lookup"><span data-stu-id="e9f06-221">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="e9f06-222">主题（必需）</span><span class="sxs-lookup"><span data-stu-id="e9f06-222">Subject (required)</span></span>
    - <span data-ttu-id="e9f06-223">邮件正文（必需）</span><span class="sxs-lookup"><span data-stu-id="e9f06-223">Message body (required)</span></span>

5. <span data-ttu-id="e9f06-224">选择 "**保存**" 以创建并保存 "通知" 模板。</span><span class="sxs-lookup"><span data-stu-id="e9f06-224">Select **Save** to create and save the notice template.</span></span>

## <a name="step-5-test-your-communication-compliance-policy-optional"></a><span data-ttu-id="e9f06-225">步骤5：测试通信合规性策略（可选）</span><span class="sxs-lookup"><span data-stu-id="e9f06-225">Step 5: Test your communication compliance policy (optional)</span></span>

<span data-ttu-id="e9f06-226">创建通信合规性策略后，最好对其进行测试，以确保策略正确地强制实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="e9f06-226">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="e9f06-227">如果通信合规性策略包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-227">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="e9f06-228">请确保为策略激活时间，以便捕获要测试的通信。</span><span class="sxs-lookup"><span data-stu-id="e9f06-228">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="e9f06-229">按照以下步骤测试您的通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="e9f06-229">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="e9f06-230">打开电子邮件客户端或 Microsoft 团队，同时以您要测试的策略中定义的监督用户的身份登录。</span><span class="sxs-lookup"><span data-stu-id="e9f06-230">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="e9f06-231">发送符合通信合规性策略中定义的条件的电子邮件或 Microsoft 团队聊天。</span><span class="sxs-lookup"><span data-stu-id="e9f06-231">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="e9f06-232">此测试可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="e9f06-232">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9f06-233">所有源通道中的通信可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="e9f06-233">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="e9f06-234">以通信合规性策略中指定的审阅者的资格登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e9f06-234">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="e9f06-235">导航到 "**通信合规性** > **警报**" 以查看策略的警报。</span><span class="sxs-lookup"><span data-stu-id="e9f06-235">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="e9f06-236">使用修正控件修正警报，并验证是否正确解决了警报。</span><span class="sxs-lookup"><span data-stu-id="e9f06-236">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>

## <a name="step-6-enable-auditing-for-your-communication-compliance-policies-optional"></a><span data-ttu-id="e9f06-237">步骤6：为您的通信合规性策略启用审核（可选）</span><span class="sxs-lookup"><span data-stu-id="e9f06-237">Step 6: Enable auditing for your communication compliance policies (optional)</span></span>

<span data-ttu-id="e9f06-238">测试策略后，您可能需要启用审核，以便记录与通信合规性管理相关的活动。</span><span class="sxs-lookup"><span data-stu-id="e9f06-238">After you've tested your policies, you may want to enable auditing so that activities associated with communication compliance management are recorded.</span></span> <span data-ttu-id="e9f06-239">这可能是与定义的组织策略相关联的所有活动的摘要，或任何与通信合规性策略更改相关的活动。</span><span class="sxs-lookup"><span data-stu-id="e9f06-239">This may be a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="e9f06-240">启用审核后，通信合规性策略具有内置审核跟踪功能，以实现内部或外部审核的完全准备就绪。</span><span class="sxs-lookup"><span data-stu-id="e9f06-240">When auditing is enabled, communication compliance policies have built-in audit trails for complete readiness for internal or external audits.</span></span> <span data-ttu-id="e9f06-241">您可以在主页面上使用 "**导出审阅活动**" 控件来生成审核文件，如果启用了审核，则可以在统一审核日志中查看审核活动。</span><span class="sxs-lookup"><span data-stu-id="e9f06-241">You can use the **Export review activities** control on the main page for any policy to generate an audit file or view audit activities in the unified audit log if auditing is enabled.</span></span>

<span data-ttu-id="e9f06-242">若要启用审核，请在 "Office 365 安全 & 合规中心" 的 "**审核日志搜索**" 页上，单击 "**开始记录用户和管理员活动**"。</span><span class="sxs-lookup"><span data-stu-id="e9f06-242">To turn auditing on, click **Start recording user and admin activity** on the **Audit log search** page in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="e9f06-243">如果未看到此链接，则已为你的组织开启审核。</span><span class="sxs-lookup"><span data-stu-id="e9f06-243">If you don't see this link, auditing has already been turned on for your organization.</span></span> <span data-ttu-id="e9f06-244">启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="e9f06-244">After you turn auditing on, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="e9f06-245">只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="e9f06-245">You only have to do this once.</span></span> <span data-ttu-id="e9f06-246">有关审核日志的详细信息，请参阅[Search the audit log](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f06-246">For more information about the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>

