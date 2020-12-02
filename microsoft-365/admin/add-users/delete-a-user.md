---
title: 从组织删除用户
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 了解如何删除用户帐户。 决定如何处理用户的电子邮件和 OneDrive 内容。 并决定是保留产品许可证还是停止付款。
ms.openlocfilehash: 45cf8b9173a3a4260fe664b809f47ab14b57d9fe
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551372"
---
# <a name="delete-a-user-from-your-organization"></a>从组织删除用户
  
**想要了解如何删除你在工作或学校中使用的 *自己* 的 Microsoft 365 用户帐户？请与你的工作或大学的技术支持部门联系，为你执行这些步骤。**

## <a name="what-you-need-to-know-about-deleting-users"></a>删除用户需知事项

- 只有对企业或学校拥有 [Microsoft 365 全局管理员](about-admin-roles.md) 或用户管理权限的用户才能删除用户帐户。
- 永久删除用户数据前 30 天内可[还原](restore-user.md)帐户。
- 若要保留用户的 OneDrive 数据，请将其移动到其他位置。 您甚至可以在删除帐户后的30天内移动数据。 请参阅[访问并备份以往用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。 无需移动其 SharePoint 文件；仍将有权访问它们。
- 若要保留用户的电子邮件，请在删除帐户 **之前** ，将电子邮件移动到其他位置。如果已删除该帐户：如果删除时间未超过 30 天，可恢复该帐户，然后移动电子邮件数据，最后删除该帐户。请参阅 [访问并备份以往用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。
- 如果你有一个企业订阅（如 Office 365 企业版 E3），则可以通过将已删除的用户帐户转换为 *非活动邮箱* 来保留该帐户的邮箱数据。 若要了解详细信息，请参阅 [管理 Exchange Online 中的非活动邮箱](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)。

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>全局管理员：删除用户，停止为其许可证付款，并选择要对其电子邮件和 OneDrive 内容执行的操作

如果您是全局管理员，则在删除用户时，还可以向其他用户授予对其电子邮件的访问权限，并选择要对其 OneDrive 内容执行的操作。

### <a name="things-to-consider"></a>要考虑的事项...

在开始之前，请考虑要对用户的电子邮件和 OneDrive 内容执行的操作，以及是否要保留许可证或停止付款。
  
|Item | 说明 |
|:-----|:-----|
|产品许可证  <br/> |您可以从用户中删除该许可证并将其从订阅中删除，以停止对该许可证付款。 如果选择此选项，将从你的订阅中自动删除许可证。  <br/><br/> 如果许可证是通过合作伙伴或批量许可购买 **的，则无法删除许可证**。 如果你正在支付年度计划，或者你正在付费周期中间，你将无法从订阅中删除许可证，直到你的承诺完成。  <br/> |
|OneDrive 内容  <br/> |如果用户将文件保存到 OneDrive，则可以向其他用户授予对这些文件的访问权限。  <br/><br/> 您需要将您想要保留的文件移到为 OneDrive 文件设置的保留期内。 **默认情况下，保留期为30天。** 如果您在删除用户后不在保留期内移动文件，则 OneDrive 内容将被永久删除。 若要增加您为已删除帐户保留的 OneDrive 文件的天数，请参阅 [设置已删除用户的 onedrive 保留](https://docs.microsoft.com/onedrive/set-retention)值。  <br/><br/> **重要说明！** 如果已删除的用户使用个人计算机从 SharePoint 和 OneDrive 下载文件，则无法擦除它们存储在计算机上的文件。 他们将继续拥有从 OneDrive 中同步的任何文件的访问权限。           |
|电子邮件  <br/> | 授予另一个用户对已删除用户的电子邮件的访问权限会将已删除用户的邮箱转换为共享邮箱。 然后，新邮箱所有者可以访问邮箱并监视新电子邮件。 此外，还将提供以下选项：  <br/>  <br/>更改显示名称-建议您更改显示名称，以便在 **活动用户** 列表中识别共享邮箱。  <br/>  打开自动答复-我们已经为你编写了礼貌的自动答复。 您可以向组织中的人员和组织外部的人员发送不同的自动答复。  <br/> <br/> 清除别名-别名是用户的其他电子邮件地址。 有些组织不使用它们，因此，如果你没有任何人，则无需在此处执行任何其他操作。 如果用户的确有别名，我们建议将其删除，以便可以重用这些电子邮件地址。 否则，将无法重用这些电子邮件地址，直到已删除邮箱的保留期通过。 默认情况下，已删除的邮箱可恢复30天。 有关详细信息，请参阅  [Delete or restore user 邮箱 In Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)。 <br/> |
|Active Directory  <br/> |如果你的公司使用与 Azure AD 同步的 **Active Directory** ，则需要从 Active Directory 中删除用户帐户。 无法通过 Office 365 删除帐户。 有关说明，请参阅 [删除用户帐户](https://go.microsoft.com/fwlink/p/?linkid=841808)。  <br/> |

### <a name="get-started"></a>入门

由于引导式体验会逐步完成删除用户的步骤，下面介绍了如何入门。

::: moniker range="o365-worldwide"
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
::: moniker-end

::: moniker range="o365-germany"
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。
::: moniker-end

::: moniker range="o365-21vianet"
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。
::: moniker-end

2. 选择要删除的用户，然后选择 " **删除用户**"。

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>用户管理管理员：从 Office 365 中删除一个或多个用户

> [!IMPORTANT]
> 如果已将用户的帐户 [转换为共享邮箱](../email/convert-user-mailbox-to-shared-mailbox.md) ，或者如果已在该帐户上设置了电子邮件转发，则不要删除该帐户。 这些函数仍需要帐户。 共享邮箱不需要许可证。 如果已将帐户转换为共享邮箱，您可以 [停止支付许可证](#stop-paying-for-the-license)。 如果已在帐户上设置了电子邮件转发，则无法删除该许可证。 执行此操作将停止电子邮件转发并停用邮箱。
  
::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  

2. 选择要删除的用户的名称，选择 " **更多选项** **" ("**) "，然后选择 "  **删除用户**"。

   虽然你删除了用户帐户，但你 **仍在支付许可证费用**。 请参阅下一个过程以停止付款许可证。  或者，可以将许可证分配给其他用户。 不会自动将其分配给某人。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要删除的用户的名称，然后在 " **批量操作** " 窗格中选择 " **删除用户**"。

   虽然你删除了用户帐户，但你 **仍在支付许可证费用**。 请参阅下一个过程以停止付款许可证。  或者，可以将许可证分配给其他用户。 不会自动将其分配给某人。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要删除的用户的名称，然后在 " **批量操作** " 窗格中选择 " **删除用户**"。

   虽然你删除了用户帐户，但你 **仍在支付许可证费用**。 请参阅下一个过程以停止付款许可证。  或者，可以将许可证分配给其他用户。 不会自动将其分配给某人。

::: moniker-end

### <a name="stop-paying-for-the-license"></a>停止支付许可证费用

减少许可证的数量是一个单独的步骤，仅可由全局管理员或帐单管理员执行。
  
::: moniker range="o365-worldwide"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。 如果看不到此选项，则不是全局管理员或帐单管理员，无法执行此步骤。

2. 在 " **产品** " 选项卡上，选择要删除其许可证的订阅。

3. 在 "订阅详细信息" 页上，选择 " **删除许可证**"。

4. 在 " **删除许可证** " 窗格中，在 " **新数量**" 下的 " **许可证总数** " 框中，输入此订阅所需的许可证总数。 例如，如果你有100个许可证，并且想要删除其中5个，请输入95。

5. 选择“**保存**”。

稍后当您完成将其他人添加到您的企业的步骤时，系统将提示您同时购买许可证，只需一步即可！

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>”页面。 如果看不到此选项，则不是全局管理员或帐单管理员，无法执行此步骤。

2. 如果您有多个) ，请选择 "订阅 ("，然后选择 " **添加/删除许可证** " 以删除许可证，以便在您雇用其他人之前不支付。  

   稍后当您完成将其他人添加到您的企业的步骤时，系统将提示您同时购买许可证，只需一步即可！

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。 如果看不到此选项，则不是全局管理员或帐单管理员，无法执行此步骤。

2. 如果您有多个) ，请选择 "订阅 ("，然后选择 " **添加/删除许可证** " 以删除许可证，以便在您雇用其他人之前不支付。  

   稍后当您完成将其他人添加到您的企业的步骤时，系统将提示您同时购买许可证，只需一步即可！

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a>同时删除多个用户

请参阅 [Get-msoluser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet。

## <a name="fix-issues-with-deleting-a-user"></a>解决删除用户时遇到的问题

以下是人们删除用户时遇到的最常见的问题：
  
- **将收到一条错误消息，其中 "无法删除用户" 一线。请稍后再试。 "** 仔细检查帐户是否设置了电子邮件转发功能，或者是否已将其转换为共享邮箱。 这两种情况都将导致该错误。 如果帐户有电子邮件转发或已转换为共享邮箱，请不要删除该帐户。

- **你没有删除用户的相应权限** 。 只有属于 [Microsoft 365 全局管理员或用户管理管理员](about-admin-roles.md) 的用户才能删除用户。 该管理员通常是学校或企业中的技术支持人员。

- **删除用户后，用户姓名继续显示在全局通讯录中** 。 企业使用 Active Directory 时会出现这种情况。 您必须从 Active Directory 中删除用户帐户。 有关说明，请参阅 [删除用户帐户。](https://go.microsoft.com/fwlink/p/?linkid=841808)

**是否要从计算机中删除 Microsoft 365？转到 " [取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)"。**

## <a name="related-articles"></a>相关文章

[还原用户](restore-user.md)
  
[永久删除邮箱](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[从 Office 365 中删除以前的员工](remove-former-employee.md)

[向 Office 365 添加新员工](add-new-employee.md)

[删除用户帐户](https://go.microsoft.com/fwlink/p/?linkid=841808)：如果您的公司使用与 Azure AD 同步的 **Active Directory** ，请使用这些说明。 无法通过 Office 365 删除帐户。