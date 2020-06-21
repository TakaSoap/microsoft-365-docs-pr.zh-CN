---
title: 单独或批量添加用户
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: 了解如何将用户添加到 Microsoft 365，一次向一个或多个用户添加一个 CSV 文件。
ms.openlocfilehash: af160b78317171bec98dcfa3d5877b53560f75a2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780657"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="f230e-103">单独或批量添加用户</span><span class="sxs-lookup"><span data-stu-id="f230e-103">Add users individually or in bulk</span></span>

<span data-ttu-id="f230e-104">团队中的人员每个人都需要用户帐户，才能登录并访问[Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395)。</span><span class="sxs-lookup"><span data-stu-id="f230e-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="f230e-105">添加用户帐户最简单的方法是在 Microsoft 365 管理中心中一次添加一个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f230e-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f230e-106">执行此步骤后，你的用户将拥有 Microsoft 365 许可证、登录凭据和 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f230e-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f230e-107">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="f230e-107">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f230e-108">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-108">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="f230e-109">在 "**设置基础知识**" 窗格中，填写以下信息，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-109">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="f230e-110">**名称**填写第一个、最后一个、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="f230e-110">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="f230e-111">**域**例如，如果用户的用户名是 Dewei，而他的域 contoso.com，他将通过键入 jakob@contoso.com 登录。</span><span class="sxs-lookup"><span data-stu-id="f230e-111">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f230e-112">**密码设置**选择 "使用自动生成的密码" 或 "为用户创建您自己的强密码"。</span><span class="sxs-lookup"><span data-stu-id="f230e-112">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="f230e-113">用户需要在 90 天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="f230e-113">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="f230e-114">或者，您可以选择**要求此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="f230e-114">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="f230e-115">选择是否要在添加用户后通过电子邮件发送密码。</span><span class="sxs-lookup"><span data-stu-id="f230e-115">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="f230e-116">在 "**分配产品许可证**" 窗格中，选择该用户的位置和相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="f230e-116">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="f230e-117">如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="f230e-117">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="f230e-118">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f230e-118">Select **Next**.</span></span>

