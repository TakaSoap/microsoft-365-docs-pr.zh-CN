---
title: 取消分配用户许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何从用户帐户中取消分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015931"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="415b5-103">取消分配用户许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="415b5-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="415b5-104">The admin center is changing.</span></span> <span data-ttu-id="415b5-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="415b5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="415b5-106">您可以在 "**活动用户**" 页或 "**许可证**" 页上取消分配用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="415b5-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="415b5-107">您使用的方法取决于您是要从特定用户分配产品许可证，还是从特定产品中取消分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="415b5-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="415b5-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="415b5-108">Before you begin</span></span>

- <span data-ttu-id="415b5-109">您必须是全局许可证，用户管理员才能取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="415b5-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="415b5-110">有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="415b5-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="415b5-111">可[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="415b5-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="415b5-112">您还可以删除已分配许可证的[用户帐户](../add-users/delete-a-user.md)，以使其许可证对其他用户可用。</span><span class="sxs-lookup"><span data-stu-id="415b5-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="415b5-113">当您删除用户帐户时，他们的许可证立即可以分配给其他人。</span><span class="sxs-lookup"><span data-stu-id="415b5-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="415b5-114">使用 "许可证" 页面取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="415b5-115">使用 "**许可证**" 页面取消分配许可证时，将为最高20个用户的特定产品取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="415b5-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="415b5-116">在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="415b5-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="415b5-117">选择要为其取消分配许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="415b5-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="415b5-118">选择要为其取消分配许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="415b5-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="415b5-119">选择 "未**分配许可证**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="415b5-120">在 "未**分配许可证**" 框中，选择 "未**分配**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="415b5-121">使用 "活动用户" 页面取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="415b5-122">使用 "**活动用户**" 页面取消分配许可证时，将从用户中取消分配产品许可证。</span><span class="sxs-lookup"><span data-stu-id="415b5-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="415b5-123">从一个用户取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="415b5-124">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="415b5-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="415b5-125">选择要为其取消分配许可证的用户的行。</span><span class="sxs-lookup"><span data-stu-id="415b5-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="415b5-126">在右侧窗格，选择“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="415b5-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="415b5-127">展开 "**许可证**" 部分，清除要取消分配的许可证的复选框，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="415b5-128">从一个用户取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="415b5-129">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="415b5-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="415b5-130">选择要为其取消分配许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="415b5-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="415b5-131">在右侧的 "**产品许可证**" 行中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="415b5-132">在 "**产品许可证**" 窗格中，将您要为该用户取消分配的许可证的开关切换到 "**关**" 位置。</span><span class="sxs-lookup"><span data-stu-id="415b5-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="415b5-133">例如，如果您关闭了 Office 365 企业版 E3 许可证，它将取消分配该许可证以及该用户的许可证下的所有服务。</span><span class="sxs-lookup"><span data-stu-id="415b5-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="415b5-134">在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="415b5-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="415b5-135">从一个用户取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="415b5-136">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="415b5-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="415b5-137">选择要为其取消分配许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="415b5-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="415b5-138">在右侧的 "**产品许可证**" 行中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="415b5-139">在 "**产品许可证**" 窗格中，将您要为该用户取消分配的许可证的开关切换到 "**关**" 位置。</span><span class="sxs-lookup"><span data-stu-id="415b5-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="415b5-140">例如，如果您关闭了 Office 365 企业版 E3 许可证，它将取消分配该许可证以及该用户的许可证下的所有服务。</span><span class="sxs-lookup"><span data-stu-id="415b5-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="415b5-141">在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="415b5-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="415b5-142">取消分配给多个用户的许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="415b5-143">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="415b5-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="415b5-144">选择要为其取消分配许可证的用户的名称旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="415b5-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="415b5-145">在顶部选择“**更多选项(...)**”，然后选择“**管理产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="415b5-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="415b5-146">在“**管理产品许可证**”窗格中，选择“**替换现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="415b5-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="415b5-147">在 "**替换现有产品**" 窗格的底部，选中 "**删除所选用户的所有产品许可证**" 复选框，然后选择 "**替换** \> **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="415b5-148">取消分配给多个用户的许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="415b5-149">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="415b5-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="415b5-150">选择要为其取消分配所有许可证的用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="415b5-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="415b5-151">在“**批量操作**”窗格中，选择“**编辑产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="415b5-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="415b5-152">在" **替换现有产品**"窗格中，选择" **替换现有产品许可证分配**"\>" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="415b5-153">在 "**替换现有产品**" 窗格的底部，选中 "**删除所选用户的所有产品许可证**" 复选框，然后选择 "**替换** \> **关闭**关闭" \> **Close**。</span><span class="sxs-lookup"><span data-stu-id="415b5-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="415b5-154">取消分配给多个用户的许可证</span><span class="sxs-lookup"><span data-stu-id="415b5-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="415b5-155">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="415b5-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="415b5-156">选择要为其取消分配所有许可证的用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="415b5-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="415b5-157">在“**批量操作**”窗格中，选择“**编辑产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="415b5-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="415b5-158">在" **替换现有产品**"窗格中，选择" **替换现有产品许可证分配**"\>" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="415b5-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="415b5-159">在 "**替换现有产品**" 窗格的底部，选中 "**删除所选用户的所有产品许可证**" 复选框，然后选择 "**替换** \> **关闭**关闭" \> **Close**。</span><span class="sxs-lookup"><span data-stu-id="415b5-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="415b5-160">删除许可证后，用户的数据会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="415b5-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="415b5-161">从用户中删除许可证后，与该帐户关联的数据将保留30天。</span><span class="sxs-lookup"><span data-stu-id="415b5-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="415b5-162">30天宽限期后，数据将被删除，并且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="415b5-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="415b5-163">在 OneDrive for Business 中保存的文件不会被删除，除非用户是从 Microsoft 365 管理中心中删除的，或者是通过 Active Directory 同步删除的。</span><span class="sxs-lookup"><span data-stu-id="415b5-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="415b5-164">有关详细信息，请参阅[OneDrive 保留和删除](https://docs.microsoft.com/onedrive/retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="415b5-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="415b5-165">删除许可证后，用户的邮箱将无法再通过使用电子数据展示工具（如内容搜索或高级电子数据展示）进行搜索。</span><span class="sxs-lookup"><span data-stu-id="415b5-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="415b5-166">有关详细信息，请参阅[Microsoft 365 中的内容搜索](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)中的 "搜索断开连接或已取消授权的邮箱"。</span><span class="sxs-lookup"><span data-stu-id="415b5-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="415b5-167">如果您拥有企业订阅（如 Office 365 企业版 E3），Exchange Online 允许您使用[非活动邮箱](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)保留已删除用户帐户的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="415b5-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="415b5-168">有关详细信息，请参阅[在 Exchange Online 中创建和管理非活动邮箱](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="415b5-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="415b5-169">若要了解如何在删除许可证后阻止用户访问 Microsoft 365 数据，以及如何在以后获取对数据的访问权限，请参阅[删除以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="415b5-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="415b5-170">如果您删除了用户的许可证，但他们仍安装了 Office 应用程序，他们会在使用 Office 应用程序时看到未获得[授权的产品和激活错误](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)。</span><span class="sxs-lookup"><span data-stu-id="415b5-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="415b5-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="415b5-171">Next steps</span></span>

<span data-ttu-id="415b5-172">如果您不打算将[未使用的许可证重新分配给其他用户](../../managed-desktop/get-started/assign-licenses.md)，请考虑[从订阅中删除许可证](../../commerce/licenses/buy-licenses.md)，以便不会支付超过所需数量的许可证。</span><span class="sxs-lookup"><span data-stu-id="415b5-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="415b5-173">相关内容</span><span class="sxs-lookup"><span data-stu-id="415b5-173">Related content</span></span>

<span data-ttu-id="415b5-174">[从订阅中删除许可证](../../commerce/licenses/remove-licenses-from-subscription.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="415b5-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="415b5-175">[向用户分配许可证](assign-licenses-to-users.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="415b5-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="415b5-176">[了解 Microsoft 365 for business 中的订阅和许可证](../../commerce/licenses/subscriptions-and-licenses.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="415b5-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>