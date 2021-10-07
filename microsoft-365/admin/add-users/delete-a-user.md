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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 了解如何删除用户帐户以及如何处理用户的电子邮件和内容OneDrive以及是否保留产品许可证。
ms.openlocfilehash: 852ebe9a99718be9bf025fbc8347bc2ca7854cc2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161818"
---
# <a name="delete-a-user-from-your-organization"></a>从组织删除用户
  
**正在查找 *如何删除Microsoft 365* 或学校使用的用户帐户？请与工作或大学中的技术支持人员联系，以执行这些步骤。**

## <a name="before-you-begin"></a>准备工作

- 只有具有全局[Microsoft 365](about-admin-roles.md)或企业或学校的用户管理权限的用户才能删除用户帐户。
- 永久删除用户数据前 30 天内可[还原](restore-user.md)帐户。
- 若要保留用户的 OneDrive 数据，请将其移动到其他位置。 您甚至可以在删除帐户后最多 30 天移动数据。 请参阅[访问并备份以往用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。 无需移动其 SharePoint 文件；仍将有权访问它们。
- 若要保留用户的电子邮件，请在删除帐户 **之前** ，将电子邮件移动到其他位置。如果已删除该帐户：如果删除时间未超过 30 天，可恢复该帐户，然后移动电子邮件数据，最后删除该帐户。请参阅 [访问并备份以往用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。
- 如果您具有 Enterprise E3 Office 365 企业版订阅，则可以通过将已删除用户帐户的邮箱数据转换为非活动邮箱来 *保留该帐户的邮箱数据*。 若要了解详细信息，请参阅 [管理 Exchange Online 中的非活动邮箱](../../compliance/inactive-mailboxes-in-office-365.md)。

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>全局管理员：删除用户、停止支付其许可证费用，然后选择使用电子邮件和内容OneDrive操作

如果您是全局管理员，当您删除某个用户时，您还可以向另一个用户授予访问其电子邮件的访问权限，并选择使用其电子邮件OneDrive操作。

### <a name="things-to-consider"></a>注意事项

在开始之前，考虑想要使用用户的电子邮件和内容OneDrive，以及是想要保留许可证还是停止支付许可证费用。
  
|项目 | 说明 |
|:-----|:-----|
|产品许可证  <br/> |你可以从用户中删除许可证，并从订阅中删除该许可证，以停止支付该许可证费用。 如果选择此选项，许可证将自动从订阅中删除。  <br/><br/> **如果通过合作伙伴或** 批量许可购买了许可证，则不能删除该许可证。 如果你为年度计划付费或正在计费周期中，那么在承诺完成之前，你将无法从订阅中删除许可证。  <br/> |
|OneDrive内容  <br/> |如果用户将文件保存到OneDrive，您可以授予其他用户对这些文件的访问权限。  <br/><br/> 你需要在为文件设置的保留期内移动OneDrive文件。 **默认情况下，保留期为 30 天。** 如果在删除用户后没有在保留期内移动文件，则已删除用户的 OneDrive 将移动到网站集回收站，其中文件将保留 93 天。 在此期间，用户将无法再访问 OneDrive 中的任何共享内容。 若要还原 OneDrive，需要使用 PowerShell。 有关信息，请参阅[还原已删除的 OneDrive](/onedrive/restore-deleted-onedrive)。<br/><br/> 若要增加保留已删除帐户OneDrive保留的天数，请参阅为已删除OneDrive[设置保留时间](/onedrive/set-retention)。  <br/><br/> **重要说明！** 如果已删除的用户使用个人计算机从 SharePoint 和 OneDrive 下载文件，则你无法擦除存储在其计算机中的文件。 他们将继续有权访问从 OneDrive 同步的任何文件。           |
|电子邮件  <br/> | 向其他用户提供对已删除用户的电子邮件的访问权限会将已删除用户的邮箱转换为共享邮箱。 然后，新邮箱所有者可以访问邮箱并监视新电子邮件。 还可以选择以下选项：  <br/>  <br/>更改显示名称 - 建议更改显示名称，以便轻松识别"活动用户"列表中的 **共享** 邮箱。  <br/>  启用自动答复 - 我们已经为用户撰写了一份很乐于回复的自动答复。 您可以向组织内部人员以及组织外部人员发送不同的自动答复。  <br/> <br/> 清理别名 - 别名是用户的其他电子邮件地址。 某些组织不使用它们，因此如果没有，则无需在这里执行任何其他工作。 如果用户具有别名，我们建议删除这些别名，以便可以重复使用这些电子邮件地址。 否则，在已删除邮箱的保留期过去之前，无法重复使用这些电子邮件地址。 默认情况下，已删除的邮箱可恢复 30 天。 有关详细信息，请参阅删除[或还原用户邮箱Exchange Online。](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) <br/> |
|Active Directory  <br/> |如果你的公司使用与 Azure AD 同步的 **Active Directory** ，则需要从 Active Directory 中删除用户帐户。 无法通过 Office 365 删除帐户。 有关说明，请参阅 [删除用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。  <br/> |

### <a name="get-started"></a>入门

由于指导体验将完成删除用户的步骤，下面介绍如何开始操作。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

 1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

2. 选择要删除的用户，然后选择"删除 **用户"。**

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>用户管理管理员：从用户中删除一个或多个Office 365

> [!IMPORTANT]
> 如果你已将其转换为共享邮箱，或者如果你已设置该帐户的电子邮件[](../email/convert-user-mailbox-to-shared-mailbox.md)转发，请不要删除该用户帐户。 这些函数仍然需要帐户。 共享邮箱不需要许可证。 如果已将帐户转换为共享邮箱，可以 [停止支付许可证费用](#stop-paying-for-the-license)。 如果已设置帐户的电子邮件转发，则不能删除许可证。 这样做将停止电子邮件转发并停用邮箱。
  
::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

2. 选择要删除的用户的名称，选择三个点 (执行更多) ，然后选择"删除 **用户"。**

   虽然删除了用户帐户， **但仍需要支付许可证费用**。 请参阅下一过程以停止支付许可证费用。  或者，你可以将许可证分配给其他用户。 它不会自动分配给某人。

### <a name="stop-paying-for-the-license"></a>停止支付许可证费用

减少许可证数量是一个单独的步骤，只有全局管理员或帐单管理员才能执行。
  
::: moniker range="o365-worldwide"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">你的产品</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">你的产品</a>”页面。
::: moniker-end

2. 在 **"产品** "选项卡上，选择要删除其许可证的订阅。

3. 在订阅详细信息页面上，选择”**删除许可证**”。

4. 在"**删除许可证"** 窗格中的"新数量"**下的**"许可证总数"框中，输入要用于此订阅的许可证总数。  例如，如果你有 100 个许可证，并且想要删除其中五个许可证，请输入 95。

5. 选择“**保存**”。

稍后，当你完成将其他人添加到你的企业的步骤时，系统将提示你同时购买许可证，只需一个步骤！

## <a name="delete-many-users-at-the-same-time"></a>同时删除多个用户

请参阅 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet。

## <a name="fix-issues-with-deleting-a-user"></a>解决删除用户时遇到的问题

以下是用户在删除用户时遇到的最常见问题：
  
- **You get an error message along the lines of "User cannot be deleted.请稍后重试。"** 仔细检查帐户是否设置了电子邮件转发，或者是否将其转换为共享邮箱。 这两者都将导致该错误。 如果帐户具有电子邮件转发或已转换为共享邮箱，请不要删除该帐户。

- **你没有删除用户的相应权限** 。 只有全局Microsoft 365管理员或[用户管理管理员才能](about-admin-roles.md)删除用户。 该管理员通常是学校或企业中的技术支持人员。

- **删除用户后，用户姓名继续显示在全局通讯录中** 。 企业使用 Active Directory 时会出现这种情况。 您必须从 Active Directory 中删除用户帐户。 有关说明，请参阅 [删除用户帐户。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**是否要从计算机Microsoft 365文件？转到 [取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)。**

## <a name="related-content"></a>相关内容

[Restore a user (](restore-user.md) article) \
[永久删除邮箱 (](/exchange/permanently-delete-a-mailbox-exchange-2013-help) 文章) \
[从新文章中Office 365 (](remove-former-employee.md)前) \
[向新员工添加Office 365 (](add-new-employee.md)文章) \
[删除用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))：如果你的企业使用与 Azure AD 同步的 **Active Directory，** 请使用以下说明。 无法通过 Office 365 删除帐户。  (文章) 
