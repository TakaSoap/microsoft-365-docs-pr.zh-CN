---
title: 添加用户并分配许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 每个团队成员都需要用户帐户，然后才能登录和访问 Microsoft 365 商业版。了解如何添加用户和分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: aaba152e73fc7284f54a9f307783a66fb055a55c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394095"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="0083c-104">同时添加用户和分配许可证</span><span class="sxs-lookup"><span data-stu-id="0083c-104">Add users and assign licenses at the same time</span></span>

<span data-ttu-id="0083c-p102">团队中的每个人都需要一个用户账户，然后才能登录和访问 [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)。添加用户账户的最简单方法是在 Microsoft 365 管理中心中逐一添加。在完成该步骤后，用户就拥有了 Microsoft 365 的许可证、登录凭证和 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0083c-p102">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business). The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center. After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0083c-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="0083c-108">Before you begin</span></span>

<span data-ttu-id="0083c-109">你必须是全局管理员、许可证管理员或用户管理员才能添加用户并分配许可证。</span><span class="sxs-lookup"><span data-stu-id="0083c-109">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="0083c-110">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0083c-110">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-user-in-the-admin-simplified-view"></a><span data-ttu-id="0083c-111">在管理员简化视图中添加用户</span><span class="sxs-lookup"><span data-stu-id="0083c-111">Add a user in the admin simplified view</span></span>

<span data-ttu-id="0083c-112">如果在管理中心看到此页面，则位于 **管理员简化视图** 上。</span><span class="sxs-lookup"><span data-stu-id="0083c-112">If you're seeing this page in the admin center, you're on the **admin simplified view**.</span></span> <span data-ttu-id="0083c-113">请按照以下步骤添加用户。</span><span class="sxs-lookup"><span data-stu-id="0083c-113">Follow the steps below to add a user.</span></span>

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="屏幕截图: 简化管理中心视图":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0083c-115">请转到位于 <https://admin.microsoft.com> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="0083c-115">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0083c-116">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="0083c-116">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0083c-117">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="0083c-117">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="0083c-118">选择 **“为其他人员创建账户”**。</span><span class="sxs-lookup"><span data-stu-id="0083c-118">Select **Create an account for another person**.</span></span>
3. <span data-ttu-id="0083c-119">在 **“添加用户帐户”** 页面，填写要用于登录的名字和姓氏、显示名称以及用户名。</span><span class="sxs-lookup"><span data-stu-id="0083c-119">On the **Add a user account** page, fill in the first and last name, display name, and username they'll use to sign in.</span></span>
4. <span data-ttu-id="0083c-120">在 **“最多 5 个电子邮件地址”** 文本框中添加用户电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0083c-120">Add the email address of the user in the **Up to 5 email addresses...** text box.</span></span> <span data-ttu-id="0083c-121">这将确保新用户获得其登录 Microsoft 365 服务时所需的信息。</span><span class="sxs-lookup"><span data-stu-id="0083c-121">This will make sure the new user gets the information they need to sign into Microsoft 365 services.</span></span>
5. <span data-ttu-id="0083c-122">若要保存此信息，请选择 **“添加用户”** 和 **“下载登录信息”**。</span><span class="sxs-lookup"><span data-stu-id="0083c-122">Select **Add user** and **Download sign-in info** if you want to save this info.</span></span>

## <a name="watch-add-users-in-the-dashboard-view"></a><span data-ttu-id="0083c-123">监视: 在仪表板视图中添加用户</span><span class="sxs-lookup"><span data-stu-id="0083c-123">Watch: Add users in the dashboard view</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="0083c-124">视频中使用的步骤显示添加用户的不同起点，但剩余步骤与以下程序相同。</span><span class="sxs-lookup"><span data-stu-id="0083c-124">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a><span data-ttu-id="0083c-125">在仪表板视图中一次添加一个用户</span><span class="sxs-lookup"><span data-stu-id="0083c-125">Add users one at a time in the dashboard view</span></span>

:::image type="content" source="../../media/classic-admin-center.png" alt-text="屏幕截图: 管理中心仪表板视图":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0083c-127">转到位于 <https://admin.microsoft.com> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="0083c-127">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0083c-128">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="0083c-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0083c-129">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="0083c-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="0083c-130">转到“**用户**” > “**活动用户**”，然后选择“**添加用户**”。</span><span class="sxs-lookup"><span data-stu-id="0083c-130">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="0083c-131">在“**设置基本信息**”窗格中，填写基本用户信息，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0083c-131">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="0083c-132">**姓名** 填写名字和姓氏、显示名和用户名。</span><span class="sxs-lookup"><span data-stu-id="0083c-132">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="0083c-p106">**域** 为用户的账户选择域。例如，如果用户的用户名是 Jakob，且该域为 contoso.com，他们将通过使用 jakob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="0083c-p106">**Domain** Choose the domain for the user's account. For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="0083c-135">**密码设置** 选择使用自动生成的密码或为用户创建你自己的强密码。</span><span class="sxs-lookup"><span data-stu-id="0083c-135">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="0083c-136">用户必须在 90 天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="0083c-136">The user must change their password after 90 days.</span></span> <span data-ttu-id="0083c-137">也可以选择 **要求此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="0083c-137">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="0083c-138">选择是否希望添加用户时通过电子邮件发送密码。</span><span class="sxs-lookup"><span data-stu-id="0083c-138">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="0083c-139">在“**分配产品许可证**”窗格中，为用户选择位置和相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="0083c-139">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="0083c-140">如果没有可用的许可证，仍然可以添加用户并购买其他许可证。</span><span class="sxs-lookup"><span data-stu-id="0083c-140">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="0083c-141">展开“**应用**”并选择或取消选择应用，以限制用户拥有许可证的应用。</span><span class="sxs-lookup"><span data-stu-id="0083c-141">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="0083c-142">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0083c-142">Select **Next**.</span></span>
5. <span data-ttu-id="0083c-143">在“**可选设置**”窗格中，展开“**角色**”以使此用户成为管理员。展开“**个人资料信息**”以添加有关用户的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0083c-143">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="0083c-144">选择“**下一步**”，查看新用户的设置，按自己的喜好更改，然后依次选择“**完成添加**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="0083c-144">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="0083c-145">同时添加多个用户</span><span class="sxs-lookup"><span data-stu-id="0083c-145">Add multiple users at the same time</span></span>

