---
title: 查看合作伙伴管理权限
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
search.appverid: MET150
description: 了解如何查看你的 Microsoft 认证解决方案提供商列表 (合作伙伴) 确定他们拥有哪些管理员权限以及如何删除这些权限。
ms.date: 12/03/2021
ms.openlocfilehash: 7dc0a52526da1f0da9cd85b438b6f30b798c2dfa
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302483"
---
# <a name="review-partner-administrative-privileges"></a>查看合作伙伴管理权限

如果你有一个 Microsoft 认证的云解决方案提供商 (经销商合作伙伴) ，我们建议你每季度审查分配给他们的 (DAP) 委派管理权限。 确保你的组织希望此合作伙伴能够访问组织的数据并代表你进行购买。

> [!IMPORTANT]
> 向任何合作伙伴授予 DAP（包括全局管理员权限）可能会带来安全风险。 拥有过多全局管理员也是一种安全风险。 [详细了解最近面向委派权限的活动](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/)。

接受经销商合作伙伴的 DAP 协议后，他们可以将组织的全局管理员角色分配给其员工。 全局管理员角色使合作伙伴的员工可以访问员工的个人数据和其他敏感信息。 它还授予他们执行租户范围操作的权限，例如以下操作：

- 更改用户密码
- 使用电子邮件帐户添加用户
- 添加和管理与组织关联的 Web 域

启用 DAP 后，你无法控制合作伙伴可以添加的全局管理员的数量。 你只能授予或拒绝合作伙伴 DAP (全局) 访问你的帐户。

## <a name="review-and-remove-roles-from-partners"></a>查看角色并从合作伙伴中删除角色

1. 在Microsoft 365 管理中心中，转到 **"设置**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">关系"</a>页面。 具有 DAP 的合作伙伴的 **"角色"****列中列出了全局** 管理员。
2. 若要从合作伙伴中删除全局管理员角色，请查找要删除的合作伙伴的名称。
3. 选择将 Reseller **作为关系****类型的行**。
4. 在合作伙伴详细信息页面上，选择 **删除角色**，**然后选择是。**

> [!NOTE]
>
> - 如果从合作伙伴 (DAP) 全局管理员角色，我们建议您联系他们，讨论未来的服务交付。 例如，可以创建具有较低特权的用户帐户，并与你的合作伙伴共享该帐户信息。 详细了解如何[添加用户](../admin/add-users/add-users.md)[和分配管理员角色](../admin/add-users/assign-admin-roles.md)。
> - 即使删除了全局管理员角色，合作伙伴仍然可以代表你进行购买。 我们建议你联系合作伙伴，要求他们在合作伙伴中心中删除该能力。

## <a name="related-content"></a>相关内容

[管理合作伙伴关系](manage-partners.md) (文章) \
[关于管理员角色](../admin/add-users/about-admin-roles.md) (文章) \
[本文中的委派](/partner-center/customers-revoke-admin-privileges#delegated-admin-privileges-in-azure-ad)管理员Azure AD (权限) 
