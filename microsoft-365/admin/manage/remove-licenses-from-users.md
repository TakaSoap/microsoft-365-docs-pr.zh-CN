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
description: 了解如何从用户帐户取消分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 5ef28b3065703ec224e6426c4fdbfffdb5269b22
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537495"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="c20a2-103">取消分配用户许可证</span><span class="sxs-lookup"><span data-stu-id="c20a2-103">Unassign licenses from users</span></span>

<span data-ttu-id="c20a2-104">您可以在"活动用户"页面或"许可证"页面上取消分配用户 **许可证**。</span><span class="sxs-lookup"><span data-stu-id="c20a2-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="c20a2-105">使用的方法取决于是希望取消分配特定用户的产品许可证，还是从特定产品取消分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="c20a2-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="c20a2-106">作为管理员，你不能为组织中用户购买的自助购买订阅分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c20a2-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="c20a2-107">你可以 [接管自助购买订阅](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)，然后分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c20a2-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c20a2-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="c20a2-108">Before you begin</span></span>

- <span data-ttu-id="c20a2-109">你必须是全局、许可证、用户管理员才能取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c20a2-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="c20a2-110">有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c20a2-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="c20a2-111">可[使用 Office 365 PowerShell 删除用户帐户的许可证](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="c20a2-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="c20a2-112">还可以 [删除分配有](../add-users/delete-a-user.md) 许可证的用户帐户，使其许可证可供其他用户使用。</span><span class="sxs-lookup"><span data-stu-id="c20a2-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="c20a2-113">删除用户帐户时，将立即将其许可证分配给其他人。</span><span class="sxs-lookup"><span data-stu-id="c20a2-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="c20a2-114">使用"许可证"页取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="c20a2-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="c20a2-115">使用"许可证 **"** 页取消分配许可证时，最多为 20 个用户取消分配特定产品的许可证。</span><span class="sxs-lookup"><span data-stu-id="c20a2-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c20a2-116">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="c20a2-117">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="c20a2-118">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-118">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="c20a2-119">选择要取消分配许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="c20a2-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="c20a2-120">选择要取消分配许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="c20a2-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="c20a2-121">选择 **"取消分配许可证"。**</span><span class="sxs-lookup"><span data-stu-id="c20a2-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="c20a2-122">在"**取消分配许可证"** 框中，选择"**取消分配"。**</span><span class="sxs-lookup"><span data-stu-id="c20a2-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="c20a2-123">使用"活动用户"页取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="c20a2-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="c20a2-124">使用"活动 **用户"** 页取消分配许可证时，将取消为用户分配产品许可证。</span><span class="sxs-lookup"><span data-stu-id="c20a2-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="c20a2-125">取消分配来自一个用户的许可证</span><span class="sxs-lookup"><span data-stu-id="c20a2-125">Unassign licenses from one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c20a2-126">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="c20a2-127">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="c20a2-128">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="c20a2-129">选择要取消分配许可证的用户的行。</span><span class="sxs-lookup"><span data-stu-id="c20a2-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="c20a2-130">在右侧窗格，选择“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="c20a2-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="c20a2-131">展开"**许可证**"部分，清除要取消分配的许可证的框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="c20a2-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="c20a2-132">取消分配多个用户的许可证</span><span class="sxs-lookup"><span data-stu-id="c20a2-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c20a2-133">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="c20a2-134">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-134">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="c20a2-135">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c20a2-135">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="c20a2-136">选择要取消分配许可证的用户姓名旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="c20a2-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="c20a2-137">At the top， select the three dots (more actions) ， then select **Manage product licenses**.</span><span class="sxs-lookup"><span data-stu-id="c20a2-137">At the top, select the three dots (more actions), then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="c20a2-138">在“**管理产品许可证**”窗格中，选择“**替换现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c20a2-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c20a2-139">在"替换现有产品"窗格的底部，选中"从所选用户删除所有产品许可证"复选框，然后选择"替换"" \> **关闭"。**</span><span class="sxs-lookup"><span data-stu-id="c20a2-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="c20a2-140">删除用户许可证时，用户数据会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="c20a2-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="c20a2-141">从用户删除许可证后，与该帐户关联的数据将存储 30 天。</span><span class="sxs-lookup"><span data-stu-id="c20a2-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="c20a2-142">30 天宽限期后，数据将被删除且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="c20a2-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="c20a2-143">保存OneDrive for Business的文件不会删除，除非用户已从管理中心Microsoft 365 Active Directory 同步删除。</span><span class="sxs-lookup"><span data-stu-id="c20a2-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="c20a2-144">有关详细信息，请参阅OneDrive[和删除](/onedrive/retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="c20a2-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="c20a2-145">删除许可证后，用户邮箱将不再可用电子数据展示工具（如内容搜索或Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="c20a2-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="c20a2-146">有关详细信息，请参阅 Content Search in Microsoft 365 中的"搜索断开连接或已取消[许可的Microsoft 365。](../../compliance/content-search.md)</span><span class="sxs-lookup"><span data-stu-id="c20a2-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="c20a2-147">如果你有一个Enterprise订阅，Office 365 企业版 E3，Exchange Online使用非活动邮箱保留已删除用户帐户的[邮箱数据](../../compliance/inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c20a2-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="c20a2-148">有关详细信息，请参阅 Create [and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="c20a2-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="c20a2-149">若要了解如何在删除用户的许可证后阻止Microsoft 365访问数据，以及如何在以后获取数据访问权限，请参阅删除[以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="c20a2-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="c20a2-150">如果你删除用户的许可证，并且他们仍然安装了Office，则当他们使用 Office 应用时，[](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)他们会看到"未授权的产品"和Office错误。</span><span class="sxs-lookup"><span data-stu-id="c20a2-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c20a2-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c20a2-151">Next steps</span></span>

<span data-ttu-id="c20a2-152">如果你不打算将未使用的许可证重新分配给[](../../managed-desktop/get-started/assign-licenses.md)其他用户，请考虑从订阅中删除许可证，这样你[](../../commerce/licenses/buy-licenses.md)无需支付超过你需要的许可证。</span><span class="sxs-lookup"><span data-stu-id="c20a2-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="c20a2-153">相关内容</span><span class="sxs-lookup"><span data-stu-id="c20a2-153">Related content</span></span>

<span data-ttu-id="c20a2-154">[从订阅中删除许可证 (](../../commerce/licenses/buy-licenses.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="c20a2-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="c20a2-155">[向用户分配许可证](assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="c20a2-155">[Assign licenses to users](assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="c20a2-156">[了解适用于企业Microsoft 365中的](../../commerce/licenses/subscriptions-and-licenses.md)订阅 (许可证) </span><span class="sxs-lookup"><span data-stu-id="c20a2-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
