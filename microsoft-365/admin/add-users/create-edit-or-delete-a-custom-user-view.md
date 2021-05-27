---
title: 创建、编辑或删除自定义用户视图
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: 了解如何使用筛选器在自定义视图中创建、编辑或删除Microsoft 365。
ms.openlocfilehash: b4177a561d13d76f6d5a0a1077fe8037d469ee48
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683219"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="4259c-103">创建、编辑或删除自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="4259c-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="4259c-104">如果你是企业版订阅的全局管理员或Microsoft 365管理员，你可以创建自定义用户视图来查看特定用户子集。</span><span class="sxs-lookup"><span data-stu-id="4259c-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="4259c-105">这些视图是标准视图集之外。</span><span class="sxs-lookup"><span data-stu-id="4259c-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="4259c-106">你可以创建、编辑或删除自定义用户视图，你创建的自定义视图可供所有管理员使用。</span><span class="sxs-lookup"><span data-stu-id="4259c-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="4259c-107">管理中心中的自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="4259c-107">Custom user views in the admin center</span></span>

<span data-ttu-id="4259c-108">创建、编辑或删除自定义用户视图时，更改将显示在公司中所有管理员转到"用户"页面时所看到的"筛选器 **"** 列表中。</span><span class="sxs-lookup"><span data-stu-id="4259c-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="4259c-109">您最多可以创建 50 个自定义视图。</span><span class="sxs-lookup"><span data-stu-id="4259c-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="4259c-110">默认情况下，标准用户视图显示在"筛选器"下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="4259c-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="4259c-111">标准筛选器包括 **所有用户**、许可用户、来宾用户、允许登录、阻止登录、未授权用户、出错用户、帐单管理员、**全局** 管理员、**支持** 管理员、服务管理员和用户管理 **管理员**。  </span><span class="sxs-lookup"><span data-stu-id="4259c-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="4259c-112">不能编辑或删除标准视图。</span><span class="sxs-lookup"><span data-stu-id="4259c-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="4259c-113">有关标准视图的一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="4259c-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="4259c-114">如果列表中的用户数超过 2，000，则某些标准视图会显示未排序的列表。</span><span class="sxs-lookup"><span data-stu-id="4259c-114">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="4259c-115">若要在此列表中查找特定用户，请使用搜索框。</span><span class="sxs-lookup"><span data-stu-id="4259c-115">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="4259c-116">如果未从 Microsoft 购买Microsoft 365，帐单管理员不会显示在标准视图列表中。</span><span class="sxs-lookup"><span data-stu-id="4259c-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="4259c-117">有关详细信息，请参阅[分配管理员角色](assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4259c-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="4259c-118">为自定义用户视图选择筛选器</span><span class="sxs-lookup"><span data-stu-id="4259c-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="4259c-119">您可以在"自定义筛选器"窗格中创建 **和编辑自定义视图** 。</span><span class="sxs-lookup"><span data-stu-id="4259c-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="4259c-120">如果选择多个筛选选项，则得到的结果将包含匹配所有选定条件的用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="4259c-121">以下示例演示如何创建一个名为"Canada users"的自定义视图，该视图显示位于加拿大的特定域中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="4259c-122">**A - 域** 如果您的组织有多个域，您可以从可用的域下拉列表中选择。</span><span class="sxs-lookup"><span data-stu-id="4259c-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="4259c-123">**B - 登录状态** 选择允许或阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="4259c-124">**C - 位置** 从国家/地区下拉列表中选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="4259c-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="4259c-125">**D - 分配的产品许可证** 从组织中可用的许可证下拉列表中选择。</span><span class="sxs-lookup"><span data-stu-id="4259c-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="4259c-126">使用此筛选器显示分配了所选许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="4259c-127">用户可能还具有其他许可证。</span><span class="sxs-lookup"><span data-stu-id="4259c-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="4259c-128">您还可以按组织中使用的其他用户配置文件详细信息（如部门、城市、省/市/自治区、国家/地区或职务）进行筛选。</span><span class="sxs-lookup"><span data-stu-id="4259c-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="4259c-129">**其他条件：**</span><span class="sxs-lookup"><span data-stu-id="4259c-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="4259c-130">**仅同步用户** 选中此框可显示已与本地 Active Directory 同步的所有用户，而不管用户是否已激活。</span><span class="sxs-lookup"><span data-stu-id="4259c-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="4259c-131">**出错的用户** 选中此框可显示可能有设置错误的用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="4259c-132">**未授权用户** 选中此框可查找尚未分配许可证的所有用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-132">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="4259c-133">此视图的结果还可以包括拥有邮箱Exchange但没有许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-133">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="4259c-134">若要专门跟踪这些用户，请使用筛选器"未授权用户Exchange **邮箱或存档。**</span><span class="sxs-lookup"><span data-stu-id="4259c-134">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="4259c-135">此视图的结果还可以包括具有存档Exchange但没有许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-135">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="4259c-136">**具有邮箱或存档Exchange未授权的用户** 选中此框可显示在 Exchange Online 中创建的用户帐户，Exchange邮箱，但没有分配Microsoft 365许可证。</span><span class="sxs-lookup"><span data-stu-id="4259c-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="4259c-137">此筛选器的结果包括拥有或分配了存档Exchange用户。</span><span class="sxs-lookup"><span data-stu-id="4259c-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="4259c-138">在 **符合以下条件时，具有Exchange许可证的用户筛选器** 可以正常工作：</span><span class="sxs-lookup"><span data-stu-id="4259c-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="4259c-139">邮箱最近从共享转换为 **用户，** 并且没有许可证。 </span><span class="sxs-lookup"><span data-stu-id="4259c-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="4259c-140">邮箱最近已迁移到 Microsoft 365但尚未分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4259c-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="4259c-141">邮箱已使用 PowerShell 创建，尚未分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4259c-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="4259c-142">为用户设置使用 New-RemoteMailbox cmdlet 在内部部署中创建的新邮箱。</span><span class="sxs-lookup"><span data-stu-id="4259c-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="4259c-143">如果创建的自定义视图返回的用户数超过 2，000，则生成的用户列表不会排序。</span><span class="sxs-lookup"><span data-stu-id="4259c-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="4259c-144">在这种情况下，使用搜索框查找用户或编辑自定义视图以优化搜索。</span><span class="sxs-lookup"><span data-stu-id="4259c-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="4259c-145">创建自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="4259c-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4259c-146">在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户"。</a></span><span class="sxs-lookup"><span data-stu-id="4259c-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4259c-147">在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户"。</a></span><span class="sxs-lookup"><span data-stu-id="4259c-147">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4259c-148">在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户"。</a></span><span class="sxs-lookup"><span data-stu-id="4259c-148">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span>  

