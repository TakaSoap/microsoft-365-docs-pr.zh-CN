---
title: 在 Microsoft 365 管理中心中创建、编辑或删除安全组
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 了解如何创建、编辑或删除安全组。
ms.openlocfilehash: 689adb46bdec4d4f669482af6b5467fdcf63482c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628875"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心中创建、编辑或删除安全组

在 "Microsoft 365**组**" 页上，您可以创建可用于在 SharePoint ONLINE 和 CRM online 中为其分配相同权限的用户帐户组。 例如，管理员可以创建一个安全组，以向特定用户组授予对 SharePoint 网站的访问权限。 只有全局管理员和"用户管理"管理员拥有创建、编辑或删除安全组的权限；有关管理员角色的详细信息，请参阅[分配管理员角色](../add-users/assign-admin-roles.md)。 
  
也存在您可以用于向用户组发送电子邮件或分配权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)和向用户授权对网站和网站集的权限和访问权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)。 
  
> [!IMPORTANT]
>  计划使用网站邮箱？ 通过安全组添加到 SharePoint 网站而不是单独添加的所有用户只能从 SharePoint 使用网站邮箱。 这些用户将无法从 Outlook 访问网站邮箱。 有关详细信息，请参阅[使用 Microsoft 365 组而不是站点邮箱](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)。 
  
## <a name="manage-security-groups-in-the-admin-center"></a>管理中心中的安全组

### <a name="add-a-security-group"></a>添加安全组

1. 在 Microsoft 365 管理中心，转到 "**组** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。
  
2. 在 "**组**" 页上，选择 "**添加组**"。
    
3. 在 "**选择组类型**" 页上，选择 "**安全性**"。 
    
4. 按照步骤完成组的创建。 
 
### <a name="add-members-to-a-security-group"></a>将成员添加到安全组

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。
    
1. 在 "**组**" 页上选择安全组名称，然后在 "**成员**" 选项卡上选择 "**查看所有和管理成员**"。 
    
2. 在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。
    
    若要删除成员，请选择其名称旁边的 X。 
  
::: moniker-end

::: moniker range="o365-germany"

1. 在 "**组**" 页上选择安全组名称，然后选择 "**成员**" 旁边的 "**编辑**"。 
    
2. 在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。
    
    若要删除成员，请选择其名称旁边的 X。 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. 在 "**组**" 页上选择安全组名称，然后选择 "**成员**" 旁边的 "**编辑**"。 
    
2. 在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。
    
    若要删除成员，请选择其名称旁边的 X。

::: moniker-end

### <a name="edit-a-security-group"></a>编辑安全组

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

1. 在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。
  
2. 在 "**组**" 页上，选择组的名称。 
    
3. 在 "设置" 窗格中，选择 "**常规**" 选项卡或 "**成员**" 选项卡以编辑组的详细信息或成员。

::: moniker-end

::: moniker range="o365-germany"

1. 在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。
  
2. 在 "**组**" 页上，选择组的名称。 
    
3. 在 "安全组" 窗格中，选择 "**名称**" 或 "**成员**" 选项卡旁边的 "**编辑**" 以编辑组的详细信息或成员。
    
4. 完成更改后，选择 "**保存** \> " "**关闭**"。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。
  
2. 在 "**组**" 页上，选择组的名称。 
    
3. 在 "安全组" 窗格中，选择 "**名称**" 或 "**成员**" 选项卡旁边的 "**编辑**" 以编辑组的详细信息或成员。
    
4. 完成更改后，选择 "**保存** > " "**关闭**"。

::: moniker-end


### <a name="delete-a-security-group"></a>删除安全组

1. 在 "管理中心" 中，转到 "**组** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。
    
2. 在 "**组**" 页上，选择组的名称。 
    
3. 选择 "**删除组**" （wasetbin 图标），然后选择 "**删除**" 进行确认。
    
    删除组后，选择 "**关闭**"。 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Exchange Online 和 SharePoint Online 中的组

如果要创建用户组，以便可以同时向其发送电子邮件，您可以通过转到 "**管理员** \> **Exchange** \> **收件人** \> **组**" 在 Exchange 管理中心中执行此操作。 接下来， **New**![选择 "](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)新建添加"，然后选择要创建的组类型： 
  
- **通讯组**：用于将邮件分发给一组用户。 它也称为*启用邮件的通讯组*或*通讯组列表*。 有关详细信息，请参阅[管理通讯组](https://technet.microsoft.com/library/bb124513.aspx)。
    
- **安全组**：可用于将邮件分发给一组用户，或授予对资源的访问权限。 该组也称为*启用邮件的安全组*。 有关详细信息，请参阅[管理启用邮件的安全组](https://technet.microsoft.com/library/bb123521.aspx)。
    
- **动态通讯组**：一种通讯组类型，每当您基于定义的筛选器和条件发送邮件时，将重新计算收件人列表。 有关详细信息，请参阅 [管理动态通讯组](https://technet.microsoft.com/library/bb123722.aspx)。
    
在 Exchange 管理中心中创建通讯组和已启用邮件的安全组之后，其名称和用户列表将显示在 "**安全组**" 页面上。 您可以在这两个位置删除这些组，但是只能在 Exchange 管理中心编辑它们。 "**安全组**" 页上未显示动态通讯组。 
  
 SharePoint 组是在您创建网站集时自动创建的。 默认组使用 SharePoint 中的默认权限级别（有时称为 SharePoint 角色）向用户授予权限和访问权限。 有关详细信息，请参阅[Sharepoint Online 中的默认 SharePoint 组](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx)。
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>在 SharePoint 中，安全组与我在 SharePoint 中创建的安全组有何不同？

安全组可与 SharePoint、Exchange、MDM、Windows 等一起使用。 在 SharePoint 中创建的安全组只能由该 SharePoint 网站集识别。
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>我是否需要使用安全组来保护组织的安全？

不正确。 这只是管理组织安全性的一种更好的方法。 您可以始终授予用户权限并单独访问网站。 但使用安全组，您可以轻松地管理更多的用户组。
  
## <a name="can-i-send-email-to-a-security-group"></a>我是否可以向安全组发送电子邮件？

可以。 但是，如果您想要使用组进行电子邮件和协作，我们建议您改为[创建 Microsoft 365 组](../create-groups/create-groups.md)。 
  
