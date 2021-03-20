---
title: 取消分配用户许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: 了解如何从用户帐户取消分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915190"
---
# <a name="unassign-licenses-from-users"></a>取消分配用户许可证

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。

::: moniker-end

::: moniker range="o365-worldwide"

您可以在"活动用户"页面或"许可证"页面上取消分配用户 **许可证**。 使用的方法取决于是希望取消分配特定用户的产品许可证，还是从特定产品取消分配用户许可证。

::: moniker-end

## <a name="before-you-begin"></a>开始之前

- 你必须是全局、许可证、用户管理员才能取消分配许可证。 有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。
- 可[使用 Office 365 PowerShell 删除用户帐户的许可证](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)。
- 还可以 [删除分配有](../add-users/delete-a-user.md) 许可证的用户帐户，使其许可证可供其他用户使用。 删除用户帐户时，将立即将其许可证分配给其他人。

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>使用"许可证"页取消分配许可证

使用"许可证 **"** 页取消分配许可证时，最多为 20 个用户取消分配特定产品的许可证。

1. 在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。
2. 选择要取消分配许可证的产品。
3. 选择要取消分配许可证的用户。
4. 选择 **"取消分配许可证"。**
5. 在"**取消分配许可证"** 框中，选择"**取消分配"。**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>使用"活动用户"页取消分配许可证

使用"活动 **用户"** 页取消分配许可证时，将取消为用户分配产品许可证。

### <a name="unassign-licenses-from-one-user"></a>取消分配来自一个用户的许可证
  
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要取消分配许可证的用户的行。
3. 在右侧窗格，选择“**许可证和应用**”。
4. 展开"**许可证**"部分，清除要取消分配的许可证的框，然后选择"保存 **更改"。**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>取消分配来自一个用户的许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。
2. 选取要取消分配许可证的用户。
3. 在右侧"产品许可证 **"行中**，选择"编辑 **"。**
4. 在 **"产品许可证**"窗格中，将要取消为用户分配的许可证的开关切换到"关"位置。 例如，如果关闭 Office 365 企业版 E3 许可证，它会为该用户取消分配该许可证及其下的所有服务。
5. 在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>取消分配来自一个用户的许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。
2. 选取要取消分配许可证的用户。
3. 在右侧"产品许可证 **"行中**，选择"编辑 **"。**
4. 在 **"产品许可证**"窗格中，将要取消为用户分配的许可证的开关切换到"关"位置。 例如，如果关闭 Office 365 企业版 E3 许可证，它会为该用户取消分配该许可证及其下的所有服务。
5. 在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>取消分配多个用户的许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要取消分配许可证的用户姓名旁边的圆圈。
3. 在顶部选择“**更多选项(...)**”，然后选择“**管理产品许可证**”。
4. 在“**管理产品许可证**”窗格中，选择“**替换现有产品许可证分配**”\>“**下一步**”。
5. 在"替换现有产品"窗格的底部，选中"从所选用户删除所有产品许可证"复选框，然后选择"替换"" \> **关闭"。**

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>取消分配多个用户的许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。
2. 选中要取消分配其所有许可证的用户姓名旁边的框。
3. 在“**批量操作**”窗格中，选择“**编辑产品许可证**”。
4. 在" **替换现有产品**"窗格中，选择" **替换现有产品许可证分配**"\>" **下一步**"。
5. 在"替换现有产品"窗格底部，选中"从所选用户删除所有产品许可证"复选框，然后选择"替换"" \> **关闭** \> **""关闭"。**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>取消分配多个用户的许可证
  
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。
2. 选中要取消分配其所有许可证的用户姓名旁边的框。
3. 在“**批量操作**”窗格中，选择“**编辑产品许可证**”。
4. 在" **替换现有产品**"窗格中，选择" **替换现有产品许可证分配**"\>" **下一步**"。
5. 在"替换现有产品"窗格底部，选中"从所选用户删除所有产品许可证"复选框，然后选择"替换"" \> **关闭** \> **""关闭"。**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>删除用户许可证时，用户数据会发生什么情况？

- 从用户删除许可证后，与该帐户关联的数据将存储 30 天。 30 天宽限期后，数据将被删除且无法恢复。
- 除非从 Microsoft 365 管理中心删除用户，或者通过 Active Directory 同步删除用户，否则不会删除保存在 OneDrive for Business 中的文件。 有关详细信息，请参阅 [OneDrive 保留和删除](/onedrive/retention-and-deletion)。
- 删除许可证后，用户邮箱将不再可用电子数据展示工具（如内容搜索或高级电子数据展示）进行搜索。 有关详细信息，请参阅 [Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes)中的内容搜索中的"搜索断开连接或已取消许可的邮箱"。
- 如果您有企业版订阅（如 Office 365 企业版 E3），Exchange Online 允许您使用非活动邮箱保留已删除用户帐户的 [邮箱数据](../../compliance/inactive-mailboxes-in-office-365.md)。 有关详细信息，请参阅在 [Exchange Online 创建和管理非活动邮箱](../../compliance/create-and-manage-inactive-mailboxes.md)。
- 若要了解如何在删除用户的许可证后阻止用户访问 Microsoft 365 数据，以及如何在以后获取对数据的访问权限，请参阅删除 [以前的员工](../add-users/remove-former-employee.md)。
- 如果删除用户的许可证，但他们仍安装了 Office 应用，则当他们使用 Office 应用时，会看到 [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 中出现未授权产品和激活错误。

## <a name="next-steps"></a>后续步骤

如果你不打算将未使用的许可证重新分配给[](../../managed-desktop/get-started/assign-licenses.md)其他用户，请考虑从订阅中删除许可证，这样你[](../../commerce/licenses/buy-licenses.md)无需支付超过你需要的许可证。

## <a name="related-content"></a>相关内容

[从订阅中删除许可证 (](../../commerce/licenses/buy-licenses.md) 文章) \
[向用户分配许可证](assign-licenses-to-users.md)
[了解 Microsoft 365 商业版](../../commerce/licenses/subscriptions-and-licenses.md) 订阅和许可证 (文章) 