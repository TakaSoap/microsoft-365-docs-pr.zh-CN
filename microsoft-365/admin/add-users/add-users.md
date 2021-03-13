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
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何同时添加用户和为 Microsoft 365 分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 71695c47bbc34a94f0040c37dd0c0bb0ab72fbba
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741409"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="7c36e-103">同时添加用户和分配许可证</span><span class="sxs-lookup"><span data-stu-id="7c36e-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7c36e-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="7c36e-104">The admin center is changing.</span></span> <span data-ttu-id="7c36e-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="7c36e-106">团队中的每个人都需要用户帐户，然后他们才能登录和访问 [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="7c36e-107">添加用户帐户的最简单方法是在 Microsoft 365 管理中心一次添加一个帐户。</span><span class="sxs-lookup"><span data-stu-id="7c36e-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7c36e-108">执行此步骤后，你的用户拥有 Microsoft 365 许可证、登录凭据和 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="7c36e-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7c36e-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="7c36e-109">Before you begin</span></span>

<span data-ttu-id="7c36e-110">你必须是全局管理员、许可证管理员或用户管理员才能添加用户并分配许可证。</span><span class="sxs-lookup"><span data-stu-id="7c36e-110">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="7c36e-111">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="7c36e-112">观看：在管理中心中添加用户</span><span class="sxs-lookup"><span data-stu-id="7c36e-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="7c36e-113">视频中使用的步骤显示添加用户的不同起点，但剩余步骤与以下程序相同。</span><span class="sxs-lookup"><span data-stu-id="7c36e-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="7c36e-114">逐个添加用户</span><span class="sxs-lookup"><span data-stu-id="7c36e-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7c36e-115">转到位于 <https://admin.microsoft.com> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="7c36e-115">Go to the admin center at <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="7c36e-116">转到“**用户**”>“**活动用户**”，然后选择“**添加用户**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="7c36e-117">在“**设置基本信息**”窗格中，填写基本用户信息，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="7c36e-118">**姓名** 填写名字和姓氏、显示名和用户名。</span><span class="sxs-lookup"><span data-stu-id="7c36e-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="7c36e-119">**域** 为用户帐户选择域。</span><span class="sxs-lookup"><span data-stu-id="7c36e-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="7c36e-120">例如，如果用户的用户名是 Jakob，并且该域为 contoso.com，他们将通过使用 jakob@contoso.com 登录。</span><span class="sxs-lookup"><span data-stu-id="7c36e-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="7c36e-121">**密码设置** 选择使用自动生成的密码或为用户创建你自己的强密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="7c36e-122">用户必须在 90 天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="7c36e-123">也可以选择 **要求此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="7c36e-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="7c36e-124">选择是否希望添加用户时通过电子邮件发送密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="7c36e-125">在“**分配产品许可证**”窗格中，为用户选择位置和相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="7c36e-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="7c36e-126">如果没有可用的许可证，仍然可以添加用户并购买其他许可证。</span><span class="sxs-lookup"><span data-stu-id="7c36e-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="7c36e-127">展开“**应用**”并选择或取消选择应用，以限制用户拥有许可证的应用。</span><span class="sxs-lookup"><span data-stu-id="7c36e-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="7c36e-128">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-128">Select **Next**.</span></span>
5. <span data-ttu-id="7c36e-129">在“**可选设置**”窗格中，展开“**角色**”以使此用户成为管理员。展开“**个人资料信息**”以添加有关用户的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7c36e-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="7c36e-130">选择“**下一步**”，查看新用户的设置，按自己的喜好更改，然后依次选择“**完成添加**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7c36e-131">转到位于 <https://portal.office.de/adminportal> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="7c36e-131">Go to the admin center at <https://portal.office.de/adminportal>.</span></span>
2. <span data-ttu-id="7c36e-132">转到“**用户**”>“**活动用户**”，然后选择“**添加用户**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="7c36e-133">在“**新用户**”窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="7c36e-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="7c36e-134">完成后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="7c36e-135">**姓名** 填写名字、姓氏、显示名和用户名。</span><span class="sxs-lookup"><span data-stu-id="7c36e-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="7c36e-136">**域** 例如，如果用户名为 Jakob，其域为 contoso.com，则用户将通过键入 jakob@contoso.com 来登录。</span><span class="sxs-lookup"><span data-stu-id="7c36e-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="7c36e-137">**联系人信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="7c36e-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="7c36e-138">**密码** 使用自动生成的密码或展开以为用户指定强密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="7c36e-139">必须在 90 天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-139">They must change their password after 90 days.</span></span> <span data-ttu-id="7c36e-140">也可以选择 **允许此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="7c36e-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="7c36e-141">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="7c36e-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="7c36e-p109">**产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="7c36e-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7c36e-144">转到位于 <https://portal.partner.microsoftonline.cn> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="7c36e-144">Go to the admin center at <https://portal.partner.microsoftonline.cn>.</span></span>
2. <span data-ttu-id="7c36e-145">转到“**用户**”>“**活动用户**”，然后选择“**添加用户**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="7c36e-146">在“**新用户**”窗格中，填写以下信息。</span><span class="sxs-lookup"><span data-stu-id="7c36e-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="7c36e-147">完成后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="7c36e-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="7c36e-148">**姓名** 填写名字、姓氏、显示名和用户名。</span><span class="sxs-lookup"><span data-stu-id="7c36e-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="7c36e-149">**域** 例如，如果用户名为 Jakob，其域为 contoso.com，则用户将通过键入 jakob@contoso.com 来登录。</span><span class="sxs-lookup"><span data-stu-id="7c36e-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="7c36e-150">**联系人信息** 展开以填写移动电话号码、地址等。</span><span class="sxs-lookup"><span data-stu-id="7c36e-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="7c36e-151">**密码** 使用自动生成的密码或展开以为用户指定强密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="7c36e-152">必须在 90 天后更改密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-152">They must change their password after 90 days.</span></span> <span data-ttu-id="7c36e-153">也可以选择 **允许此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="7c36e-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="7c36e-154">**角色** 如果需要使此用户成为管理员，请展开。</span><span class="sxs-lookup"><span data-stu-id="7c36e-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="7c36e-p112">**产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="7c36e-p112">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="7c36e-157">同时添加多个用户</span><span class="sxs-lookup"><span data-stu-id="7c36e-157">Add multiple users at the same time</span></span>

