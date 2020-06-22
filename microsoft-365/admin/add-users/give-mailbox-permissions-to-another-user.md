---
title: 向其他用户授予邮箱权限 - 管理员帮助
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: '了解如何授予用户访问其他用户的邮箱的权限。 这将使用户拥有从其他用户的邮箱读取邮件和发送邮件的权限。 '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780597"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>向其他用户授予邮箱权限 - 管理员帮助

作为管理员，你可能需要按照公司要求允许某些用户访问其他用户的邮箱。 例如，你可能希望使助理可以从其经理的邮箱发送或阅读电子邮件，或者希望其中某一位用户可以代表另一用户发送电子邮件。 本主题介绍如何实现这一目的。
  
如果需要查找有关创建和管理共享邮箱的信息，请查看[创建共享邮箱](../email/create-a-shared-mailbox.md)。
    
## <a name="looking-to-set-up-mailbox-permissions"></a>需要设置邮箱权限？

Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:
  
 **设置权限：**
  
The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:
  
- [从其他用户的邮箱读取电子邮件](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [从其他用户的邮箱发送电子邮件](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [代表其他用户发送电子邮件](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **更改传播：**
  
设置权限后，更改项在系统传播和生效可能需要长达 60 分钟的时间。
  
 **权限设置后如何使用：**
  
There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)
  
## <a name="send-email-from-another-users-mailbox"></a>从其他用户的邮箱发送电子邮件

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  
    
2. 选择用户的名称（你打算向其授予发送权限），打开其 "属性" 窗格。
    
3. 在 **邮件** 选项卡上，选择 **管理邮箱权限**。

4. 在"**发送方式**" 旁，选择“**编辑**”。 

5. 选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。 
    
6. 选择“**保存**”。
 
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。

3. 在"**发送方式**" 旁，选择“**编辑**”。 

4. 选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。 
    
5. 选择“**保存**”。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。

3. 在"**发送方式**" 旁，选择“**编辑**”。 

4. 选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。 
    
5. 选择“**保存**”。

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>读取其他用户邮箱中的电子邮件

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  
    
2. 选择用户名（你想要允许阅读的邮箱）以打开其 "属性" 窗格。
    
3. 在 **邮件** 选项卡上，选择 **管理邮箱权限**。
    
4. 在 "**读取和管理**" 旁，选择“**编辑**”。 
    
5. 选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。

6. 选择“**保存**”。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  
  
2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。
    
3. 在 "**读取和管理**" 旁，选择“**编辑**”。 
    
4. 选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。

5. 选择“**保存**”。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 
  
2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。
    
3. 在 "**读取和管理**" 旁，选择“**编辑**”。 
    
4. 选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。

5. 选择“**保存**”。

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>代表其他用户发送电子邮件

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  

2. 选择用户的名称（你打算向其授予**代表发送**权限），打开其 "属性" 窗格。
    
3. 在 **邮件** 选项卡上，选择 **管理邮箱权限**。
    
4. 在"**代表发送**”旁边，选择“**编辑**"。

5. 选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。

6. 选择“**保存**”。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。

3. 在"**代表发送**”旁边，选择“**编辑**"。
    
4. 选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。

5. 选择“**保存**”。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。

3. 在"**代表发送**”旁边，选择“**编辑**"。
    
4. 选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。

5. 选择“**保存**”。

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a>从 Outlook 和适用于企业的 Outlook 网页版发送和阅读电子邮件


Want to know how to send email from another user's mailbox? Check out the following topics:
  
- [管理他人的邮件和日历项目](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [代表他人或组发送电子邮件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
