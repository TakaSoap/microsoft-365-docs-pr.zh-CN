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
description: 了解如何使用筛选器在 Microsoft 365 中创建、编辑或删除自定义用户视图。
ms.openlocfilehash: 265aa1a7c22475710a12a93c2bfee0b7749f438b
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431637"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="9cb81-103">在 Office 365 中创建、编辑或删除自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="9cb81-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="9cb81-104">如果您是 Office 365 的全局管理员或用户管理管理员，则可以创建自定义用户视图以查看特定的用户子集。</span><span class="sxs-lookup"><span data-stu-id="9cb81-104">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="9cb81-105">这些视图是与 Office 365 附带的标准视图集的补充。</span><span class="sxs-lookup"><span data-stu-id="9cb81-105">These views are in addition to the standard set of views that come with Office 365.</span></span> <span data-ttu-id="9cb81-106">您可以创建、编辑或删除自定义用户视图，您创建的自定义视图可供所有管理员使用。</span><span class="sxs-lookup"><span data-stu-id="9cb81-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="9cb81-107">管理员中心内的自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="9cb81-107">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="9cb81-108">在创建、编辑或删除自定义用户视图时，所做的更改将显示在公司中的所有管理员都可以看到的**筛选器**列表中，在转到 "**用户**" 页时。</span><span class="sxs-lookup"><span data-stu-id="9cb81-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="9cb81-109">最高可创建50个自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-109">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="9cb81-110">在创建、编辑或删除自定义用户视图时，所做的更改将显示在公司中的所有管理员在转到 "**用户**" 页面时看到的 "**视图**" 列表中。</span><span class="sxs-lookup"><span data-stu-id="9cb81-110">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="9cb81-111">最高可创建50个自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-111">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="9cb81-112">在创建、编辑或删除自定义用户视图时，所做的更改将显示在公司中的所有管理员在转到 "**用户**" 页面时看到的 "**视图**" 列表中。</span><span class="sxs-lookup"><span data-stu-id="9cb81-112">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="9cb81-113">最高可创建50个自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-113">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="9cb81-114">默认情况下，在 "**筛选器**" 下拉列表中显示标准用户视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-114">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="9cb81-115">标准筛选器包括**所有用户**、**许可用户**、**来宾用户**、**允许登录**、**登录被阻止**、**未经许可的用户**、**有错误的用户**、**帐单管理员**、**全局管理员**、**支持人员管理员**、**服务管理员**和**用户管理管理员**。</span><span class="sxs-lookup"><span data-stu-id="9cb81-115">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="9cb81-116">您不能编辑或删除标准视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-116">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="9cb81-117">有关标准视图的几点注意事项：</span><span class="sxs-lookup"><span data-stu-id="9cb81-117">A few things to note about standard views:</span></span> 

