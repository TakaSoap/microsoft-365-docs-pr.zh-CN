---
title: 配置电子邮件转发
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 使用 Office365 设置电子邮件转发到一个或多个电子邮件帐户。
ms.openlocfilehash: 4b205c0a21f076b9c7858c8a8fc46e240920cd32
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332626"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>在 Microsoft 365 中配置电子邮件转发

作为组织的管理员，您可能有公司要求为用户邮箱设置电子邮件转发。 通过电子邮件转发，你可以将发送到用户邮箱的电子邮件转发到组织内部或外部的其他用户邮箱。

> [!IMPORTANT]
> 您可以使用出站垃圾邮件筛选器策略来控制自动转发给外部收件人。 有关详细信息，请参阅在 [Microsoft 365 中控制自动外部电子邮件转发](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。

## <a name="configure-email-forwarding"></a>配置电子邮件转发

在设置电子邮件转发之前，请注意以下事项：

- 设置电子邮件转发后，只会转发发送到从邮箱发送的新电子邮件。 

- 电子邮件转发要求 from  *帐户*  具有许可证。 如果由于用户已离开组织而设置电子邮件转发，另一个选项是将其邮箱 [转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。 这样一来，多个人员就可以访问它。 但是，共享邮箱不能超过 50GB。

您必须是 Microsoft 365 中的 Exchange 管理员或全局管理员才能执行这些步骤。 有关详细信息，请参阅关于 [管理员角色的主题](../add-users/about-admin-roles.md)。

1. 在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=834822)** 页面。

2. 选择要转发其电子邮件的用户的名称，然后打开属性页。

3. 在"**邮件"** 选项卡上，选择 **"管理电子邮件转发"。**

4. 在"电子邮件转发"页面上，选择"转发发送到此邮箱的所有电子邮件"，输入转发地址，然后选择是否要保留转发电子邮件的副本。 如果看不到此选项，请确保将许可证分配给用户帐户。 选择“**保存更改**”。

    **若要转发到多个电子邮件地址**，可以要求用户在 Outlook 中设置规则以转发到这些地址。 若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

     或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。

5. 请勿删除要转发的电子邮件用户的帐户，或删除其许可证！  如果这样做，电子邮件转发将停止。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=847686)** 页面。

2. 选择要转发其电子邮件的用户的名称，以打开属性页。

3. 展开 **"邮件设置**"，然后在"电子邮件 **转发"部分**，选择"编辑 **"。**

4. 在电子邮件转发页面上，将切换设置为 **"** 打开"，输入转发地址，然后选择是否要保留转发电子邮件的副本。 如果看不到此选项，请确保将许可证分配给用户帐户。 选择“**保存**”。

   **若要转发到多个电子邮件地址**，可以要求用户在 Outlook 中设置规则以转发到这些地址。 若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。

5. 请勿删除要转发的电子邮件用户的帐户，或删除其许可证！  如果这样做，电子邮件转发将停止。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=850628)** 页面。

2. 选择要转发其电子邮件的用户的名称，以打开属性页。

3. 展开 **"邮件设置**"，然后在"电子邮件 **转发"部分**，选择"编辑 **"。**

4. 在电子邮件转发页面上，将切换设置为 **"** 打开"，输入转发地址，然后选择是否要保留转发电子邮件的副本。 如果看不到此选项，请确保将许可证分配给用户帐户。 选择“**保存**”。

   **若要转发到多个电子邮件地址**，可以要求用户在 Outlook 中设置规则以转发到这些地址。 若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。

5. 请勿删除要转发的电子邮件用户的帐户，或删除其许可证！  如果这样做，电子邮件转发将停止。

::: moniker-end

