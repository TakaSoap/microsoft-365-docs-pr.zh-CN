---
title: 了解企业Microsoft 365中的订阅和许可证
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: 你收到的应用程序和服务取决于购买的Microsoft 365产品，如Microsoft 365 商业应用版。
ms.date: 07/01/2020
ms.openlocfilehash: 984b46954ab57391d5f7c1e48e42527e5c95b412
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824435"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>了解企业Microsoft 365中的订阅和许可证

购买企业Microsoft 365订阅时，可注册一组按月或按年付费的应用和服务。 作为订阅的一部分收到的应用程序和服务取决于购买的产品，例如Microsoft 365 商业应用版或Microsoft 365 商业标准版。 可以在“中[小型企业Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)页上查看每个产品的内容。

购买订阅时，根据组织中的人数指定所需的许可证数。 购买订阅后，为组织中的人员创建帐户，然后为每个人分配许可证。 随着组织需求的变化，你可以购买更多许可证来容纳新用户，或在某人离开组织时将许可证重新分配给其他用户。

如果有一个以上的订阅，则可以针对每个订阅将许可证分配给不同人员。 例如，可以将所有用户分配给所有Microsoft 365应用程序和服务，作为Microsoft 365 商业标准版订阅的一部分。 还可以通过单独的Visio订阅将一部分用户分配到 Visio Online。

## <a name="how-many-devices-can-people-install-office-on"></a>可以在多少台设备上安装 Office？

如果你的订阅包含以下任何产品，则每个人都可以在最多五台电脑或 Mac、五台平板电脑和五部手机上安装Office。

:::row:::
   :::column span="":::
        - Microsoft 365 商业应用版 - Microsoft 365 企业应用版 - Microsoft 365 商业标准版 - Microsoft 365 商业高级版 - Microsoft 365 A3 -Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1加 - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>将许可证分配给某人时会发生什么情况？

下表列出了在为某人分配许可证时会自动发生的情况：
  
|如果订阅中有此服务|将会自动发生该情况|
|:-----|:-----|
|Exchange Online|将为该人员创建一个邮箱。 <br/> 若要了解要完成此任务的 SLA，请参阅[“设置...”Microsoft 365 管理中心中的消息](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。 |
|SharePoint Online|将为该人员分配默认 SharePoint Online 团队网站的编辑权限。|
|Skype for Business Online|该人员有权访问与许可证关联的功能。|
|Microsoft 365 企业应用版和Microsoft 365 商业应用版|此人最多可以在五台 Mac 或电脑、五台平板电脑和五台智能手机上下载Office应用。|

## <a name="understand-licenses-for-non-user-mailboxes"></a>了解非用户邮箱的许可证

不需要为资源邮箱、会议室邮箱和共享邮箱分配许可证，除非这些邮箱超过了其 50 千兆字节 (GB) 的存储配额。有关非用户邮箱的详细信息，请参阅以下文章：
  
- [创建共享邮箱](../../admin/email/create-a-shared-mailbox.md)
- [从共享邮箱删除许可证](../../admin/email/remove-license-from-shared-mailbox.md)
- [所有其他Microsoft 365计划的Exchange Online共享邮箱](/exchange/collaboration-exo/shared-mailboxes)。

## <a name="who-can-assign-licenses"></a>Who可以分配许可证？

不同类型的管理员可以根据其角色以不同方式处理许可证。下表列出了最常见的选项。有关管理员角色和特权的完整列表，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  
|管理员角色|分配许可证|取消分配许可证|购买更多许可证|删除帐户|
|:-----|:-----|:-----|:-----|:-----|
|帐务管理员|否|否|是|否|
|全局管理员|是|是|是|是|
|许可证管理员|是|是|否|否|
|服务支持管理员|否|否|否|否|
|用户管理员|是|是|否|是|

## <a name="related-content"></a>相关内容

[购买或删除业务订阅的许可证](buy-licenses.md) (文章) \
[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)
[取消向用户分配许可证](../../admin/manage/remove-licenses-from-users.md)（文章）\
[从共享邮箱删除许可证](../../admin/email/remove-license-from-shared-mailbox.md)（文章）
