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
description: 了解如何使用筛选器在 Microsoft 365 中创建自定义用户视图、编辑或删除自定义用户视图。
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755568"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>创建、编辑或删除自定义用户视图

如果你是 Microsoft 365 商业版订阅的全局管理员或用户管理管理员，你可以创建自定义用户视图来查看特定用户子集。 这些视图是标准视图集之外。 你可以创建、编辑或删除自定义用户视图，你创建的自定义视图可供所有管理员使用。
  
## <a name="custom-user-views-in-the-admin-center"></a>管理中心中的自定义用户视图

创建、编辑或删除自定义用户视图时，更改将显示在公司中所有管理员转到"用户"页面时所看到的"筛选器 **"** 列表中。 您最多可以创建 50 个自定义视图。 

> [!TIP]
>  默认情况下，标准用户视图显示在"筛选器"下拉列表中。 标准筛选器包括 **所有用户**、许可用户、来宾用户、允许登录、阻止登录、未授权用户、出错用户、帐单管理员、**全局** 管理员、**支持** 管理员、服务管理员和用户管理 **管理员**。   不能编辑或删除标准视图。 

有关标准视图的一些注意事项： 

- 如果列表中的用户数超过 2，000，则某些标准视图会显示未排序的列表。 若要在此列表中查找特定用户，请使用搜索框。 
- 如果未从 Microsoft 购买 Microsoft 365，则帐单管理员不会显示在标准视图列表中。 有关详细信息，请参阅[分配管理员角色](assign-admin-roles.md)。 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>为自定义用户视图选择筛选器

您可以在"自定义筛选器"窗格中创建 **和编辑自定义视图** 。 如果选择多个筛选选项，则得到的结果将包含匹配所有选定条件的用户。 以下示例演示如何创建一个名为"Canada users"的自定义视图，该视图显示位于加拿大的特定域中的所有用户。 

  
 **A - 域** 如果您的组织有多个域，您可以从可用的域下拉列表中选择。 
  
 **B - 登录状态** 选择允许或阻止的用户。 
  
 **C - 位置** 从国家/地区下拉列表中选择一个位置。 
  
 **D - 分配的产品许可证** 从组织中可用的许可证下拉列表中选择。 使用此筛选器显示分配了所选许可证的用户。 用户可能还具有其他许可证。 
  
您还可以按组织中使用的其他用户配置文件详细信息（如部门、城市、省/市/自治区、国家/地区或职务）进行筛选。
  
 **其他条件：**
  
- **仅同步用户** 选中此框可显示已与本地 Active Directory 同步的所有用户，而不管用户是否已激活。 
    
- **出错的用户** 选中此框可显示可能有设置错误的用户。 
    
- **未授权用户** 选中此框可查找尚未分配许可证的所有用户。 此视图的结果还可以包括拥有 Exchange 邮箱但没有许可证的用户。 若要专门跟踪这些用户，请使用筛选器 **"未授权用户和 Exchange 邮箱或存档"。** 此视图的结果还可以包括具有 Exchange 存档但没有许可证的用户。
    
- **具有 Exchange 邮箱或存档的未授权用户** 选中此框可显示在 Exchange Online 中创建且具有 Exchange 邮箱但没有分配 Microsoft 365 许可证的用户帐户。 此筛选器的结果包括拥有或分配有 Exchange 存档的用户。 

> [!NOTE]
> 具有 **Exchange 邮箱的未授权用户筛选器** 在以下时间工作：
1. 邮箱最近从共享转换为 **用户，** 并且没有许可证。 
2. 邮箱最近已迁移到 Microsoft 365，但尚未分配许可证。
3. 邮箱已使用 PowerShell 创建，尚未分配许可证。
4. 为用户设置使用 New-RemoteMailbox cmdlet 在内部部署中创建的新邮箱。
    
> [!TIP]
> 如果创建的自定义视图返回的用户数超过 2，000，则生成的用户列表不会排序。 在这种情况下，使用搜索框查找用户或编辑自定义视图以优化搜索。 
  
## <a name="create-a-custom-user-view"></a>创建自定义用户视图

::: moniker range="o365-worldwide"

1. 在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户"。</a>
    
2. 在"**活动用户"** 页上，选择"**筛选器**"，然后选择"**新建筛选器"。**
  
3. 在"**自定义筛选器**"页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择"添加 **"。** 您的自定义视图现在包含在筛选器的下拉列表中。
    
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户"。</a>  

2. 在"**活动用户"** 页上，选择 **"视图**"，然后选择"**添加自定义视图"。**
  
3. 在"**自定义视图**"页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择"添加 **"。** 您的自定义视图现在包含在筛选器的下拉列表中。

::: moniker-end


::: moniker range="o365-21vianet"

1. 在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户"。</a> 

2. 在"**活动用户"** 页上，选择 **"视图**"，然后选择"**添加自定义视图"。**
  
3. 在"**自定义视图**"页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择"添加 **"。** 您的自定义视图现在包含在筛选器的下拉列表中。

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>编辑或删除自定义用户视图

::: moniker range="o365-worldwide"

1. 在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户"。</a>
    
2. 在"**活动用户"** 页上，选择"筛选器"，选择要更改的筛选器，然后选择"编辑 **筛选器"。** 
    
    > [!TIP]
    > 只能编辑自定义视图。 
  
3. 在"**自定义筛选器"** 页上，根据需要编辑信息，然后选择"保存 **"。** 或者，若要删除筛选器，请在页面底部选择"删除 **"。** 
    
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户"。</a>  

2. 在"**活动用户"** 页上，选择"**视图**"，选择要更改的筛选器，然后选择"**编辑此视图"。** 
    
    > [!TIP]
    > 只能编辑自定义视图。 
  
3. 在"**自定义视图"** 页上，根据需要编辑信息，然后选择"保存 **"。** 或者，若要删除筛选器，请在页面底部选择"删除 **自定义视图"。** 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到"用户 **""** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户"。</a> 

2. 在"**活动用户"** 页上，选择"**视图**"，选择要更改的筛选器，然后选择"**编辑此视图"。** 
    
    > [!TIP]
    > 只能编辑自定义视图。 
  
3. 在"**自定义视图"** 页上，根据需要编辑信息，然后选择"保存 **"。** 或者，若要删除筛选器，请在页面底部选择"删除 **自定义视图"。** 

::: moniker-end


     