---
title: 集中部署常见问题
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 查看有关从 Microsoft 365 管理中心进行集中部署的常见问题解答。
ms.openlocfilehash: 39df2ec5a1671f800572bc845581bdbe2716d209
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209660"
---
# <a name="centralized-deployment-faq"></a>集中部署常见问题

通过集中部署，Office 365 管理员可以将 Office 外接程序（Word、Excel、PowerPoint 和 Outlook）部署到组织内的用户和组，前提是组织满足本文中所述的使用集中部署的所有要求。   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>如何知道我的组织是否设置了集中式部署？  

集中部署加载项需要用户使用 Office 365 专业增强版（并使用组织的登录凭据登录到 Office）并拥有 Exchange Online 邮箱。 你的订阅目录必须在 Azure Active Directory 中或联合到 Azure Active Directory。  
 
仅联机邮箱支持集中部署。 它不支持部署到本地 Exchange 邮箱。
 
您可以使用[Office 365 集中部署兼容性检查器](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) 来确定您的订阅是否符合条件。 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>如何将加载项用户分配与集中部署进行定位？  

集中部署支持对租户中的单个用户、组和每个人的工作分配。 集中部署可用于顶级组或没有父组的组中的用户，但不能用于具有父组的嵌套组或组中的用户。 集中部署也是大多数 Azure Active Directory 组（包括 Office 365 组、通讯组列表和安全组）的一部分。  

最好使用组分配（而不是单个用户分配）来简化管理。
 
有关更多详细信息，请参阅[User And Group 赋值](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)。  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>为所有用户显示外接程序需要多长时间？  

加载项最长可能需要24小时才能显示给所有用户。 加载项更新、打开或关闭更改或外接程序的更改可能需要相同的时间量。 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>作为管理员，如何管理用户对我的组织的外接程序的访问？

为了方便地将外接程序部署到用户、组或整个组织，我们建议管理员使用集中部署。

有关管理用户访问的详细信息，请参阅 </br>[通过在所有客户端（Outlook 除外）中关闭 Office 应用商店来阻止外接程序下载](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) </br>[指定可以安装和管理适用于 Outlook 的外接程序的管理员和用户](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN)。

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>集中部署是否为管理员提供了选择 Outlook 外接程序的部署方法的灵活性？  

正确。 集中部署为管理员提供了在加载项部署过程中选择 Outlook 外接程序的三种部署方法之一的灵活性：

**固定（默认值）**  外接将自动部署到分配的用户，并且无法将其删除。  
 
**可用**用户可以通过选择 "家庭 > 获取更多加载项 > 管理员管理" 来在 Outlook 中安装外接程序。   
 
**可选**加载项将自动部署到分配的用户，但可以选择将其删除。  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>管理员是否可以更新业务线（LOB）加载项？  

正确。 管理员可以上传新的清单文件，以支持管理员部署的 LOB 外接程序的元数据更改。下次 Office 应用程序启动时，外接程序会更新。 Web 应用程序可以随时更改。  
 
有关详细信息，请参阅[业务线外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins)。  

## <a name="can-admins-turn-off-add-ins"></a>管理员是否可以关闭外接程序？  

正确。 管理员可以打开或关闭他们为 Microsoft 管理中心中的所有用户部署的外接程序。

有关详细信息，请参阅[外接程序状态](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states)。  

##  <a name="can-admins-delete-or-remove-add-ins"></a>是否可以管理员删除或删除加载项？

正确。 管理员可以从 Microsoft 管理中心删除为所有用户部署的外接程序。

有关详细信息，请参阅[删除外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in)。 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>管理员是否可以使用集中部署从 Office 应用商店部署付费的外接程序？ 

不是。 此时无法使用集中部署从 Office 应用商店中部署付费的外接程序。  
 
建议与付费外接程序的 ISV 开发人员联系，以请求清单文件或 URL。 然后，租户管理员可以使用集中部署将加载项部署为 LOB 加载项。
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>我需要哪些管理员角色来管理组织的外接程序？  

您必须具有全局管理员角色才能管理外接程序。如果你是购买 Microsoft 365 for business 订阅的人员，则表示你是全局管理员。 
 
您的订阅附带有一组管理员角色，您可以将其分配给组织中的其他用户。 每个管理员角色都映射到常用业务功能，并向组织中的人员授予在 Microsoft 365 管理中心中执行特定任务的权限。  
 
有关详细信息，请参阅[分配管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)。  