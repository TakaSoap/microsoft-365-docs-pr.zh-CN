---
title: 了解 Microsoft 365 for business 中的订阅和许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解 Microsoft 365 for business 中的订阅和许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 9f8576b00b942c4b38d6192770bd2128afb4b104
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015955"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>了解 Microsoft 365 for business 中的订阅和许可证

当你购买 Microsoft 365 for business 订阅时，你需要注册一组通过每月或每年的费用支付的应用和服务。 作为订阅的一部分收到的应用程序和服务取决于所购买的产品，如 Microsoft 365 应用程序或 Microsoft 365 商业标准。 您可以在 "中小型企业" 页面上看到 " [Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)中的每个产品" 所附带的内容。

购买订阅时，根据组织中的人数指定所需的许可证数。 购买订阅后，请为组织中的人员创建帐户，然后将许可证分配给每个人。 当您的组织需求发生变化时，您可以购买更多许可证以适应新人员，或在某人离开你的组织时将许可证重新分配给其他用户。

如果有一个以上的订阅，则可以针对每个订阅将许可证分配给不同人员。 例如，您可以将所有用户作为 Microsoft 365 商业标准订阅的一部分分配给所有 Microsoft 365 应用程序和服务。 您还可以通过单独的 Visio 订阅将一小部分用户分配到 Visio Online。

## <a name="how-many-devices-can-people-install-office-on"></a>可以在多少台设备上安装 Office？

如果你的订阅包括以下任何产品，每个人都可以在最大5台电脑或 Mac、五个平板电脑和五个手机上安装 Office。

:::row:::
   :::column span="":::
        -Microsoft 365 应用程序-适用于企业的 Microsoft 365 应用-Microsoft 365 商业标准-Microsoft 365 商业高级版-Microsoft 365 A3-Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        -Microsoft 365 E3-Microsoft 365 E5-Office 365 A1 Plus-office 365 A3-office 365 A5-Office 365 E3-Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>向某人分配许可证时会发生什么情况？

下表列出了在为某人分配许可证时会自动发生的情况：
  
|**如果订阅中有此服务**|**将会自动发生该情况**|
|:-----|:-----|
|Exchange Online  <br/> |将为该人员创建一个邮箱。 <br/> 若要了解此任务的完成 SLA，请参阅["设置 ..."Microsoft 365 管理中心中的邮件](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。 |
|SharePoint Online  <br/> |将为该人员分配默认 SharePoint Online 团队网站的编辑权限。  <br/> |
|Skype for Business Online  <br/> |此人有权访问与许可证关联的功能。  <br/> |
|Microsoft 365 企业应用版  <br/> |此人最高可下载5台 Mac 或电脑、五个平板电脑和五台智能手机上的 Office 应用。  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>了解非用户邮箱的许可证

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [创建共享邮箱](../../admin/email/create-a-shared-mailbox.md)
- [从共享邮箱删除许可证](../../admin/email/remove-license-from-shared-mailbox.md)
- [Exchange Online 中的共享邮箱](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)，用于所有其他 Microsoft 365 计划。
- [创建和管理会议室邮箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [管理设备邮箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>谁可以分配许可证？

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**管理员角色**|**分配许可证**|**取消分配许可证**|**购买更多许可证**|**删除帐户**|
|:-----|:-----|:-----|:-----|:-----|
|帐务管理员  <br/> |否  <br/> |否  <br/> |必需  <br/> |否  <br/> |
|全局管理员  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|许可证管理员 <br/> |是 <br/>|是 <br/> |否 <br/> |否 <br/> |
|服务支持管理员  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|用户管理员  <br/> |是  <br/> |是  <br/> |否  <br/> |可访问  <br/> |

## <a name="related-content"></a>相关内容

[为你的业务订阅购买或删除许可证](buy-licenses.md)（文章） \
[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)（文章） \
[取消分配给用户的许可证](../../admin/manage/remove-licenses-from-users.md)（文章） \
[从共享邮箱中删除许可证](../../admin/email/remove-license-from-shared-mailbox.md)（文章）