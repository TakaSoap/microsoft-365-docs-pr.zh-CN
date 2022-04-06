---
title: 使用 PowerShell 管理 Skype for Business Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: 使用 PowerShell for Microsoft 365 管理 Skype for Business Online 策略、每用户策略和会议设置。
ms.openlocfilehash: cb546a7e4130509d7acd0021b3cb78df23c1819f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474463"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>使用 PowerShell 管理 Skype for Business Online

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Skype for Business Online 管理员负责管理策略。 虽然你可以在 Microsoft 365 管理中心中执行其中一些任务，但在 PowerShell 中执行其他任务更容易。

## <a name="before-you-start"></a>准备工作

> [!NOTE]
> Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新 **Teams PowerShell** 公共版本，则无需安装 Skype for Business Online 连接器。

> [!NOTE]
> Skype for Business Online 管理员可以通过 PowerShell 管理 **Teams** 和 **Skype for Business Online** 应用策略。

安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。

## <a name="connect-using-admin-credentials"></a>使用管理员凭据连接

1. 打开 Windows PowerShell 命令提示符窗口并运行以下命令：

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. 在 “**Windows PowerShell 凭据请求**”对话框中，键入你的 管理员帐户名和密码，然后选择“**确定**”。

## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>使用具有多重身份验证的管理员帐户进行连接

1. 打开 Windows PowerShell 命令提示符窗口并运行以下命令：

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. 系统提示时，输入 Skype for Business Online 管理员帐户名称。

3. 在“**登录到你的帐户**”对话框中，键入你的 Skype for Business Online 管理员密码，然后选择“**登录**”。

4. 在“**登录到你的帐户**”对话框中，按照说明添加身份验证信息（如验证码），然后选择“**验证**”。

有关详细信息，请参阅：

- [使用 PowerShell 管理 Skype for Business Online 策略](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)

- [使用 PowerShell 指定每个用户 Skype for Business Online 策略](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)

[Skype for Business PowerShell cmdlet 参考](/powershell/module/skype/)
