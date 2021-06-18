---
title: 取消分配用户许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: 用于取消分配产品许可证的方法取决于是取消分配特定用户许可证还是从特定产品分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: f79ffecc22fe4531076ccacd83c25e44b81052a6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2021
ms.locfileid: "53006969"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="bbb1e-103">取消分配用户许可证</span><span class="sxs-lookup"><span data-stu-id="bbb1e-103">Unassign licenses from users</span></span>

<span data-ttu-id="bbb1e-104">您可以在"活动用户"页面或"许可证"页面上取消分配用户 **许可证**。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="bbb1e-105">使用的方法取决于是希望取消分配特定用户的产品许可证，还是从特定产品取消分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="bbb1e-106">作为管理员，你不能为组织中用户购买的自助购买订阅分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="bbb1e-107">你可以 [接管自助购买订阅](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)，然后分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bbb1e-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="bbb1e-108">Before you begin</span></span>

- <span data-ttu-id="bbb1e-109">你必须是全局、许可证、用户管理员才能取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="bbb1e-110">有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="bbb1e-111">可[使用 Office 365 PowerShell 删除用户帐户的许可证](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="bbb1e-112">还可以 [删除分配有](../add-users/delete-a-user.md) 许可证的用户帐户，使其许可证可供其他用户使用。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="bbb1e-113">删除用户帐户时，将立即将其许可证分配给其他人。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="bbb1e-114">使用"许可证"页取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="bbb1e-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="bbb1e-115">使用"许可证 **"** 页取消分配许可证时，最多为 20 个用户取消分配特定产品的许可证。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bbb1e-116">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="bbb1e-117">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="bbb1e-118">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-118">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="bbb1e-119">选择要取消分配许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="bbb1e-120">选择要取消分配许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="bbb1e-121">选择 **"取消分配许可证"。**</span><span class="sxs-lookup"><span data-stu-id="bbb1e-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="bbb1e-122">在"**取消分配许可证"** 框中，选择"**取消分配"。**</span><span class="sxs-lookup"><span data-stu-id="bbb1e-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="bbb1e-123">使用"活动用户"页取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="bbb1e-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="bbb1e-124">使用"活动 **用户"** 页取消分配许可证时，将取消为用户分配产品许可证。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="bbb1e-125">取消分配来自一个用户的许可证</span><span class="sxs-lookup"><span data-stu-id="bbb1e-125">Unassign licenses from one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bbb1e-126">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="bbb1e-127">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="bbb1e-128">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="bbb1e-129">选择要取消分配许可证的用户的行。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="bbb1e-130">在右侧窗格，选择“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="bbb1e-131">展开"**许可证**"部分，清除要取消分配的许可证的框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="bbb1e-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="bbb1e-132">取消分配多个用户的许可证</span><span class="sxs-lookup"><span data-stu-id="bbb1e-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bbb1e-133">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="bbb1e-134">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-134">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="bbb1e-135">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-135">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="bbb1e-136">选择要取消分配许可证的用户姓名旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-136">Select the circles next to the names of the users who you want to unassign licenses for.</span></span>
3. <span data-ttu-id="bbb1e-137">在顶部，选择管理 **产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-137">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="bbb1e-138">在"**管理产品许可证"** 窗格中，选择"**取消分配所有**  >  **保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="bbb1e-138">In the **Manage product licenses** pane, select **Unassign all** > **Save changes**.</span></span>
5. <span data-ttu-id="bbb1e-139">在窗格底部，选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="bbb1e-139">At the bottom of the pane, select **Done**.</span></span>  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="bbb1e-140">删除用户许可证时，用户数据会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bbb1e-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="bbb1e-141">从用户删除许可证后，Exchange帐户关联的联机数据将进行 30 天。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-141">When a license is removed from a user, Exchange online data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="bbb1e-142">30 天宽限期后，数据将被删除且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="bbb1e-143">保存OneDrive for Business的文件不会删除，除非用户已从 active Directory Microsoft 365 管理中心或 Active Directory 同步中删除。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="bbb1e-144">有关详细信息，请参阅OneDrive[和删除](/onedrive/retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="bbb1e-145">删除许可证后，用户邮箱将不再可用电子数据展示工具（如内容搜索或Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="bbb1e-146">有关详细信息，请参阅 Content Search in Microsoft 365 中的"搜索断开连接或已取消[许可的Microsoft 365。](../../compliance/content-search.md)</span><span class="sxs-lookup"><span data-stu-id="bbb1e-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="bbb1e-147">如果你有一个Enterprise订阅，Office 365 Enterprise E3，Exchange Online使用非活动邮箱保留已删除用户帐户的[邮箱数据](../../compliance/inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="bbb1e-148">有关详细信息，请参阅 Create [and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="bbb1e-149">若要了解如何在删除用户的许可证后阻止Microsoft 365访问数据，以及如何在以后获取数据访问权限，请参阅删除[以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="bbb1e-150">如果你删除用户的许可证，并且他们仍然安装了Office，则当他们使用 Office 应用时，[](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)他们会看到"未授权的产品"和Office错误。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bbb1e-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bbb1e-151">Next steps</span></span>

<span data-ttu-id="bbb1e-152">如果你不打算将未使用的许可证重新分配给[](../../managed-desktop/get-started/assign-licenses.md)其他用户，请考虑从订阅中删除许可证，这样你[](../../commerce/licenses/buy-licenses.md)无需支付超过你需要的许可证。</span><span class="sxs-lookup"><span data-stu-id="bbb1e-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="bbb1e-153">相关内容</span><span class="sxs-lookup"><span data-stu-id="bbb1e-153">Related content</span></span>

<span data-ttu-id="bbb1e-154">[从订阅中删除许可证 (](../../commerce/licenses/buy-licenses.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="bbb1e-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="bbb1e-155">[向用户分配许可证](assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="bbb1e-155">[Assign licenses to users](assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="bbb1e-156">[了解适用于企业Microsoft 365中的](../../commerce/licenses/subscriptions-and-licenses.md)订阅 (许可证) </span><span class="sxs-lookup"><span data-stu-id="bbb1e-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
