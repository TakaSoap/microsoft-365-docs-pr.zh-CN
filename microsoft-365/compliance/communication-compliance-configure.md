---
title: 配置通信合规性
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
ms.openlocfilehash: 027189a10e34687833e6a266d5fe4382a1e14e3a
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42632893"
---
# <a name="configure-communication-compliance-in-microsoft-365"></a><span data-ttu-id="6cf0c-103">在 Microsoft 365 中配置通信合规性</span><span class="sxs-lookup"><span data-stu-id="6cf0c-103">Configure communication compliance in Microsoft 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="6cf0c-104">本主题适用于在 Microsoft 365 订阅中配置通信合规性。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="6cf0c-105">如果要为 Office 365 订阅配置监督策略，请参阅[configure 监督 For office 365](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="6cf0c-106">使用通信合规性策略，以捕获内部或外部审阅者进行检查的员工通信。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="6cf0c-107">有关通信合规性策略如何帮助您监视组织中的通信的详细信息，请参阅[Microsoft 365 中的通信合规性策略](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6cf0c-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="6cf0c-108">Before you begin</span></span>

<span data-ttu-id="6cf0c-109">在开始进行通信合规性之前，应确认你的 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-109">Before you get started with communication compliance, you should confirm your Microsoft 365 subscription.</span></span> <span data-ttu-id="6cf0c-110">通信合规性策略中包含的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或者包含在 Office 365 企业版 E5 订阅中，或包含在 Microsoft365 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-110">Users included in communication compliance policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription, or be included in a Microsoft 365 E5 subscription.</span></span>

