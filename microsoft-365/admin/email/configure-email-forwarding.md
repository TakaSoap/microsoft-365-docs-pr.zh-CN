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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 使用 Office365 设置向一个或多个电子邮件帐户转发电子邮件。
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560788"
---
# <a name="configure-email-forwarding"></a>配置电子邮件转发

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end
  
作为组织的管理员，您可能需要为用户的邮箱设置电子邮件转发功能的公司要求。 通过电子邮件转发，可以将发送到用户邮箱的电子邮件转发到组织内部或外部的其他用户邮箱。

> [!IMPORTANT]
> 您可以使用出站垃圾邮件筛选器策略来控制自动转发到外部收件人。 有关详细信息，请参阅 [在 Microsoft 365 中控制自动外部电子邮件转发](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。

  
## <a name="configure-email-forwarding"></a>配置电子邮件转发

 在设置电子邮件转发之前，请注意以下事项： 

- 一旦设置了电子邮件转发，则只会转发发送到 "*发件人*" 邮箱的 **新** 电子邮件。 
    
- 电子邮件转发要求 "  *发件人*  " 帐户具有许可证。 如果你正在设置电子邮件转发，因为用户已离开你的组织，另一种方法是 [将其邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。 通过这种方式，多个人可以对其进行访问。 但是，共享邮箱不能超过50GB。 
    
您必须是 Microsoft 365 中的 Exchange 管理员或全局管理员才能执行这些步骤。 有关详细信息，请参阅 [有关管理员角色](../add-users/about-admin-roles.md)的主题。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。 
 
3. 在 " **邮件** " 选项卡上，选择 " **管理电子邮件转发**"。 
  
4. 在 "电子邮件转发" 页面上，选择 " **转发所有发送到此邮箱的电子邮件**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。 如果看不到此选项，请确保将许可证分配给用户帐户。 选择“**保存更改**”。
    
    **若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。 若要了解详细信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。 
    
     或者，在 "管理中心" 中， [创建一个通讯组](../setup/create-distribution-lists.md)， [向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。
    
5. 请勿删除要转发的电子邮件的用户帐户或删除其许可证！  如果这样做，电子邮件转发将停止。 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。 
    
2. 选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。 

3. 展开 " **邮件设置**"，然后在 " **电子邮件转发** " 部分，选择 " **编辑**"。

4. 在 "电子邮件转发" 页面上，将 "切换到" 设置为 **"开**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。 如果看不到此选项，请确保将许可证分配给用户帐户。 选择“**保存**”。
    
    **若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。 若要了解详细信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。 
    
     或者，在 "管理中心" 中， [创建一个通讯组](../setup/create-distribution-lists.md)， [向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。
    
5. 请勿删除要转发的电子邮件的用户帐户或删除其许可证！  如果这样做，电子邮件转发将停止。    

::: moniker-end

::: moniker range="o365-21vianet"

 1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 
    
2. 选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。 

3. 展开 " **邮件设置**"，然后在 " **电子邮件转发** " 部分，选择 " **编辑**"。

4. 在 "电子邮件转发" 页面上，将 "切换到" 设置为 **"开**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。 如果看不到此选项，请确保将许可证分配给用户帐户。 选择“**保存**”。
    
    **若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。 若要了解详细信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。 
    
     或者，在 "管理中心" 中， [创建一个通讯组](../setup/create-distribution-lists.md)， [向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。
    
5. 请勿删除要转发的电子邮件的用户帐户或删除其许可证！  如果这样做，电子邮件转发将停止。 


::: moniker-end 
