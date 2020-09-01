---
title: 在单个 PowerShell 窗口中连接所有 Microsoft 365 服务
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307621"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="21a8a-103">在单个 PowerShell 窗口中连接所有 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="21a8a-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="21a8a-104">使用 PowerShell 管理 Microsoft 365 时，可以同时在不同的 PowerShell 窗口中打开多个 PowerShell 会话，这些窗口分别用于管理用户帐户、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="21a8a-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="21a8a-105">这不是用于管理 Microsoft 365 的最佳方法，因为你不能在这些窗口间交换数据，因此无法实现跨服务管理。</span><span class="sxs-lookup"><span data-stu-id="21a8a-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="21a8a-106">本主题介绍如何使用 PowerShell 的单个实例，你可以从中管理 Microsoft 365 帐户、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="21a8a-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="21a8a-107">本文目前只包含连接到全球 (+GCC) 云的命令。</span><span class="sxs-lookup"><span data-stu-id="21a8a-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="21a8a-108">“备注”中提供了有关连接到其他 Microsoft 365 云的信息的文章链接。</span><span class="sxs-lookup"><span data-stu-id="21a8a-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="21a8a-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="21a8a-109">Before you begin</span></span>

<span data-ttu-id="21a8a-110">在可以从 PowerShell 的单个实例管理所有 Microsoft 365 之前，请考虑以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="21a8a-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="21a8a-111">在这些过程中使用的 Microsoft 365 工作或学校帐户必须是 Microsoft 365 管理员角色的成员。</span><span class="sxs-lookup"><span data-stu-id="21a8a-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="21a8a-112">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="21a8a-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="21a8a-113">这是对 PowerShell for Microsoft 365 的要求，不一定适用于所有其他 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="21a8a-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="21a8a-114">可以使用以下 64 位版本的 Windows：</span><span class="sxs-lookup"><span data-stu-id="21a8a-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="21a8a-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="21a8a-115">Windows 10</span></span>
    
  - <span data-ttu-id="21a8a-116">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="21a8a-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="21a8a-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="21a8a-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="21a8a-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="21a8a-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="21a8a-119">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="21a8a-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="21a8a-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="21a8a-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="21a8a-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="21a8a-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="21a8a-122">\* 需要安装 Microsoft .NET Framework 4.5.*x*，然后安装 Windows Management Framework 3.0 或 Windows Management Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="21a8a-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="21a8a-123">有关详细信息，请参阅[安装 .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868)、[Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) 或 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)。</span><span class="sxs-lookup"><span data-stu-id="21a8a-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="21a8a-124">出于对 Skype for Business Online 模块和一个 Microsoft 365 模块的要求，你需要使用 64 位版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="21a8a-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="21a8a-125">需要安装 Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online 和 Teams 所需的模块：</span><span class="sxs-lookup"><span data-stu-id="21a8a-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="21a8a-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="21a8a-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="21a8a-127">SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="21a8a-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="21a8a-128">Skype for Business Online、PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="21a8a-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="21a8a-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="21a8a-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="21a8a-130">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="21a8a-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="21a8a-131">需要对 PowerShell 进行配置才能为 Skype for Business Online 和安全 &amp; 合规中心运行签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="21a8a-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="21a8a-132">若要执行此操作，请在提升的 PowerShell 会话（通过选择“**以管理员身份运行**”打开的 PowerShell 窗口）中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="21a8a-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="21a8a-133">仅使用密码时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="21a8a-133">Connection steps when using just a password</span></span>

