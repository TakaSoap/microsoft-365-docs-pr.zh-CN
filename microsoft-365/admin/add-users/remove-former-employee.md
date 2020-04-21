---
title: 删除以前的员工
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: '按照此检查表操作，从 Microsoft 365 中删除员工并保护数据。 '
ms.openlocfilehash: 593460c2e49b7136972c084a9927544e6194cb90
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617118"
---
# <a name="remove-a-former-employee"></a>删除以前的员工
  
## <a name="sign-out-now"></a>立即注销！

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

观看有关删除员工的简短视频。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

删除员工：

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
  
以下是快速概述。本文详细介绍了每个步骤。
  
|||
|:-----|:-----|
|**步骤** <br/> |**为什么执行此操作** <br/> |
|1. [保存以前员工的邮箱的内容](#save-the-contents-of-a-former-employees-mailbox) <br/> |此功能对要接管此员工工作的人员或在发生诉讼时非常有用。  <br/> |
|2.[将前员工的电子邮件转发给其他员工或转换为共享邮箱](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |这可保证前员工的电子邮件地址处于活动状态。如果客户或合作伙伴仍向以前员工的地址发送电子邮件，此功能可让他们发送给接管该工作的员工。  <br/> |
|3.[擦除并阻止以前员工的移动设备](#wipe-and-block-a-former-employees-mobile-device) <br/> |从手机或平板电脑删除业务数据。  <br/> |
|4.[阻止以前的员工对 Microsoft 365 数据的访问权限](#block-a-former-employees-access-to-microsoft-365-data)<br/> |阻止用户访问其旧的 Microsoft 365 邮箱和数据。  <br/><br/> **提示**：当您阻止用户的访问时，您仍在为其许可证付费。 必须删除订阅中的许可证，才可停止付费（步骤 5）。           |
|5.[移动员工的 OneDrive 内容](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |如果仅删除用户的许可证但不删除其帐户，则甚至 30 天后仍可访问该用户的 OneDrive 中的内容。  <br/><br/> 删除帐户之前，应将其 OneDrive 内容移至另一个易访问的位置。删除员工帐户后，其 OneDrive 中的内容会保留 **30** 天。在此 30 天中可以还原用户帐户并获取访问其 OneDrive 内容的权限。如果还原用户帐户，即使是在 30 天后也可以访问 OneDrive 内容。  <br/> |
|5a.如果用户使用其个人计算机访问 OneDrive 和 SharePoint，将发生什么情况？  <br/> |如果用户使用个人计算机（而不是公司计算机）从 OneDrive 和 SharePoint 下载文件，则无法擦除其存储的文件。  <br/><br/> 他们将继续有权访问已同步到计算机的任意文件。  <br/> |
|6.[从以前的员工处删除并删除 Microsoft 365 许可证](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |移除许可证后，可将许可证分配给其他人。也可删除许可证，以便在聘用其他人员之前，无需为其付费。  <br/><br/> 移除或删除许可证时，用户的旧电子邮件、联系人和日历将保留 **30 days** ，然后永久删除。如果删除许可证但不删除其帐户，则在 30 天后仍可以访问该用户的 OneDrive 中的内容。  <br/> |
|7.[删除以前员工的用户帐户](#delete-a-former-employees-user-account)<br/> |这将从您的管理中心删除帐户。 进行清除，保持干净。  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>保存以前员工的邮箱的内容
<a name="bkmk_preserve"> </a>

有两种方法可以保存以前员工邮箱的内容：
  
1. 将以前员工的电子邮件地址添加到 Outlook 2013 或 2016 版，然后将数据导出到 .pst 文件。可以根据需要将数据导入到其他电子邮件帐户。若要了解如何执行此操作，请参阅[访问并备份以前用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。
    
    或者
    
2. 在删除用户帐户之前，对邮箱执行诉讼保留或就地保留功能。这比第一种方式复杂得多，但在以下情况下是值得的：企业版计划包括存档和法定保留项，可能进行诉讼且拥有强大的 IT 部门。
    
    将邮箱转换为"非活动邮箱"后，管理员、合规部主管或记录管理者就可以使用 Exchange Online 中的就地电子数据展示工具访问和搜索内容。
    
    非活动状态的邮箱无法接收电子邮件且不在组织的共享通讯簿或其他列表中显示。
    
    若要了解如何在邮箱中放置保留，请参阅[在 Exchange Online 中管理非活动邮箱](https://docs.microsoft.com/office365/securitycompliance/create-and-manage-inactive-mailboxes)。
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>将前员工的电子邮件转发给其他员工或转换为共享邮箱
<a name="bkmk_forward"> </a>

在此步骤中，将前员工的电子邮件地址分配给其他员工，或者将[该用户的邮箱转换成之前创建的共享邮箱](../email/convert-user-mailbox-to-shared-mailbox.md)。 
  
- 创建共享邮箱是一种较为便宜的方法，因为 **只要邮箱小于 50 GB** ，就不必支付许可证费用。如果超过 50 GB 就需向其分配许可证。 
    
- 如果将邮箱转换为共享邮箱，则所有的旧电子邮件也仍然可用。这会占用大量空间。
    
- If you set up email forwarding, only  *new*  emails sent to the former employee will now be sent to the current employee. 
    
- 电子邮件转发要求以前员工的帐户具有许可证。
    
 > [!IMPORTANT] 
 > 如果你正在设置电子邮件转发或共享邮箱，在末尾，请勿删除以前的员工帐户。 需要保留该帐户以定位电子邮件转发或共享邮箱。 

::: moniker range="o365-worldwide"  

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工的姓名，然后选择 "**邮件**" 选项卡。

3. 在 "**电子邮件转发**" 下，选择 "**管理电子邮件转发**"。

4. 启用" **转发发至此邮箱的所有电子邮件** "。在" **转发地址** "框中，键入将收到电子邮件的当前员工（或共享邮箱）的电子邮件地址。 
  
5. 选择“**保存**”。 
    
6. 注意，切勿删除以前员工的帐户。
 
::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工并展开 "**邮件设置**"。

3. 在 "**电子邮件转发**" 旁边，选择 "**编辑**"。

4. 启用" **转发发至此邮箱的所有电子邮件** "。在" **转发地址** "框中，键入将收到电子邮件的当前员工（或共享邮箱）的电子邮件地址。 
  
5. 选择“**保存**”。 
    
6. 注意，切勿删除以前员工的帐户。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工并展开 "**邮件设置**"。

3. 在 "**电子邮件转发**" 旁边，选择 "**编辑**"。

4. 启用" **转发发至此邮箱的所有电子邮件** "。在" **转发地址** "框中，键入将收到电子邮件的当前员工（或共享邮箱）的电子邮件地址。 
  
5. 选择“**保存**”。 
    
6. 注意，切勿删除以前员工的帐户。

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>擦除并阻止以前员工的移动设备
<a name="bkmk_mobile"> </a>

如果以前的员工具有组织电话，则可使用 Exchange 管理中心 擦除并阻止设备，从而让所有组织数据都从设备中删除且不再连接到 Office 365。
  

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

3. 在 Exchange 管理中心 中，导航到" **收件人** "\>" **邮箱** "。 
    
4. 选择用户，在 "**移动设备**" 下，选择 "**查看详细信息**"。 
    
5. 在 "**移动设备详细信息**" 页的 "**移动设备**" 下，选择移动设备，选择 "](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png)**擦除数据**![擦除设备"，然后选择 "**阻止**"。 
    
6. 选择“**保存**”。 
    
    **提示** ：请确保从本地 BlackBerry 企业服务删除或禁用用户。还应禁用该用户的所有 BlackBerry 设备。有关如何禁用用户的具体步骤，可参阅 BlackBerry(R) 商务云服务管理指南。 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>阻止以前的员工对 Microsoft 365 数据的访问权限
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > 阻止帐户可能需要长达24小时才会生效。 如果需要立即阻止用户登录访问，则应[重置其密码](reset-passwords.md)，然后启动一次性事件，以便在所有设备上将其从 Microsoft 365 会话中注销。 请参阅[立即注销！](#sign-out-now)
 

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

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

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

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



1. 在管理中心，转到“**账单**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品和服务</a>”页面。


::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**账单**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**账单**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。

::: moniker-end
    
2. 选择 "**添加/删除许可证**" 以删除许可证，以便在你雇用其他人之前，不要支付此许可证。

将其他人[添加](add-users.md)到您的企业中时，系统将提示您同时购买许可证，只需一步即可！
    
有关管理 Microsoft 365 for business 的用户许可证的详细信息，请参阅[在 microsoft 365 for business 中向用户分配许可证](../manage/assign-licenses-to-users.md)和[删除 microsoft 365 for business 中的用户的许可证](../manage/remove-licenses-from-users.md)。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>已删除的员工帐户如何影响 Skype for Business
<a name="bkmk_remove"> </a>

从 Office 365 删除用户许可证时，与该用户相关联的 PSTN 呼叫号码将被释放。可将其分配给其他用户。
  
如果用户属于队列组，则他不再是呼叫队列代理的可行目标。因此，我们还建议将该用户从与呼叫队列相关联的组中删除。 
  
## <a name="delete-a-former-employees-user-account"></a>删除以前员工的用户帐户
<a name="bkmk_delete"> </a>

保存并访问以前员工的所有用户数据之后，可以删除以前员工的帐户。
  
如果设置了电子邮件转发或将帐户转换成共享邮箱，则不要删除该帐户。这两项都需要帐户来定位转发或共享邮箱。

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

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

删除用户后，其帐户将在大约 30 天内处于非活动状态。在永久删除用户之前，可还原帐户。
  
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
|终止会话并阻止对未来会话的访问（针对所有协议）  <br/> |禁用帐户。示例（在 Exchange 管理中心或使用 PowerShell）：  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|针对特定协议终止会话（如 ActiveSync）  <br/> |禁用协议示例（在 Exchange 管理中心或使用 PowerShell）：<br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
可以在 3 个位置完成上述操作：
  
|||
|:-----|:-----|
|**如果在此处终止会话** <br/> |**所需时长** <br/> |
|在 Exchange 管理中心或使用 PowerShell  <br/> |预期的延迟为 30 分钟以内  <br/> |
|在 Azure Active Directory 管理中心中  <br/> |预期的延迟为 60 分钟  <br/> |
|在本地环境中  <br/> |预期的延迟为 3 小时或以上  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>如何最迅速地响应帐户终止

 **最快** ：使用 Exchange 管理中心（使用 PowerShell）或 Azure Active Directory 管理中心。在本地环境中可能需要数小时才能通过 DirSync 同步更改。 
  
 **对于本地和 Exchange 数据中心中的用户最快** ：使用 Azure Active Directory 管理中心/Exchange 管理中心终止会话，同时在本地环境中进行更改。否则，DirSync 将覆盖 Azure Active Directory 管理中心/Exchange 管理中心中的更改。 
  
## <a name="related-articles"></a>相关文章

[还原用户](restore-user.md)
  