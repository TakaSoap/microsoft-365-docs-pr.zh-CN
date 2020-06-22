---
title: 更改用户名和电子邮件地址
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: '了解全局管理员可以如何更改用户的电子邮件地址和显示名称。 '
ms.openlocfilehash: 76a2124c7fc73e40650a18985a5aa10acf57737a
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780621"
---
# <a name="change-a-user-name-and-email-address"></a>更改用户名和电子邮件地址

例如，若用户结婚和更改姓氏，则可能需要更改该用户的电子邮件地址和显示名称。

请观看有关更改用户电子邮件地址的简短视频。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="change-a-users-email-address"></a>更改用户的电子邮件地址

必须是[全局管理员](about-admin-roles.md)才能执行这些步骤。 

::: moniker range="o365-worldwide"
 
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 选择用户的姓名，然后在“**帐户**”选项卡上选择“**管理用户名**”。
    
3. 在第一个框中，键入新电子邮件地址的第一部分。 如果已将自己的域添加到 Office 365，可以使用下拉列表，选择新电子邮件别名的域。 

4. 选择“**保存更改**”。

   
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 在第一个框中，键入新电子邮件地址的第一部分。 如果已将自己的域添加到 Office 365，可以使用下拉列表，选择新电子邮件别名的域。

4. 选择“**保存**”。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 在第一个框中，键入新电子邮件地址的第一部分。 如果已将自己的域添加到 Office 365，可以使用下拉列表，选择新电子邮件别名的域。

4. 选择“**保存**”。

::: moniker-end

