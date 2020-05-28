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
ms.openlocfilehash: faea21f0e5142d197cc2b90d6ade99490f9f88e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387209"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a>在 Office 365 中创建、编辑或删除自定义用户视图

如果您是 Office 365 的全局管理员或用户管理管理员，则可以创建自定义用户视图以查看特定的用户子集。 这些视图是与 Office 365 附带的标准视图集的补充。 您可以创建、编辑或删除自定义用户视图，您创建的自定义视图可供所有管理员使用。

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a>管理员中心内的自定义用户视图

::: moniker range="o365-worldwide"

在创建、编辑或删除自定义用户视图时，所做的更改将显示在公司中的所有管理员都可以看到的**筛选器**列表中，在转到 "**用户**" 页时。 最高可创建50个自定义视图。 

::: moniker-end

::: moniker range="o365-germany"

在创建、编辑或删除自定义用户视图时，所做的更改将显示在公司中的所有管理员在转到 "**用户**" 页面时看到的 "**视图**" 列表中。 最高可创建50个自定义视图。 

::: moniker-end

::: moniker range="o365-21vianet"

在创建、编辑或删除自定义用户视图时，所做的更改将显示在公司中的所有管理员在转到 "**用户**" 页面时看到的 "**视图**" 列表中。 最高可创建50个自定义视图。 

::: moniker-end

> [!TIP]
>  默认情况下，在 "**筛选器**" 下拉列表中显示标准用户视图。 标准筛选器包括**所有用户**、**许可用户**、**来宾用户**、**允许登录**、**登录被阻止**、**未经许可的用户**、**有错误的用户**、**帐单管理员**、**全局管理员**、**支持人员管理员**、**服务管理员**和**用户管理管理员**。 您不能编辑或删除标准视图。 

有关标准视图的几点注意事项： 

- 如果列表中有超过2000个用户，一些标准视图将显示一个未排序的列表。 若要在此列表中查找特定用户，请使用搜索框。 
- 如果你未从 Microsoft 购买 Microsoft 365，则**计费管理员**不会显示在 "标准视图" 列表中。 有关详细信息，请参阅[分配管理员角色](assign-admin-roles.md)。 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>选择自定义用户视图的筛选器

您可以在**自定义筛选器**窗格中创建和编辑自定义视图。 如果选择 "多个筛选器选项"，则会获得包含符合所有选定条件的用户的结果。 下面的示例演示如何创建一个名为 "加拿大用户" 的自定义视图，该视图显示位于加拿大的特定域中的所有用户。 

  
 **A-域**如果您的组织具有多个域，则可以从可用域的下拉列表中进行选择。 
  
 **B-登录状态**选择允许或阻止的用户。 
  
 **C-位置**从国家/地区下拉列表中选择一个位置。 
  
 **D-分配的产品许可证**从组织中可用的许可证下拉列表中进行选择。 使用此筛选器可显示为其分配了所选许可证的用户。 用户还可能有其他许可证。 
  
您还可以按组织中使用的其他用户配置文件详细信息进行筛选，如部门、城市、省/市/自治区、国家或地区或职务。
  
 **其他条件：**
  
- **仅同步用户**选择此框以显示已与本地 Active Directory 同步的所有用户，而不管是否已激活用户。 
    
- **有错误的用户**选择此框以显示可能有预配错误的用户。 
    
- **未经许可的用户**选中此框以查找尚未分配许可证的所有用户。 此视图的结果还包括拥有 Exchange 邮箱但没有许可证的用户。 若要专门跟踪这些用户，请使用**Exchange 邮箱或存档的 "筛选未经授权的用户**"。 此视图的结果还包括具有 Exchange 存档的用户，但没有许可证。
    
- **拥有 Exchange 邮箱或存档的未授权用户**选择此框以显示在 Exchange Online 中创建并拥有 Exchange 邮箱，但未分配 Microsoft 365 许可证的用户帐户。 此筛选器的结果包括拥有或分配了 Exchange 存档的用户。 

> [!NOTE]
> **具有 Exchange 邮箱的未授权用户**在以下情况运行：
1. 邮箱最近已从**共享**用户转换为**用户**，并且没有许可证。
2. 邮箱最近迁移到 Microsoft 365，但尚未分配许可证。
3. 邮箱已使用 PowerShell 创建，但尚未分配许可证。
4. 已使用 New-remotemailbox cmdlet 创建的新邮箱已为该用户设置。
    
> [!TIP]
> 如果创建的自定义视图返回的用户多于2000个，则不会对生成的用户列表进行排序。 在这种情况下，请使用搜索框查找用户或编辑自定义视图以优化搜索。 
  
## <a name="create-a-custom-user-view"></a>创建自定义用户视图

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 在 "**活动用户**" 页上，选择 "**筛选器**" 并选择 "**新建筛选器**"。
  
3. 在 "**自定义筛选器**" 页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择 "**添加**"。 您的自定义视图现在包含在筛选器的下拉列表中。
    
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 在 "**活动用户**" 页上，选择 "**视图**"，然后选择 "**添加自定义视图**"。
  
3. 在 "**自定义视图**" 页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择 "**添加**"。 您的自定义视图现在包含在筛选器的下拉列表中。

::: moniker-end


::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 在 "**活动用户**" 页上，选择 "**视图**"，然后选择 "**添加自定义视图**"。
  
3. 在 "**自定义视图**" 页上，输入筛选器的名称，选择自定义筛选器的条件，然后选择 "**添加**"。 您的自定义视图现在包含在筛选器的下拉列表中。

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>编辑或删除自定义用户视图

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 在 "**活动用户**" 页上，选择 "**筛选**器"，选择要更改的筛选器，然后选择 "**编辑筛选器**"。 
    
    > [!TIP]
    > 您只能编辑自定义视图。 
  
3. 在 "**自定义筛选器**" 页上，根据需要编辑信息，然后选择 "**保存**"。 或者，若要删除筛选器，请在页面底部选择 "**删除**"。 
    
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 在 "**活动用户**" 页上，选择 "**视图**"，选择要更改的筛选器，然后选择 "**编辑此视图**"。 
    
    > [!TIP]
    > 您只能编辑自定义视图。 
  
3. 在 "**自定义视图**" 页上，根据需要编辑信息，然后选择 "**保存**"。 或者，若要删除筛选器，请在页面底部选择 "**删除自定义视图**"。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 在 "**活动用户**" 页上，选择 "**视图**"，选择要更改的筛选器，然后选择 "**编辑此视图**"。 
    
    > [!TIP]
    > 您只能编辑自定义视图。 
  
3. 在 "**自定义视图**" 页上，根据需要编辑信息，然后选择 "**保存**"。 或者，若要删除筛选器，请在页面底部选择 "**删除自定义视图**"。 

::: moniker-end


     