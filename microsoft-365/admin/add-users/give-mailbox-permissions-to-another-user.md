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
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 授予用户访问其他用户邮箱的权限，此操作允许用户从其他用户的邮箱读取和发送电子邮件。
ms.openlocfilehash: ec014a744f47b97dd0a65b432510c2e90dea17e4
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370268"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>向其他用户授予邮箱权限 - 管理员帮助

作为管理员，你可能需要按照公司要求允许某些用户访问其他用户的邮箱。例如，你可能希望使助理可以从其经理的邮箱发送或阅读电子邮件，或者希望其中某一位用户可以代表另一用户发送电子邮件。本主题介绍如何实现这一目的。
  
如果需要查找有关创建和管理共享邮箱的信息，请查看[创建共享邮箱](../email/create-a-shared-mailbox.md)。
    
## <a name="looking-to-set-up-mailbox-permissions"></a>需要设置邮箱权限？

通过邮箱权限，你可以向其他用户授予邮箱读取/写入访问权限。以下文章可提供设置和使用此功能所需的帮助：
  
 **设置权限：**
  
设置权限的第一步是确定你希望允许其他用户在特定邮箱中可以执行哪些操作。你可以允许用户阅读邮箱中的电子邮件、代表其他用户发送电子邮件和以如同邮件从该邮箱发送的形式发送电子邮件。请参阅以下文章，了解如何设置每类权限：
  
- [从其他用户的邮箱读取电子邮件](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [从其他用户的邮箱发送电子邮件](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [代表其他用户发送电子邮件](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **更改传播：**
  
设置权限后，更改项在系统传播和生效可能需要长达 60 分钟的时间。
  
 **权限设置后如何使用：**
  
获得访问权限后，你可通过几种不同的方式访问邮箱。相关帮助请参阅[访问他人的邮箱](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)一文。

> [!NOTE]
> 只能在当前组织租户中设置权限。 无法在没有租户用户的情况下设置邮箱权限。
  
## <a name="send-email-from-another-users-mailbox"></a>从其他用户的邮箱发送电子邮件

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  
    
2. 选择用户的名称（你打算向其授予发送权限），打开其 "属性" 窗格。
    
3. 在 **邮件** 选项卡上，选择 **管理邮箱权限**。

4. 在"**发送方式**" 旁，选择“**编辑**”。 

5. 选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。 
    
6. 选择“**添加**”。
 
::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。

3. 在"**发送方式**" 旁，选择“**编辑**”。 

4. 选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。 
    
5. 选择“**添加**”。

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>读取其他用户邮箱中的电子邮件

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  
    
2. 选择用户名（你想要允许阅读的邮箱）以打开其 "属性" 窗格。
    
3. 在 **邮件** 选项卡上，选择 **管理邮箱权限**。
    
4. 在 "**读取和管理**" 旁，选择“**编辑**”。 
    
5. 选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。

6. 选择“**添加**”。


> [!NOTE]
> “**读取**”和“**管理**”权限在 Exchange 管理中心中授予时称为“**完全访问**”权限。 此权限允许分配的用户邮箱读取和管理分配权限的用户邮箱中的电子邮件。 完全访问权限不授予 **“发送方式”** 或 **“代表发送”** 权限。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 
  
2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。
    
3. 在 "**读取和管理**" 旁，选择“**编辑**”。 
    
4. 选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。

5. 选择“**添加**”。

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>代表其他用户发送电子邮件

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  

2. 选择用户的名称（你打算向其授予 **代表发送** 权限），打开其 "属性" 窗格。
    
3. 在 **邮件** 选项卡上，选择 **管理邮箱权限**。
    
4. 在"**代表发送**”旁边，选择“**编辑**"。

5. 选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。

6. 选择“**添加**”。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。

3. 在"**代表发送**”旁边，选择“**编辑**"。
    
4. 选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。

5. 选择“**添加**”。

::: moniker-end


## <a name="related-content"></a>相关内容
  
[管理他人的邮件和日历项目](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)（文章）\   
[代表他人或组发送电子邮件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)（文章）\
[更改用户名和电子邮件地址](../add-users/change-a-user-name-and-email-address.md)（视频）