**重要提示**：如果收到错误消息，请参阅[处理错误消息](#resolve-error-messages)。

## <a name="set-the-primary-email-address"></a>设置主要电子邮件地址

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 选择用户的姓名，然后在“**帐户**”选项卡上选择“**管理电子邮件别名**”。

3. 对于要为该用户设置为主要电子邮件地址的地址，选择“**设置为主要电子邮件地址**”。 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    此外，只有全局管理员才能看到此选项。如果没有看到此选项，则表明你不具有更改用户名称和主要电子邮件地址的权限。
  
4. 你会看到一个大的黄色警告，提示你将更改用户的登录信息。 依次选择“**保存**”和“**关闭**”。
    
5. 告知用户以下信息：
 
  - 此更改可能需要一些时间才会生效。
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - 如果用户使用 Skype for Business Online，需告知用户重新安排其组织召开的所有 Skype for Business Online 会议并通知其需要告知外部联系人以更新旧联系人信息。

  - 如果他们使用的是 OneDrive，请告诉他们此位置的 URL 已更改。 如果他们的 OneDrive 中有 OneNote 笔记本，可能需要在 OneNote 中关闭并重新打开笔记本。 如果他们具有 OneDrive 中的共享文件，则指向这些文件的链接可能不起作用，这种情况下，用户可以重新共享。    
  
  - 如果还更改了密码，需告知用户系统将提示他们在移动设备上输入新密码，否则将不会同步。
  
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 对于要为该用户设置为主要电子邮件地址的地址，选择“**设置为主要电子邮件地址**”。 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    此外，只有全局管理员才能看到此选项。如果没有看到此选项，则表明你不具有更改用户名称和主要电子邮件地址的权限。
  
4. 你会看到一个大的黄色警告，提示你将更改用户的登录信息。 依次选择“**保存**”和“**关闭**”。
    
5. 告知用户以下信息：
 
  - 此更改可能需要一些时间才会生效。
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - 如果用户使用 Skype for Business Online，需告知用户重新安排其组织召开的所有 Skype for Business Online 会议并通知其需要告知外部联系人以更新旧联系人信息。

  - 如果他们使用的是 OneDrive，请告诉他们此位置的 URL 已更改。 如果他们的 OneDrive 中有 OneNote 笔记本，可能需要在 OneNote 中关闭并重新打开笔记本。 如果他们具有 OneDrive 中的共享文件，则指向这些文件的链接可能不起作用，这种情况下，用户可以重新共享。    
  
  - 如果还更改了密码，需告知用户系统将提示他们在移动设备上输入新密码，否则将不会同步。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择该用户。 在浮出窗格中的“**用户名/电子邮件**”旁，选择“**编辑**”。

3. 对于要为该用户设置为主要电子邮件地址的地址，选择“**设置为主要电子邮件地址**”。 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    此外，只有全局管理员才能看到此选项。如果没有看到此选项，则表明你不具有更改用户名称和主要电子邮件地址的权限。
  
4. 你会看到一个大的黄色警告，提示你将更改用户的登录信息。 依次选择“**保存**”和“**关闭**”。
    
5. 告知用户以下信息：
 
  - 此更改可能需要一些时间才会生效。
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - 如果用户使用 Skype for Business Online，需告知用户重新安排其组织召开的所有 Skype for Business Online 会议并通知其需要告知外部联系人以更新旧联系人信息。

  - 如果他们使用的是 OneDrive，请告诉他们此位置的 URL 已更改。 如果他们的 OneDrive 中有 OneNote 笔记本，可能需要在 OneNote 中关闭并重新打开笔记本。 如果他们具有 OneDrive 中的共享文件，则指向这些文件的链接可能不起作用，这种情况下，用户可以重新共享。    
  
  - 如果还更改了密码，需告知用户系统将提示他们在移动设备上输入新密码，否则将不会同步。

::: moniker-end
  
## <a name="change-a-users-display-name"></a>更改用户的显示名称

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择用户的姓名，然后在“**帐户**”选项卡上选择“**管理联系人信息**”。

3. 在“**显示名称**”框中，键入该用户的新名称，然后选择“**保存**”。

    如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”，请参阅[处理错误消息](#resolve-error-messages)。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择该用户。 在浮出窗格中的“**联系人信息**”旁，选择“**编辑**”。

3. 在“**显示名称**”框中，键入该用户的新名称，然后选择“**保存**”。

    如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”，请参阅[处理错误消息](#resolve-error-messages)。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择该用户。 在浮出窗格中的“**联系人信息**”旁，选择“**编辑**”。

3. 在“**显示名称**”框中，键入该用户的新名称，然后选择“**保存**”。

    如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”，请参阅[处理错误消息](#resolve-error-messages)。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>解决错误消息

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>“找不到与参数名称‘EmailAddresses’匹配的参数”

If you get the error message " **A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call Support and they will do a full sync for you.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>“很抱歉，无法编辑该用户。 请查看用户信息，请查看用户信息并重试”

如果收到错误消息“**很抱歉，无法编辑该用户。请查看用户信息并重试**”， 这意味着你不是全局管理员，不具有更改用户名的权限。 找到企业中的全局管理员，请他们进行更改。


## <a name="what-to-do-with-old-email-addresses"></a>对旧电子邮件地址的处理

A person's previous primary email address is retained as an additional email address. **We strongly recommend that you don't remove the old email address.**
  
Some people will likely continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft will automatically route it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>用户的脱机通讯簿未与全局地址列表同步怎么办？

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you may see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Office 365. You can subsequently change the username in the Active Directory, but it will not change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
若要修复此问题，请使用 Microsoft 365 管理员凭据登录到[用于 PowerShell 的 Azure Active Directory 模块]( https://go.microsoft.com/fwlink/?LinkId=823193)， 然后使用以下语法： 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> 这会更改用户的 **userPrincipalName** 属性，不会影响其 Microsoft 联机电子邮件路由地址 (MOERA) 电子邮件地址。 但是，最佳做法是使用户的登录 UPN 与其主要 SMTP 地址相匹配。 
  
若要了解如何使用 Windows Server 2003 及更早版本在 Active Directory 中更改用户的用户名，请参阅[重命名用户帐户](https://go.microsoft.com/fwlink/?LinkId=809091)。
  
## <a name="related-articles"></a>相关文章

[管理员：重置一个或多个用户的密码](reset-passwords.md)
  
[为用户添加另一个电子邮件地址](../email/add-another-email-alias-for-a-user.md)
