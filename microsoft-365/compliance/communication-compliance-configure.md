---
title: 为 Microsoft 365 配置通信合规性（预览）
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
description: 设置通信合规性策略以配置员工通信以供审阅。
ms.openlocfilehash: 24b821158ca0f6d7486d1177256f5b1ce9123479
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633621"
---
# <a name="configure-communication-compliance-for-microsoft-365-preview"></a><span data-ttu-id="298d9-103">为 Microsoft 365 配置通信合规性（预览）</span><span class="sxs-lookup"><span data-stu-id="298d9-103">Configure communication compliance for Microsoft 365 (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="298d9-104">本主题适用于在 Microsoft 365 订阅中配置通信合规性。</span><span class="sxs-lookup"><span data-stu-id="298d9-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="298d9-105">如果要为 Office 365 订阅配置监督策略，请参阅[configure 监督 For office 365](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="298d9-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="298d9-106">使用通信合规性策略，以捕获内部或外部审阅者进行检查的员工通信。</span><span class="sxs-lookup"><span data-stu-id="298d9-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="298d9-107">有关通信合规性策略如何帮助您监视组织中的通信的详细信息，请参阅[Microsoft 365 中的通信合规性策略](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="298d9-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span>

> [!NOTE]
> <span data-ttu-id="298d9-108">通过通信合规性策略监控的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或包含在 Office 365 企业版 E5 订阅中。</span><span class="sxs-lookup"><span data-stu-id="298d9-108">Users monitored by communication compliance policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
> <span data-ttu-id="298d9-109">如果你没有现有的企业版 E5 计划，并且想要尝试进行通信合规性，则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="298d9-109">If you don't have an existing Enterprise E5 plan and want to try communication compliance, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="298d9-110">按照以下步骤在 Microsoft 365 组织中设置和使用通信合规性：</span><span class="sxs-lookup"><span data-stu-id="298d9-110">Follow these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>
  
