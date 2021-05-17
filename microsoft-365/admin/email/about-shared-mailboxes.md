---
title: 关于共享邮箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 当多个用户需要访问同一个邮箱时，会使用共享邮箱。 在创建共享邮箱之前，了解您需要了解的内容。
ms.openlocfilehash: 83e779d59a8e763b3d0c0482966e75604d5f1574
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903210"
---
# <a name="about-shared-mailboxes"></a>关于共享邮箱

当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址、接待台或其他可能由多个用户共享的其他功能）时，将使用共享邮箱。

如果管理员已授予用户执行该操作的权限，具有组邮箱权限的用户可以作为或代表邮箱电子邮件地址发送。 这对帮助和支持邮箱尤其有用，因为用户可从 "Contoso 支持" 或 "构建 A 接待台" 发送电子邮件。

创建 [共享邮箱之前](create-a-shared-mailbox.md)，应了解以下一些情况：

- **许可证：** 共享邮箱可以存储多达 50 GB 的数据，而无需为其分配许可证。 在此之后，需要向邮箱分配许可证才能存储更多的数据。 有关共享邮箱许可的更多详细信息，请参阅Exchange Online[限制。](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits) 共享邮箱达到存储空间时，短时间内还可以收到电子邮件，但不能发送新的电子邮件。 然后，它会停止接收电子邮件。 邮箱的发件人将收到未送达回执。

- **用户权限：** 您需要向用户授予 (成员身份) 使用共享邮箱。 只有组织内部人员才能使用共享邮箱。

- **外部用户：** 不能向企业外部人员授予 (，例如拥有 Gmail 帐户) 访问共享邮箱。 如果你希望这么做，请考虑改为创建 Outlook 组。 若要了解更多信息，请参阅[在Microsoft 365创建一个组](../create-groups/create-groups.md)。

- **与Outlook：** 除了通过浏览器Outlook Web 上的浏览器访问共享邮箱外，您还可以使用 Outlook for iOS 应用或 Outlook for Android 应用。 若要了解更多信息，请参阅[将共享邮箱添加到Outlook移动。](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f) 另一个选项是，为共享邮箱创建组。 若要了解详细信息，请参阅[比较组](../create-groups/compare-groups.md)。

- **加密：** 无法加密从共享邮箱发送的电子邮件。 这是因为共享邮箱没有自己的安全上下文 (用户名/密码) 因此无法为其分配密钥。 如果多个用户是成员，并且他们发送/接收使用自己的密钥加密的电子邮件，则其他成员可能无法阅读电子邮件，其他人可能无法阅读，具体取决于电子邮件已加密的公钥。

- **邮箱转换：** 可以将用户邮箱转换为共享邮箱。 请参阅[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。

- **管理员角色：** 具有全局管理员或Exchange管理员角色的用户可以创建共享邮箱。

- **订阅要求：** 若要创建共享邮箱，您需要订阅包含电子邮件Microsoft 365商业 (订阅Exchange Online服务) 。 the Microsoft 365 商业应用版 subscription doesn't include email. Microsoft 365 商业标准版包括电子邮件。

- **登录：** 共享邮箱不用于通过关联的用户帐户直接登录。 应始终阻止共享邮箱帐户的登录，并阻止登录。

- **用户过多：** 当同时访问共享邮箱的指定用户过多时，他们可能间歇性地无法连接到此邮箱。 在这种情况下，你可以考虑减少用户数或使用不同的工作负荷，如Microsoft 365或公用文件夹。

- **邮件删除：** 遗憾的是，无法阻止用户删除共享邮箱中的邮件。 这样做的唯一方法就是创建一个Microsoft 365组，而不是共享邮箱。 邮箱中的Outlook就像共享邮箱。 有关这两个组的比较，请参阅 [比较组](../create-groups/compare-groups.md)。 若要详细了解组，请参阅 [了解有关组的更多信息](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。


> [!NOTE]
> 若要访问共享邮箱，用户必须具有Exchange Online许可证，但共享邮箱不需要单独的许可证。 每个共享邮箱都有相应的用户帐户。 注意到你在创建共享邮箱时未被要求提供密码？ 该帐户有一个密码，但密码是系统生成的（未知）。 不应使用该帐户登录共享邮箱。 没有许可证，共享邮箱限制为 50 GB。 若要将大小限制增加到 100 GB，必须将共享邮箱分配给 Exchange Online Plan 2 许可证或 exchange Online Plan 1 许可证，后者包含 Exchange Online Archiving 附加许可证。 这样一来，还可针对无限数量的存档存储容量启用自动扩展存档。 同样，如果要将共享邮箱置于诉讼保留状态，共享邮箱必须具有 Exchange Online 计划 2 许可证或 Exchange Online 计划 1 许可证以及 Exchange Online Archiving 附加设备许可证。 如果要应用高级功能（如 Microsoft Defender for Office 365、Advanced eDiscovery 或自动保留策略），共享邮箱必须获得这些功能的许可。

## <a name="related-content"></a>相关内容

[创建共享邮箱](create-a-shared-mailbox.md)

[配置共享邮箱](configure-a-shared-mailbox.md)

[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)

[解决共享邮箱问题](resolve-issues-with-shared-mailboxes.md)