---
title: 关于共享邮箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 当多个用户需要访问同一个邮箱时，将使用共享邮箱。 了解在创建共享邮箱之前需要了解的内容。
ms.openlocfilehash: 6d9b7f59840b8eb4ce38822945066e14d9a86a4d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400204"
---
# <a name="about-shared-mailboxes"></a>关于共享邮箱

当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址、接待台或其他可能由多个用户共享的其他功能）时，将使用共享邮箱。

如果管理员已授予用户执行该操作的权限，具有组邮箱权限的用户可以作为或代表邮箱电子邮件地址发送。 这对帮助和支持邮箱尤其有用，因为用户可从 "Contoso 支持" 或 "构建 A 接待台" 发送电子邮件。

[创建共享邮箱](create-a-shared-mailbox.md)之前，应注意以下事项：

- **许可证：** 共享邮箱可以存储最大为50GB 的数据，而无需向其分配许可证。 在此之后，需要向邮箱分配许可证才能存储更多的数据。 有关共享邮箱许可的更多详细信息，请参阅[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。 共享邮箱达到存储空间时，短时间内还可以收到电子邮件，但不能发送新的电子邮件。 然后，它会停止接收电子邮件。 邮箱的发件人将收到未送达回执。

- **用户权限：** 您需要向用户授予权限（成员身份）才能使用共享邮箱。 只有组织内部人员才能使用共享邮箱。

- **外部用户：** 你无法向你的企业外部的人员（如具有 Gmail 帐户的人员）授予对共享邮箱的访问权限。 如果你希望这么做，请考虑改为创建 Outlook 组。 若要了解详细信息，请参阅[admin center 中的创建 Microsoft 365 组](../create-groups/create-groups.md)。

-  **与 Outlook 一起使用：** 除了使用浏览器上的 Outlook 访问共享邮箱之外，您还可以使用 Outlook for iOS 应用或 Outlook for Android 应用。 若要了解详细信息，请参阅<a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">将共享邮箱添加到 Outlook mobile</a>。 另一种方法是为共享邮箱创建组。 若要了解详细信息，请参阅[比较组](../create-groups/compare-groups.md)。  

- **加密：** 无法对从共享邮箱发送的电子邮件进行加密。 这是因为共享邮箱没有自己的安全上下文（用户名/密码），因此无法为其分配密钥。 如果有多个用户是成员，并且他们发送/接收使用自己的密钥加密的电子邮件，则其他成员可能能够读取电子邮件，而其他成员可能无法读取电子邮件，具体取决于电子邮件已加密的公钥。

- **邮箱转换：** 您可以将用户邮箱转换为共享邮箱。 请参阅[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。

- **管理员角色：** 具有全局管理员或 Exchange 管理员角色的用户可以创建共享邮箱。

- **订阅要求：** 若要创建共享邮箱，您需要订阅 Microsoft 365 for business plan，其中包括电子邮件（Exchange Online 服务）。 适用于商业版的 Microsoft 365 应用订阅不包括电子邮件;Microsoft 365 商业标准。

- **登录：** 共享邮箱不用于由其关联的用户帐户进行直接登录。 应始终阻止登录共享邮箱帐户并使其阻止。

- **用户太多：** 当同时访问共享邮箱的指定用户过多时，他们可能会间歇无法连接到此邮箱。 在这种情况下，您可以考虑减少用户数或使用不同的工作负荷，如 Microsoft 365 组或公用文件夹。

- **邮件删除：** 遗憾的是，您无法阻止他人删除共享邮箱中的邮件。 解决此情况的唯一方法是创建 Microsoft 365 组，而不是共享邮箱。 Outlook 中的组类似于共享邮箱。 有关两者的比较，请参阅[比较组](../create-groups/compare-groups.md)。 若要了解有关组的详细信息，请参阅[了解有关组的详细信息](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)。

## <a name="related-articles"></a>相关文章

[创建共享邮箱](create-a-shared-mailbox.md)

[配置共享邮箱](configure-a-shared-mailbox.md)

[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)

[解决共享邮箱问题](resolve-issues-with-shared-mailboxes.md)
