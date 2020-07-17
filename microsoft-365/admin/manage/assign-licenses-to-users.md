---
title: 向用户分配许可证
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何向用户分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015943"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="9b206-103">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9b206-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="9b206-104">The admin center is changing.</span></span> <span data-ttu-id="9b206-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="9b206-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="9b206-106">可在“**活动用户**”页面或“**许可证**”页面上向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9b206-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="9b206-107">所使用的方法取决于是要向特定用户分配产品许可证还是向特定产品分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="9b206-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="9b206-108">[了解如何同时添加用户帐户和分配许可证](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="9b206-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9b206-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="9b206-109">Before you begin</span></span>

- <span data-ttu-id="9b206-110">你必须是全局、许可证或用户管理员才能分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9b206-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="9b206-111">有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="9b206-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="9b206-112">你可以[使用 Office 365 PowerShell 向用户帐户分配许可证](https://go.microsoft.com/fwlink/p/?linkid=850410)。</span><span class="sxs-lookup"><span data-stu-id="9b206-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="9b206-113">若要使用基于组的许可，请参阅[在 Azure Active Directory 中按组成员身份向用户分配许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="9b206-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="9b206-114">某些服务（如 Sway）会自动分配给用户，无需单独分配。</span><span class="sxs-lookup"><span data-stu-id="9b206-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="9b206-115">使用“许可证”页面向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="9b206-116">使用“**许可证**”页面分配许可证时，最多可向 20 名用户分配特定产品的许可证。</span><span class="sxs-lookup"><span data-stu-id="9b206-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="9b206-117">在“**许可证**”页面上，你将看到你所订阅的所有产品的列表。</span><span class="sxs-lookup"><span data-stu-id="9b206-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="9b206-118">你还将看到每个产品的许可证总数、分配的许可证数以及可用的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="9b206-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="9b206-119">在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="9b206-120">选择产品。</span><span class="sxs-lookup"><span data-stu-id="9b206-120">Select a product.</span></span>
3. <span data-ttu-id="9b206-121">在产品详细信息页面上，选择“**分配许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="9b206-122">在“**向用户分配许可证**”窗格中，开始键入名称，然后从结果中将其选中，将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="9b206-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="9b206-123">一次最多可添加 20 名用户。</span><span class="sxs-lookup"><span data-stu-id="9b206-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="9b206-124">选择“**打开或关闭应用和服务**”，向特定项目分配访问权限或删除其访问权限。</span><span class="sxs-lookup"><span data-stu-id="9b206-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="9b206-125">完成后，选择“分配”\*\*\*\*，然后选择“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9b206-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="9b206-126">如果出现冲突，则将显示一则消息，指出问题是什么以及如何修复它。</span><span class="sxs-lookup"><span data-stu-id="9b206-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="9b206-127">例如，如果选择包含冲突服务的许可证，错误消息将指示审阅随每个许可证包含的服务并重试。</span><span class="sxs-lookup"><span data-stu-id="9b206-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="9b206-128">更改用户有权访问的应用和服务</span><span class="sxs-lookup"><span data-stu-id="9b206-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="9b206-129">在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="9b206-130">在“**许可证**”页面上，选择特定用户所对应的行。</span><span class="sxs-lookup"><span data-stu-id="9b206-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="9b206-131">在右侧窗格中，选择或取消选择要授予或取消访问权限的应用和服务。</span><span class="sxs-lookup"><span data-stu-id="9b206-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="9b206-132">完成后，选择“**保存**”，然后选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="9b206-133">使用“活动用户”页面分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="9b206-134">使用“**活动用户**”页面分配许可证时，将向产品分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="9b206-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="9b206-135">向多个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="9b206-136">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9b206-137">选中要向其分配许可证的用户姓名旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="9b206-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="9b206-138">在顶部选择“**更多选项(...)**”，然后选择“**管理产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="9b206-139">在“**管理产品许可证**”窗格中，选择“**添加到现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9b206-140">在“**添加到现有产品**”窗格中，将希望所选用户具备的许可证的开关切换到“**开**”位置。</span><span class="sxs-lookup"><span data-stu-id="9b206-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="9b206-141">默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="9b206-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="9b206-142">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="9b206-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="9b206-143">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="9b206-144">在窗格底部，选择“**添加**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="9b206-145">向多个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="9b206-146">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9b206-147">选中要向其分配许可证的用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="9b206-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="9b206-148">在“**批量操作**”窗格中，选择“**编辑产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="9b206-149">在“**分配产品**”窗格中，选择“**添加到现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9b206-150">将希望所选用户具备的许可证的开关切换到“**开**”位置。</span><span class="sxs-lookup"><span data-stu-id="9b206-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="9b206-151">默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="9b206-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="9b206-152">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="9b206-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="9b206-153">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="9b206-154">在“**添加到现有产品**”窗格底部，选择“**添加**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="9b206-155">向多个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="9b206-156">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9b206-157">选中要向其分配许可证的用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="9b206-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="9b206-158">在“**批量操作**”窗格中，选择“**编辑产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="9b206-159">在“**分配产品**”窗格中，选择“**添加到现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9b206-160">将希望所选用户具备的许可证的开关切换到“**开**”位置。</span><span class="sxs-lookup"><span data-stu-id="9b206-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="9b206-161">默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="9b206-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="9b206-162">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="9b206-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="9b206-163">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="9b206-164">在“**添加到现有产品**”窗格底部，选择“**添加**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="9b206-165">向一个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="9b206-166">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9b206-167">选择要向其分配许可证的用户所对应的行。</span><span class="sxs-lookup"><span data-stu-id="9b206-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="9b206-168">在右侧窗格，选择“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="9b206-169">展开“**许可证**”部分，选择要分配的许可证的框，然后选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="9b206-170">向一个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="9b206-171">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9b206-172">选中要向其分配许可证的用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="9b206-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="9b206-173">在右侧窗格的“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="9b206-174">在“**产品许可证**”窗格中，将要分配给此用户的许可证的开关切换到“**开**”位置。</span><span class="sxs-lookup"><span data-stu-id="9b206-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="9b206-175">默认情况下，与该许可证关联的所有服务都将自动分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="9b206-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="9b206-176">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="9b206-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="9b206-177">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="9b206-178">在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="9b206-179">向一个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9b206-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="9b206-180">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9b206-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9b206-181">选中要向其分配许可证的用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="9b206-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="9b206-182">在右侧窗格的“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="9b206-183">在“**产品许可证**”窗格中，将要分配给此用户的许可证的开关切换到“**开**”位置。</span><span class="sxs-lookup"><span data-stu-id="9b206-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="9b206-184">默认情况下，与该许可证关联的所有服务都将自动分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="9b206-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="9b206-185">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="9b206-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="9b206-186">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="9b206-187">在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9b206-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="9b206-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9b206-188">Next steps</span></span>

<span data-ttu-id="9b206-189">如果用户尚未安装 Office 应用，你可以与其共享[员工快速入门指南](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)以进行各项设置，如[如何在电脑或 Mac 上下载并安装 Microsoft 365 或 Office 2019](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)以及[如何在移动设备上设置 Office 应用和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="9b206-189">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="9b206-190">相关内容</span><span class="sxs-lookup"><span data-stu-id="9b206-190">Related content</span></span>

<span data-ttu-id="9b206-191">[了解订阅和许可证](../../commerce/licenses/subscriptions-and-licenses.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="9b206-191">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="9b206-192">[取消向用户分配许可证](remove-licenses-from-users.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="9b206-192">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="9b206-193">[购买或删除订阅的许可证](../../commerce/licenses/buy-licenses.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="9b206-193">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>