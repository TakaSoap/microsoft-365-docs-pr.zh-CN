---
title: 了解 Microsoft 365 for business 中的订阅和许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: '了解 Microsoft 365 for business 中的订阅和许可证，并了解谁可以分配许可证以及在将许可证分配给某人时，会发生什么情况。 '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844676"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>了解 Microsoft 365 for business 中的订阅和许可证

本文介绍了订阅和许可证之间的关系，并提供了有关[可分配许可证的人员](#find-out-who-can-assign-licenses)的详细信息，[了解在向某人分配许可证时会发生什么](#understand-what-happens-when-you-assign-a-license-to-someone)，以及[用户可以在哪些设备上安装 Office](#how-many-devices-can-people-install-office-on)。 它还包括[了解非用户邮箱的许可证的](#understand-licenses-for-non-user-mailboxes)链接，以及[有关管理许可证的文章](#articles-about-managing-licenses)。
  
当你购买 Microsoft 365 for business 订阅时，你需要注册一组应用程序和服务，这些应用程序和服务按月或按年的频率付费。 作为订阅的一部分收到的应用程序和服务取决于所购买的产品，如 Microsoft 365 应用程序或 Microsoft 365 商业标准。 您可以查看[购买 Microsoft 365 页面](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)上的每个产品所附带的功能。 

你可以在 Microsoft 365 中查看适用于中小型[企业的](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)不同许可选项

购买订阅时，根据组织中的人数指定所需的许可证数。 完成购买后，为这些人员创建帐户，然后将许可证分配给每个人。 当您的组织需求发生变化时，您可以购买更多许可证以适应新人员，或在某人离开你的组织时将许可证重新分配给其他用户。 

如果有一个以上的订阅，则可以针对每个订阅将许可证分配给不同人员。 例如，您的所有用户都可以作为 Microsoft 365 业务标准订阅的一部分分配给所有 Microsoft 365 应用程序和服务，而用户的子集也可以通过单独的 Visio 订阅分配给 Visio Online。 

  
## <a name="find-out-who-can-assign-licenses"></a>了解谁可以分配许可证

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**管理员角色**|**分配许可证**|**删除许可证**|**购买更多许可证**|**删除帐户**|
|:-----|:-----|:-----|:-----|:-----|
|全局管理员  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|帐务管理员  <br/> |否  <br/> |否  <br/> |必需  <br/> |否  <br/> |
|用户管理管理员  <br/> |是  <br/> |是  <br/> |否  <br/> |可访问  <br/> |
|服务管理员  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|密码管理员  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a>了解为某人分配许可证时会发生的情况

下表列出了在为某人分配许可证时会自动发生的情况：
  
|**如果订阅中有此服务**|**将会自动发生该情况**|
|:-----|:-----|
|Exchange Online  <br/> |将为该人员创建一个邮箱。  <br/> 若要了解此任务的完成 SLA，请参阅["设置 ..."Microsoft 365 管理中心中的邮件](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。 |
|SharePoint Online  <br/> |将为该人员分配默认 SharePoint Online 团队网站的编辑权限。  <br/> |
|Skype for Business Online  <br/> |该人员将拥有与许可证关联的功能的访问权限。  <br/> |
|Microsoft 365 企业应用版  <br/> |此人将能够将 Microsoft Office 下载到多达 5 台的 Mac 或电脑、5 台平板电脑和 5 部智能手机上。  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a>可以在多少台设备上安装 Office？

如果订阅中包含以下任何产品，则每个人都可以将 Office 安装到多达 5 台的 Mac 或电脑、5 台平板电脑和 5 部手机上。
  
- Microsoft 365 商业应用版
    
- Microsoft 365 商业标准版
    
- Microsoft 365 企业应用版
    
- Office 365 企业版 E3
    
- Office 365 企业版 E5
    
## <a name="understand-licenses-for-non-user-mailboxes"></a>了解非用户邮箱的许可证

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [创建共享邮箱](../../admin/email/create-a-shared-mailbox.md)
    
- [Exchange Online 中的共享邮箱](https://go.microsoft.com/fwlink/p/?linkid=847433)，用于所有其他 Microsoft 365 计划。 
    
- [创建和管理会议室邮箱](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [管理设备邮箱](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a>有关管理许可证的文章

- [向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)
    
- [删除用户许可证](../../admin/manage/remove-licenses-from-users.md)
    
- [购买订阅的许可证](buy-licenses.md)
    
- [购买另一个订阅](../buy-another-subscription.md)
    
- [购买或编辑附加设备](../buy-or-edit-an-add-on.md)
    
- [从订阅中删除许可证](remove-licenses-from-subscription.md)
    
- [解决许可证冲突](../../admin/manage/resolve-license-conflicts.md)
    
- [管理 Yammer 用户许可证](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
