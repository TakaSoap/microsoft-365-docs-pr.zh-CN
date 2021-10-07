---
title: 取消分配用户许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: 用于取消分配产品许可证的方法取决于是取消分配特定用户许可证还是从特定产品分配许可证。
ms.date: 09/16/2021
ms.openlocfilehash: ecbf39fc0daa4696581dc1665cfacb8c96c6c85f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171803"
---
# <a name="unassign-licenses-from-users"></a>取消分配用户许可证

您可以在"活动用户"页面或"许可证"页面上取消分配 **用户许可证。** 使用的方法取决于是希望取消分配特定用户的产品许可证，还是从特定产品取消分配用户许可证。

> [!NOTE]
> 
> - 作为管理员，你不能为组织中用户购买的自助购买订阅分配或取消分配许可证。 你可以 [接管自助购买订阅](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)，然后分配或取消分配许可证。
> 
> - 对于某些订阅，只能在购买或续订订阅后的有限时间段内取消。 如果取消时段已过，请在订阅期限结束时关闭定期计费以取消订阅。

## <a name="before-you-begin"></a>开始之前

- 你必须是全局、许可证、用户管理员才能取消分配许可证。 有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。
- 可[使用 Office 365 PowerShell 删除用户帐户的许可证](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)。
- 还可以 [删除分配有](../add-users/delete-a-user.md) 许可证的用户帐户，使其许可证可供其他用户使用。 删除用户帐户时，将立即将其许可证分配给其他人。

## <a name="use-the-licenses-page-to-unassign-licenses"></a>使用"许可证"页取消分配许可证

使用"许可证 **"** 页取消分配许可证时，最多为 20 个用户取消分配特定产品的许可证。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">许可证</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>”页面。

::: moniker-end

2. 选择要取消分配许可证的产品。

3. 选择要取消分配许可证的用户。

4. 选择 **"取消分配许可证"。**

5. 在"**取消分配许可证"** 框中，选择"**取消分配"。**

## <a name="use-the-active-users-page-to-unassign-licenses"></a>使用"活动用户"页取消分配许可证

使用"活动 **用户"** 页取消分配许可证时，将取消为用户分配产品许可证。

### <a name="unassign-licenses-from-one-user"></a>取消分配来自一个用户的许可证

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

2. 选择要取消分配许可证的用户的行。

3. 在右侧窗格，选择“**许可证和应用**”。

4. 展开"**许可证**"部分，清除要取消分配的许可证的框，然后选择"保存 **更改"。**

### <a name="unassign-licenses-from-multiple-users"></a>取消分配多个用户的许可证

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

2. 选择要取消分配许可证的用户姓名旁边的圆圈。

3. 在顶部，选择“**管理产品许可证**”。

4. 在"**管理产品许可证"** 窗格中，选择"**取消分配所有**  >  **保存更改"。**

5. 在窗格底部，选择"完成 **"。**  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>删除用户许可证时，用户数据会发生什么情况？

- 从用户删除许可证后，Exchange与该帐户关联的联机数据将进行 30 天。 30 天宽限期后，数据将被删除且无法恢复。
- 保存OneDrive for Business的文件不会删除，除非用户已从 active Directory Microsoft 365 管理中心或 Active Directory 同步删除。 有关详细信息，请参阅OneDrive[和删除](/onedrive/retention-and-deletion)。
- 删除许可证后，用户邮箱将不再可用电子数据展示工具（如内容搜索或Advanced eDiscovery。 有关详细信息，请参阅 Content Search in Microsoft 365 中的"搜索断开连接或已取消许可[的Microsoft 365。](../../compliance/content-search.md)
- 如果你有一个Enterprise订阅，Office 365 企业版 E3，Exchange Online使用非活动邮箱保留已删除用户帐户的[邮箱数据](../../compliance/inactive-mailboxes-in-office-365.md)。 有关详细信息，请参阅 Create [and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md)。
- 若要了解如何在删除用户的许可证后阻止Microsoft 365访问数据，以及如何在以后获取数据访问权限，请参阅删除[以前的员工](../add-users/remove-former-employee.md)。
- 如果你删除用户的许可证，但他们仍安装了 Office 应用，则当他们使用 Office 应用[](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)时，他们会看到"未授权的产品"和Office错误。

## <a name="next-steps"></a>后续步骤

如果你不打算将未使用的许可证重新分配给[](../../managed-desktop/get-started/assign-licenses.md)其他用户，请考虑从订阅中删除许可证，这样你[](../../commerce/licenses/buy-licenses.md)无需支付超过你需要的许可证。

## <a name="related-content"></a>相关内容

[从订阅中删除许可证](../../commerce/licenses/buy-licenses.md) (文章) \
[向用户分配许可证](assign-licenses-to-users.md)
[了解 Microsoft 365 商业版中的订阅和许可证](../../commerce/licenses/subscriptions-and-licenses.md)（文章）
