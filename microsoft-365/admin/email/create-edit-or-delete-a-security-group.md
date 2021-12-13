---
title: 创建、编辑或删除安全Microsoft 365 管理中心
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 了解如何创建、编辑或删除安全组。
ms.openlocfilehash: 3f054842abc5111c654b8da02afc418c36f7db11
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61422275"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>创建、编辑或删除安全Microsoft 365 管理中心

在Microsoft 365 **组**"页上，可以创建用户帐户组，这些用户帐户组可用于在 SharePoint Online 和 CRM Online 中分配相同的权限。 例如，管理员可以创建一个安全组，以向特定用户组授予对 SharePoint 网站的访问权限。 只有全局管理员和"用户管理"管理员拥有创建、编辑或删除安全组的权限；有关管理员角色的详细信息，请参阅[分配管理员角色](../add-users/assign-admin-roles.md)。 
  
也存在您可以用于向用户组发送电子邮件或分配权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)和向用户授权对网站和网站集的权限和访问权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)。 
  
> [!IMPORTANT]
>  计划使用网站邮箱？ 通过安全组添加到 SharePoint 网站而不是单独添加的所有用户只能从 SharePoint 使用网站邮箱。 这些用户将无法从 Outlook 访问网站邮箱。 有关详细信息，请参阅 Use [Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)。 
  
## <a name="manage-security-groups-in-the-admin-center"></a>管理管理中心中的安全组

### <a name="add-a-security-group"></a>添加安全组

1. In the Microsoft 365 管理中心， go to the **Groups**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.
  
2. 在"**组"** 页上，选择 **"添加组"。**
    
3. 在"**选择组类型"页上，** 选择"安全性 **"。** 
    
4. 按照步骤完成组的创建。 
 
### <a name="add-members-to-a-security-group"></a>向安全组添加成员
    
1. 在"组"页上 **选择安全组** 名称，在"成员 **"选项卡上**，选择"**查看所有和管理成员"。** 
    
2. 在组窗格中，选择"**添加** 成员"，然后从列表中选择人员，或在"搜索"框中键入要添加的人的姓名，然后选择"保存 **"。**
    
    若要删除成员，请选择其名称旁边的 X。 
  
### <a name="edit-a-security-group"></a>编辑安全组

1. 在管理中心，转到组 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。
  
2. 在 **"组** "页上，选择组的名称。 
    
3. 在设置窗格中，选择"常规 **"** 选项卡或" **成员** "选项卡以编辑组详细信息或成员。

### <a name="delete-a-security-group"></a>删除安全组

1. 在管理中心，转到组  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。
    
2. 在 **"组** "页上，选择组的名称。 
    
3. 选择 **删除组** (wasetbin) ，然后选择删除 **进行确认**。
    
    选择 **"删除** 组后关闭"。 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Exchange Online 和 SharePoint Online 中的组

如果要创建用户组，以便可以同时向所有用户发送电子邮件，可以在 Exchange 管理中心中通过访问"管理员"Exchange \>  \> **收件人** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**组"。**</a> 接下来，**选择"新建** ![ 添加 ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) "。，然后选择要创建的组类型： 
  
- **通讯组**：用于将邮件分发给一组用户。 它也称为启用邮件的  *通讯组* 或 通讯  *组列表*。 有关详细信息，请参阅管理 [通讯组](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)。
    
- **安全组**：可用于将邮件分发给一组用户，或授予对资源的访问权限。 此组也称为启用 *邮件的安全组*。 有关详细信息，请参阅[管理启用邮件的安全组](/Exchange/recipients/mail-enabled-security-groups)。
    
- **动态通讯组**：一种通讯组类型，每当您基于定义的筛选器和条件发送邮件时，将重新计算收件人列表。 有关详细信息，请参阅 [管理动态通讯组](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)。
    
在管理中心内创建通讯组和启用邮件的安全Exchange，<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank"></a>其名称和用户列表将显示在"安全组 **"** 页面上。 您可以在这两个位置删除这些组，但是只能在 Exchange 管理中心编辑它们。 动态通讯组不会显示在"安全组 **"** 页上。 
  
 SharePoint 组是在您创建网站集时自动创建的。 默认组使用 SharePoint 中的默认权限级别（有时称为 SharePoint 角色）向用户授予权限和访问权限。 有关详细信息，请参阅[Default SharePoint groups in SharePoint Online。](/sharepoint/default-sharepoint-groups)
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>安全组与我在安全组中创建的安全组SharePoint？

安全组可以与 SharePoint、Exchange、MDM Windows等一同使用。 仅在网站集中SharePoint安全组才能识别SharePoint组。
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>是否必须使用安全组来保证我的组织的安全？

否。 这只是您可以为组织管理安全性的另外一种方法。 您始终可以单独授予用户权限和网站访问权限。 但是，使用安全组，可以轻松管理更大的用户组。
  
## <a name="can-i-send-email-to-a-security-group"></a>我能否向安全组发送电子邮件？

是。 但是，如果你想要将组用于电子邮件和协作，我们建议你改为创建Microsoft 365[组](../create-groups/create-groups.md)。 

## <a name="related-content"></a>相关内容

[在文章 Microsoft 365 管理中心](../create-groups/create-groups.md) (创建) \
[向Microsoft 365解释组 (](../create-groups/explain-groups-knowledge-worker.md)文章) \
[在管理组Microsoft 365 管理中心 (](../create-groups/manage-groups.md)管理) 