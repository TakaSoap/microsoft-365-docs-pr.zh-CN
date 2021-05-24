---
title: 关闭你的帐户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
search.appverid: MET150
description: 关闭 Microsoft 帐户时，将删除与帐户相关的所有信息，包括许可证、用户和用户数据。
ms.date: 04/02/2021
ms.openlocfilehash: b212911707b5d6a967ab833a5a06bc76f5ceeb3b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624321"
---
# <a name="close-your-account"></a><span data-ttu-id="cc719-103">关闭你的帐户</span><span class="sxs-lookup"><span data-stu-id="cc719-103">Close your account</span></span>

<span data-ttu-id="cc719-104">当关闭你的 Microsoft 帐户时，与你的帐户相关的所有信息都将被删除。</span><span class="sxs-lookup"><span data-stu-id="cc719-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="cc719-105">此信息包括订阅、许可证、付款方式、用户和用户数据。</span><span class="sxs-lookup"><span data-stu-id="cc719-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cc719-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="cc719-106">Before you begin</span></span>

<span data-ttu-id="cc719-107">开始此过程之前，请确保备份要保留的所有数据。</span><span class="sxs-lookup"><span data-stu-id="cc719-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="cc719-108">你必须是全局管理员或帐单管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="cc719-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="cc719-109">有关详细信息，请参阅 [关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="cc719-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="cc719-110">步骤 1：删除用户</span><span class="sxs-lookup"><span data-stu-id="cc719-110">Step 1: Delete users</span></span>

<span data-ttu-id="cc719-111">删除除一个全局管理员以外的所有用户。</span><span class="sxs-lookup"><span data-stu-id="cc719-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="cc719-112">全局管理员完成关闭帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="cc719-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="cc719-113">在此过程结束时，必须先删除所有其他用户，然后才能删除该目录。</span><span class="sxs-lookup"><span data-stu-id="cc719-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="cc719-114">如果用户从本地同步，请首先关闭同步，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。</span><span class="sxs-lookup"><span data-stu-id="cc719-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="cc719-115">若要删除用户，请参阅用户 [管理管理员：删除一个或多个用户](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)。</span><span class="sxs-lookup"><span data-stu-id="cc719-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="cc719-116">您还可以使用 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet 批量删除用户。</span><span class="sxs-lookup"><span data-stu-id="cc719-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="cc719-117">如果你的组织使用与 Azure AD Microsoft Azure Active Directory (同步的 Active Directory) ，请改为从 Active Directory 中删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cc719-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="cc719-118">有关说明，请参阅批量[删除用户Azure Active Directory。](/azure/active-directory/users-groups-roles/users-bulk-delete)</span><span class="sxs-lookup"><span data-stu-id="cc719-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="cc719-119">步骤 2：取消所有活动订阅</span><span class="sxs-lookup"><span data-stu-id="cc719-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="cc719-120">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cc719-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="cc719-121">在" **产品"** 选项卡上，查找活动订阅。</span><span class="sxs-lookup"><span data-stu-id="cc719-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="cc719-122">选择三个点（更多操作），然后选择“**取消订阅**”。</span><span class="sxs-lookup"><span data-stu-id="cc719-122">Select the three dots (more actions), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="cc719-p106">在“**取消订阅**”窗格中，选择取消原因。可选择提供任何反馈。</span><span class="sxs-lookup"><span data-stu-id="cc719-p106">In the **Cancel subscription** pane, choose a reason why you're canceling. Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="cc719-125">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cc719-125">Select **Save**.</span></span>
5. <span data-ttu-id="cc719-126">重复步骤 1 至 4 以取消所有活动订阅。</span><span class="sxs-lookup"><span data-stu-id="cc719-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="cc719-127">步骤 3：删除所有已禁用的订阅</span><span class="sxs-lookup"><span data-stu-id="cc719-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="cc719-128">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cc719-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="cc719-129">在" **产品"** 选项卡上，选择已禁用的订阅。</span><span class="sxs-lookup"><span data-stu-id="cc719-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="cc719-130">On the subscription details page， in the **Subscription and payment settings section，** select Delete **subscription**.</span><span class="sxs-lookup"><span data-stu-id="cc719-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="cc719-131">在"**删除订阅"窗格中**，选择"**删除订阅"。**</span><span class="sxs-lookup"><span data-stu-id="cc719-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="cc719-132">在"**删除订阅**"对话框中，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="cc719-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="cc719-133">对于每个已禁用的订阅，重复步骤 3 至 5，直到删除所有订阅。</span><span class="sxs-lookup"><span data-stu-id="cc719-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="cc719-134">如果无法立即删除已禁用的订阅，请联系 [支持人员](../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="cc719-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="cc719-135">步骤 4：禁用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="cc719-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="cc719-136">使用全局管理员帐户登录管理中心。</span><span class="sxs-lookup"><span data-stu-id="cc719-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="cc719-137">若要验证你拥有的角色，请参阅 [检查你的组织的管理员角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="cc719-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="cc719-138">转到"**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">""活动用户"</a>页。</span><span class="sxs-lookup"><span data-stu-id="cc719-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="cc719-139">选择 **"多重身份验证"。**</span><span class="sxs-lookup"><span data-stu-id="cc719-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="cc719-140">在多重身份验证页面上，禁用除当前使用的全局管理员帐户之外的所有帐户。</span><span class="sxs-lookup"><span data-stu-id="cc719-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="cc719-141">您还可以使用 [PowerShell 为多个用户禁用多重身份验证](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cc719-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="cc719-142">步骤 5：删除Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc719-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="cc719-143">使用全局管理员帐户登录到 <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> 管理中心。</span><span class="sxs-lookup"><span data-stu-id="cc719-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="cc719-144">选择 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="cc719-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="cc719-145">切换到要删除的组织。</span><span class="sxs-lookup"><span data-stu-id="cc719-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="cc719-146">选择 **"删除租户"。**</span><span class="sxs-lookup"><span data-stu-id="cc719-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="cc719-147">如果您的组织未能通过一项或多项检查，则会看到一个链接，该链接指向有关通过检查详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc719-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="cc719-148">通过所有检查后，选择" **删除** "以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="cc719-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="cc719-149">完成最后一步后，Microsoft 帐户将关闭并删除。</span><span class="sxs-lookup"><span data-stu-id="cc719-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>

## <a name="related-content"></a><span data-ttu-id="cc719-150">相关内容</span><span class="sxs-lookup"><span data-stu-id="cc719-150">Related content</span></span> 

<span data-ttu-id="cc719-151">[了解适用于企业Microsoft 365的](./billing-and-payments/understand-your-invoice2.md)帐单 (发票) </span><span class="sxs-lookup"><span data-stu-id="cc719-151">[Understand your bill or invoice for Microsoft 365 for business](./billing-and-payments/understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="cc719-152">[取消订阅 (](./subscriptions/cancel-your-subscription.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="cc719-152">[Cancel your subscription](./subscriptions/cancel-your-subscription.md) (article)</span></span>

