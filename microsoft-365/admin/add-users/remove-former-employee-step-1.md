---
title: 步骤 1 - 阻止员工登录Microsoft 365
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
description: 阻止以前的员工登录并阻止访问Microsoft 365服务。
ms.openlocfilehash: 60f4cf6b5c9a0b5dc2023b3ef7b6460685142d07
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244172"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>步骤 1 - 阻止以前的员工登录并阻止对 Microsoft 365 服务的访问

如果需要立即阻止用户的登录访问，应重置其密码。 在此步骤中，强制注销用户Microsoft 365。

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择用户名旁边的框，然后选择重置 **密码**。
3. 输入新密码，然后选择"重置 **"。**  (不要将其发送给他们。) 
4. 选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**启动注销"。**

在一小时内（或离开当前Microsoft 365页面后）将提示他们重新登录。 访问令牌适合一小时，因此时间线取决于该令牌所剩的时间，以及他们是否导航到当前网页。
  
> [!IMPORTANT]
> 如果用户在 web Outlook，只需在邮箱中四处单击，可能不会立即退出。 当他们选择其他磁贴（如OneDrive或刷新浏览器）时，即会启动注销。
  
若要使用 PowerShell 立即注销用户，请参阅 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet。
  
有关阻止某人继续使用电子邮件所需时长的详细信息，请参阅[终止员工电子邮件会话须知事项](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)。

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>阻止以前的员工访问Microsoft 365服务

> [!IMPORTANT]
 > 阻止帐户可能需要 24 小时才能生效。 如果需要立即阻止用户的登录访问，请按照上述步骤操作并重置其密码。

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要阻止的员工的姓名，在用户名下，选择"阻止此 **用户"的符号**。
3. 选择 **"阻止用户登录"，** 然后选择"保存 **"。**

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>阻止以前的员工访问电子邮件 (Exchange Online)

如果你有电子邮件作为你的 Microsoft 365订阅的一部分，请登录到 Exchange 管理中心，并按照以下步骤阻止以前的员工访问他们的电子邮件。
  
1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
2. 在 Exchange 管理中心 中，导航到" **收件人** "\>" **邮箱** "。
3. 双击用户，然后转到" **邮箱功能"** 页。 在 **"移动设备"** 下，选择"禁用 **Exchange ActiveSync"** 和"**禁用适用于设备的 OWA"，** 当系统提示时，对两者回答"是"。 
4. 在 **"电子邮件连接"** 下 **，选择"禁用****"，在系统提示** 时回答"是"。