- <span data-ttu-id="298d9-111">**步骤1（可选）**：[设置组以实现通信合规性](#step-1-set-up-groups-for-communication-compliance-optional)</span><span class="sxs-lookup"><span data-stu-id="298d9-111">**Step 1 (optional)**: [Set up groups for communication compliance](#step-1-set-up-groups-for-communication-compliance-optional)</span></span> 

    <span data-ttu-id="298d9-112">在开始使用通信合规性之前，请确定哪些用户需要查看通信以及谁在进行审阅。</span><span class="sxs-lookup"><span data-stu-id="298d9-112">Before you start using communication compliance, determine who needs communications reviewed and who does reviews.</span></span> <span data-ttu-id="298d9-113">如果要开始使用几个用户查看通信合规性的工作方式，则可以跳过 "立即" 设置组。</span><span class="sxs-lookup"><span data-stu-id="298d9-113">If you want to get started with just a few users to see how communication compliance works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="298d9-114">**步骤2（必需）**：[在组织中提供通信合规性](#step-2-make-communication-compliance-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="298d9-114">**Step 2 (required)**: [Make communication compliance available in your organization](#step-2-make-communication-compliance-available-in-your-organization-required)</span></span>

    <span data-ttu-id="298d9-115">将自己添加到**监管审核管理员**角色，以便您可以设置策略。</span><span class="sxs-lookup"><span data-stu-id="298d9-115">Add yourself to the **Supervisory Review Administrator** role so you can set up policies.</span></span> <span data-ttu-id="298d9-116">您还需要创建一个具有**监管审核管理员**、**案例管理**和**审阅**角色的组，以便对具有策略匹配的邮件执行调查和修正操作的人员或组的角色。</span><span class="sxs-lookup"><span data-stu-id="298d9-116">You'll also need to create a group with the **Supervisory Review Administrator**, **Case Management**, and **Review** roles to people or groups that will take investigative and remediation action on messages with policy matches.</span></span> <span data-ttu-id="298d9-117">分配了这些角色的任何人都可以访问 Microsoft 365 合规性中心中的**通信合规性**页面。</span><span class="sxs-lookup"><span data-stu-id="298d9-117">Anyone who has these roles assigned can access the **Communication compliance** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="298d9-118">如果 reviewable 电子邮件托管在 Exchange Online 中，则每个审阅者都必须具有[对 Exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="298d9-118">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="298d9-119">**步骤3（必需）**：[设置通信合规性策略](#step-3-create-a-communication-compliance-policy-required)</span><span class="sxs-lookup"><span data-stu-id="298d9-119">**Step 3 (required)**: [Set up a communication compliance policy](#step-3-create-a-communication-compliance-policy-required)</span></span>

    <span data-ttu-id="298d9-120">在 Microsoft 365 合规性中心创建通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="298d9-120">You create communication compliance policies in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="298d9-121">这些策略定义哪些通信将在组织中进行审核，并指定谁进行审阅。</span><span class="sxs-lookup"><span data-stu-id="298d9-121">These policies define which communications are subject to review in your organization and specifies who does reviews.</span></span> <span data-ttu-id="298d9-122">通信包括电子邮件、Microsoft 团队、Skype for Business 和第三方平台通信（如 Facebook、Twitter 等）。</span><span class="sxs-lookup"><span data-stu-id="298d9-122">Communications include email, Microsoft Teams, Skype for Business, and third-party platform communications (such as Facebook, Twitter, and so on).</span></span>

- <span data-ttu-id="298d9-123">**步骤4（可选）**：[创建员工通知模板](#step-4-create-employee-notice-templates-optional)</span><span class="sxs-lookup"><span data-stu-id="298d9-123">**Step 4 (optional)**: [Create employee notice templates](#step-4-create-employee-notice-templates-optional)</span></span>

    <span data-ttu-id="298d9-124">创建自定义通知模板以向员工发送电子邮件通知，作为策略匹配项的修正选项。</span><span class="sxs-lookup"><span data-stu-id="298d9-124">Create custom notice templates to send email notifications to employees as a remediation option for policy matches.</span></span>

- <span data-ttu-id="298d9-125">**步骤5（可选）**：[测试通信合规性策略](#step-5-test-your-communication-compliance-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="298d9-125">**Step 5 (optional)**: [Test your communication compliance policy](#step-5-test-your-communication-compliance-policy-optional)</span></span>

    <span data-ttu-id="298d9-126">测试通信合规性策略以确保其按预期工作。</span><span class="sxs-lookup"><span data-stu-id="298d9-126">Test your communication compliance policy to make sure it functions as desired.</span></span> <span data-ttu-id="298d9-127">务必确保合规性策略满足标准。</span><span class="sxs-lookup"><span data-stu-id="298d9-127">It's important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a><span data-ttu-id="298d9-128">步骤1：为通信合规性设置组（可选）</span><span class="sxs-lookup"><span data-stu-id="298d9-128">Step 1: Set up groups for communication compliance (optional)</span></span>

 <span data-ttu-id="298d9-129">创建通信合规性策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。</span><span class="sxs-lookup"><span data-stu-id="298d9-129">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="298d9-130">在策略中，您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="298d9-130">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="298d9-131">为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="298d9-131">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="298d9-132">如果使用的是组，可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="298d9-132">If you're using groups, you may need several.</span></span> <span data-ttu-id="298d9-133">例如，如果要监视两个不同的人员组之间的通信，或者要指定不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="298d9-133">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="298d9-134">使用下图可帮助您为组织中的通信合规性策略配置组：</span><span class="sxs-lookup"><span data-stu-id="298d9-134">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="298d9-135">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="298d9-135">**Policy Member**</span></span> | <span data-ttu-id="298d9-136">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="298d9-136">**Supported Groups**</span></span> | <span data-ttu-id="298d9-137">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="298d9-137">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="298d9-138">受监督用户</span><span class="sxs-lookup"><span data-stu-id="298d9-138">Supervised users</span></span> <br> <span data-ttu-id="298d9-139">非监督用户</span><span class="sxs-lookup"><span data-stu-id="298d9-139">Non-supervised users</span></span> | <span data-ttu-id="298d9-140">通讯组</span><span class="sxs-lookup"><span data-stu-id="298d9-140">Distribution groups</span></span> <br> <span data-ttu-id="298d9-141">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="298d9-141">Office 365 groups</span></span> | <span data-ttu-id="298d9-142">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="298d9-142">Dynamic distribution groups</span></span> |
| <span data-ttu-id="298d9-143">Reviewers</span><span class="sxs-lookup"><span data-stu-id="298d9-143">Reviewers</span></span> | <span data-ttu-id="298d9-144">启用邮件功能的安全组</span><span class="sxs-lookup"><span data-stu-id="298d9-144">Mail-enabled security groups</span></span>  | <span data-ttu-id="298d9-145">通讯组</span><span class="sxs-lookup"><span data-stu-id="298d9-145">Distribution groups</span></span> <br> <span data-ttu-id="298d9-146">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="298d9-146">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="298d9-147">当您为受监督的用户选择 Office 365 组时，该策略将监视共享 Office 365 邮箱的内容以及与该组关联的 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="298d9-147">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="298d9-148">当您选择通讯组列表时，该策略将监视单个用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="298d9-148">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="298d9-149">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="298d9-149">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="298d9-150">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="298d9-150">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="298d9-151">管理启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="298d9-151">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="298d9-152">Office 365 组概述</span><span class="sxs-lookup"><span data-stu-id="298d9-152">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a><span data-ttu-id="298d9-153">步骤2：在您的组织中提供通信合规性（必需）</span><span class="sxs-lookup"><span data-stu-id="298d9-153">Step 2: Make communication compliance available in your organization (required)</span></span>

<span data-ttu-id="298d9-154">若要在 Microsoft 365 合规性中心中将**通信合规性**用作菜单选项，您必须分配有**监管审核管理员**角色。</span><span class="sxs-lookup"><span data-stu-id="298d9-154">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="298d9-155">此外，若要使用策略匹配来调查和修正邮件，您必须为具有**监管审核管理员**、**案例管理**和**审阅**角色的审阅者创建一个组。</span><span class="sxs-lookup"><span data-stu-id="298d9-155">Additionally, to investigate and remediate messages with policy matches, you must create a group for reviewers with the **Supervisory Review Administrator**, **Case Management**, and **Review** roles.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="298d9-156">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="298d9-156">Create a new role group</span></span>

1. <span data-ttu-id="298d9-157">在 Office [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="298d9-157">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="298d9-158">在 Microsoft 365 合规性中心中，转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-158">In the Microsoft 365 compliance center, go to **Permissions**.</span></span> <span data-ttu-id="298d9-159">选择用于查看和管理 Office 365 中的角色的链接。</span><span class="sxs-lookup"><span data-stu-id="298d9-159">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="298d9-160">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="298d9-160">Select **Create**.</span></span>

4. <span data-ttu-id="298d9-161">在 "**名称**" 字段中，为新角色组指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="298d9-161">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="298d9-162">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="298d9-162">Select **Next**.</span></span>

5. <span data-ttu-id="298d9-163">选择 "**选择角色**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-163">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="298d9-164">选中 "**监察审核管理员**、**案例管理**和**审阅**" 复选框，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-164">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="298d9-165">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="298d9-165">Select **Next**.</span></span>

6. <span data-ttu-id="298d9-166">选择 "**选择成员**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-166">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="298d9-167">选中您想要创建策略的所有用户和组的复选框，并使用策略匹配来管理邮件，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-167">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="298d9-168">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="298d9-168">Select **Next**.</span></span>

7. <span data-ttu-id="298d9-169">选择 "**创建角色组**" 以完成。</span><span class="sxs-lookup"><span data-stu-id="298d9-169">Select **Create role group** to finish.</span></span>

<span data-ttu-id="298d9-170">有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="298d9-170">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-3-create-a-communication-compliance-policy-required"></a><span data-ttu-id="298d9-171">步骤3：创建通信合规性策略（必需）</span><span class="sxs-lookup"><span data-stu-id="298d9-171">Step 3: Create a communication compliance policy (required)</span></span>
  
1. <span data-ttu-id="298d9-172">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="298d9-172">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="298d9-173">在 Microsoft 365 合规性中心中，选择 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-173">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="298d9-174">选择 "**策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="298d9-174">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="298d9-175">选择 "**创建策略**"，从模板创建和配置新策略，或创建和配置自定义策略。</span><span class="sxs-lookup"><span data-stu-id="298d9-175">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="298d9-176">如果选择策略模板来创建策略，您将：</span><span class="sxs-lookup"><span data-stu-id="298d9-176">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="298d9-177">确认或更新策略名称。</span><span class="sxs-lookup"><span data-stu-id="298d9-177">Confirm or update the policy name.</span></span> <span data-ttu-id="298d9-178">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="298d9-178">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="298d9-179">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="298d9-179">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="298d9-180">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="298d9-180">Choose the reviewers for the policy.</span></span> <span data-ttu-id="298d9-181">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="298d9-181">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="298d9-182">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="298d9-182">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="298d9-183">选择 "受限条件" 字段，通常是要应用于策略的敏感信息类型或关键字词典。</span><span class="sxs-lookup"><span data-stu-id="298d9-183">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="298d9-184">如果您选择使用策略向导创建自定义策略，您将：</span><span class="sxs-lookup"><span data-stu-id="298d9-184">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="298d9-185">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="298d9-185">Give the policy a name and description.</span></span> <span data-ttu-id="298d9-186">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="298d9-186">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="298d9-187">选择要监督的用户或组，包括组织中的所有用户、特定用户和组，或者要排除的其他用户和组。</span><span class="sxs-lookup"><span data-stu-id="298d9-187">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span> -
    - <span data-ttu-id="298d9-188">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="298d9-188">Choose the reviewers for the policy.</span></span> <span data-ttu-id="298d9-189">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="298d9-189">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="298d9-190">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="298d9-190">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="298d9-191">选择要扫描的通信通道，包括 Exchange、Microsoft 团队或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="298d9-191">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="298d9-192">如果您在 Microsoft 365 中配置了连接器，您还将选择扫描第三方源。</span><span class="sxs-lookup"><span data-stu-id="298d9-192">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="298d9-193">选择要监视的通信方向，包括入站、出站或内部通信。</span><span class="sxs-lookup"><span data-stu-id="298d9-193">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="298d9-194">定义通信合规性策略[条件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="298d9-194">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="298d9-195">您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="298d9-195">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="298d9-196">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="298d9-196">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="298d9-197">你可以在此处选择默认和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="298d9-197">This is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="298d9-198">从 "通信合规性策略向导" 中的现有自定义敏感信息类型或自定义关键字词典中进行选择。</span><span class="sxs-lookup"><span data-stu-id="298d9-198">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="298d9-199">如果需要，可以在运行向导之前创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="298d9-199">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="298d9-200">您还可以在 "通信合规性策略" 向导中创建新的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="298d9-200">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="298d9-201">选择是否要启用冒犯性语言模型。</span><span class="sxs-lookup"><span data-stu-id="298d9-201">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="298d9-202">这将检测在电子邮件正文中发送或接收的不正确的语言。</span><span class="sxs-lookup"><span data-stu-id="298d9-202">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="298d9-203">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="298d9-203">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="298d9-204">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="298d9-204">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="298d9-205">使用 "自定义策略" 向导时，选择 "使用模板或**提交**时**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-205">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="298d9-206">**您的策略已创建**页面将显示有关何时激活策略以及将捕获哪些通信的指南。</span><span class="sxs-lookup"><span data-stu-id="298d9-206">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-4-create-employee-notice-templates-optional"></a><span data-ttu-id="298d9-207">步骤4：创建员工通知模板（可选）</span><span class="sxs-lookup"><span data-stu-id="298d9-207">Step 4: Create employee notice templates (optional)</span></span>

<span data-ttu-id="298d9-208">如果希望通过向关联的员工发送提醒通知来选择对策略警报做出响应，您需要在您的组织中至少创建一个通知模板。</span><span class="sxs-lookup"><span data-stu-id="298d9-208">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="298d9-209">在将 "通知模板" 字段作为警报修正过程的一部分发送并为每个通信合规性策略创建自定义的通知模板之前，这些字段都是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="298d9-209">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="298d9-210">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="298d9-210">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="298d9-211">在 Microsoft 365 合规性中心中，转到 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-211">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="298d9-212">选择 "**通知模板**" 选项卡，然后选择 "**创建通知模板**"。</span><span class="sxs-lookup"><span data-stu-id="298d9-212">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="298d9-213">在 "**修改通知模板**" 页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="298d9-213">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="298d9-214">通知模板名称（必需）</span><span class="sxs-lookup"><span data-stu-id="298d9-214">Notice template name (required)</span></span>
    - <span data-ttu-id="298d9-215">发件人（必需）</span><span class="sxs-lookup"><span data-stu-id="298d9-215">Send from (required)</span></span>
    - <span data-ttu-id="298d9-216">"抄送" 和 "密件抄送" （可选）</span><span class="sxs-lookup"><span data-stu-id="298d9-216">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="298d9-217">主题（必需）</span><span class="sxs-lookup"><span data-stu-id="298d9-217">Subject (required)</span></span>
    - <span data-ttu-id="298d9-218">邮件正文（必需）</span><span class="sxs-lookup"><span data-stu-id="298d9-218">Message body (required)</span></span>

5. <span data-ttu-id="298d9-219">选择 "**保存**" 以创建并保存 "通知" 模板。</span><span class="sxs-lookup"><span data-stu-id="298d9-219">Select **Save** to create and save the notice template.</span></span>

## <a name="step-5-test-your-communication-compliance-policy-optional"></a><span data-ttu-id="298d9-220">步骤5：测试通信合规性策略（可选）</span><span class="sxs-lookup"><span data-stu-id="298d9-220">Step 5: Test your communication compliance policy (optional)</span></span>

<span data-ttu-id="298d9-221">创建通信合规性策略后，最好对其进行测试，以确保策略正确地强制实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="298d9-221">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="298d9-222">如果通信合规性策略包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="298d9-222">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="298d9-223">请确保为策略激活时间，以便捕获要测试的通信。</span><span class="sxs-lookup"><span data-stu-id="298d9-223">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="298d9-224">按照以下步骤测试您的通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="298d9-224">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="298d9-225">打开电子邮件客户端或 Microsoft 团队，同时以您要测试的策略中定义的监督用户的身份登录。</span><span class="sxs-lookup"><span data-stu-id="298d9-225">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="298d9-226">发送符合通信合规性策略中定义的条件的电子邮件或 Microsoft 团队聊天。</span><span class="sxs-lookup"><span data-stu-id="298d9-226">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="298d9-227">它可以是关键字、附件大小、域等。</span><span class="sxs-lookup"><span data-stu-id="298d9-227">This can be a keyword, attachment size, domain, and so on.</span></span> <span data-ttu-id="298d9-228">请确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="298d9-228">Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="298d9-229">所有源通道中的通信可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="298d9-229">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="298d9-230">以通信合规性策略中指定的审阅者的资格登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="298d9-230">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="298d9-231">导航到 "**通信合规性** > **警报**" 以查看策略的警报。</span><span class="sxs-lookup"><span data-stu-id="298d9-231">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="298d9-232">使用修正控件修正警报，并验证是否正确解决了警报。</span><span class="sxs-lookup"><span data-stu-id="298d9-232">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>
