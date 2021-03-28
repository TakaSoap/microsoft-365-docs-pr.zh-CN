---
title: 向用户分配许可证
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce
search.appverid:
- MET150
description: 了解如何向用户分配许可证。
ms.openlocfilehash: 3622be180ae622d5d08066cc03773a8175fe9342
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398153"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="e677b-103">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="e677b-103">Assign licenses to users</span></span>

<span data-ttu-id="e677b-104">可在“**活动用户**”页面或“**许可证**”页面上向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="e677b-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="e677b-105">所使用的方法取决于是要向特定用户分配产品许可证还是向特定产品分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="e677b-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="e677b-106">作为管理员，你不能为组织中用户购买的自助购买订阅分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="e677b-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="e677b-107">你可以 [接管自助购买订阅](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)，然后分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="e677b-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="e677b-108">[了解如何同时添加用户帐户和分配许可证](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="e677b-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e677b-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="e677b-109">Before you begin</span></span>

- <span data-ttu-id="e677b-110">你必须是全局、许可证或用户管理员才能分配许可证。</span><span class="sxs-lookup"><span data-stu-id="e677b-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="e677b-111">有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e677b-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="e677b-112">你可以[使用 Office 365 PowerShell 向用户帐户分配许可证](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="e677b-112">You can [assign licenses to user accounts with Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="e677b-113">若要使用基于组的许可，请参阅[在 Azure Active Directory 中按组成员身份向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="e677b-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="e677b-114">某些服务（如 Sway）会自动分配给用户，无需单独分配。</span><span class="sxs-lookup"><span data-stu-id="e677b-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="e677b-115">使用“许可证”页面向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="e677b-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="e677b-116">使用“**许可证**”页面分配许可证时，最多可向 20 名用户分配特定产品的许可证。</span><span class="sxs-lookup"><span data-stu-id="e677b-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="e677b-117">在“**许可证**”页面上，你将看到你所订阅的所有产品的列表。</span><span class="sxs-lookup"><span data-stu-id="e677b-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="e677b-118">你还将看到每个产品的许可证总数、分配的许可证数以及可用的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="e677b-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e677b-119">在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e677b-120">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a> 内，转到“**计费**”>“**许可证**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e677b-121">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a> 内，转到“**计费**”>“**许可证**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="e677b-122">选择产品。</span><span class="sxs-lookup"><span data-stu-id="e677b-122">Select a product.</span></span>
3. <span data-ttu-id="e677b-123">在产品详细信息页面上，选择“**分配许可证**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="e677b-124">在“**向用户分配许可证**”窗格中，开始键入名称，然后从结果中将其选中，将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="e677b-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="e677b-125">一次最多可添加 20 名用户。</span><span class="sxs-lookup"><span data-stu-id="e677b-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="e677b-126">选择“**打开或关闭应用和服务**”，向特定项目分配访问权限或删除其访问权限。</span><span class="sxs-lookup"><span data-stu-id="e677b-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="e677b-127">完成后，选择“分配”，然后选择“关闭”。</span><span class="sxs-lookup"><span data-stu-id="e677b-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="e677b-128">如果出现冲突，则将显示一则消息，指出问题是什么以及如何修复它。</span><span class="sxs-lookup"><span data-stu-id="e677b-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="e677b-129">例如，如果选择包含冲突服务的许可证，错误消息将指示审阅随每个许可证包含的服务并重试。</span><span class="sxs-lookup"><span data-stu-id="e677b-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="e677b-130">更改用户有权访问的应用和服务</span><span class="sxs-lookup"><span data-stu-id="e677b-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e677b-131">在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-131">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e677b-132">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a> 内，转到“**计费**”>“**许可证**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e677b-133">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a> 内，转到“**计费**”>“**许可证**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-133">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="e677b-134">在“**许可证**”页面上，选择特定用户所对应的行。</span><span class="sxs-lookup"><span data-stu-id="e677b-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="e677b-135">在右侧窗格中，选择或取消选择要授予或取消访问权限的应用和服务。</span><span class="sxs-lookup"><span data-stu-id="e677b-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="e677b-136">完成后，选择“**保存**”，然后选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="e677b-137">使用“活动用户”页面分配许可证</span><span class="sxs-lookup"><span data-stu-id="e677b-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="e677b-138">使用“**活动用户**”页面分配许可证时，将向产品分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="e677b-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="e677b-139">向多个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="e677b-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e677b-140">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e677b-141">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a> 内，转到“**计费**”>“**活动用户**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-141">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e677b-142">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a> 内，转到“**计费**”>“**活动用户**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-142">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="e677b-143">选中要向其分配许可证的用户姓名旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="e677b-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="e677b-144">在顶部选择“**更多选项(...)**”，然后选择“**管理产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-144">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="e677b-145">在“**管理产品许可证**”窗格中，选择“**添加到现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-145">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="e677b-146">在“**添加到现有产品**”窗格中，将希望所选用户具备的许可证的开关切换到“**开**”位置。</span><span class="sxs-lookup"><span data-stu-id="e677b-146">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="e677b-147">默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="e677b-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="e677b-148">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="e677b-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="e677b-149">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-149">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="e677b-150">在窗格底部，选择“**添加**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-150">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="e677b-151">向一个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="e677b-151">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e677b-152">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e677b-153">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a> 内，转到“**计费**”>“**活动用户**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e677b-154">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a> 内，转到“**计费**”>“**活动用户**”页面。</span><span class="sxs-lookup"><span data-stu-id="e677b-154">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="e677b-155">选择要向其分配许可证的用户所对应的行。</span><span class="sxs-lookup"><span data-stu-id="e677b-155">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="e677b-156">在右侧窗格，选择“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-156">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="e677b-157">展开“**许可证**”部分，选择要分配的许可证的框，然后选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-157">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="e677b-158">向来宾用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="e677b-158">Assign a license to a guest user</span></span>

<span data-ttu-id="e677b-159">可在 Azure Active directory 管理中心中邀请来宾用户与你的组织进行协作。</span><span class="sxs-lookup"><span data-stu-id="e677b-159">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="e677b-160">若要了解有关来宾用户的信息，请参阅 [Azure Active Directory B2B 中的来宾用户访问是什么？](/azure/active-directory/external-identities/what-is-b2b)。</span><span class="sxs-lookup"><span data-stu-id="e677b-160">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="e677b-161">如果你没有任何来宾用户，请参阅[快速入门：在 Azure 门户中将来宾用户添加到你的目录](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。</span><span class="sxs-lookup"><span data-stu-id="e677b-161">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e677b-162">必须是全局管理员才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e677b-162">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="e677b-163">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 管理中心</a></span><span class="sxs-lookup"><span data-stu-id="e677b-163">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="e677b-164">在导航窗格中，选择“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-164">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="e677b-165">在“**用户 | 所有用户（预览）**”页面上，选择“**添加筛选器**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-165">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="e677b-166">在“**选择字段**”菜单中，选择“**用户类型**”，然后选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-166">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="e677b-167">在下一个菜单中，选择“**来宾**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-167">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="e677b-168">在结果列表中，选择需要许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="e677b-168">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="e677b-169">在“**管理**”下，选择“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-169">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="e677b-170">选择“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-170">Select **Assignments**.</span></span>
9. <span data-ttu-id="e677b-171">在“**更新许可证分配**”页面上，选择要为其分配许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="e677b-171">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="e677b-172">在右侧，清除不希望来宾用户拥有访问权限的任何服务所对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="e677b-172">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="e677b-173">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e677b-173">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e677b-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e677b-174">Next steps</span></span>

<span data-ttu-id="e677b-175">如果用户尚未安装 Office 应用，你可以与其共享[员工快速入门指南](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)以进行各项设置，如[如何在电脑或 Mac 上下载并安装 Microsoft 365 或 Office 2019](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)以及[如何在移动设备上设置 Office 应用和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="e677b-175">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="e677b-176">相关内容</span><span class="sxs-lookup"><span data-stu-id="e677b-176">Related content</span></span>

<span data-ttu-id="e677b-177">[了解订阅和许可证](../../commerce/licenses/subscriptions-and-licenses.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="e677b-177">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="e677b-178">[取消向用户分配许可证](remove-licenses-from-users.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="e677b-178">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="e677b-179">[购买或删除订阅的许可证](../../commerce/licenses/buy-licenses.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="e677b-179">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>