5. <span data-ttu-id="f230e-119">如果要将此用户设为管理员，请在 "**可选设置**" 页中展开 "**角色**"，如果想要添加有关用户的其他信息，请展开 "**配置文件信息**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-119">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="f230e-120">选择 "**下一步**"，查看新用户的设置，进行任何所需的更改，然后选择 "**完成添加**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-120">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="f230e-121">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="f230e-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="f230e-122">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-122">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="f230e-123">在 "**新建用户**" 窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="f230e-123">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="f230e-124">完成后，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-124">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="f230e-125">**姓名** 填写名字、姓氏、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="f230e-125">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="f230e-126">**域**例如，如果用户的用户名是 Dewei，而他的域 contoso.com，他将通过键入 jakob@contoso.com 登录。</span><span class="sxs-lookup"><span data-stu-id="f230e-126">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f230e-127">**联系信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="f230e-127">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="f230e-128">**密码** 使用自动生成的密码或展开以为用户指定强密码。</span><span class="sxs-lookup"><span data-stu-id="f230e-128">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="f230e-129">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="f230e-129">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="f230e-130">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="f230e-130">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="f230e-131">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="f230e-131">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="f230e-132">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="f230e-132">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="f230e-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="f230e-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f230e-134">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="f230e-134">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="f230e-135">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-135">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="f230e-136">在 "**新建用户**" 窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="f230e-136">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="f230e-137">完成后，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="f230e-137">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="f230e-138">**姓名** 填写名字、姓氏、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="f230e-138">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="f230e-139">**域**例如，如果用户的用户名是 Dewei，而他的域 contoso.com，他将通过键入 jakob@contoso.com 登录。</span><span class="sxs-lookup"><span data-stu-id="f230e-139">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f230e-140">**联系信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="f230e-140">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="f230e-141">**密码** 使用自动生成的密码或展开以为用户指定强密码。</span><span class="sxs-lookup"><span data-stu-id="f230e-141">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="f230e-142">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="f230e-142">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="f230e-143">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="f230e-143">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="f230e-144">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="f230e-144">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="f230e-145">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="f230e-145">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="f230e-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="f230e-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="f230e-147">添加用户后，将收到一封来自 Microsoft Online Services 团队的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f230e-147">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="f230e-148">电子邮件将包含用户的用户 ID 和密码，以便他们可以登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f230e-148">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="f230e-149">您需要告诉新用户其 Microsoft 365 登录信息。</span><span class="sxs-lookup"><span data-stu-id="f230e-149">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="f230e-150">使用正常的过程传递新密码。</span><span class="sxs-lookup"><span data-stu-id="f230e-150">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="f230e-151">如果通过迁移邮箱创建用户，将需要通过分配许可证来激活用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f230e-151">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="f230e-152">如果不向用户分配许可证，则在30天宽限期后将禁用其邮箱。</span><span class="sxs-lookup"><span data-stu-id="f230e-152">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="f230e-153">请参阅如何使用 Microsoft 365 管理中心[将许可证分配给用户](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)。</span><span class="sxs-lookup"><span data-stu-id="f230e-153">See how to [assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="f230e-154">视频：添加和管理管理中心中的用户</span><span class="sxs-lookup"><span data-stu-id="f230e-154">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="f230e-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f230e-155">Next steps</span></span>

<span data-ttu-id="f230e-156">与新用户共享[员工快速入门指南](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，实现快速使用，如[电脑或 Mac 上的 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)、[Office 移动应用](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="f230e-156">Share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set things up, like [Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [Office mobile apps](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="f230e-157">需要帮助？</span><span class="sxs-lookup"><span data-stu-id="f230e-157">Need help?</span></span>

<span data-ttu-id="f230e-158">[请联系 Microsoft 365 以寻求商业支持](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="f230e-158">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="f230e-159">有成百上千个用户需要添加？</span><span class="sxs-lookup"><span data-stu-id="f230e-159">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="f230e-160">若要同时添加多个用户，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f230e-160">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="f230e-161">**使用电子表格批量添加用户。**</span><span class="sxs-lookup"><span data-stu-id="f230e-161">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="f230e-162">请参阅[同时添加多个用户](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)。</span><span class="sxs-lookup"><span data-stu-id="f230e-162">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="f230e-163">**自动添加帐户并分配许可证。**</span><span class="sxs-lookup"><span data-stu-id="f230e-163">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="f230e-164">请参阅[Create user accounts With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f230e-164">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="f230e-165">如果可以熟练使用 Windows PowerShell cmdlet，请选择此方法。</span><span class="sxs-lookup"><span data-stu-id="f230e-165">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="f230e-166">**使用 ActiveDirectory？**</span><span class="sxs-lookup"><span data-stu-id="f230e-166">**Using ActiveDirectory?**</span></span> <span data-ttu-id="f230e-167">[设置 Office 365 的目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="f230e-167">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="f230e-168">使用 Azure AD Connect 工具复制 Office 365 中的 Active Directory 用户帐户（和其他 Active Directory 对象）。</span><span class="sxs-lookup"><span data-stu-id="f230e-168">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="f230e-169">同步只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f230e-169">The sync only adds the user accounts.</span></span> <span data-ttu-id="f230e-170">需要向已同步的用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="f230e-170">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="f230e-171">**从 Exchange 迁移？**</span><span class="sxs-lookup"><span data-stu-id="f230e-171">**Migrating from Exchange?**</span></span> <span data-ttu-id="f230e-172">[将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="f230e-172">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="f230e-173">当您使用直接转换、暂存或混合 Exchange 方法将多个邮箱迁移到 Microsoft 365 时，将自动在迁移过程中添加用户。</span><span class="sxs-lookup"><span data-stu-id="f230e-173">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="f230e-174">迁移只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f230e-174">The migration only adds the user accounts.</span></span> <span data-ttu-id="f230e-175">需要向用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="f230e-175">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f230e-176">相关文章</span><span class="sxs-lookup"><span data-stu-id="f230e-176">Related articles</span></span>

[<span data-ttu-id="f230e-177">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="f230e-177">Assign licenses to users</span></span>](../manage/assign-licenses-to-users.md)

[<span data-ttu-id="f230e-178">将新员工添加到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f230e-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="f230e-179">从组织中删除用户</span><span class="sxs-lookup"><span data-stu-id="f230e-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="f230e-180">在 Microsoft 365 中还原用户</span><span class="sxs-lookup"><span data-stu-id="f230e-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="f230e-181">同时将多个用户添加到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f230e-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