<span data-ttu-id="6cf0c-111">如果您没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试使用内幕风险管理，则可以[将 microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)到现有的 Office 365 订阅中，或注册 Microsoft 365 企业版 e5 的[试用版](https://www.microsoft.com/microsoft-365/enterprise)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-111">If you don't have an existing Microsoft 365 Enterprise E5 plan and want to try insider risk management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>
  
<span data-ttu-id="6cf0c-112">完成以下步骤以设置和使用 Microsoft 365 组织中的通信合规性：</span><span class="sxs-lookup"><span data-stu-id="6cf0c-112">Complete these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="6cf0c-113">步骤1（必需）：启用通信合规性的权限</span><span class="sxs-lookup"><span data-stu-id="6cf0c-113">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="6cf0c-114">默认情况下，全局管理员不具有对通信合规性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-114">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="6cf0c-115">在此步骤中分配的角色在所有通信合规性功能都可访问之前是必需的。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-115">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span>

<span data-ttu-id="6cf0c-116">若要在 Microsoft 365 合规性中心中将**通信合规性**用作菜单选项，您必须分配有**监管审核管理员**角色。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-116">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="6cf0c-117">您必须为具有**监管审核管理员**、**案例管理**、**合规性管理员**和**审阅**角色的审阅者创建新的角色组，以使用策略匹配来调查和修正邮件。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-117">You must create a new role group for reviewers with the **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="6cf0c-118">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-118">Create a new role group</span></span>

1. <span data-ttu-id="6cf0c-119">在 Microsoft [https://protection.office.com/permissions](https://protection.office.com/permissions) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-119">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="6cf0c-120">在 Microsoft Office 365 安全与合规中心中，转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-120">In the Microsoft Office 365 security and compliance center, go to **Permissions**.</span></span> <span data-ttu-id="6cf0c-121">选择用于查看和管理 Office 365 中的角色的链接。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-121">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="6cf0c-122">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-122">Select **Create**.</span></span>

4. <span data-ttu-id="6cf0c-123">在 "**名称**" 字段中，为新角色组指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-123">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="6cf0c-124">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-124">Select **Next**.</span></span>

5. <span data-ttu-id="6cf0c-125">选择 "**选择角色**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-125">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="6cf0c-126">选中 "**监察审核管理员**、**案例管理**、**合规性管理员**和**审阅**" 复选框，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-126">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="6cf0c-127">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-127">Select **Next**.</span></span>

    ![满足通信合规性角色组](../media/communication-compliance-role-groups-1.png)

6. <span data-ttu-id="6cf0c-129">选择 "**选择成员**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-129">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="6cf0c-130">选中您想要创建策略的所有用户和组的复选框，并使用策略匹配来管理邮件，然后选择 "**添加**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-130">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="6cf0c-131">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-131">Select **Next**.</span></span>

7. <span data-ttu-id="6cf0c-132">选择 "**创建角色组**" 以完成。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-132">Select **Create role group** to finish.</span></span>

<span data-ttu-id="6cf0c-133">有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-133">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-office-365-audit-log"></a><span data-ttu-id="6cf0c-134">步骤2（必需）：启用 Office 365 审核日志</span><span class="sxs-lookup"><span data-stu-id="6cf0c-134">Step 2 (required): Enable the Office 365 audit log</span></span>

<span data-ttu-id="6cf0c-135">通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-135">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="6cf0c-136">审核日志是与定义的组织策略关联的所有活动的摘要，也是任何与通信合规性策略更改相关的活动。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-136">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="6cf0c-137">有关启用审核的分步说明，请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-137">For step-by-step instructions to turn on auditing, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="6cf0c-138">启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-138">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="6cf0c-139">您只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-139">You only have to do this action once.</span></span> <span data-ttu-id="6cf0c-140">有关使用审核日志的详细信息，请参阅[Search the audit log](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-140">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>


## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="6cf0c-141">步骤3（可选）：设置组以实现通信合规性</span><span class="sxs-lookup"><span data-stu-id="6cf0c-141">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="6cf0c-142">创建通信合规性策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-142">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="6cf0c-143">在策略中，您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-143">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="6cf0c-144">为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-144">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="6cf0c-145">如果使用的是组，可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-145">If you're using groups, you may need several.</span></span> <span data-ttu-id="6cf0c-146">例如，如果要监视两个不同的人员组之间的通信，或者要指定不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-146">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="6cf0c-147">使用下图可帮助您为组织中的通信合规性策略配置组：</span><span class="sxs-lookup"><span data-stu-id="6cf0c-147">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="6cf0c-148">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="6cf0c-148">**Policy Member**</span></span> | <span data-ttu-id="6cf0c-149">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="6cf0c-149">**Supported Groups**</span></span> | <span data-ttu-id="6cf0c-150">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="6cf0c-150">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="6cf0c-151">受监督用户</span><span class="sxs-lookup"><span data-stu-id="6cf0c-151">Supervised users</span></span> <br> <span data-ttu-id="6cf0c-152">非监督用户</span><span class="sxs-lookup"><span data-stu-id="6cf0c-152">Non-supervised users</span></span> | <span data-ttu-id="6cf0c-153">通讯组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-153">Distribution groups</span></span> <br> <span data-ttu-id="6cf0c-154">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-154">Office 365 groups</span></span> | <span data-ttu-id="6cf0c-155">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-155">Dynamic distribution groups</span></span> |
| <span data-ttu-id="6cf0c-156">Reviewers</span><span class="sxs-lookup"><span data-stu-id="6cf0c-156">Reviewers</span></span> | <span data-ttu-id="6cf0c-157">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-157">Mail-enabled security groups</span></span>  | <span data-ttu-id="6cf0c-158">通讯组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-158">Distribution groups</span></span> <br> <span data-ttu-id="6cf0c-159">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-159">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="6cf0c-160">当您为受监督的用户选择 Office 365 组时，该策略将监视共享 Office 365 邮箱的内容以及与该组关联的 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-160">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="6cf0c-161">当您选择通讯组列表时，该策略将监视单个用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-161">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="6cf0c-162">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6cf0c-162">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="6cf0c-163">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-163">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="6cf0c-164">管理启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="6cf0c-164">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="6cf0c-165">Office 365 组概述</span><span class="sxs-lookup"><span data-stu-id="6cf0c-165">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-required-create-a-communication-compliance-policy"></a><span data-ttu-id="6cf0c-166">步骤4（必需）：创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="6cf0c-166">Step 4 (required): Create a communication compliance policy</span></span>
  
1. <span data-ttu-id="6cf0c-167">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-167">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="6cf0c-168">在 Microsoft 365 合规性中心中，选择 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-168">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="6cf0c-169">选择 "**策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-169">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="6cf0c-170">选择 "**创建策略**"，从模板创建和配置新策略，或创建和配置自定义策略。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-170">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="6cf0c-171">如果选择策略模板来创建策略，您将：</span><span class="sxs-lookup"><span data-stu-id="6cf0c-171">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="6cf0c-172">确认或更新策略名称。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-172">Confirm or update the policy name.</span></span> <span data-ttu-id="6cf0c-173">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-173">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="6cf0c-174">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-174">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="6cf0c-175">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-175">Choose the reviewers for the policy.</span></span> <span data-ttu-id="6cf0c-176">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-176">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="6cf0c-177">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-177">All reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="6cf0c-178">在这里添加的审阅者是在调查和修正工作流中上报通知时可供选择的审阅者。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-178">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span>
    - <span data-ttu-id="6cf0c-179">选择 "受限条件" 字段，通常是要应用于策略的敏感信息类型或关键字词典。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-179">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="6cf0c-180">如果您选择使用策略向导创建自定义策略，您将：</span><span class="sxs-lookup"><span data-stu-id="6cf0c-180">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="6cf0c-181">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-181">Give the policy a name and description.</span></span> <span data-ttu-id="6cf0c-182">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-182">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="6cf0c-183">选择要监督的用户或组，包括组织中的所有用户、特定用户和组，或者要排除的其他用户和组。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-183">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span>
    - <span data-ttu-id="6cf0c-184">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-184">Choose the reviewers for the policy.</span></span> <span data-ttu-id="6cf0c-185">审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-185">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="6cf0c-186">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-186">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="6cf0c-187">选择要扫描的通信通道，包括 Exchange、Microsoft 团队或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-187">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="6cf0c-188">如果您在 Microsoft 365 中配置了连接器，您还将选择扫描第三方源。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-188">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="6cf0c-189">选择要监视的通信方向，包括入站、出站或内部通信。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-189">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="6cf0c-190">定义通信合规性策略[条件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-190">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="6cf0c-191">您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-191">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="6cf0c-192">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-192">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="6cf0c-193">在此步骤中，您可以选择默认和自定义的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-193">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="6cf0c-194">从 "通信合规性策略向导" 中的现有自定义敏感信息类型或自定义关键字词典中进行选择。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-194">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="6cf0c-195">如果需要，可以在运行向导之前创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-195">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="6cf0c-196">您还可以在 "通信合规性策略" 向导中创建新的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-196">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="6cf0c-197">选择是否要启用冒犯性语言分类器。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-197">Choose if you'd like to enable the offensive language classifier.</span></span> <span data-ttu-id="6cf0c-198">此分类器检测在电子邮件正文中发送或接收的不正确语言。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-198">This  classifier detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="6cf0c-199">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-199">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="6cf0c-200">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-200">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="6cf0c-201">使用 "自定义策略" 向导时，选择 "使用模板或**提交**时**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-201">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="6cf0c-202">**您的策略已创建**页面将显示有关何时激活策略以及将捕获哪些通信的指南。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-202">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-5-optional-create-employee-notice-templates"></a><span data-ttu-id="6cf0c-203">步骤5（可选）：创建员工通知模板</span><span class="sxs-lookup"><span data-stu-id="6cf0c-203">Step 5 (optional): Create employee notice templates</span></span>

<span data-ttu-id="6cf0c-204">如果希望通过向关联的员工发送提醒通知来选择对策略警报做出响应，您需要在您的组织中至少创建一个通知模板。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-204">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="6cf0c-205">在将 "通知模板" 字段作为警报修正过程的一部分发送并为每个通信合规性策略创建自定义的通知模板之前，这些字段都是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-205">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="6cf0c-206">在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-206">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="6cf0c-207">在 Microsoft 365 合规性中心中，转到 "**通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-207">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="6cf0c-208">选择 "**通知模板**" 选项卡，然后选择 "**创建通知模板**"。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-208">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="6cf0c-209">在 "**修改通知模板**" 页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="6cf0c-209">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="6cf0c-210">通知模板名称（必需）</span><span class="sxs-lookup"><span data-stu-id="6cf0c-210">Notice template name (required)</span></span>
    - <span data-ttu-id="6cf0c-211">发件人（必需）</span><span class="sxs-lookup"><span data-stu-id="6cf0c-211">Send from (required)</span></span>
    - <span data-ttu-id="6cf0c-212">"抄送" 和 "密件抄送" （可选）</span><span class="sxs-lookup"><span data-stu-id="6cf0c-212">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="6cf0c-213">主题（必需）</span><span class="sxs-lookup"><span data-stu-id="6cf0c-213">Subject (required)</span></span>
    - <span data-ttu-id="6cf0c-214">邮件正文（必需）</span><span class="sxs-lookup"><span data-stu-id="6cf0c-214">Message body (required)</span></span>

5. <span data-ttu-id="6cf0c-215">选择 "**保存**" 以创建并保存 "通知" 模板。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-215">Select **Save** to create and save the notice template.</span></span>

## <a name="step-6-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="6cf0c-216">步骤6（可选）：测试通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="6cf0c-216">Step 6 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="6cf0c-217">创建通信合规性策略后，最好对其进行测试，以确保策略正确地强制实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-217">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="6cf0c-218">如果通信合规性策略包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-218">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="6cf0c-219">请确保为策略激活时间，以便捕获要测试的通信。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-219">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="6cf0c-220">按照以下步骤测试您的通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="6cf0c-220">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="6cf0c-221">打开电子邮件客户端或 Microsoft 团队，同时以您要测试的策略中定义的监督用户的身份登录。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-221">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="6cf0c-222">发送符合通信合规性策略中定义的条件的电子邮件或 Microsoft 团队聊天。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-222">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="6cf0c-223">此测试可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-223">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cf0c-224">所有源通道中的通信可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-224">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="6cf0c-225">以通信合规性策略中指定的审阅者的资格登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-225">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="6cf0c-226">导航到 "**通信合规性** > **警报**" 以查看策略的警报。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-226">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="6cf0c-227">使用修正控件修正警报，并验证是否正确解决了警报。</span><span class="sxs-lookup"><span data-stu-id="6cf0c-227">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>
