---
title: 添加用户并分配许可证
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
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何同时添加用户并将许可证分配给 Microsoft 365。
ms.date: 07/01/2020
ms.openlocfilehash: 016c98fc93bfa1a92274a5b991cf8adbd1131bc9
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015883"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="d1f89-103">同时添加用户和分配许可证</span><span class="sxs-lookup"><span data-stu-id="d1f89-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d1f89-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="d1f89-104">The admin center is changing.</span></span> <span data-ttu-id="d1f89-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="d1f89-106">团队中的人员每个人都需要用户帐户，才能登录并访问[Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="d1f89-107">添加用户帐户最简单的方法是在 Microsoft 365 管理中心中一次添加一个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d1f89-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d1f89-108">执行此步骤后，你的用户将拥有 Microsoft 365 许可证、登录凭据和 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="d1f89-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d1f89-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="d1f89-109">Before you begin</span></span>

<span data-ttu-id="d1f89-110">您必须是全局、许可证或用户管理员才能添加用户并分配许可证。</span><span class="sxs-lookup"><span data-stu-id="d1f89-110">You must be a Global, License, or a User admin to add users and assign licenses.</span></span> <span data-ttu-id="d1f89-111">有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="d1f89-112">手表：在管理中心添加用户</span><span class="sxs-lookup"><span data-stu-id="d1f89-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="d1f89-113">视频中使用的步骤显示了用于添加用户的不同起点，但其余步骤与以下过程相同。</span><span class="sxs-lookup"><span data-stu-id="d1f89-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="d1f89-114">一次添加一个用户</span><span class="sxs-lookup"><span data-stu-id="d1f89-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d1f89-115">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="d1f89-115">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="d1f89-116">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="d1f89-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="d1f89-117">在 "**设置基础知识**" 窗格中，填写基本用户信息，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d1f89-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="d1f89-118">**名称**填写姓氏和名字、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="d1f89-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="d1f89-119">**域**为用户帐户选择域。</span><span class="sxs-lookup"><span data-stu-id="d1f89-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="d1f89-120">例如，如果用户的用户名为 Dewei，并且该域为 contoso.com，则他们将使用 jakob@contoso.com 登录。</span><span class="sxs-lookup"><span data-stu-id="d1f89-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="d1f89-121">**密码设置**选择使用自动生成的密码或为用户创建您自己的强密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="d1f89-122">用户必须在90天后更改其密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="d1f89-123">或者，您可以选择**要求此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="d1f89-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="d1f89-124">选择是否要在添加用户时通过电子邮件发送密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="d1f89-125">在 "**分配产品许可证**" 窗格中，选择该用户的位置和相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="d1f89-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="d1f89-126">如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="d1f89-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="d1f89-127">展开 "**应用程序**"，然后选择或取消选择 "应用"，以限制用户拥有许可证的应用。</span><span class="sxs-lookup"><span data-stu-id="d1f89-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="d1f89-128">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d1f89-128">Select **Next**.</span></span>
5. <span data-ttu-id="d1f89-129">在 "**可选设置**" 窗格中，展开 "**角色**" 以使此用户成为管理员。展开 "**配置文件信息**" 以添加有关用户的其他信息。</span><span class="sxs-lookup"><span data-stu-id="d1f89-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="d1f89-130">选择 "**下一步**"，查看新用户的设置，进行任何所需的更改，然后选择 "**完成添加**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="d1f89-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d1f89-131">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="d1f89-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>
2. <span data-ttu-id="d1f89-132">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="d1f89-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="d1f89-133">在 "**新建用户**" 窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="d1f89-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="d1f89-134">完成后，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="d1f89-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="d1f89-135">**姓名** 填写名字、姓氏、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="d1f89-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="d1f89-136">**域**例如，如果用户的用户名为 Dewei，并且该域为 contoso.com，则他们将通过键入 jakob@contoso.com 登录到。</span><span class="sxs-lookup"><span data-stu-id="d1f89-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="d1f89-137">**联系信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="d1f89-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="d1f89-138">**密码**使用自动生成的密码或展开以指定用户的强密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="d1f89-139">他们必须在90天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-139">They must change their password after 90 days.</span></span> <span data-ttu-id="d1f89-140">也可以选择 **允许此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="d1f89-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="d1f89-141">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="d1f89-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="d1f89-p109">**产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="d1f89-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d1f89-144">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="d1f89-144">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>
2. <span data-ttu-id="d1f89-145">转到 "**用户** > **活动用户**"，然后选择 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="d1f89-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="d1f89-146">在 "**新建用户**" 窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="d1f89-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="d1f89-147">完成后，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="d1f89-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="d1f89-148">**姓名** 填写名字、姓氏、显示名称和用户名。</span><span class="sxs-lookup"><span data-stu-id="d1f89-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="d1f89-149">**域**例如，如果用户的用户名为 Dewei，并且该域为 contoso.com，则他们将通过键入 jakob@contoso.com 登录到。</span><span class="sxs-lookup"><span data-stu-id="d1f89-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="d1f89-150">**联系信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="d1f89-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="d1f89-151">**密码**使用自动生成的密码或展开以指定用户的强密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="d1f89-152">他们必须在90天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-152">They must change their password after 90 days.</span></span> <span data-ttu-id="d1f89-153">也可以选择 **允许此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="d1f89-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="d1f89-154">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="d1f89-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="d1f89-p112">**产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="d1f89-p112">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="d1f89-157">同时添加多个用户</span><span class="sxs-lookup"><span data-stu-id="d1f89-157">Add multiple users at the same time</span></span>

