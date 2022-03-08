---
title: 步骤 1 - 阻止以前的员工登录并阻止Microsoft 365服务
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
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
description: 阻止以前的员工登录并阻止访问Microsoft 365服务。
ms.openlocfilehash: abd6a6f47952b5af190b08f1ecae337840eaa312
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315955"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>步骤 1 - 阻止以前的员工登录并阻止Microsoft 365服务

如果需要立即阻止用户的登录访问，应重置其密码。 在此步骤中，强制注销用户Microsoft 365。

> [!NOTE]
> 你需要是全局管理员才能启动其他管理员的注销。 对于非管理员用户，可以使用用户管理员或支持管理员用户执行此操作。 [详细了解管理员角色](about-admin-roles.md)

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择用户名旁边的框，然后选择"重置 **密码"**。
3. 输入新密码，然后选择"重置 **"**。  (不要将其发送给他们。) 
4. 选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**注销所有会话"**。

在一小时内或离开当前Microsoft 365页面后，系统将提示他们重新登录。 访问令牌适合一小时，因此时间线取决于该令牌所剩的时间，以及他们是否导航到当前网页。
  
> [!IMPORTANT]
> 如果用户在邮箱Outlook 网页版，只需在邮箱中四处单击，可能不会立即启动。 当他们选择其他磁贴（如OneDrive或刷新浏览器）时，即会启动注销。
  
若要使用 PowerShell 立即注销用户，请参阅 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet。
  
有关阻止某人继续使用电子邮件所需时长的详细信息，请参阅[终止员工电子邮件会话须知事项](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)。

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>阻止以前的员工访问Microsoft 365服务

> [!IMPORTANT]
 > 阻止帐户可能需要 24 小时才能生效。 如果需要立即阻止用户的登录访问，请按照上述步骤操作并重置其密码。

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要阻止的员工的姓名，在用户名下，选择"阻止此 **用户"的符号**。
3. 选择 **"阻止用户登录"，** 然后选择"保存 **"**。

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>阻止以前的员工访问电子邮件 (Exchange Online)

如果你有电子邮件作为你的 Microsoft 365订阅的一部分，请登录到 Exchange 管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">并按照</a>以下步骤阻止以前的员工访问他们的电子邮件。
  
1. 转到收件人Exchange管理>**管理** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183135" target="_blank">中心</a>。
1. 从列表中选择用户邮箱，然后在右侧"详细信息窗格" ( "电子邮件) "电子邮件应用程序"下选择"管理 **电子邮件应用程序设置"**。 **关闭所有** 选项的滑块;**移动 (Exchange ActiveSync)**、**Outlook 网页版**、**Outlook桌面 (MAPI)**、**Exchange Web 服务**、**POP3** 和 **IMAP**。
1. 选择“**保存**”。

## <a name="related-content"></a>相关内容

[Exchange文章 Exchange Online](/exchange/exchange-admin-center) (管理) \

[Restore a user (](restore-user.md) article) 
