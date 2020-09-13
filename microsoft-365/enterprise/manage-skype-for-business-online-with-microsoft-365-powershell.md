---
title: 使用 PowerShell 管理 Skype for Business Online
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: 使用 PowerShell for Microsoft 365 管理 Skype for Business Online 策略、每用户策略和会议设置。
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430030"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>使用 PowerShell 管理 Skype for Business Online

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Skype for Business Online 管理员负责管理策略。 虽然你可以在 Microsoft 365 管理中心中执行其中一些任务，但在 PowerShell 中执行其他任务更容易。

## <a name="before-you-start"></a>准备工作

下载并安装 [Skype for Business Online Windows PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后重新启动计算机。


## <a name="connect-using-skype-for-business-online-admin-credentials"></a>使用 Skype for Business Online 管理员凭据进行连接

1. 打开 Windows PowerShell 命令提示符窗口并运行以下命令：
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. 在“**Windows PowerShell 凭据请求**”对话框中，键入你的 Skype for Business Online 管理员帐户名和密码，然后选择“**确定**”。


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>使用具有多重身份验证的管理员帐户进行连接

1. 打开 Windows PowerShell 命令提示符窗口并运行以下命令：

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. 当出现 **New-CsOnlineSession** 命令提示时，请输入 Skype for Business Online 管理员帐户名称。

3. 在“**登录到你的帐户**”对话框中，键入你的 Skype for Business Online 管理员密码，然后选择“**登录**”。

4. 在“**登录到你的帐户**”对话框中，按照说明添加身份验证信息（如验证码），然后选择“**验证**”。

有关详细信息，请参阅：
  
- [使用 PowerShell 管理 Skype for Business Online 策略](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [使用 PowerShell 指定每个用户 Skype for Business Online 策略](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)

[Skype for Business PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