::: moniker-end
    
2. <span data-ttu-id="4259c-149">在"**活动用户"** 页上，选择"**筛选器**"，然后选择"**新建筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4259c-149">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="4259c-150">在"**自定义筛选器**"页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="4259c-150">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="4259c-151">您的自定义视图现在包含在筛选器的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="4259c-151">Your custom view is now included in the drop-down list of filters.</span></span>

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="4259c-152">编辑或删除自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="4259c-152">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4259c-153">在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户"。</a></span><span class="sxs-lookup"><span data-stu-id="4259c-153">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4259c-154">在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户"。</a></span><span class="sxs-lookup"><span data-stu-id="4259c-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4259c-155">在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户"。</a></span><span class="sxs-lookup"><span data-stu-id="4259c-155">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

::: moniker-end 
    
2. <span data-ttu-id="4259c-156">在"**活动用户"** 页上，选择"筛选器"，选择要更改的筛选器，然后选择"编辑 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4259c-156">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4259c-157">只能编辑自定义视图。</span><span class="sxs-lookup"><span data-stu-id="4259c-157">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="4259c-158">在"**自定义筛选器"** 页上，根据需要编辑信息，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="4259c-158">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="4259c-159">或者，若要删除筛选器，请在页面底部选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="4259c-159">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 

## <a name="related-content"></a><span data-ttu-id="4259c-160">相关内容</span><span class="sxs-lookup"><span data-stu-id="4259c-160">Related content</span></span>

<span data-ttu-id="4259c-161">[管理中心Microsoft 365视频](../../business-video/admin-center-overview.md) (概述) </span><span class="sxs-lookup"><span data-stu-id="4259c-161">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>\
<span data-ttu-id="4259c-162">[关于管理员角色](../add-users/about-admin-roles.md) (视频) </span><span class="sxs-lookup"><span data-stu-id="4259c-162">[About admin roles](../add-users/about-admin-roles.md) (video)</span></span>\
<span data-ttu-id="4259c-163">[自定义Microsoft 365主题， (](../setup/customize-your-organization-theme.md)文章) </span><span class="sxs-lookup"><span data-stu-id="4259c-163">[Customize the Microsoft 365 theme for your organization](../setup/customize-your-organization-theme.md) (article)</span></span>


     