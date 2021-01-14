---
title: 在单个 PowerShell 窗口中连接所有 Microsoft 365 服务
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
ms.openlocfilehash: 4266b4f216b4c9df48f0c19d1d2123269eb32cae
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849585"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="00c9c-103">在单个 PowerShell 窗口中连接所有 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="00c9c-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="00c9c-104">使用 PowerShell 管理 Microsoft 365 时，可以同时打开多个 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="00c9c-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="00c9c-105">你可能有不同的 PowerShell 窗口来管理用户帐户、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="00c9c-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="00c9c-106">这不是用于管理 Microsoft 365 的最佳方案，因为你不能在这些窗口间交换数据，因此无法实现跨服务管理。</span><span class="sxs-lookup"><span data-stu-id="00c9c-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="00c9c-107">本文章介绍如何使用 PowerShell 的单个实例来管理 Microsoft 365 帐户、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="00c9c-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="00c9c-108">本文目前只包含连接到全球 (+GCC) 云的命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="00c9c-109">“备注”中提供了有关连接到其他 Microsoft 365 云的文章链接。</span><span class="sxs-lookup"><span data-stu-id="00c9c-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="00c9c-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="00c9c-110">Before you begin</span></span>

<span data-ttu-id="00c9c-111">在可以从 PowerShell 的单个实例管理所有 Microsoft 365 之前，请考虑以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="00c9c-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="00c9c-112">你使用的 Microsoft 365 工作或学校帐户必须是 Microsoft 365 管理员角色的成员。</span><span class="sxs-lookup"><span data-stu-id="00c9c-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="00c9c-113">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="00c9c-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="00c9c-114">这是对 PowerShell for Microsoft 365 的要求，但不一定适用于所有其他 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="00c9c-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="00c9c-115">可以使用以下 64 位版本的 Windows：</span><span class="sxs-lookup"><span data-stu-id="00c9c-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="00c9c-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="00c9c-116">Windows 10</span></span>
    
  - <span data-ttu-id="00c9c-117">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="00c9c-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="00c9c-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="00c9c-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="00c9c-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="00c9c-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="00c9c-120">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="00c9c-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="00c9c-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="00c9c-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="00c9c-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="00c9c-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="00c9c-123">\*需要安裝 Microsoft.NET Framework 4.5.*x* 然後是 Windows Management Framework 3.0 或 4.0。</span><span class="sxs-lookup"><span data-stu-id="00c9c-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="00c9c-124">有关详细信息，请参阅 [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="00c9c-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).</span></span>
    
    <span data-ttu-id="00c9c-125">出于对 Skype for Business Online 模块和一个 Microsoft 365 模块的要求，你需要使用 64 位版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="00c9c-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="00c9c-126">需要安装 Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online 和 Teams 所需的模块：</span><span class="sxs-lookup"><span data-stu-id="00c9c-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="00c9c-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="00c9c-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="00c9c-128">SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="00c9c-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="00c9c-129">Skype for Business Online、PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="00c9c-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="00c9c-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="00c9c-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="00c9c-131">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="00c9c-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="00c9c-132">必须对 PowerShell 进行配置才能为 Skype for Business Online 和安全 &amp; 合规中心运行签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="00c9c-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="00c9c-133">在提升的 PowerShell 会话（**以管理员身份运行** 的 PowerShell 会话）中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="00c9c-134">Exchange Online和安全与合规中心以及 Exchange Online PowerShell V2 模块 &amp;</span><span class="sxs-lookup"><span data-stu-id="00c9c-134">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="00c9c-135">本文中的过程使用 Exchange Online PowerShell V2 模块连接到 Exchange Online 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="00c9c-135">The procedures in this article use the Exchange Online PowerShell V2 module to connect to both Exchange Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="00c9c-136">但目前无法 *在同一个 PowerShell 窗口* 中同时连接到这两处。</span><span class="sxs-lookup"><span data-stu-id="00c9c-136">But currently you can't connect to both *in the same PowerShell window*.</span></span> <span data-ttu-id="00c9c-137">因此，在为多个 Microsoft 365 服务配置 PowerShell 窗口时，必须选择连接到其中一个。</span><span class="sxs-lookup"><span data-stu-id="00c9c-137">So you have to choose to connect to one or the other when you configure a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="00c9c-138">仅使用密码时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="00c9c-138">Connection steps when using just a password</span></span>