<span data-ttu-id="d1f89-158">您可以使用以下任何一种方法同时添加多个用户：</span><span class="sxs-lookup"><span data-stu-id="d1f89-158">You can use any of the following methods to add multiple users at the same time:</span></span>
  
- <span data-ttu-id="d1f89-159">**使用电子表格批量添加用户。**</span><span class="sxs-lookup"><span data-stu-id="d1f89-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="d1f89-160">请参阅[同时添加多个用户](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-160">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
- <span data-ttu-id="d1f89-161">**自动添加帐户并分配许可证。**</span><span class="sxs-lookup"><span data-stu-id="d1f89-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="d1f89-162">请参阅[Create user accounts With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-162">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="d1f89-163">如果可以熟练使用 Windows PowerShell cmdlet，请选择此方法。</span><span class="sxs-lookup"><span data-stu-id="d1f89-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="d1f89-164">**使用 ActiveDirectory？**</span><span class="sxs-lookup"><span data-stu-id="d1f89-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="d1f89-165">[设置 Office 365 的目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-165">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="d1f89-166">使用 Azure AD Connect 工具在 Microsoft 365 中复制 Active Directory 用户帐户（和其他 Active Directory 对象）。</span><span class="sxs-lookup"><span data-stu-id="d1f89-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="d1f89-167">同步只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d1f89-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="d1f89-168">您必须先将许可证分配给已同步的用户，然后才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="d1f89-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="d1f89-169">**从 Exchange 迁移？**</span><span class="sxs-lookup"><span data-stu-id="d1f89-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="d1f89-170">查看[将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-170">See [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="d1f89-171">当您使用直接转换、暂存或混合 Exchange 方法将多个邮箱迁移到 Microsoft 365 时，将自动在迁移过程中添加用户。</span><span class="sxs-lookup"><span data-stu-id="d1f89-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="d1f89-172">迁移只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d1f89-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="d1f89-173">您必须向用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="d1f89-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="d1f89-174">如果不向用户分配许可证，则在30天宽限期后将禁用其邮箱。</span><span class="sxs-lookup"><span data-stu-id="d1f89-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="d1f89-175">了解如何[将许可证分配给](../manage/assign-licenses-to-users.md)Microsoft 365 管理中心中的用户。</span><span class="sxs-lookup"><span data-stu-id="d1f89-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1f89-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d1f89-176">Next steps</span></span>

<span data-ttu-id="d1f89-177">添加用户后，会收到 Microsoft 发送的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="d1f89-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="d1f89-178">电子邮件包含用户的用户 ID 和密码，以便他们可以登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d1f89-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="d1f89-179">使用正常的过程传递新密码。</span><span class="sxs-lookup"><span data-stu-id="d1f89-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="d1f89-180">与新用户共享[员工快速入门指南](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，以设置内容，如如何[在电脑或 Mac 上下载和安装 office 应用](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何[在移动设备上设置 office 应用和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="d1f89-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="d1f89-181">相关内容</span><span class="sxs-lookup"><span data-stu-id="d1f89-181">Related content</span></span>

<span data-ttu-id="d1f89-182">[将新员工添加到 Microsoft 365](add-new-employee.md) （文章） </span><span class="sxs-lookup"><span data-stu-id="d1f89-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="d1f89-183">[同时将多个用户添加到 Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) （文章） </span><span class="sxs-lookup"><span data-stu-id="d1f89-183">[Add several users at the same time to Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) (article)</span></span>\
<span data-ttu-id="d1f89-184">[在 Microsoft 365 （文章）中还原用户](restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="d1f89-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="d1f89-185">[向用户分配许可证](../manage/assign-licenses-to-users.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="d1f89-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="d1f89-186">[从组织中删除用户](delete-a-user.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="d1f89-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>