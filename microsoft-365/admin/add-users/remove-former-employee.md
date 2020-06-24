---
title: 删除前员工
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
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: '按照此检查表操作，从 Microsoft 365 中删除员工并保护数据。 '
ms.openlocfilehash: 51fd26835cd74fa8403437397d37395fcf1c7301
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844854"
---
# <a name="remove-a-former-employee"></a>删除前员工

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end
  
## <a name="sign-out-now"></a>立即注销！

::: moniker range="o365-worldwide"

观看有关删除员工的简短视频。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

若要阻止员工登录，请执行以下操作：

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择用户名称旁边的框，然后选择 "**重置密码**"。

3. 输入新密码，然后选择 "**重置**"。 （不要将其发送给它们。）
    
4. 选择要转到其属性窗格的用户的名称，然后在 " **OneDrive** " 选项卡上，选择 "**启动注销**"。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择该用户，然后选择 "**重置密码**"。

3. 输入新密码，然后选择 "**重置**"。 （不要将其发送给它们。）

4. 再次选择该用户，展开 " **OneDrive 设置**"，然后选择 "**启动**" "**注销**"。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择该用户，然后选择 "**重置密码**"。

3. 输入新密码，然后选择 "**重置**"。 （不要将其发送给它们。）

4. 再次选择该用户，展开 " **OneDrive 设置**"，然后选择 "**启动**" "**注销**"。

::: moniker-end

    
在一个小时内，或者在它们离开当前的 Microsoft 365 页面时，系统会提示他们重新登录。 （Access 令牌适用于一个小时，因此时间线取决于该令牌所剩的时间，以及它们是否从当前网页中移出。）
  
 **警告** ：如果用户是在 Outlook 网页版中，只需在其邮箱中单击，但可能不会立即退出。 一旦选择了不同的磁贴（如 OneDrive）或刷新其浏览器，就会启动注销。 
  
若要使用 PowerShell 立即注销用户，请参阅 [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) cmdlet。 
  
