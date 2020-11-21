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
description: 了解如何使用 Microsoft 关闭你的帐户。
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376313"
---
# <a name="close-your-account"></a><span data-ttu-id="20fd7-103">关闭你的帐户</span><span class="sxs-lookup"><span data-stu-id="20fd7-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="20fd7-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="20fd7-104">The admin center is changing.</span></span> <span data-ttu-id="20fd7-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="20fd7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="20fd7-106">当关闭你的 Microsoft 帐户时，与你的帐户相关的所有信息都将被删除。</span><span class="sxs-lookup"><span data-stu-id="20fd7-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="20fd7-107">此信息包括订阅、许可证、付款方式、用户和用户数据。</span><span class="sxs-lookup"><span data-stu-id="20fd7-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="20fd7-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="20fd7-108">Before you begin</span></span>

<span data-ttu-id="20fd7-109">开始此过程之前，请确保备份要保留的所有数据。</span><span class="sxs-lookup"><span data-stu-id="20fd7-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="20fd7-110">您必须是全局管理员或帐单管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="20fd7-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="20fd7-111">有关详细信息，请参阅[关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="20fd7-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="20fd7-112">步骤1：删除用户</span><span class="sxs-lookup"><span data-stu-id="20fd7-112">Step 1: Delete users</span></span>

<span data-ttu-id="20fd7-113">删除除一个全局管理员之外的所有用户。</span><span class="sxs-lookup"><span data-stu-id="20fd7-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="20fd7-114">全局管理员完成关闭帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="20fd7-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="20fd7-115">必须删除所有其他用户，然后才能在此过程结束后删除该目录。</span><span class="sxs-lookup"><span data-stu-id="20fd7-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="20fd7-116">如果用户从本地同步，请先关闭 sync，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。</span><span class="sxs-lookup"><span data-stu-id="20fd7-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="20fd7-117">若要删除用户，请参阅 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">用户管理管理员：删除一个或多个用户</a>。</span><span class="sxs-lookup"><span data-stu-id="20fd7-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="20fd7-118">您还可以使用 <a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell cmdlet 批量删除用户。</span><span class="sxs-lookup"><span data-stu-id="20fd7-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="20fd7-119">如果你的组织使用 Active Directory 与 Microsoft Azure Active Directory (Azure AD) ，请改为从 Active Directory 中删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="20fd7-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="20fd7-120">有关说明，请参阅 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">批量删除用户在 Azure Active Directory 中</a>。</span><span class="sxs-lookup"><span data-stu-id="20fd7-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="20fd7-121">步骤2：取消所有活动订阅</span><span class="sxs-lookup"><span data-stu-id="20fd7-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="20fd7-122">在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。</span><span class="sxs-lookup"><span data-stu-id="20fd7-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="20fd7-123">在 " **产品** " 选项卡上，查找 "活动订阅"。</span><span class="sxs-lookup"><span data-stu-id="20fd7-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="20fd7-124">选择“**更多操作**”（三个点），然后选择“**取消订阅**”。</span><span class="sxs-lookup"><span data-stu-id="20fd7-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="20fd7-125">在“**取消订阅**”窗格中，选择取消原因。</span><span class="sxs-lookup"><span data-stu-id="20fd7-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="20fd7-126">(可选)提供反馈。</span><span class="sxs-lookup"><span data-stu-id="20fd7-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="20fd7-127">选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="20fd7-127">Select **Save**.</span></span>
5. <span data-ttu-id="20fd7-128">重复步骤1到4以取消所有活动订阅。</span><span class="sxs-lookup"><span data-stu-id="20fd7-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="20fd7-129">步骤3：删除所有禁用的订阅</span><span class="sxs-lookup"><span data-stu-id="20fd7-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="20fd7-130">在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。</span><span class="sxs-lookup"><span data-stu-id="20fd7-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="20fd7-131">在 " **产品** " 选项卡上，选择一个已禁用的订阅。</span><span class="sxs-lookup"><span data-stu-id="20fd7-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="20fd7-132">在 "订阅详细信息" 页上的 " **订阅和付款设置** " 部分中，选择 " **删除订阅**"。</span><span class="sxs-lookup"><span data-stu-id="20fd7-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="20fd7-133">在 " **删除订阅** " 窗格中，选择 " **删除订阅**"。</span><span class="sxs-lookup"><span data-stu-id="20fd7-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="20fd7-134">在 " **删除订阅** " 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="20fd7-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="20fd7-135">对于每个禁用的订阅，重复步骤3到5，直到删除所有订阅。</span><span class="sxs-lookup"><span data-stu-id="20fd7-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="20fd7-136">如果你无法立即删除禁用的订阅， <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">请联系支持人员</a></span><span class="sxs-lookup"><span data-stu-id="20fd7-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="20fd7-137">步骤4：禁用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="20fd7-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="20fd7-138">使用全局管理员帐户登录到管理员中心。</span><span class="sxs-lookup"><span data-stu-id="20fd7-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="20fd7-139">若要验证您拥有的角色，请参阅 [检查组织中的管理员角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="20fd7-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="20fd7-140">转到 "**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="20fd7-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="20fd7-141">选择 **多因素身份验证**。</span><span class="sxs-lookup"><span data-stu-id="20fd7-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="20fd7-142">在 "多重身份验证" 页上，禁用除当前正在使用的全局管理员帐户之外的所有帐户。</span><span class="sxs-lookup"><span data-stu-id="20fd7-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="20fd7-143">您还可以 <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用 PowerShell 为多个用户禁用多重身份验证</a>。</span><span class="sxs-lookup"><span data-stu-id="20fd7-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="20fd7-144">步骤5：删除 Azure Active Directory 中的目录</span><span class="sxs-lookup"><span data-stu-id="20fd7-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="20fd7-145">使用全局管理员帐户登录到 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理中心</a> 。</span><span class="sxs-lookup"><span data-stu-id="20fd7-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="20fd7-146">选择“**Azure Active Directory**”。</span><span class="sxs-lookup"><span data-stu-id="20fd7-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="20fd7-147">切换到要删除的组织。</span><span class="sxs-lookup"><span data-stu-id="20fd7-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="20fd7-148">选择 " **删除租户**"。</span><span class="sxs-lookup"><span data-stu-id="20fd7-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="20fd7-149">如果你的组织未通过一项或多项检查，你将看到有关如何传递检查的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="20fd7-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="20fd7-150">传递所有检查后，选择 " **删除** " 以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="20fd7-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="20fd7-151">完成此最后一步之后，你的 Microsoft 帐户将关闭并被删除。</span><span class="sxs-lookup"><span data-stu-id="20fd7-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>