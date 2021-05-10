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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- MET150
description: 了解如何关闭 Microsoft 帐户。
ms.date: 04/02/2021
ms.openlocfilehash: 86232e3f433526cc60ef369eda03ef8d20ab08c9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293663"
---
# <a name="close-your-account"></a><span data-ttu-id="0807d-103">关闭你的帐户</span><span class="sxs-lookup"><span data-stu-id="0807d-103">Close your account</span></span>

<span data-ttu-id="0807d-104">当关闭你的 Microsoft 帐户时，与你的帐户相关的所有信息都将被删除。</span><span class="sxs-lookup"><span data-stu-id="0807d-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="0807d-105">此信息包括订阅、许可证、付款方式、用户和用户数据。</span><span class="sxs-lookup"><span data-stu-id="0807d-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0807d-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="0807d-106">Before you begin</span></span>

<span data-ttu-id="0807d-107">开始此过程之前，请确保备份要保留的所有数据。</span><span class="sxs-lookup"><span data-stu-id="0807d-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="0807d-108">你必须是全局管理员或帐单管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="0807d-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="0807d-109">有关详细信息，请参阅 [关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0807d-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="0807d-110">步骤 1：删除用户</span><span class="sxs-lookup"><span data-stu-id="0807d-110">Step 1: Delete users</span></span>

<span data-ttu-id="0807d-111">删除除一个全局管理员以外的所有用户。</span><span class="sxs-lookup"><span data-stu-id="0807d-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="0807d-112">全局管理员完成关闭帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="0807d-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="0807d-113">在此过程结束时，必须先删除所有其他用户，然后才能删除该目录。</span><span class="sxs-lookup"><span data-stu-id="0807d-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="0807d-114">如果用户从本地同步，请首先关闭同步，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。</span><span class="sxs-lookup"><span data-stu-id="0807d-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="0807d-115">若要删除用户，请参阅用户 [管理管理员：删除一个或多个用户](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)。</span><span class="sxs-lookup"><span data-stu-id="0807d-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="0807d-116">您还可以使用 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet 批量删除用户。</span><span class="sxs-lookup"><span data-stu-id="0807d-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="0807d-117">如果你的组织使用与 Azure AD Microsoft Azure Active Directory (同步的 Active Directory) ，请改为从 Active Directory 中删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0807d-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="0807d-118">有关说明，请参阅批量[删除用户Azure Active Directory。](/azure/active-directory/users-groups-roles/users-bulk-delete)</span><span class="sxs-lookup"><span data-stu-id="0807d-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="0807d-119">步骤 2：取消所有活动订阅</span><span class="sxs-lookup"><span data-stu-id="0807d-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="0807d-120">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="0807d-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="0807d-121">在" **产品"** 选项卡上，查找活动订阅。</span><span class="sxs-lookup"><span data-stu-id="0807d-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="0807d-122">选择“**更多操作**”（三个点），然后选择“**取消订阅**”。</span><span class="sxs-lookup"><span data-stu-id="0807d-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="0807d-123">在“**取消订阅**”窗格中，选择取消原因。</span><span class="sxs-lookup"><span data-stu-id="0807d-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="0807d-124">(可选)提供反馈。</span><span class="sxs-lookup"><span data-stu-id="0807d-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="0807d-125">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0807d-125">Select **Save**.</span></span>
5. <span data-ttu-id="0807d-126">重复步骤 1 至 4 以取消所有活动订阅。</span><span class="sxs-lookup"><span data-stu-id="0807d-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="0807d-127">步骤 3：删除所有已禁用的订阅</span><span class="sxs-lookup"><span data-stu-id="0807d-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="0807d-128">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="0807d-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="0807d-129">在" **产品"** 选项卡上，选择已禁用的订阅。</span><span class="sxs-lookup"><span data-stu-id="0807d-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="0807d-130">On the subscription details page， in the **Subscription and payment settings section，** select Delete **subscription**.</span><span class="sxs-lookup"><span data-stu-id="0807d-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="0807d-131">在"**删除订阅"窗格中**，选择"**删除订阅"。**</span><span class="sxs-lookup"><span data-stu-id="0807d-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="0807d-132">在"**删除订阅**"对话框中，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="0807d-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="0807d-133">对于每个已禁用的订阅，重复步骤 3 至 5，直到删除所有订阅。</span><span class="sxs-lookup"><span data-stu-id="0807d-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="0807d-134">如果无法立即删除已禁用的订阅，请联系 [支持人员](../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="0807d-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="0807d-135">步骤 4：禁用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="0807d-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="0807d-136">使用全局管理员帐户登录管理中心。</span><span class="sxs-lookup"><span data-stu-id="0807d-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="0807d-137">若要验证你拥有的角色，请参阅 [检查你的组织的管理员角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="0807d-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="0807d-138">转到"**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">""活动用户"</a>页。</span><span class="sxs-lookup"><span data-stu-id="0807d-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="0807d-139">选择 **"多重身份验证"。**</span><span class="sxs-lookup"><span data-stu-id="0807d-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="0807d-140">在多重身份验证页面上，禁用除当前使用的全局管理员帐户之外的所有帐户。</span><span class="sxs-lookup"><span data-stu-id="0807d-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="0807d-141">您还可以使用 [PowerShell 为多个用户禁用多重身份验证](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0807d-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="0807d-142">步骤 5：删除Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0807d-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="0807d-143">使用全局管理员帐户登录到 <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0807d-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="0807d-144">选择 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="0807d-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0807d-145">切换到要删除的组织。</span><span class="sxs-lookup"><span data-stu-id="0807d-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="0807d-146">选择 **"删除租户"。**</span><span class="sxs-lookup"><span data-stu-id="0807d-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="0807d-147">如果您的组织未能通过一项或多项检查，则会看到一个链接，该链接指向有关通过检查详细信息。</span><span class="sxs-lookup"><span data-stu-id="0807d-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="0807d-148">通过所有检查后，选择" **删除** "以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="0807d-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="0807d-149">完成最后一步后，Microsoft 帐户将关闭并删除。</span><span class="sxs-lookup"><span data-stu-id="0807d-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>