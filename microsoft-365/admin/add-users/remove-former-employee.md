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
description: '按照此清单从 Microsoft 365 中删除员工和安全数据。 '
ms.openlocfilehash: 50355a20e0d0e8ff782deebd9be65fdabf875bb2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860769"
---
# <a name="remove-or-delete-a-former-employee"></a>删除或删除以前的员工

## <a name="sign-out-now"></a>立即注销！

::: moniker range="o365-worldwide"

观看有关删除员工的简短视频。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

防止员工登录：

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择用户名旁边的框，然后选择重置 **密码**。
3. 输入新密码，然后选择"重置 **"。**  (不要将其发送给他们。) 
4. 选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**启动注销"。**

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择用户，然后选择"重置 **密码"。**

3. 输入新密码，然后选择"重置 **"。**  (不要将其发送给他们。) 

4. 选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**启动注销"。**

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择用户，然后选择"重置 **密码"。**

3. 输入新密码，然后选择"重置 **"。**  (不要将其发送给他们。) 

4. 选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**启动注销"。**

::: moniker-end

> [!NOTE]
> 你需要是全局管理员才能启动注销。

在一小时内或离开他们当前位于的 Microsoft 365 页面后，系统将提示他们重新登录。 访问令牌适合一小时，因此时间线取决于该令牌所剩的时间，以及他们是否导航到当前网页。
  
> [!IMPORTANT]
> 如果用户在 Outlook 网页中，只需单击其邮箱中的四处，可能不会立即启动。 一旦他们选择其他磁贴（如 OneDrive）或刷新浏览器，即会启动注销。
  
若要使用 PowerShell 立即注销用户，请参阅 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet。
  
