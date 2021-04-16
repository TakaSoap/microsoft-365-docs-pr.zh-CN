---
title: 关闭你的帐户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: 了解如何关闭 Microsoft 帐户。
ms.openlocfilehash: 44428654946d31ad249bfd3e7a3609da3e3634a6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860543"
---
# <a name="close-your-account"></a><span data-ttu-id="0f776-103">关闭你的帐户</span><span class="sxs-lookup"><span data-stu-id="0f776-103">Close your account</span></span>

<span data-ttu-id="0f776-104">当关闭你的 Microsoft 帐户时，与你的帐户相关的所有信息都将被删除。</span><span class="sxs-lookup"><span data-stu-id="0f776-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="0f776-105">此信息包括订阅、许可证、付款方式、用户和用户数据。</span><span class="sxs-lookup"><span data-stu-id="0f776-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0f776-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="0f776-106">Before you begin</span></span>

<span data-ttu-id="0f776-107">开始此过程之前，请确保备份要保留的所有数据。</span><span class="sxs-lookup"><span data-stu-id="0f776-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="0f776-108">你必须是全局管理员或帐单管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="0f776-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="0f776-109">有关详细信息，请参阅 [关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0f776-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="0f776-110">步骤 1：删除用户</span><span class="sxs-lookup"><span data-stu-id="0f776-110">Step 1: Delete users</span></span>

<span data-ttu-id="0f776-111">删除除一个全局管理员以外的所有用户。</span><span class="sxs-lookup"><span data-stu-id="0f776-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="0f776-112">全局管理员完成关闭帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="0f776-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="0f776-113">在此过程结束时，必须先删除所有其他用户，然后才能删除该目录。</span><span class="sxs-lookup"><span data-stu-id="0f776-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="0f776-114">如果用户从本地同步，请首先关闭同步，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。</span><span class="sxs-lookup"><span data-stu-id="0f776-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="0f776-115">若要删除用户，请参阅用户 <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">管理管理员：删除一个或多个用户</a>。</span><span class="sxs-lookup"><span data-stu-id="0f776-115">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="0f776-116">您还可以使用 <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser</a> PowerShell cmdlet 批量删除用户。</span><span class="sxs-lookup"><span data-stu-id="0f776-116">You can also use the <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="0f776-117">如果你的组织使用与 Microsoft Azure Active Directory 同步的 Active Directory (Azure AD) ，请改为从 Active Directory 中删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0f776-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="0f776-118">有关说明，请参阅 <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">在 Azure Active Directory</a>中批量删除用户。</span><span class="sxs-lookup"><span data-stu-id="0f776-118">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="0f776-119">步骤 2：取消所有活动订阅</span><span class="sxs-lookup"><span data-stu-id="0f776-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="0f776-120">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="0f776-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="0f776-121">在" **产品"** 选项卡上，查找活动订阅。</span><span class="sxs-lookup"><span data-stu-id="0f776-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="0f776-122">选择“**更多操作**”（三个点），然后选择“**取消订阅**”。</span><span class="sxs-lookup"><span data-stu-id="0f776-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="0f776-123">在“**取消订阅**”窗格中，选择取消原因。</span><span class="sxs-lookup"><span data-stu-id="0f776-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="0f776-124">(可选)提供反馈。</span><span class="sxs-lookup"><span data-stu-id="0f776-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="0f776-125">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0f776-125">Select **Save**.</span></span>
5. <span data-ttu-id="0f776-126">重复步骤 1 至 4 以取消所有活动订阅。</span><span class="sxs-lookup"><span data-stu-id="0f776-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="0f776-127">步骤 3：删除所有已禁用的订阅</span><span class="sxs-lookup"><span data-stu-id="0f776-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="0f776-128">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="0f776-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="0f776-129">在" **产品"** 选项卡上，选择已禁用的订阅。</span><span class="sxs-lookup"><span data-stu-id="0f776-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="0f776-130">On the subscription details page， in the **Subscription and payment settings section，** select Delete **subscription**.</span><span class="sxs-lookup"><span data-stu-id="0f776-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="0f776-131">在"**删除订阅"窗格中**，选择"**删除订阅"。**</span><span class="sxs-lookup"><span data-stu-id="0f776-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="0f776-132">在"**删除订阅**"对话框中，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="0f776-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="0f776-133">对于每个已禁用的订阅，重复步骤 3 至 5，直到删除所有订阅。</span><span class="sxs-lookup"><span data-stu-id="0f776-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="0f776-134">如果无法立即删除已禁用的订阅，请联系 <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">支持人员</a></span><span class="sxs-lookup"><span data-stu-id="0f776-134">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="0f776-135">步骤 4：禁用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="0f776-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="0f776-136">使用全局管理员帐户登录管理中心。</span><span class="sxs-lookup"><span data-stu-id="0f776-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="0f776-137">若要验证你拥有的角色，请参阅 [检查你的组织的管理员角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="0f776-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="0f776-138">转到"**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">""活动用户"</a>页。</span><span class="sxs-lookup"><span data-stu-id="0f776-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="0f776-139">选择 **"多重身份验证"。**</span><span class="sxs-lookup"><span data-stu-id="0f776-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="0f776-140">在多重身份验证页面上，禁用除当前使用的全局管理员帐户之外的所有帐户。</span><span class="sxs-lookup"><span data-stu-id="0f776-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="0f776-141">您还可以使用 <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell 为多个用户禁用多重身份验证</a>。</span><span class="sxs-lookup"><span data-stu-id="0f776-141">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="0f776-142">步骤 5：删除 Azure Active Directory 中的目录</span><span class="sxs-lookup"><span data-stu-id="0f776-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="0f776-143">使用全局管理员帐户登录到 <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0f776-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="0f776-144">选择 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="0f776-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0f776-145">切换到要删除的组织。</span><span class="sxs-lookup"><span data-stu-id="0f776-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="0f776-146">选择 **"删除租户"。**</span><span class="sxs-lookup"><span data-stu-id="0f776-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="0f776-147">如果您的组织未能通过一项或多项检查，则会看到一个链接，该链接指向有关通过检查详细信息。</span><span class="sxs-lookup"><span data-stu-id="0f776-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="0f776-148">通过所有检查后，选择" **删除** "以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="0f776-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="0f776-149">完成最后一步后，Microsoft 帐户将关闭并删除。</span><span class="sxs-lookup"><span data-stu-id="0f776-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>