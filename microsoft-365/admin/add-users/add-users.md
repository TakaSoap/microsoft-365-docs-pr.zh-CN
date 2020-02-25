---
title: 将用户逐个或批量添加到 Office 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: 了解如何将用户添加到 Office 365，一次向一个或多个用户添加一个 CSV 文件。
ms.openlocfilehash: 708bce2cb5a2c1b6a621bffc3ce56a2744bb518d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238180"
---
# <a name="add-users-individually-or-in-bulk-to-office-365"></a><span data-ttu-id="976cd-103">将用户逐个或批量添加到 Office 365</span><span class="sxs-lookup"><span data-stu-id="976cd-103">Add users individually or in bulk to Office 365</span></span>

<span data-ttu-id="976cd-104">你团队中的人员每人需要一个用户帐户，才能登录并访问 [Office 365 商业版](https://go.microsoft.com/fwlink/?LinkID=519395)。</span><span class="sxs-lookup"><span data-stu-id="976cd-104">The people on your team each need a user account before they can sign in and access [Office 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="976cd-105">添加用户帐户最简单的方法是在 Microsoft 365 管理中心中一次添加一个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="976cd-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="976cd-106">执行此步骤后，你的用户将具有 Office 365 许可证、登录凭据和 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="976cd-106">After you do this step, your users will have Office 365 licenses, sign in credentials, and Office 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="976cd-107">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="976cd-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="976cd-108">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="976cd-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="976cd-109">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="976cd-110">在 "**设置基础知识**" 窗格中，填写以下信息，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="976cd-111">**名称**填写第一个、最后一个、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="976cd-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="976cd-112">**域** 例如，如果用户名为 Dewei，其域为 contoso.com，则他将通过键入 Dewei@contoso.com 来登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="976cd-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="976cd-113">**密码设置**选择 "使用自动生成的密码" 或 "为用户创建您自己的强密码"。</span><span class="sxs-lookup"><span data-stu-id="976cd-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="976cd-114">用户需要在 90 天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="976cd-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="976cd-115">或者，您可以选择**要求此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="976cd-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="976cd-116">选择是否要在添加用户后通过电子邮件发送密码。</span><span class="sxs-lookup"><span data-stu-id="976cd-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="976cd-117">在 "**分配产品许可证**" 窗格中，选择该用户的位置和相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="976cd-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="976cd-118">如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="976cd-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="976cd-119">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="976cd-119">Select **Next**.</span></span>

5. <span data-ttu-id="976cd-120">如果要将此用户设为管理员，请在 "**可选设置**" 页中展开 "**角色**"，如果想要添加有关用户的其他信息，请展开 "**配置文件信息**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="976cd-121">选择 "**下一步**"，查看新用户的设置，进行任何所需的更改，然后选择 "**完成添加**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="976cd-122">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="976cd-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="976cd-123">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="976cd-124">在 "**新建用户**" 窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="976cd-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="976cd-125">完成后，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="976cd-126">**姓名** 填写名字、姓氏、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="976cd-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="976cd-127">**域** 例如，如果用户名为 Dewei，其域为 contoso.com，则他将通过键入 Dewei@contoso.com 来登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="976cd-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="976cd-128">**联系信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="976cd-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="976cd-129">**密码** 使用自动生成的密码或展开以为用户指定强密码。</span><span class="sxs-lookup"><span data-stu-id="976cd-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="976cd-p105">用户需要在 90 天后更改密码。也可以选择 **允许此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="976cd-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="976cd-132">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="976cd-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="976cd-p106">**产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="976cd-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="976cd-135">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="976cd-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="976cd-136">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="976cd-137">在 "**新建用户**" 窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="976cd-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="976cd-138">完成后，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="976cd-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="976cd-139">**姓名** 填写名字、姓氏、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="976cd-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="976cd-140">**域** 例如，如果用户名为 Dewei，其域为 contoso.com，则他将通过键入 Dewei@contoso.com 来登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="976cd-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="976cd-141">**联系信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="976cd-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="976cd-142">**密码** 使用自动生成的密码或展开以为用户指定强密码。</span><span class="sxs-lookup"><span data-stu-id="976cd-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="976cd-p108">用户需要在 90 天后更改密码。也可以选择 **允许此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="976cd-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="976cd-145">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="976cd-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="976cd-p109">**产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="976cd-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="976cd-148">添加用户后，将收到一封来自 Microsoft Online Services 团队的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="976cd-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="976cd-149">该电子邮件包含对应用户的Office 365用户 ID 和密码，使其可以登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="976cd-149">The email will contain the person's Office 365 user ID and password so they can sign in to Office 365.</span></span> <span data-ttu-id="976cd-150">需要告知新用户其 Office 365 登录信息。</span><span class="sxs-lookup"><span data-stu-id="976cd-150">You need to tell your new user about their Office 365 sign in information.</span></span> <span data-ttu-id="976cd-151">使用正常的过程传递新密码。</span><span class="sxs-lookup"><span data-stu-id="976cd-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="976cd-152">如果通过迁移邮箱创建用户，将需要通过分配许可证来激活 Office 365 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="976cd-152">If you create users by migrating mail boxes, you will need to activate Office 365 user accounts by assigning licenses.</span></span> <span data-ttu-id="976cd-153">如果不向用户分配许可证，则在30天宽限期后将禁用其邮箱。</span><span class="sxs-lookup"><span data-stu-id="976cd-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="976cd-154">请参阅如何使用 Microsoft 365 管理中心[将许可证分配给用户](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="976cd-154">See how to [assign licenses to users](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="976cd-155">视频：添加和管理管理中心中的用户</span><span class="sxs-lookup"><span data-stu-id="976cd-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="976cd-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="976cd-156">Next steps</span></span>

<span data-ttu-id="976cd-157">与新用户共享[员工快速入门指南](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx)，实现快速使用，如[电脑或 Mac 上的 Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)、[Office 移动应用](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="976cd-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="976cd-158">是否需要帮助？</span><span class="sxs-lookup"><span data-stu-id="976cd-158">Need help?</span></span>

<span data-ttu-id="976cd-159">[联系 Office 365 获取商业版支持人员](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="976cd-159">[Contact Office 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="976cd-160">有成百上千个用户需要添加？</span><span class="sxs-lookup"><span data-stu-id="976cd-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="976cd-161">若要同时添加多个用户，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="976cd-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="976cd-162">**使用电子表格批量添加用户。**</span><span class="sxs-lookup"><span data-stu-id="976cd-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="976cd-163">请参阅[同时添加多个用户](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)。</span><span class="sxs-lookup"><span data-stu-id="976cd-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="976cd-164">**自动添加帐户并分配许可证。**</span><span class="sxs-lookup"><span data-stu-id="976cd-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="976cd-165">请参阅[Create user accounts With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="976cd-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="976cd-166">如果可以熟练使用 Windows PowerShell cmdlet，请选择此方法。</span><span class="sxs-lookup"><span data-stu-id="976cd-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="976cd-167">**使用 ActiveDirectory？**</span><span class="sxs-lookup"><span data-stu-id="976cd-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="976cd-168">[设置 Office 365 的目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="976cd-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="976cd-169">使用 Azure AD Connect 工具复制 Office 365 中的 Active Directory 用户帐户（和其他 Active Directory 对象）。</span><span class="sxs-lookup"><span data-stu-id="976cd-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="976cd-170">同步只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="976cd-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="976cd-171">需要向已同步的用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="976cd-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="976cd-172">**从 Exchange 迁移？**</span><span class="sxs-lookup"><span data-stu-id="976cd-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="976cd-173">[将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="976cd-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="976cd-174">通过使用直接转换、分阶段或混合 Exchange 方法将多个邮箱迁移到 Office 365 时，将在迁移期间自动添加用户。</span><span class="sxs-lookup"><span data-stu-id="976cd-174">When you migrate multiple mailboxes to Office 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="976cd-175">迁移只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="976cd-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="976cd-176">需要向用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="976cd-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="976cd-177">相关文章</span><span class="sxs-lookup"><span data-stu-id="976cd-177">Related articles</span></span>

[<span data-ttu-id="976cd-178">向 Office 365 添加新员工</span><span class="sxs-lookup"><span data-stu-id="976cd-178">Add a new employee to Office 365</span></span>](add-new-employee.md)

[<span data-ttu-id="976cd-179">从组织中删除用户</span><span class="sxs-lookup"><span data-stu-id="976cd-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="976cd-180">在 Office 365 中还原用户</span><span class="sxs-lookup"><span data-stu-id="976cd-180">Restore a user in Office 365</span></span>](restore-user.md)

[<span data-ttu-id="976cd-181">同时将多个用户添加到 Office 365</span><span class="sxs-lookup"><span data-stu-id="976cd-181">Add several users at the same time to Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)