- <span data-ttu-id="9cb81-118">如果列表中有超过2000个用户，一些标准视图将显示一个未排序的列表。</span><span class="sxs-lookup"><span data-stu-id="9cb81-118">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="9cb81-119">若要在此列表中查找特定用户，请使用搜索框。</span><span class="sxs-lookup"><span data-stu-id="9cb81-119">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="9cb81-120">如果你未从 Microsoft 购买 Microsoft 365，则**计费管理员**不会显示在 "标准视图" 列表中。</span><span class="sxs-lookup"><span data-stu-id="9cb81-120">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="9cb81-121">有关详细信息，请参阅[分配管理员角色](assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="9cb81-121">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="9cb81-122">选择自定义用户视图的筛选器</span><span class="sxs-lookup"><span data-stu-id="9cb81-122">Choose the filters for your custom user view</span></span>

<span data-ttu-id="9cb81-123">您可以在**自定义筛选器**窗格中创建和编辑自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-123">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="9cb81-124">如果选择 "多个筛选器选项"，则会获得包含符合所有选定条件的用户的结果。</span><span class="sxs-lookup"><span data-stu-id="9cb81-124">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="9cb81-125">下面的示例演示如何创建一个名为 "加拿大用户" 的自定义视图，该视图显示位于加拿大的特定域中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-125">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="9cb81-126">**A-域**如果您的组织具有多个域，则可以从可用域的下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="9cb81-126">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="9cb81-127">**B-登录状态**选择允许或阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-127">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="9cb81-128">**C-位置**从国家/地区下拉列表中选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="9cb81-128">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="9cb81-129">**D-分配的产品许可证**从组织中可用的许可证下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="9cb81-129">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="9cb81-130">使用此筛选器可显示为其分配了所选许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-130">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="9cb81-131">用户还可能有其他许可证。</span><span class="sxs-lookup"><span data-stu-id="9cb81-131">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="9cb81-132">您还可以按组织中使用的其他用户配置文件详细信息进行筛选，如部门、城市、省/市/自治区、国家或地区或职务。</span><span class="sxs-lookup"><span data-stu-id="9cb81-132">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="9cb81-133">**其他条件：**</span><span class="sxs-lookup"><span data-stu-id="9cb81-133">**Other conditions:**</span></span>
  
- <span data-ttu-id="9cb81-134">**仅同步用户**选择此框以显示已与本地 Active Directory 同步的所有用户，而不管是否已激活用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-134">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="9cb81-135">**有错误的用户**选择此框以显示可能有预配错误的用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-135">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="9cb81-136">**未经许可的用户**选中此框以查找尚未分配许可证的所有用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-136">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="9cb81-137">此视图的结果还包括拥有 Exchange 邮箱但没有许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-137">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="9cb81-138">若要专门跟踪这些用户，请使用**Exchange 邮箱或存档的 "筛选未经授权的用户**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-138">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="9cb81-139">此视图的结果还包括具有 Exchange 存档的用户，但没有许可证。</span><span class="sxs-lookup"><span data-stu-id="9cb81-139">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="9cb81-140">**拥有 Exchange 邮箱或存档的未授权用户**选择此框以显示在 Exchange Online 中创建并拥有 Exchange 邮箱，但未分配 Microsoft 365 许可证的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-140">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="9cb81-141">此筛选器的结果包括拥有或分配了 Exchange 存档的用户。</span><span class="sxs-lookup"><span data-stu-id="9cb81-141">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="9cb81-142">**具有 Exchange 邮箱的未授权用户**在以下情况运行：</span><span class="sxs-lookup"><span data-stu-id="9cb81-142">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="9cb81-143">邮箱最近已从**共享**用户转换为**用户**，并且没有许可证。</span><span class="sxs-lookup"><span data-stu-id="9cb81-143">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="9cb81-144">邮箱最近迁移到 Microsoft 365，但尚未分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9cb81-144">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="9cb81-145">邮箱已使用 PowerShell 创建，但尚未分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9cb81-145">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="9cb81-146">已使用 New-remotemailbox cmdlet 创建的新邮箱已为该用户设置。</span><span class="sxs-lookup"><span data-stu-id="9cb81-146">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="9cb81-147">如果创建的自定义视图返回的用户多于2000个，则不会对生成的用户列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="9cb81-147">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="9cb81-148">在这种情况下，请使用搜索框查找用户或编辑自定义视图以优化搜索。</span><span class="sxs-lookup"><span data-stu-id="9cb81-148">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="9cb81-149">创建自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="9cb81-149">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cb81-150">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cb81-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="9cb81-151">在 "**活动用户**" 页上，选择 "**筛选器**" 并选择 "**新建筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-151">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="9cb81-152">在 "**自定义筛选器**" 页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-152">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="9cb81-153">您的自定义视图现在包含在筛选器的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="9cb81-153">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cb81-154">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cb81-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="9cb81-155">在 "**活动用户**" 页上，选择 "**视图**"，然后选择 "**添加自定义视图**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="9cb81-156">在 "**自定义视图**" 页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="9cb81-157">您的自定义视图现在包含在筛选器的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="9cb81-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cb81-158">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cb81-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="9cb81-159">在 "**活动用户**" 页上，选择 "**视图**"，然后选择 "**添加自定义视图**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-159">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="9cb81-160">在 "**自定义视图**" 页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-160">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="9cb81-161">您的自定义视图现在包含在筛选器的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="9cb81-161">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="9cb81-162">编辑或删除自定义用户视图</span><span class="sxs-lookup"><span data-stu-id="9cb81-162">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cb81-163">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cb81-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="9cb81-164">在 "**活动用户**" 页上，选择 "**筛选**器"，选择要更改的筛选器，然后选择 "**编辑筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-164">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="9cb81-165">您只能编辑自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-165">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="9cb81-166">在 "**自定义筛选器**" 页上，根据需要编辑信息，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-166">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="9cb81-167">或者，若要删除筛选器，请在页面底部选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-167">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cb81-168">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cb81-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="9cb81-169">在 "**活动用户**" 页上，选择 "**视图**"，选择要更改的筛选器，然后选择 "**编辑此视图**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-169">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="9cb81-170">您只能编辑自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-170">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="9cb81-171">在 "**自定义视图**" 页上，根据需要编辑信息，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-171">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="9cb81-172">或者，若要删除筛选器，请在页面底部选择 "**删除自定义视图**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-172">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cb81-173">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cb81-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="9cb81-174">在 "**活动用户**" 页上，选择 "**视图**"，选择要更改的筛选器，然后选择 "**编辑此视图**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-174">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="9cb81-175">您只能编辑自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9cb81-175">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="9cb81-176">在 "**自定义视图**" 页上，根据需要编辑信息，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-176">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="9cb81-177">或者，若要删除筛选器，请在页面底部选择 "**删除自定义视图**"。</span><span class="sxs-lookup"><span data-stu-id="9cb81-177">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     