<span data-ttu-id="0083c-146">可以使用以下任意方法同时添加多个用户：</span><span class="sxs-lookup"><span data-stu-id="0083c-146">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="0083c-147">**使用电子表格批量添加人员。**</span><span class="sxs-lookup"><span data-stu-id="0083c-147">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="0083c-148">请参阅 [同时添加若干用户](../../enterprise/add-several-users-at-the-same-time.md)。</span><span class="sxs-lookup"><span data-stu-id="0083c-148">See [Add several users at the same time](../../enterprise/add-several-users-at-the-same-time.md).</span></span>
- <span data-ttu-id="0083c-149">**自动添加帐户并分配许可证。**</span><span class="sxs-lookup"><span data-stu-id="0083c-149">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="0083c-150">请参阅 [通过 Microsoft 365 PowerShell 创建用户账户](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="0083c-150">See [Create user accounts with Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="0083c-151">如果可以熟练使用 Windows PowerShell cmdlet，请选择此方法。</span><span class="sxs-lookup"><span data-stu-id="0083c-151">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="0083c-152">**使用 ActiveDirectory？**</span><span class="sxs-lookup"><span data-stu-id="0083c-152">**Using ActiveDirectory?**</span></span> <span data-ttu-id="0083c-153">[设置 Microsoft 365 的目录同步](../../enterprise/set-up-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="0083c-153">[Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md).</span></span> <span data-ttu-id="0083c-154">在 Microsoft 365 中，使用 Azure AD Connect 工具复制 Active Directory 用户帐户（和其他 Active Directory 对象）。</span><span class="sxs-lookup"><span data-stu-id="0083c-154">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="0083c-155">同步只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0083c-155">The sync only adds the user accounts.</span></span> <span data-ttu-id="0083c-156">你必须向同步用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="0083c-156">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="0083c-157">**从 Exchange 迁移？**</span><span class="sxs-lookup"><span data-stu-id="0083c-157">**Migrating from Exchange?**</span></span> <span data-ttu-id="0083c-158">请参阅 [将多个电子邮件帐户迁移到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="0083c-158">See [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="0083c-159">通过使用直接转换、分阶段或混合 Exchange 方法将多个邮箱迁移到 Microsoft 365 时，将在迁移期间自动添加用户。</span><span class="sxs-lookup"><span data-stu-id="0083c-159">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="0083c-160">迁移只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0083c-160">The migration only adds the user accounts.</span></span> <span data-ttu-id="0083c-161">你必须向用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="0083c-161">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="0083c-162">如果不向用户分配许可证，则其邮箱在 30 天的宽限期后将处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="0083c-162">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="0083c-163">了解如何在 Microsoft 365 管理中心内 [向用户分配许可证](../manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="0083c-163">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0083c-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0083c-164">Next steps</span></span>

<span data-ttu-id="0083c-165">添加用户后，你收到一封来自 Microsoft 的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="0083c-165">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="0083c-166">该电子邮件包含对应人员的用户 ID 和密码，使其可以登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0083c-166">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="0083c-167">使用常规流程告知新密码。</span><span class="sxs-lookup"><span data-stu-id="0083c-167">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="0083c-168">与新用户共享 [员工快速入门指南](../../business-video/employee-quick-setup.md)，以设置一些内容，例如怎样从 [在电脑或 Mac 上下载和安装 Office 应用](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何 [在移动设备上设置 Office 应用和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="0083c-168">Share the [Employee quickstart guide](../../business-video/employee-quick-setup.md) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="0083c-169">相关内容</span><span class="sxs-lookup"><span data-stu-id="0083c-169">Related content</span></span>

<span data-ttu-id="0083c-170">[向 Microsoft 365 添加新员工](add-new-employee.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="0083c-170">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="0083c-171">[同时向 Microsoft 365 网站添加若干用户](../../enterprise/add-several-users-at-the-same-time.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="0083c-171">[Add several users at the same time to Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (article)</span></span>\
<span data-ttu-id="0083c-172">[在 Microsoft 365 网站中还原用户](restore-user.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="0083c-172">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="0083c-173">[向用户分配许可证](../manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="0083c-173">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="0083c-174">[从组织删除用户](delete-a-user.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="0083c-174">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
