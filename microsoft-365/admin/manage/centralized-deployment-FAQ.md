---
title: 集中部署常见问题解答
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 从 Microsoft 365 管理中心查看有关集中部署的常见问题解答。
ms.openlocfilehash: 06e3b7973a209cdf40446c5a9511713d779373b8
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221831"
---
# <a name="centralized-deployment-faq"></a>集中部署常见问题解答

建议 Office 365 管理员使用集中部署将 Office 外接程序 (Word、Excel、PowerPoint 和 Outlook) 部署到组织内部的用户和组，只要组织满足本文中概述的集中部署的所有要求。   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>我如何知道我的组织是否设置为集中部署？  

外接程序的集中部署要求用户使用 Microsoft 365 企业应用版 (并且使用组织的登录凭据登录 Office) 并拥有 Exchange Online 邮箱。 订阅目录必须位于 Azure Active Directory 中或已联合到 Azure Active Directory 中。  
 
仅联机邮箱支持集中部署。 它不支持部署到本地 Exchange 邮箱。

可以使用集中[部署兼容性检查器](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   来确定你的订阅是否符合条件。 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>如何使用集中部署将外接程序用户分配作为目标？  

集中部署支持向租户中的单个用户、组和每个人分配工作。 集中部署可用于顶级组或没有父组的组的用户，但不能用于嵌套组或具有父组的组的用户。 集中部署也是大多数 Azure Active Directory 组的一部分，包括 Office 365 组、通讯组列表和安全组。  

为了便于管理，最好使用组分配而不是单个用户分配。
 
有关详细信息，请参阅用户 [和组分配](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)。  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>加载项向所有用户显示需要多久？  

外接程序最多可能需要 24 小时才能显示给所有用户。 外接程序更新、打开或关闭的更改或者外接程序删除可能需要相同的时间。 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>作为管理员，如何管理用户对组织的外接程序的访问权限？

为了便于将加载项部署到用户、组或整个组织，我们建议管理员使用集中部署。

有关管理用户访问权的信息，请参阅：
 - [通过在所有客户端上关闭 Office 应用商店来阻止外接程序下载 (Outlook) ](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [指定可安装和管理 Outlook 加载项的管理员和用户](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>集中部署是否使管理员能够灵活地选择 Outlook 外接程序的部署方法？  

是。 集中部署使管理员能够灵活地选择外接程序部署期间 Outlook 外接程序的三种部署方法之一：

**修复 (默认值)**  外接程序将自动部署到已分配的用户，并且他们无法删除它。  
 
**可用** 用户可以在 Outlook 中安装外接程序，方法为选择"主页">管理员管理的"获取>**加载项"。**
 
**可选** 外接程序将自动部署到分配的用户，但他们可以选择将其删除。  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>管理员能否在外接程序中 (业务) LOB) ？  

是。 管理员可以上载新的清单文件以支持管理员部署的 LOB 加载项的元数据更改。外接程序在下次启动 Office 应用程序时更新。 Web 应用程序可以随时更改。  
 
有关详细信息，请参阅 [业务线加载项](./manage-addins-in-the-admin-center.md)。  

## <a name="can-admins-turn-off-add-ins"></a>管理员可以关闭加载项吗？  

是。 管理员可以从 Microsoft 管理中心为所有用户打开或关闭他们部署的外接程序。

有关详细信息，请参阅 [加载项状态](./manage-addins-in-the-admin-center.md#add-in-states)。  

##  <a name="can-admins-delete-or-remove-add-ins"></a>管理员能否删除或删除加载项？

是。 管理员可以从 Microsoft 管理中心删除为所有用户部署的外接程序。

有关详细信息，请参阅 [删除加载项](./manage-addins-in-the-admin-center.md#delete-an-add-in)。 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>管理员能否使用集中部署从 Office 应用商店部署付费加载项？ 

不正确。 目前，你无法通过集中部署从 Office 应用商店部署付费加载项。  
 
我们建议向 ISV 开发人员联系付费加载项，以请求清单文件或 URL。 然后，租户管理员可以使用集中部署将加载项部署为 LOB 加载项。
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>我需要哪个管理员角色来管理我的组织的外接程序？  

全局管理员是建议的角色，具有对加载项管理生命周期的完全访问权限。 其他管理员角色对外接程序部署生命周期的访问权限有限。 如果你是购买 Microsoft 365 商业版订阅的人，你是全局管理员。 
 
你的订阅附带了一组管理员角色，你可以将其分配给你组织中其他用户。 每个管理员角色映射到常见的业务功能，并授予你组织中人员在 Microsoft 365 管理中心执行特定任务的权限。  
 
有关详细信息，请参阅分配 [管理员角色](../add-users/assign-admin-roles.md?view=o365-worldwide)。 