有关阻止某人继续使用电子邮件所需时长的详细信息，请参阅[终止员工电子邮件会话须知事项](#what-you-need-to-know-about-terminating-an-employees-email-session)。
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>有关删除员工和安全数据的完整步骤的概述
<a name="bkmk_now"> </a>

我们经常收到一个问题，即"当员工离开组织时该如何保护数据？ 本文介绍如何阻止对 Microsoft 365 的访问以及应采取的措施保护数据的步骤。
  
> [!NOTE]
> 如果你是全局管理员，你可以删除员工，转发其电子邮件，选择使用新的引导式体验对其 OneDrive 内容执行的操作。 有关详细信息，请参阅[全局管理员：删除用户](remove-former-employee.md)。 但是，我们建议您完成此处列出的所有其他步骤，以确保员工无法访问贵公司的数据。 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**步骤** <br/> |**为什么执行此操作** <br/> |
|1. [保存以前员工的邮箱的内容](#save-the-contents-of-a-former-employees-mailbox) <br/> |此功能对要接管此员工工作的人员或在发生诉讼时非常有用。  <br/> |
|2.[将前员工的电子邮件转发给其他员工或转换为共享邮箱](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3.[擦除并阻止以前员工的移动设备](#wipe-and-block-a-former-employees-mobile-device) <br/> |从手机或平板电脑删除业务数据。  <br/> |
|4.[阻止以前的员工对 Microsoft 365 数据的访问权限](#block-a-former-employees-access-to-microsoft-365-data)<br/> |阻止用户访问其旧的 Microsoft 365 邮箱和数据。  <br/><br/> **提示**：当您阻止用户的访问时，您仍在为其许可证付费。 必须删除订阅中的许可证，才可停止付费（步骤 5）。           |
|5.[移动员工的 OneDrive 内容](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |如果仅删除用户的许可证但不删除其帐户，则甚至 30 天后仍可访问该用户的 OneDrive 中的内容。  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |如果用户使用个人计算机（而不是公司计算机）从 OneDrive 和 SharePoint 下载文件，则无法擦除其存储的文件。  <br/><br/> 他们将继续有权访问已同步到计算机的任意文件。  <br/> |
|6.[从以前的员工处删除并删除 Microsoft 365 许可证](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7.[删除以前员工的用户帐户](#delete-a-former-employees-user-account)<br/> |这将从您的管理中心删除帐户。 进行清除，保持干净。  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>保存以前员工的邮箱的内容
<a name="bkmk_preserve"> </a>

有两种方法可以保存以前员工邮箱的内容：
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    或者
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    将邮箱转换为"非活动邮箱"后，管理员、合规部主管或记录管理者就可以使用 Exchange Online 中的就地电子数据展示工具访问和搜索内容。
    
    非活动状态的邮箱无法接收电子邮件且不在组织的共享通讯簿或其他列表中显示。
    
    若要了解如何在邮箱中放置保留，请参阅[在 Exchange Online 中管理非活动邮箱](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)。
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>将前员工的电子邮件转发给其他员工或转换为共享邮箱
<a name="bkmk_forward"> </a>

在此步骤中，将前员工的电子邮件地址分配给其他员工，或者将[该用户的邮箱转换成之前创建的共享邮箱](../email/convert-user-mailbox-to-shared-mailbox.md)。 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- If you set up email forwarding, only  *new*  emails sent to the former employee will now be sent to the current employee. 
    
- 电子邮件转发要求以前员工的帐户具有许可证。
    
 > [!IMPORTANT] 
 > 如果你正在设置电子邮件转发或共享邮箱，在末尾，请勿删除以前的员工帐户。 需要保留该帐户以定位电子邮件转发或共享邮箱。 

::: moniker range="o365-worldwide"  

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工的姓名，然后选择 "**邮件**" 选项卡。

3. 在 "**电子邮件转发**" 下，选择 "**管理电子邮件转发**"。

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. 选择“**保存**”。 
    
6. 注意，切勿删除以前员工的帐户。
 
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工并展开 "**邮件设置**"。

3. 在 "**电子邮件转发**" 旁边，选择 "**编辑**"。

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. 选择“**保存**”。 
    
6. 注意，切勿删除以前员工的帐户。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工并展开 "**邮件设置**"。

3. 在 "**电子邮件转发**" 旁边，选择 "**编辑**"。

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. 选择“**保存**”。 
    
6. 注意，切勿删除以前员工的帐户。

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>擦除并阻止以前员工的移动设备
<a name="bkmk_mobile"> </a>

如果以前的员工具有组织电话，则可使用 Exchange 管理中心 擦除并阻止设备，从而让所有组织数据都从设备中删除且不再连接到 Office 365。
  

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

3. 在 Exchange 管理中心 中，导航到" **收件人** "\>" **邮箱** "。 
    
4. 选择用户，在 "**移动设备**" 下，选择 "**查看详细信息**"。 
    
5. 在 "**移动设备详细信息**" 页的 "**移动设备**" 下，选择移动设备，选择 "**擦除数据** ![ 擦除设备 ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) "，然后选择 "**阻止**"。 
    
6. 选择“**保存**”。 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>阻止以前的员工对 Microsoft 365 数据的访问权限
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > 阻止帐户可能需要长达24小时才会生效。 如果需要立即阻止用户登录访问，则应[重置其密码](reset-passwords.md)，然后启动一次性事件，以便在所有设备上将其从 Microsoft 365 会话中注销。 请参阅[立即注销！](#sign-out-now)
 

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工的姓名，在用户的名称下，选择 "**阻止此用户**" 的符号。

3. 选择 "**阻止用户登录**"，然后选择 "**保存**"。 

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后选择 "**阻止登录**"。

3. 选择 "**阻止用户登录**"，然后选择 "**保存**"。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后选择 "**阻止登录**"。

3. 选择 "**阻止用户登录**"，然后选择 "**保存**"。 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>阻止以前的员工访问电子邮件 (Exchange Online)
<a name="bkmk_block_email"> </a>

如果您的电子邮件是 Microsoft 365 订阅的一部分，您需要登录到 Exchange 管理中心，以阻止您的前一名员工访问其电子邮件。
  

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
     
2. 在 Exchange 管理中心 中，导航到" **收件人** "\>" **邮箱** "。 
    
3. 双击该用户并转到 "**邮箱功能**" 页。 在 "**移动设备**" 下，选择 "**禁用 Exchange ActiveSync** " 和 "**禁用设备的 OWA"，** 并在收到提示时回答 **"是"** 。 
    
4. 在 "**电子邮件连接**" 下，选择 "**禁用**并在出现提示时回答**是"** 。 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>从以前的员工处删除并删除 Microsoft 365 许可证
<a name="bkmk_remove"> </a>

因此，在有人离开你的组织后，你不会继续支付许可证，你需要删除其 Microsoft 365 许可证，然后将其从订阅中删除。 如果选择不从订阅中删除该许可证，可将其分配给其他用户。
  
删除许可证后，该用户的所有数据将保留 30 天。 可[访问](get-access-to-and-back-up-a-former-user-s-data.md)该数据，或在用户返回时[还原](restore-user.md)该帐户。 30天后，用户的所有数据（存储在 SharePoint Online 上的文档除外）将从 Microsoft 365 中永久删除，并且无法恢复。 

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工的名称，然后选择 "**许可证和应用**" 选项卡。

4. 清除要删除的许可证对应的复选框，然后选择 "**保存更改**"。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后选择 "**产品许可证**" 旁边的 "**编辑**"。

3. 在 "**产品许可证**" 页上，关闭要删除的许可证，然后选择 "**保存**"。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后选择 "**产品许可证**" 旁边的 "**编辑**"。

3. 在 "**产品许可证**" 页上，关闭要删除的许可证，然后选择 "**保存**"。

::: moniker-end


若要在聘用其他人之前 **减少付费的许可证数量** ，请执行以下操作： 

::: moniker range="o365-worldwide"



1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。


::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。

::: moniker-end
    
2. 选择 "**添加/删除许可证**" 以删除许可证，以便在你雇用其他人之前，不要支付此许可证。

将其他人[添加](add-users.md)到您的企业中时，系统将提示您同时购买许可证，只需一步即可！
    
有关管理 Microsoft 365 for business 的用户许可证的详细信息，请参阅[在 microsoft 365 for business 中向用户分配许可证](../manage/assign-licenses-to-users.md)和[删除 microsoft 365 for business 中的用户的许可证](../manage/remove-licenses-from-users.md)。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>已删除的员工帐户如何影响 Skype for Business
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>删除以前员工的用户帐户
<a name="bkmk_delete"> </a>

保存并访问以前员工的所有用户数据之后，可以删除以前员工的帐户。
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要删除的雇员的姓名。

3. 在用户的名称下，选择 "**删除用户**" 的符号。 为此用户选择所需的选项，然后选择 "**删除用户**"。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要删除的雇员的姓名。

3. 在页面顶部，选择 "**删除用户**"。 为此用户选择所需的选项，然后选择 "**删除用户**"。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要删除的雇员的姓名。

3. 在页面顶部，选择 "**删除用户**"。 为此用户选择所需的选项，然后选择 "**删除用户**"。

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>组织是否使用 Active Directory？

如果您的组织将用户帐户从本地 Active Directory 环境同步到 Microsoft 365，则必须在本地 Active Directory 服务中删除和还原这些用户帐户。 你无法在 Office 365 中删除或还原它们。
  
有关说明，请参阅本文：[删除用户帐户](https://go.microsoft.com/fwlink/?linkid=841808)。
  
如果使用 Azure Active Directory，请参阅 [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet。 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>终止员工电子邮件会话须知事项
<a name="bkmk_session"> </a>

下面的内容介绍了如何阻止员工继续使用电子邮件 (Exchange)。
  
|||
|:-----|:-----|
|**可执行的操作** <br/> |**实现方式** <br/> |
|终止会话（如 Outlook 网页版、Outlook、Exchange Active Sync 等）并强制打开一个新的会话  <br/> |重置密码  <br/> |
|终止会话并阻止对未来会话的访问（针对所有协议）  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|针对特定协议终止会话（如 ActiveSync）  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
可以在 3 个位置完成上述操作：
  
|||
|:-----|:-----|
|**如果在此处终止会话** <br/> |**所需时长** <br/> |
|在 Exchange 管理中心或使用 PowerShell  <br/> |预期的延迟为 30 分钟以内  <br/> |
|在 Azure Active Directory 管理中心中  <br/> |预期的延迟为 60 分钟  <br/> |
|在本地环境中  <br/> |预期的延迟为 3 小时或以上  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>如何最迅速地响应帐户终止

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>相关文章

[还原用户](restore-user.md)
  
