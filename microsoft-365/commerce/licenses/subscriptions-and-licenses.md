---
title: 了解企业版Microsoft 365订阅和许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: 您收到的应用程序和服务取决于您Microsoft 365购买的产品，例如Microsoft 365 商业应用版。
ms.date: 07/01/2020
ms.openlocfilehash: e380ac61033435a86118f7178da9e014d13ad436
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524041"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>了解企业版Microsoft 365订阅和许可证

购买适用于Microsoft 365订阅时，需要注册一组按月或按年付费的应用和服务。 作为订阅的一部分收到的应用程序和服务取决于您购买的产品，例如Microsoft 365 商业应用版或Microsoft 365 商业标准版。 您可以在适用于中小型企业的 Microsoft 365 页面上查看每个产品[随附的内容](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)。

购买订阅时，根据组织中的人数指定所需的许可证数。 购买订阅后，为组织成员创建帐户，然后为每个人分配许可证。 随着组织需求的变化，你可以购买更多许可证来容纳新人，或在某人离开组织时将许可证重新分配给其他用户。

如果有一个以上的订阅，则可以针对每个订阅将许可证分配给不同人员。 例如，您可以将所有用户分配给作为 Microsoft 365 订阅的一部分的所有 Microsoft 365 商业标准版应用程序和服务。 您还可以通过单独的订阅将一部分Visio分配给 Visio Online。

## <a name="how-many-devices-can-people-install-office-on"></a>可以在多少台设备上安装 Office？

如果你的订阅包括以下任一产品，则每个人Office安装在五台电脑或 Mac、五台平板电脑和五部手机上。

:::row:::
   :::column span="":::
        - Microsoft 365 商业应用版 - Microsoft 365 企业应用版 - Microsoft 365 商业标准版 - Microsoft 365 商业高级版 - Microsoft 365 A3 -Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>将许可证分配给某人时会发生什么情况？

下表列出了在为某人分配许可证时会自动发生的情况：
  
|**如果订阅中有此服务**|**将会自动发生该情况**|
|:-----|:-----|
|Exchange Online  <br/> |将为该人员创建一个邮箱。 <br/> 若要了解要完成此任务的 SLA，请参阅["设置..."。邮件Microsoft 365 管理中心](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。 |
|SharePoint Online  <br/> |将为该人员分配默认 SharePoint Online 团队网站的编辑权限。  <br/> |
|Skype for Business Online  <br/> |用户有权访问与许可证关联的功能。  <br/> |
|Microsoft 365 企业应用版 和 Microsoft 365 商业应用版  <br/> |用户可以在最多Office台 Mac 或 PC、五台平板电脑和五台智能手机上下载这些应用。  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>了解非用户邮箱的许可证

不需要为资源邮箱、会议室邮箱和共享邮箱分配许可证，除非这些邮箱超过了其 50 千兆字节 (GB) 的存储配额。有关非用户邮箱的详细信息，请参阅以下文章：
  
- [创建共享邮箱](../../admin/email/create-a-shared-mailbox.md)
- [从共享邮箱删除许可证](../../admin/email/remove-license-from-shared-mailbox.md)
- [其他所有Exchange Online](/exchange/collaboration-exo/shared-mailboxes)计划的共享Microsoft 365邮箱。

## <a name="who-can-assign-licenses"></a>Who分配许可证？

不同类型的管理员可以根据其角色以不同方式处理许可证。下表列出了最常见的选项。有关管理员角色和特权的完整列表，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  
|**管理员角色**|**分配许可证**|**取消分配许可证**|**购买更多许可证**|**删除帐户**|
|:-----|:-----|:-----|:-----|:-----|
|帐务管理员  <br/> |否  <br/> |否  <br/> |是  <br/> |否  <br/> |
|全局管理员  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|许可证管理员 <br/> |是 <br/>|是 <br/> |否 <br/> |否 <br/> |
|服务支持管理员  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|用户管理员  <br/> |是  <br/> |是  <br/> |否  <br/> |是  <br/> |

## <a name="related-content"></a>相关内容

[购买或删除商业版订阅的许可证 (](buy-licenses.md) 文章) \
[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)
[取消向用户分配许可证](../../admin/manage/remove-licenses-from-users.md)（文章）\
[从共享邮箱删除许可证](../../admin/email/remove-license-from-shared-mailbox.md)（文章）