有关阻止某人继续使用电子邮件所需时长的详细信息，请参阅[终止员工电子邮件会话须知事项](#what-you-need-to-know-about-terminating-an-employees-email-session)。
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>有关删除员工和安全数据的完整步骤的概述

我们经常收到一个问题，即"当员工离开组织时该如何保护数据？ 本文介绍了如何阻止访问 Microsoft 365 以及保护数据应执行的步骤。
  
> [!NOTE]
> 如果你是全局管理员，可以删除员工，转发他们的电子邮件，选择使用新的指导体验处理 OneDrive 内容。 有关详细信息，请参阅全局 [管理员：删除用户](remove-former-employee.md)。 但是，我们建议完成此处列出的所有其他步骤，以确保员工无法访问贵公司的数据。 
  
以下是快速概述。本文详细介绍了每个步骤。
  
|||
|:-----|:-----|
|**步骤** <br/> |**为什么执行此操作** <br/> |
|1. [保存以前员工的邮箱的内容](#save-the-contents-of-a-former-employees-mailbox) <br/> |这对将要接管员工工作或者存在诉讼的人很有用。  <br/> |
|2.[将前员工的电子邮件转发给其他员工或转换为共享邮箱](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |这可保证前员工的电子邮件地址处于活动状态。如果客户或合作伙伴仍向以前员工的地址发送电子邮件，此功能可让他们发送给接管该工作的员工。  <br/> |
|3.[擦除并阻止以前员工的移动设备](#wipe-and-block-a-former-employees-mobile-device) <br/> |从手机或平板电脑删除业务数据。  <br/> |
|4. [阻止以前的员工访问 Microsoft 365 数据](#block-a-former-employees-access-to-microsoft-365-data)<br/> |它会阻止用户访问其旧 Microsoft 365 邮箱和数据。  <br/><br/> **提示**：阻止用户访问时，仍需要支付其许可证费用。 若要停止付费，请从你的订阅中删除许可证 (步骤 5) 。  |
|5.[移动员工的 OneDrive 内容](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |如果仅删除用户的许可证但不删除其帐户，则甚至 30 天后仍可访问该用户的 OneDrive 中的内容。  <br/><br/> 删除帐户之前，应将其 OneDrive 内容移至另一个易访问的位置。删除员工帐户后，其 OneDrive 中的内容会保留 **30** 天。在此 30 天中可以还原用户帐户并获取访问其 OneDrive 内容的权限。如果还原用户帐户，即使是在 30 天后也可以访问 OneDrive 内容。  <br/> |
|5a.如果用户使用其个人计算机访问 OneDrive 和 SharePoint，将发生什么情况？  <br/> |如果用户使用个人计算机（而不是公司计算机）从 OneDrive 和 SharePoint 下载文件，则无法擦除其存储的文件。  <br/><br/> 他们仍然有权访问已同步到计算机的任何文件。  <br/> |
|6. [从以前的员工删除和删除 Microsoft 365 许可证](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |移除许可证后，可将许可证分配给其他人。也可删除许可证，以便在聘用其他人员之前，无需为其付费。  <br/><br/> 移除或删除许可证时，用户的旧电子邮件、联系人和日历将保留 **30 days** ，然后永久删除。如果删除许可证但不删除其帐户，则在 30 天后仍可以访问该用户的 OneDrive 中的内容。  <br/> |
|7.[删除以前员工的用户帐户](#delete-a-former-employees-user-account)<br/> |这将从管理中心中删除帐户。 进行清除，保持干净。  <br/> |

## <a name="save-the-contents-of-a-former-employees-mailbox"></a>保存以前员工的邮箱的内容

有两种方法可以保存以前员工邮箱的内容：
  
1. 将以前员工的电子邮件地址添加到 Outlook 2013 或 2016 版，然后将数据导出到 .pst 文件。可以根据需要将数据导入到其他电子邮件帐户。若要了解如何执行此操作，请参阅[访问并备份以前用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。

    或者

2. 在删除用户帐户之前，对邮箱执行诉讼保留或就地保留功能。这比第一种方式复杂得多，但在以下情况下是值得的：企业版计划包括存档和法定保留项，可能进行诉讼且拥有强大的 IT 部门。

    将邮箱转换为"非活动邮箱"后，管理员、合规部主管或记录管理员可以使用 Exchange Online 中的 In-Place 电子数据展示工具访问和搜索内容。

    非活动状态的邮箱无法接收电子邮件且不在组织的共享通讯簿或其他列表中显示。

    若要了解如何将邮箱置于保留状态，请参阅 [管理 Exchange Online 中的非活动邮箱](../../compliance/create-and-manage-inactive-mailboxes.md)。

## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>将前员工的电子邮件转发给其他员工或转换为共享邮箱

在此步骤中，将前员工的电子邮件地址分配给其他员工，或者将[该用户的邮箱转换成之前创建的共享邮箱](../email/convert-user-mailbox-to-shared-mailbox.md)。
  
- 创建共享邮箱是一种较为便宜的方法，因为 **只要邮箱小于 50 GB** ，就不必支付许可证费用。如果超过 50 GB 就需向其分配许可证。
- 如果将邮箱转换为共享邮箱，则所有的旧电子邮件也仍然可用。这会占用大量空间。
- If you set up email forwarding, only  *new*  emails sent to the former employee will now be sent to the current employee.

 > [!IMPORTANT]
 > 如果要设置电子邮件转发或共享邮箱，则最后不要删除以前员工的帐户。 需要保留该帐户以定位电子邮件转发或共享邮箱。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要阻止的员工的姓名，然后选择"邮件 **"** 选项卡。
3. 在 **"电子邮件转发"下**，选择 **"管理电子邮件转发"。**
4. 启用" **转发发至此邮箱的所有电子邮件** "。 在 **"转发地址** "框中，键入要获取电子邮件的当前员工的电子邮件地址。
5. 选择“**保存**”。
6. 注意，切勿删除以前员工的帐户。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后展开"邮件 **设置"。**

3. 在"**电子邮件转发"旁边，选择**"编辑 **"。**

4. 启用" **转发发至此邮箱的所有电子邮件** "。在" **转发地址** "框中，键入将收到电子邮件的当前员工（或共享邮箱）的电子邮件地址。
  
5. 选择“**保存**”。

6. 注意，切勿删除以前员工的帐户。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后展开"邮件 **设置"。**

3. 在"**电子邮件转发"旁边，选择**"编辑 **"。**

4. 启用" **转发发至此邮箱的所有电子邮件** "。在" **转发地址** "框中，键入将收到电子邮件的当前员工（或共享邮箱）的电子邮件地址。
  
5. 选择“**保存**”。

6. 注意，切勿删除以前员工的帐户。

::: moniker-end

## <a name="wipe-and-block-a-former-employees-mobile-device"></a>擦除并阻止以前员工的移动设备

如果以前的员工有组织电话，可以使用 Exchange 管理中心擦除和阻止该设备，以便从设备中删除所有组织数据，并且它无法再连接到 Office 365。

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
2. 在 Exchange 管理中心 中，导航到" **收件人** "\>" **邮箱** "。
3. 选择用户，在"**移动设备"下**，选择"**查看详细信息"。**
4. 在"**移动设备详细信息"** 页上 **的"移动设备**"下，选择移动设备，选择"**擦除数据** ![ 擦除设备"， ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) 然后选择"阻止 **"。**
5. 选择“**保存**”。
   > [!TIP]
   > 请确保从本地 Blackberry 企业服务中删除或禁用用户。 还应禁用该用户的所有 BlackBerry 设备。 有关如何禁用用户的具体步骤，可参阅 BlackBerry(R) 商务云服务管理指南。

## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>阻止以前的员工访问 Microsoft 365 数据

 > [!IMPORTANT]
 > 阻止帐户可能需要 24 小时才能生效。 如果需要立即阻止用户的登录访问，应重置其密码，然后启动一次事件[](reset-passwords.md)，以注销所有设备的 Microsoft 365 会话。 请参阅[立即注销！](#sign-out-now)

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要阻止的员工的姓名，在用户名下，选择"阻止此 **用户"的符号**。
3. 选择 **"阻止用户登录"，** 然后选择"保存 **"。**

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后选择"**阻止登录"。**

3. 选择 **"阻止用户登录"，** 然后选择"保存 **"。**

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后选择"**阻止登录"。**

3. 选择 **"阻止用户登录"，** 然后选择"保存 **"。**

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>阻止以前的员工访问电子邮件 (Exchange Online)

如果你有电子邮件作为 Microsoft 365 订阅的一部分，你需要登录到 Exchange 管理中心，按照以下步骤操作，阻止以前的员工访问他们的电子邮件。
  
1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
2. 在 Exchange 管理中心 中，导航到" **收件人** "\>" **邮箱** "。
3. 双击用户，然后转到" **邮箱功能"** 页。 在 **"移动设备"下**，选择"禁用 **Exchange ActiveSync"** 和"**禁用适用于设备的 OWA"，** 当系统提示时，对两者回答"是"。 
4. 在 **"电子邮件连接"** 下 **，选择"禁用****"，在系统提示** 时回答"是"。

## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>从以前的员工删除和删除 Microsoft 365 许可证

因此，在某人离开组织后，你无需继续支付许可证费用，你需要删除其 Microsoft 365 许可证，然后从订阅中删除它。 如果选择不从订阅中删除该许可证，可将其分配给其他用户。
  
删除许可证后，该用户的所有数据将保留 30 天。 可[访问](get-access-to-and-back-up-a-former-user-s-data.md)该数据，或在用户返回时[还原](restore-user.md)该帐户。 30 天后，用户的所有数据 (存储在 SharePoint Online) 上的文档除外）将从 Microsoft 365 中永久删除，并且无法恢复。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要阻止的员工的姓名，然后选择"许可证 **和应用"** 选项卡。
3. 清除要删除 (许可证) 复选框，然后选择"保存 **更改"。**

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后在"产品许可证"旁边，选择"编辑 **"。**

3. 在"**产品许可证"** 页面上， (要) 许可证，然后选择"保存 **"。**

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要阻止的员工，然后在"产品许可证"旁边，选择"编辑 **"。**

3. 在"**产品许可证"** 页面上， (要) 许可证，然后选择"保存 **"。**

::: moniker-end

**若要在聘用** 其他人之前减少你支付的许可证数量，请执行以下步骤：

::: moniker range="o365-worldwide"
1. 在管理中心，转到" **帐单** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">""产品"页面</a> ，然后选择" **产品"** 选项卡。
2. 选择要从中删除许可证的订阅。
3. 在详细信息页面上，选择删除 **许可证**。
4. 在"**删除许可证"** 窗格中的"新数量"下的"许可证总数"框中，输入此订阅的许可证总数。 例如，如果你有 25 个许可证，并且想要删除其中一个许可证，请输入 24。
5. 选择“**保存**”。
::: moniker-end

::: moniker range="o365-germany"
1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>”页面。
2. 选择 **"添加/删除** 许可证"以删除许可证，这样你才会在聘用其他人之前支付许可证费用。
::: moniker-end

::: moniker range="o365-21vianet"
1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。
2. 选择 **"添加/删除** 许可证"以删除许可证，这样你才会在聘用其他人之前支付许可证费用。
::: moniker-end

向 [企业添加其他人](add-users.md) 时，系统会提示你同时购买许可证，只需一个步骤！

有关管理 Microsoft 365 商业版用户许可证的信息，请参阅在 [Microsoft 365](../manage/assign-licenses-to-users.md)商业版 中向用户分配许可证和取消分配 [Microsoft 365](../manage/remove-licenses-from-users.md)商业版中的用户许可证。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>已删除的员工帐户如何影响 Skype for Business

从 Office 365 删除用户许可证时，与该用户相关联的 PSTN 呼叫号码将被释放。可将其分配给其他用户。
  
如果用户属于队列组，则他不再是呼叫队列代理的可行目标。因此，我们还建议将该用户从与呼叫队列相关联的组中删除。

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>设置呼叫转发给组织人员

如果需要为离职员工的电话号码设置呼叫转发，呼叫策略下的呼叫转发设置可以设置转发，其中传入呼叫可以转发给其他用户，也可以同时呼叫其他人。 有关详细信息，请参阅 [Microsoft Teams 中的通话策略](/microsoftteams/teams-calling-policy)。
  
## <a name="delete-a-former-employees-user-account"></a>删除以前员工的用户帐户

保存并访问以前员工的所有用户数据之后，可以删除以前员工的帐户。
  
如果设置了电子邮件转发或将帐户转换成共享邮箱，则不要删除该帐户。这两项都需要帐户来定位转发或共享邮箱。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要删除的员工的姓名。
3. 在用户名称下，选择"删除用户 **"符号**。 选择此用户需要的选项，然后选择"删除 **用户"。**

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要删除的员工的姓名。

3. 在页面顶部，选择"删除 **用户"。** 选择此用户需要的选项，然后选择"删除 **用户"。**

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要删除的员工的姓名。

3. 在页面顶部，选择"删除 **用户"。** 选择此用户需要的选项，然后选择"删除 **用户"。**

::: moniker-end

删除用户后，其帐户将在大约 30 天内处于非活动状态。在永久删除用户之前，可还原帐户。
  
### <a name="does-your-organization-use-active-directory"></a>组织是否使用 Active Directory？

如果你的组织将用户帐户从本地 Active Directory 环境同步到 Microsoft 365，则必须在本地 Active Directory 服务中删除和还原这些用户帐户。 你无法在 Office 365 中删除或还原它们。
  
若要了解如何删除和还原 Active Directory 中的用户帐户，请参阅删除 [用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。
  
如果使用的是 Azure Active Directory，请参阅 [Remove-MsolUser](https://docs.microsoft.com/powershell/module/msonline/remove-msoluser) PowerShell cmdlet。
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>终止员工电子邮件会话须知事项

下面的内容介绍了如何阻止员工继续使用电子邮件 (Exchange)。
  
|||
|:-----|:-----|
|**可执行的操作** <br/> |**实现方式** <br/> |
|终止会话（如 Outlook 网页版、Outlook、Exchange Active Sync 等）并强制打开一个新的会话  <br/> |重置密码  <br/> |
|终止会话并阻止对未来会话的访问（针对所有协议）  <br/> |禁用帐户。 例如， (Exchange 管理中心或 PowerShell) ：  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|针对特定协议终止会话（如 ActiveSync）  <br/> |禁用协议。 例如， (Exchange 管理中心或 PowerShell) ：  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

可在三处完成上述操作：
  
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