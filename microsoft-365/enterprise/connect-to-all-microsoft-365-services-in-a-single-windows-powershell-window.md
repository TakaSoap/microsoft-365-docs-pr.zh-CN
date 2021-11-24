---
title: 在单个 PowerShell 窗口中连接所有 Microsoft 365 服务
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/23/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 摘要：在单个 PowerShell 窗口中连接所有 Microsoft 365 服务。
ms.openlocfilehash: 4df9a16aba22587adbe289bca2d74e78a64db4ba
ms.sourcegitcommit: b51bfed24a9e3b7adf82d4918b76462cd40dffaf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61153744"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>在单个 PowerShell 窗口中连接所有 Microsoft 365 服务

使用 PowerShell 管理 Microsoft 365 时，可以同时打开多个 PowerShell 会话。你可能有不同的 PowerShell 窗口来管理用户帐户、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams 和安全 &amp; 合规中心。
  
这不是用于管理 Microsoft 365 的最佳方案，因为你不能在这些窗口间交换数据，因此无法实现跨服务管理。 本文章介绍如何使用 PowerShell 的单个实例来管理 Microsoft 365 帐户、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams 和安全 &amp; 合规中心。

>[!Note]
>本文目前只包含连接到全球 (+GCC) 云的命令。 “备注”中提供了有关连接到其他 Microsoft 365 云的文章链接。

## <a name="before-you-begin"></a>准备工作

在可以从 PowerShell 的单个实例管理所有 Microsoft 365 之前，请考虑以下先决条件：
  
- 你使用的 Microsoft 365 工作或学校帐户必须是 Microsoft 365 管理员角色的成员。 有关详细信息，请参阅[关于管理员角色](../admin/add-users/about-admin-roles.md)。 这是对 PowerShell for Microsoft 365 的要求，但不一定适用于所有其他 Microsoft 365 服务。
    
- 可以使用以下 64 位版本的 Windows：
    
  - Windows 10
    
  - Windows 8.1 或 Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 或 Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \*需要安裝 Microsoft.NET Framework 4.5.*x* 然後是 Windows Management Framework 3.0 或 4.0。 有关详细信息，请参阅 [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview)。
    
    出于对 Skype for Business Online 模块和一个 Microsoft 365 模块的要求，你需要使用 64 位版本的 Windows。
    
- 需要安装 Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online 和 Teams 所需的模块：
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype for Business Online、PowerShell 模块](/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Teams PowerShell 概览](/microsoftteams/teams-powershell-overview)
    
-  必须对 PowerShell 进行配置才能为 Skype for Business Online 和安全 &amp; 合规中心运行签名的脚本。 在提升的 PowerShell 会话（**以管理员身份运行** 的 PowerShell 会话）中运行以下命令。
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>仅使用密码时的连接步骤

仅使用密码登录时，请按照以下步骤连接到单个 PowerShell 窗口中的所有服务。
  
1. 打开 Windows PowerShell。
    
2. 运行以下命令并输入你的 Microsoft 365 工作或学校帐户凭据。
    
   ```powershell
   $credential = Get-Credential
   ```

3. 运行以下命令，透过使用 Azure Active Directory PowerShell for Graph 模块连接到 Azure AD。
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   或者，如果你使用的是用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，请运行以下命令。
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。必须从 PowerShell 运行这些 cmdlet。

4. 运行以下命令以连接到 SharePoint Online。 指定域的组织名称。 例如，对于litwareinc\.onmicrosoft.com”，组织名称值为“litwareinc”。
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. 运行以下命令以连接到 Exchange Online。
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > 若要连接到除全球云以外的其他 Microsoft 365 云的 Exchange Online，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

6. 运行以下命令以连接到安全 &amp; 合规中心。
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > 若要连接到除全球云以外的其他 Microsoft 365 云的安全 &amp; 合规中心，请参阅[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

7. 运行以下命令以连接到 Teams PowerShell（和 Skype for Business Online）。
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。
  
   > [!Note]
   > 若要连接到除 *全球* 云以外的其他 Microsoft Teams 云，请参阅 [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams)。
  


### <a name="azure-active-directory-powershell-for-graph-module"></a>“用于图表的 Azure Active Directory PowerShell”模块

下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块所有服务的命令。 为登录指定域主机名和 UPN，并同时运行它们。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块

下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中所有服务的命令。 为登录指定域主机的名称和 UPN，并同时运行它们。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>使用多重身份验证时的连接步骤

### <a name="azure-active-directory-powershell-for-graph-module"></a>“用于图表的 Azure Active Directory PowerShell”模块

下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务的命令。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块

下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务的所有命令。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>关闭 PowerShell 窗口

若要关闭 PowerShell 窗口，请运行以下命令以删除 SharePoint Online 和 Teams 的活动会话：
  
```powershell
Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>另请参阅

- [使用 PowerShell 连接 Microsoft 365](connect-to-microsoft-365-powershell.md)
- [使用 PowerShell 管理 SharePoint Online](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
