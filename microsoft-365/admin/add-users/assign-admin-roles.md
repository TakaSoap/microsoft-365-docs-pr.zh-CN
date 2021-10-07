---
title: 分配管理员角色Microsoft 365 管理中心
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
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 了解如何将管理员角色分配给企业中的一个或多个用户，以便他们可以在管理中心执行特定任务。
ms.openlocfilehash: e06533b70ddd7101f2ba160aa6796ee77e250c17
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161902"
---
# <a name="assign-admin-roles"></a>分配管理员角色

如果你是购买 Microsoft 商业版订阅的人，你是全局管理员。这意味着你可以无限制地控制订阅中的产品，并且可以访问大部分数据。

有关详细信息，请参阅 [关于管理员角色](about-admin-roles.md)。

添加新用户时，如果你没有为其分配管理员角色，则他们担任用户角色，并且没有任何 Microsoft管理中心的管理员权限。 但是，如果你需要有关完成工作的帮助，你可以将管理员角色分配给用户。 例如，如果需要某人来帮助重置密码，则不应为其分配全局管理员角色，而应为其分配密码管理员角色。 全局管理员太多，且可无限访问数据和在线业务，因此存在安全风险。

## <a name="watch-add-an-adminbrbr"></a>观看：添加管理员<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../../business-video/index.yml)。

## <a name="assign-admin-roles"></a>分配管理员角色 

可以通过两种不同的方式将用户分配给角色：

- 可以转到用户的详细信息和管理 **角色以** 向用户分配角色。
- 或者，你可以转到 **角色** 并选择角色，然后向该角色添加多个用户。

### <a name="assign-admin-roles-to-users-using-roles"></a>使用角色向用户分配管理员角色

1. 在管理中心中，转到"<a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**角色分配"。**</a> 选择 **Azure AD 或** **Intune** 选项卡以查看适用于你的组织的管理员角色。
2. 选择要为其分配用户的管理员角色。
3. 选择 **分配管理员添加**  >  。
4. 键入 **用户的显示名称****或用户名**，然后从建议列表中选择用户。
5. 添加多个用户，直到完成。
6. 选择 **"** 保存"，然后将用户添加到分配的管理员列表中。

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>从活动用户向管理员角色分配用户

::: moniker range="o365-worldwide"

1. 在管理中心，转到"用户 > [""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=834822)页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

2. 在 **"活动用户"** 页上，选择要更改其管理员角色的用户。 在飞出窗格中的"角色 **"下**，选择"**管理角色"。**

3. 选择要分配给这些用户的管理员角色。 如果看不到要查找的角色，请选择列表底部的"全部显示"。 

## <a name="assign-admin-roles-to-multiple-users"></a>向多个用户分配管理员角色

如果您知道 PowerShell，请参阅使用 [PowerShell 向用户帐户分配角色](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)。 它非常适合为数百个用户分配角色。
  
请按照以下说明向数十个用户分配角色。

## <a name="check-admin-roles-in-your-organization"></a>检查贵组织的管理员角色

您可能没有将管理员角色分配给其他用户的正确权限。 检查以确保你拥有正确的权限，或要求其他管理员为你分配角色。

可以通过两种不同的方式检查管理员角色权限：

- 你可以转到用户的详细信息，然后查看 **"帐户"** 页面上 **的角色下。**
- 或者，你可以转到 **角色** 并选择管理员角色，然后选择分配的管理员以查看分配了哪些用户。

## <a name="related-content"></a>相关内容

[关于 Microsoft 365 管理员角色](about-admin-roles.md)（文章）\
[Azure AD 内置角色 (](/azure/active-directory/roles/permissions-reference) 文章) \
[使用 PowerShell 向用户帐户分配](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) 角色 (文章) \
[授权或删除 (](../misc/add-partner.md) 文章) 