<span data-ttu-id="21a8a-134">下面是仅使用密码进行登录时在单个 PowerShell 窗口中连接到所有服务的步骤。</span><span class="sxs-lookup"><span data-stu-id="21a8a-134">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="21a8a-135">打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="21a8a-135">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="21a8a-136">运行以下命令并输入你的 Microsoft 365 工作或学校帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="21a8a-136">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="21a8a-137">运行以下命令，使用 Azure Active Directory PowerShell for Graph 模块连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="21a8a-137">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="21a8a-138">或者，如果你使用的是用于 PowerShell 的 Microsoft Azure Active Directory 模块，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="21a8a-138">Alternately, if you are using the Microsoft Azure Active Directory Module for PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="21a8a-139">PowerShell Core 不支持用于 PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="21a8a-139">PowerShell Core does not support the Microsoft Azure Active Directory Module for PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="21a8a-140">若要继续使用这些 cmdlet，必须从 PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="21a8a-140">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="21a8a-141">运行以下命令以连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="21a8a-141">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="21a8a-142">指定域的组织名称。</span><span class="sxs-lookup"><span data-stu-id="21a8a-142">Specify the organization name for your domain.</span></span> <span data-ttu-id="21a8a-143">例如，对于“litwareinc.onmicrosoft.com”，组织名称值为“litwareinc”。</span><span class="sxs-lookup"><span data-stu-id="21a8a-143">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="21a8a-144">运行以下命令以连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="21a8a-144">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="21a8a-145">有关增加 `WSMan NetworkDelayms` 值的警告应在首次连接时出现，并应予以忽略。</span><span class="sxs-lookup"><span data-stu-id="21a8a-145">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="21a8a-146">运行以下命令以连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="21a8a-146">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="21a8a-147">若要连接到除全球云以外的其他 Microsoft 365 云的 Exchange Online，请使用 **-ExchangeEnvironmentName** 参数。</span><span class="sxs-lookup"><span data-stu-id="21a8a-147">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="21a8a-148">有关详细信息，请参阅 [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="21a8a-148">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="21a8a-149">运行以下命令以连接到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="21a8a-149">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="21a8a-150">若要连接到除全球云以外的其他 Microsoft Teams 云，请参阅 [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="21a8a-150">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="21a8a-151">运行以下命令以连接到安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="21a8a-151">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="21a8a-152">若要连接到除全球云以外的其他 Microsoft 365 云的安全 &amp; 合规中心，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="21a8a-152">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="21a8a-153">下面是使用 Azure Active Directory PowerShell for Graph 模块时的单个块中的所有命令。</span><span class="sxs-lookup"><span data-stu-id="21a8a-153">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="21a8a-154">指定你的域主机的名称，然后一次性全部运行。</span><span class="sxs-lookup"><span data-stu-id="21a8a-154">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="21a8a-155">此外，下面是使用用于 PowerShell 的 Microsoft Azure Active Directory 模块时的单个块中的所有命令。</span><span class="sxs-lookup"><span data-stu-id="21a8a-155">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span> <span data-ttu-id="21a8a-156">指定你的域主机的名称，然后一次性全部运行。</span><span class="sxs-lookup"><span data-stu-id="21a8a-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="21a8a-157">当你准备好关闭 PowerShell 窗口时，请运行以下命令以删除与 Skype for Business Online、SharePoint Online、安全 &amp; 合规中心和 Teams 的活动会话：</span><span class="sxs-lookup"><span data-stu-id="21a8a-157">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="21a8a-158">使用多重身份验证时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="21a8a-158">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="21a8a-159">下面是使用 Azure Active Directory PowerShell for Graph 模块在单个窗口中通过多重身份验证连接到 Azure AD、SharePoint Online、Skype for Business、Exchange Online 和 Teams 时单个块中的所有命令。</span><span class="sxs-lookup"><span data-stu-id="21a8a-159">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="21a8a-160">指定用户帐户的用户主体名称 (UPN) 和你的域主机名称，然后一次性全部运行。</span><span class="sxs-lookup"><span data-stu-id="21a8a-160">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="21a8a-161">此外，下面是使用用于 PowerShell 的 Microsoft Azure Active Directory 模块时的所有命令。</span><span class="sxs-lookup"><span data-stu-id="21a8a-161">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="21a8a-162">对于安全 &amp; 合规中心，要使用多重身份验证进行连接，请参阅[使用多重身份验证连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps)：</span><span class="sxs-lookup"><span data-stu-id="21a8a-162">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="21a8a-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21a8a-163">See also</span></span>

- [<span data-ttu-id="21a8a-164">使用 PowerShell 连接 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21a8a-164">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="21a8a-165">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="21a8a-165">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="21a8a-166">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="21a8a-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
