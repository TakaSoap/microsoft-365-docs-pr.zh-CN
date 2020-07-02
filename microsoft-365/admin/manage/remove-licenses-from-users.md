---
title: 取消分配用户许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何从用户帐户中取消分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015931"
---
# <a name="unassign-licenses-from-users"></a>取消分配用户许可证

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

::: moniker range="o365-worldwide"

您可以在 "**活动用户**" 页或 "**许可证**" 页上取消分配用户的许可证。 您使用的方法取决于您是要从特定用户分配产品许可证，还是从特定产品中取消分配用户许可证。

::: moniker-end

## <a name="before-you-begin"></a>准备工作

- 您必须是全局许可证，用户管理员才能取消分配许可证。 有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。
- 可[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)。
- 您还可以删除已分配许可证的[用户帐户](../add-users/delete-a-user.md)，以使其许可证对其他用户可用。 当您删除用户帐户时，他们的许可证立即可以分配给其他人。

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>使用 "许可证" 页面取消分配许可证

使用 "**许可证**" 页面取消分配许可证时，将为最高20个用户的特定产品取消分配许可证。

1. 在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。
2. 选择要为其取消分配许可证的产品。
3. 选择要为其取消分配许可证的用户。
4. 选择 "未**分配许可证**"。
5. 在 "未**分配许可证**" 框中，选择 "未**分配**"。

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>使用 "活动用户" 页面取消分配许可证

使用 "**活动用户**" 页面取消分配许可证时，将从用户中取消分配产品许可证。

### <a name="unassign-licenses-from-one-user"></a>从一个用户取消分配许可证
  
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要为其取消分配许可证的用户的行。
3. 在右侧窗格，选择“**许可证和应用**”。
4. 展开 "**许可证**" 部分，清除要取消分配的许可证的复选框，然后选择 "**保存更改**"。

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>从一个用户取消分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。
2. 选择要为其取消分配许可证的用户。
3. 在右侧的 "**产品许可证**" 行中，选择 "**编辑**"。
4. 在 "**产品许可证**" 窗格中，将您要为该用户取消分配的许可证的开关切换到 "**关**" 位置。 例如，如果您关闭了 Office 365 企业版 E3 许可证，它将取消分配该许可证以及该用户的许可证下的所有服务。
5. 在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>从一个用户取消分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。
2. 选择要为其取消分配许可证的用户。
3. 在右侧的 "**产品许可证**" 行中，选择 "**编辑**"。
4. 在 "**产品许可证**" 窗格中，将您要为该用户取消分配的许可证的开关切换到 "**关**" 位置。 例如，如果您关闭了 Office 365 企业版 E3 许可证，它将取消分配该许可证以及该用户的许可证下的所有服务。
5. 在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>取消分配给多个用户的许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要为其取消分配许可证的用户的名称旁边的圆圈。
3. 在顶部选择“**更多选项(...)**”，然后选择“**管理产品许可证**”。
4. 在“**管理产品许可证**”窗格中，选择“**替换现有产品许可证分配**”\>“**下一步**”。
5. 在 "**替换现有产品**" 窗格的底部，选中 "**删除所选用户的所有产品许可证**" 复选框，然后选择 "**替换** \> **关闭**"。

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>取消分配给多个用户的许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。
2. 选择要为其取消分配所有许可证的用户的名称旁边的框。
3. 在“**批量操作**”窗格中，选择“**编辑产品许可证**”。
4. 在" **替换现有产品**"窗格中，选择" **替换现有产品许可证分配**"\>" **下一步**"。
5. 在 "**替换现有产品**" 窗格的底部，选中 "**删除所选用户的所有产品许可证**" 复选框，然后选择 "**替换** \> **关闭**关闭" \> **Close**。

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>取消分配给多个用户的许可证
  
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。
2. 选择要为其取消分配所有许可证的用户的名称旁边的框。
3. 在“**批量操作**”窗格中，选择“**编辑产品许可证**”。
4. 在" **替换现有产品**"窗格中，选择" **替换现有产品许可证分配**"\>" **下一步**"。
5. 在 "**替换现有产品**" 窗格的底部，选中 "**删除所选用户的所有产品许可证**" 复选框，然后选择 "**替换** \> **关闭**关闭" \> **Close**。

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>删除许可证后，用户的数据会发生什么情况？

- 从用户中删除许可证后，与该帐户关联的数据将保留30天。 30天宽限期后，数据将被删除，并且无法恢复。
- 在 OneDrive for Business 中保存的文件不会被删除，除非用户是从 Microsoft 365 管理中心中删除的，或者是通过 Active Directory 同步删除的。 有关详细信息，请参阅[OneDrive 保留和删除](https://docs.microsoft.com/onedrive/retention-and-deletion)。
- 删除许可证后，用户的邮箱将无法再通过使用电子数据展示工具（如内容搜索或高级电子数据展示）进行搜索。 有关详细信息，请参阅[Microsoft 365 中的内容搜索](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)中的 "搜索断开连接或已取消授权的邮箱"。
- 如果您拥有企业订阅（如 Office 365 企业版 E3），Exchange Online 允许您使用[非活动邮箱](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)保留已删除用户帐户的邮箱数据。 有关详细信息，请参阅[在 Exchange Online 中创建和管理非活动邮箱](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)。
- 若要了解如何在删除许可证后阻止用户访问 Microsoft 365 数据，以及如何在以后获取对数据的访问权限，请参阅[删除以前的员工](../add-users/remove-former-employee.md)。
- 如果您删除了用户的许可证，但他们仍安装了 Office 应用程序，他们会在使用 Office 应用程序时看到未获得[授权的产品和激活错误](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)。

## <a name="next-steps"></a>后续步骤

如果您不打算将[未使用的许可证重新分配给其他用户](../../managed-desktop/get-started/assign-licenses.md)，请考虑[从订阅中删除许可证](../../commerce/licenses/buy-licenses.md)，以便不会支付超过所需数量的许可证。

## <a name="related-content"></a>相关内容

[从订阅中删除许可证](../../commerce/licenses/remove-licenses-from-subscription.md)（文章） \
[向用户分配许可证](assign-licenses-to-users.md)（文章） \
[了解 Microsoft 365 for business 中的订阅和许可证](../../commerce/licenses/subscriptions-and-licenses.md)（文章）