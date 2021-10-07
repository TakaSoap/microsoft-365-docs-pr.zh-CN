---
title: 步骤 7 - 删除以前员工的用户帐户
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 按照以下步骤删除以前员工的用户帐户。
ms.openlocfilehash: 631405b66c777060463a4e98620ff3c8b06c7e77
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157238"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>步骤 7 - 删除以前员工的用户帐户

保存并访问以前员工的所有用户数据之后，可以删除以前员工的帐户。

> [!IMPORTANT]
> 如果设置了电子邮件转发或将帐户转换成共享邮箱，则不要删除该帐户。这两项都需要帐户来定位转发或共享邮箱。

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要删除的员工的姓名。
3. 在用户名称下，选择"删除 **用户"。** 选择此用户需要的选项，然后选择"删除 **用户"。** 如果已向其他用户提供访问此用户的电子邮件和OneDrive，则不必在此处再次执行。

删除用户后，其帐户将在大约 30 天内处于非活动状态。在永久删除用户之前，可还原帐户。

## <a name="watch-delete-a-former-employees-user-account"></a>观看：删除以前员工的用户帐户

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../../business-video/index.yml)。

## <a name="does-your-organization-use-active-directory"></a>组织是否使用 Active Directory？

如果组织将用户帐户与本地 Active Directory Microsoft 365同步，则必须在本地 Active Directory 服务中删除和还原这些用户帐户。 你无法在 Office 365 中删除或还原它们。

若要了解如何删除和还原 Active Directory 中的用户帐户，请参阅删除 [用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。
  
如果您使用的是 Azure Active Directory，请参阅[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet。
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>终止员工电子邮件会话须知事项

下面的内容介绍了如何阻止员工继续使用电子邮件 (Exchange)。

<br>

****

|可执行的操作|实现方式|
|:-----|:-----|
|终止会话（如 Outlook 网页版、Outlook、Exchange Active Sync 等）并强制打开一个新的会话|重置密码|
|终止会话并阻止对未来会话的访问（针对所有协议）|禁用帐户。 例如， (管理Exchange或 PowerShell) ： <p>  `Set-Mailbox user@contoso.com -AccountDisabled:$true`|
|针对特定协议终止会话（如 ActiveSync）|禁用协议。 例如， (管理Exchange或 PowerShell) ： <p>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false`|
|

可在三处完成上述操作：
  
<br>

****

|如果在此处终止会话|所需时长|
|---|---|
|在 Exchange 管理中心或使用 PowerShell|预期的延迟为 30 分钟以内|
|在 Azure Active Directory 管理中心中|预期的延迟为 60 分钟|
|在本地环境中|预期的延迟为 3 小时或以上|
|

### <a name="how-to-get-fastest-response-for-account-termination"></a>如何最迅速地响应帐户终止

**最快** ：使用 Exchange 管理中心（使用 PowerShell）或 Azure Active Directory 管理中心。在本地环境中可能需要数小时才能通过 DirSync 同步更改。
  
**对于本地和 Exchange 数据中心中的用户最快** ：使用 Azure Active Directory 管理中心/Exchange 管理中心终止会话，同时在本地环境中进行更改。否则，DirSync 将覆盖 Azure Active Directory 管理中心/Exchange 管理中心中的更改。
  
## <a name="related-content"></a>相关内容

[Restore a user (](restore-user.md) article) 

[重置密码](reset-passwords.md)（文章）