<span data-ttu-id="00c9c-139">仅使用密码登录时，请按照以下步骤连接到单个 PowerShell 窗口中的所有服务。</span><span class="sxs-lookup"><span data-stu-id="00c9c-139">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="00c9c-140">打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="00c9c-140">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="00c9c-141">运行以下命令并输入你的 Microsoft 365 工作或学校帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="00c9c-141">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="00c9c-142">运行以下命令，透过使用 Azure Active Directory PowerShell for Graph 模块连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="00c9c-142">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="00c9c-143">或者，如果你使用的是用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-143">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="00c9c-144">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="00c9c-144">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="00c9c-145">必须从 PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00c9c-145">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="00c9c-146">运行以下命令以连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="00c9c-146">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="00c9c-147">指定域的组织名称。</span><span class="sxs-lookup"><span data-stu-id="00c9c-147">Specify the organization name for your domain.</span></span> <span data-ttu-id="00c9c-148">例如，对于litwareinc\.onmicrosoft.com”，组织名称值为“litwareinc”。</span><span class="sxs-lookup"><span data-stu-id="00c9c-148">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="00c9c-149">运行以下命令以连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="00c9c-149">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="00c9c-150">首次连接时，将出现一条有关增加 `WSMan NetworkDelayms` 值的警告。</span><span class="sxs-lookup"><span data-stu-id="00c9c-150">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="00c9c-151">忽略它。</span><span class="sxs-lookup"><span data-stu-id="00c9c-151">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="00c9c-152">Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="00c9c-152">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="00c9c-153">如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="00c9c-153">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="00c9c-154">运行以下命令以连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="00c9c-154">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="00c9c-155">若要连接到除全球云以外的其他 Microsoft 365 云的 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="00c9c-155">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   <span data-ttu-id="00c9c-156">或者，运行以下命令以连接到安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="00c9c-156">Alternatively, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="00c9c-157">若要连接到除全球云以外的其他 Microsoft 365 云的安全 &amp; 合规中心，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="00c9c-157">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="00c9c-158">运行以下命令以连接到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="00c9c-158">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="00c9c-159">若要连接到除 *全球* 云以外的其他 Microsoft Teams 云，请参阅 [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)。</span><span class="sxs-lookup"><span data-stu-id="00c9c-159">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="00c9c-160">“用于图表的 Azure Active Directory PowerShell”模块</span><span class="sxs-lookup"><span data-stu-id="00c9c-160">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="00c9c-161">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块所有服务（*安全 &amp; 合规中心除外*）的命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-161">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="00c9c-162">指定域主机的名称并同时运行它们。</span><span class="sxs-lookup"><span data-stu-id="00c9c-162">Specify the name of your domain host and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="00c9c-163">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块所有服务（*Exchange Online 除外*）的命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-163">Here are the commands for all the services *except Exchange Online* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="00c9c-164">为登录指定域主机名和 UPN，并同时运行它们。</span><span class="sxs-lookup"><span data-stu-id="00c9c-164">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="00c9c-165">“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块</span><span class="sxs-lookup"><span data-stu-id="00c9c-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="00c9c-166">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中所有服务（*安全 &amp; 合规中心除外*）的命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-166">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="00c9c-167">指定域主机的名称并同时运行它们。</span><span class="sxs-lookup"><span data-stu-id="00c9c-167">Specify the name of your domain host and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="00c9c-168">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中所有服务（*Exchange Online 除外*）的命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-168">Here are the commands for all the services *except Exchange Online* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="00c9c-169">为登录指定域主机的名称和 UPN，并同时运行它们。</span><span class="sxs-lookup"><span data-stu-id="00c9c-169">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="00c9c-170">使用多重身份验证时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="00c9c-170">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="00c9c-171">“用于图表的 Azure Active Directory PowerShell”模块</span><span class="sxs-lookup"><span data-stu-id="00c9c-171">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="00c9c-172">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*安全 &amp; 合规中心除外*）的命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="00c9c-173">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*Exchange Online 除外*）的所有命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-173">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication when you use the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="00c9c-174">“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块</span><span class="sxs-lookup"><span data-stu-id="00c9c-174">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="00c9c-175">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*安全 &amp; 合规中心除外*）的所有命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-175">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="00c9c-176">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*Exchange Online 除外*）的所有命令。</span><span class="sxs-lookup"><span data-stu-id="00c9c-176">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="00c9c-177">关闭 PowerShell 窗口</span><span class="sxs-lookup"><span data-stu-id="00c9c-177">Close the PowerShell window</span></span>

<span data-ttu-id="00c9c-178">若要关闭 PowerShell 窗口，请运行以下命令以删除与 Skype for Business Online、SharePoint Online 和 Teams 的活动会话：</span><span class="sxs-lookup"><span data-stu-id="00c9c-178">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="00c9c-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00c9c-179">See also</span></span>

- [<span data-ttu-id="00c9c-180">使用 PowerShell 连接 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00c9c-180">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="00c9c-181">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="00c9c-181">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="00c9c-182">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="00c9c-182">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