<span data-ttu-id="7c36e-158">可以使用以下任意方法同时添加多个用户：</span><span class="sxs-lookup"><span data-stu-id="7c36e-158">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="7c36e-159">**使用电子表格批量添加人员。**</span><span class="sxs-lookup"><span data-stu-id="7c36e-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="7c36e-160">请参阅 [同时添加若干用户](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-160">See [Add several users at the same time](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time).</span></span>
- <span data-ttu-id="7c36e-161">**自动添加帐户并分配许可证。**</span><span class="sxs-lookup"><span data-stu-id="7c36e-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="7c36e-162">请参阅 [通过 Microsoft 365 PowerShell 创建用户账户](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-162">See [Create user accounts with Microsoft 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell).</span></span> <span data-ttu-id="7c36e-163">如果可以熟练使用 Windows PowerShell cmdlet，请选择此方法。</span><span class="sxs-lookup"><span data-stu-id="7c36e-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="7c36e-164">**使用 ActiveDirectory？**</span><span class="sxs-lookup"><span data-stu-id="7c36e-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="7c36e-165">[设置 Microsoft 365 的目录同步](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-165">[Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="7c36e-166">在 Microsoft 365 中，使用 Azure AD Connect 工具复制 Active Directory 用户帐户（和其他 Active Directory 对象）。</span><span class="sxs-lookup"><span data-stu-id="7c36e-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="7c36e-167">同步只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7c36e-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="7c36e-168">你必须向同步用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="7c36e-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="7c36e-169">**从 Exchange 迁移？**</span><span class="sxs-lookup"><span data-stu-id="7c36e-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="7c36e-170">请参阅 [将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-170">See [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="7c36e-171">通过使用直接转换、分阶段或混合 Exchange 方法将多个邮箱迁移到 Microsoft 365 时，将在迁移期间自动添加用户。</span><span class="sxs-lookup"><span data-stu-id="7c36e-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="7c36e-172">迁移只添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7c36e-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="7c36e-173">你必须向用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="7c36e-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="7c36e-174">如果不向用户分配许可证，则其邮箱在 30 天的宽限期后将处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="7c36e-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="7c36e-175">了解如何在 Microsoft 365 管理中心内 [向用户分配许可证](../manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7c36e-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7c36e-176">Next steps</span></span>

<span data-ttu-id="7c36e-177">添加用户后，你收到一封来自 Microsoft 的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7c36e-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="7c36e-178">该电子邮件包含对应人员的用户 ID 和密码，使其可以登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7c36e-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="7c36e-179">使用常规流程告知新密码。</span><span class="sxs-lookup"><span data-stu-id="7c36e-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="7c36e-180">与新用户共享 [员工快速入门指南](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，以设置一些内容，例如怎样从 [在电脑或 Mac 上下载和安装 Office 应用](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何 [在移动设备上设置 Office 应用和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="7c36e-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="7c36e-181">相关内容</span><span class="sxs-lookup"><span data-stu-id="7c36e-181">Related content</span></span>

<span data-ttu-id="7c36e-182">[向 Microsoft 365 添加新员工](add-new-employee.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="7c36e-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="7c36e-183">[同时向 Microsoft 365 网站添加若干用户](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)（文章）</span><span class="sxs-lookup"><span data-stu-id="7c36e-183">[Add several users at the same time to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (article)</span></span>\
<span data-ttu-id="7c36e-184">[在 Microsoft 365 网站中还原用户](restore-user.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="7c36e-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="7c36e-185">[向用户分配许可证](../manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="7c36e-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="7c36e-186">[从组织删除用户](delete-a-user.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="7c36e-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
