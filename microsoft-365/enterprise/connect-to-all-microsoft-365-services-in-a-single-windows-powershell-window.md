---
title: 在单个 PowerShell 窗口中连接所有 Microsoft 365 服务
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
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
ms.openlocfilehash: cd030018dabff628af18d173cf542a3d375b27d0
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515108"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="1f808-103">在单个 PowerShell 窗口中连接所有 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="1f808-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="1f808-104">使用 PowerShell 管理 Microsoft 365 时，可以同时打开多个 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="1f808-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="1f808-105">你可能有不同的 PowerShell 窗口来管理用户帐户、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="1f808-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="1f808-106">这不是用于管理 Microsoft 365 的最佳方案，因为你不能在这些窗口间交换数据，因此无法实现跨服务管理。</span><span class="sxs-lookup"><span data-stu-id="1f808-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="1f808-107">本文章介绍如何使用 PowerShell 的单个实例来管理 Microsoft 365 帐户、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="1f808-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="1f808-108">本文目前只包含连接到全球 (+GCC) 云的命令。</span><span class="sxs-lookup"><span data-stu-id="1f808-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="1f808-109">“备注”中提供了有关连接到其他 Microsoft 365 云的文章链接。</span><span class="sxs-lookup"><span data-stu-id="1f808-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1f808-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="1f808-110">Before you begin</span></span>

<span data-ttu-id="1f808-111">在可以从 PowerShell 的单个实例管理所有 Microsoft 365 之前，请考虑以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="1f808-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="1f808-112">你使用的 Microsoft 365 工作或学校帐户必须是 Microsoft 365 管理员角色的成员。</span><span class="sxs-lookup"><span data-stu-id="1f808-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="1f808-113">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="1f808-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="1f808-114">这是对 PowerShell for Microsoft 365 的要求，但不一定适用于所有其他 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="1f808-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="1f808-115">可以使用以下 64 位版本的 Windows：</span><span class="sxs-lookup"><span data-stu-id="1f808-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="1f808-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1f808-116">Windows 10</span></span>
    
  - <span data-ttu-id="1f808-117">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="1f808-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="1f808-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="1f808-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="1f808-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1f808-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="1f808-120">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1f808-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="1f808-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="1f808-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="1f808-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="1f808-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="1f808-123">\*需要安裝 Microsoft.NET Framework 4.5.*x* 然後是 Windows Management Framework 3.0 或 4.0。</span><span class="sxs-lookup"><span data-stu-id="1f808-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="1f808-124">有关详细信息，请参阅 [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview)。</span><span class="sxs-lookup"><span data-stu-id="1f808-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="1f808-125">出于对 Skype for Business Online 模块和一个 Microsoft 365 模块的要求，你需要使用 64 位版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="1f808-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="1f808-126">需要安装 Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online 和 Teams 所需的模块：</span><span class="sxs-lookup"><span data-stu-id="1f808-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="1f808-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="1f808-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="1f808-128">SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="1f808-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="1f808-129">Skype for Business Online、PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1f808-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="1f808-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="1f808-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="1f808-131">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="1f808-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="1f808-132">必须对 PowerShell 进行配置才能为 Skype for Business Online 和安全 &amp; 合规中心运行签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="1f808-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1f808-133">在提升的 PowerShell 会话（**以管理员身份运行** 的 PowerShell 会话）中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1f808-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="1f808-134">仅使用密码时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="1f808-134">Connection steps when using just a password</span></span>

<span data-ttu-id="1f808-135">仅使用密码登录时，请按照以下步骤连接到单个 PowerShell 窗口中的所有服务。</span><span class="sxs-lookup"><span data-stu-id="1f808-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="1f808-136">打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1f808-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="1f808-137">运行以下命令并输入你的 Microsoft 365 工作或学校帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="1f808-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="1f808-138">运行以下命令，透过使用 Azure Active Directory PowerShell for Graph 模块连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1f808-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="1f808-139">或者，如果你使用的是用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1f808-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="1f808-140">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="1f808-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1f808-141">必须从 PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1f808-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="1f808-142">运行以下命令以连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="1f808-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="1f808-143">指定域的组织名称。</span><span class="sxs-lookup"><span data-stu-id="1f808-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="1f808-144">例如，对于litwareinc\.onmicrosoft.com”，组织名称值为“litwareinc”。</span><span class="sxs-lookup"><span data-stu-id="1f808-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="1f808-145">运行以下命令以连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="1f808-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="1f808-146">首次连接时，将出现一条有关增加 `WSMan NetworkDelayms` 值的警告。</span><span class="sxs-lookup"><span data-stu-id="1f808-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="1f808-147">忽略它。</span><span class="sxs-lookup"><span data-stu-id="1f808-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="1f808-148">Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="1f808-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1f808-149">如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="1f808-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. <span data-ttu-id="1f808-150">运行以下命令以连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1f808-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="1f808-151">若要连接到除全球云以外的其他 Microsoft 365 云的 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1f808-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="1f808-152">运行以下命令以连接到安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="1f808-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="1f808-153">若要连接到除全球云以外的其他 Microsoft 365 云的安全 &amp; 合规中心，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1f808-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="1f808-154">运行以下命令以连接到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1f808-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="1f808-155">若要连接到除 *全球* 云以外的其他 Microsoft Teams 云，请参阅 [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)。</span><span class="sxs-lookup"><span data-stu-id="1f808-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>
  



### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1f808-156">“用于图表的 Azure Active Directory PowerShell”模块</span><span class="sxs-lookup"><span data-stu-id="1f808-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1f808-157">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块所有服务的命令。</span><span class="sxs-lookup"><span data-stu-id="1f808-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="1f808-158">为登录指定域主机名和 UPN，并同时运行它们。</span><span class="sxs-lookup"><span data-stu-id="1f808-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="1f808-159">“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块</span><span class="sxs-lookup"><span data-stu-id="1f808-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="1f808-160">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中所有服务的命令。</span><span class="sxs-lookup"><span data-stu-id="1f808-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="1f808-161">为登录指定域主机的名称和 UPN，并同时运行它们。</span><span class="sxs-lookup"><span data-stu-id="1f808-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="1f808-162">使用多重身份验证时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="1f808-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1f808-163">“用于图表的 Azure Active Directory PowerShell”模块</span><span class="sxs-lookup"><span data-stu-id="1f808-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1f808-164">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务的命令。</span><span class="sxs-lookup"><span data-stu-id="1f808-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="1f808-165">“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块</span><span class="sxs-lookup"><span data-stu-id="1f808-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="1f808-166">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务的所有命令。</span><span class="sxs-lookup"><span data-stu-id="1f808-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="1f808-167">关闭 PowerShell 窗口</span><span class="sxs-lookup"><span data-stu-id="1f808-167">Close the PowerShell window</span></span>

<span data-ttu-id="1f808-168">若要关闭 PowerShell 窗口，请运行以下命令以删除与 Skype for Business Online、SharePoint Online 和 Teams 的活动会话：</span><span class="sxs-lookup"><span data-stu-id="1f808-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="1f808-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f808-169">See also</span></span>

- [<span data-ttu-id="1f808-170">使用 PowerShell 连接 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f808-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="1f808-171">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1f808-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1f808-172">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="1f808-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
