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
ms.openlocfilehash: 36b16b491aa97e7329e440e2c1fb01b8a221a2b6
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477049"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="f4392-103">在单个 PowerShell 窗口中连接所有 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="f4392-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="f4392-104">使用 PowerShell 管理 Microsoft 365 时，可以同时在不同的 PowerShell 窗口中打开多个 PowerShell 会话，这些窗口分别用于管理用户帐户、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="f4392-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="f4392-105">这不是用于管理 Microsoft 365 的最佳方法，因为你不能在这些窗口间交换数据，因此无法实现跨服务管理。</span><span class="sxs-lookup"><span data-stu-id="f4392-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="f4392-106">本主题介绍如何使用 PowerShell 的单个实例，你可以从中管理 Microsoft 365 帐户、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams 和安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="f4392-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="f4392-107">本文目前只包含连接到全球 (+GCC) 云的命令。</span><span class="sxs-lookup"><span data-stu-id="f4392-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="f4392-108">“备注”中提供了有关连接到其他 Microsoft 365 云的信息的文章链接。</span><span class="sxs-lookup"><span data-stu-id="f4392-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="f4392-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="f4392-109">Before you begin</span></span>

<span data-ttu-id="f4392-110">在可以从 PowerShell 的单个实例管理所有 Microsoft 365 之前，请考虑以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="f4392-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="f4392-111">在这些过程中使用的 Microsoft 365 工作或学校帐户必须是 Microsoft 365 管理员角色的成员。</span><span class="sxs-lookup"><span data-stu-id="f4392-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="f4392-112">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="f4392-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="f4392-113">这是对 PowerShell for Microsoft 365 的要求，不一定适用于所有其他 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="f4392-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="f4392-114">可以使用以下 64 位版本的 Windows：</span><span class="sxs-lookup"><span data-stu-id="f4392-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="f4392-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f4392-115">Windows 10</span></span>
    
  - <span data-ttu-id="f4392-116">Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="f4392-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="f4392-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f4392-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="f4392-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f4392-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="f4392-119">Windows Server 2012 R2 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f4392-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="f4392-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="f4392-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="f4392-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="f4392-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="f4392-122">\* 需要安装 Microsoft .NET Framework 4.5.*x*，然后安装 Windows Management Framework 3.0 或 Windows Management Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="f4392-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="f4392-123">有关详细信息，请参阅[安装 .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868)、[Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) 或 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)。</span><span class="sxs-lookup"><span data-stu-id="f4392-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="f4392-124">出于对 Skype for Business Online 模块和一个 Microsoft 365 模块的要求，你需要使用 64 位版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="f4392-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="f4392-125">需要安装 Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online 和 Teams 所需的模块：</span><span class="sxs-lookup"><span data-stu-id="f4392-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="f4392-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="f4392-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="f4392-127">SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="f4392-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="f4392-128">Skype for Business Online、PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="f4392-128">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="f4392-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="f4392-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="f4392-130">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="f4392-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="f4392-131">需要对 PowerShell 进行配置才能为 Skype for Business Online 和安全 &amp; 合规中心运行签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="f4392-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f4392-132">若要执行此操作，请在提升的 PowerShell 会话（通过选择“**以管理员身份运行**”打开的 PowerShell 窗口）中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f4392-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="f4392-133">Exchange Online和安全与合规中心以及 Exchange Online PowerShell V2 模块 &amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="f4392-134">本文使用 Exchange Online PowerShell V2 模块连接到 Exchange Online 和安全与合规中心。&amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="f4392-135">但是，此时无法**在同一 PowerShell 窗口中**连接到 Exchange Online 和安全与合规中心。&amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="f4392-136">因此，在为多个 Microsoft 365 服务配置 PowerShell 窗口时，你必须选择与 Exchange Online *或*安全与合规中心的连接。&amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="f4392-137">仅使用密码时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="f4392-137">Connection steps when using just a password</span></span>

<span data-ttu-id="f4392-138">下面是仅使用密码进行登录时在单个 PowerShell 窗口中连接到所有服务的步骤。</span><span class="sxs-lookup"><span data-stu-id="f4392-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="f4392-139">打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f4392-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="f4392-140">运行以下命令并输入你的 Microsoft 365 工作或学校帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="f4392-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="f4392-141">运行以下命令，使用 Azure Active Directory PowerShell for Graph 模块连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="f4392-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="f4392-142">或者，如果你使用的是用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f4392-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="f4392-143">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="f4392-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f4392-144">若要继续使用这些 cmdlet，必须从 PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="f4392-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="f4392-145">运行以下命令以连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="f4392-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="f4392-146">指定域的组织名称。</span><span class="sxs-lookup"><span data-stu-id="f4392-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="f4392-147">例如，对于“litwareinc.onmicrosoft.com”，组织名称值为“litwareinc”。</span><span class="sxs-lookup"><span data-stu-id="f4392-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="f4392-148">运行以下命令以连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="f4392-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="f4392-149">有关增加 `WSMan NetworkDelayms` 值的警告应在首次连接时出现，并应予以忽略。</span><span class="sxs-lookup"><span data-stu-id="f4392-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   > [!Note]
   > <span data-ttu-id="f4392-150">Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4392-150">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="f4392-151">如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="f4392-151">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector..</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="f4392-152">运行以下命令以连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f4392-152">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="f4392-153">若要连接到除全球云以外的其他 Microsoft 365 云的 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f4392-153">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="f4392-154">或者，运行以下命令以连接到安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="f4392-154">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="f4392-155">若要连接到除全球云以外的其他 Microsoft 365 云的安全 &amp; 合规中心，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f4392-155">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="f4392-156">运行以下命令以连接到 Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f4392-156">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="f4392-157">若要连接到除全球云以外的其他 Microsoft Teams 云，请参阅 [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)。</span><span class="sxs-lookup"><span data-stu-id="f4392-157">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f4392-158">“用于图表的 Azure Active Directory PowerShell”模块</span><span class="sxs-lookup"><span data-stu-id="f4392-158">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f4392-159">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块所有服务（*安全与合规中心除外*）的命令。&amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-159">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="f4392-160">指定你的域主机的名称，然后一次性全部运行。</span><span class="sxs-lookup"><span data-stu-id="f4392-160">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="f4392-161">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块所有服务（*Exchange Online 除外*）的命令。</span><span class="sxs-lookup"><span data-stu-id="f4392-161">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="f4392-162">指定域主机的名称和用于登录的 UPN，然后一次性全部运行。</span><span class="sxs-lookup"><span data-stu-id="f4392-162">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
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

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="f4392-163">“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块</span><span class="sxs-lookup"><span data-stu-id="f4392-163">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="f4392-164">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中所有服务（*安全与合规中心除外*）的命令。&amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-164">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="f4392-165">指定你的域主机的名称，然后一次性全部运行。</span><span class="sxs-lookup"><span data-stu-id="f4392-165">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="f4392-166">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中所有服务（*Exchange Online 除外*）的命令。</span><span class="sxs-lookup"><span data-stu-id="f4392-166">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="f4392-167">指定域主机的名称和用于登录的 UPN，然后一次性全部运行。</span><span class="sxs-lookup"><span data-stu-id="f4392-167">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
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
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="f4392-168">使用多重身份验证时的连接步骤</span><span class="sxs-lookup"><span data-stu-id="f4392-168">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f4392-169">“用于图表的 Azure Active Directory PowerShell”模块</span><span class="sxs-lookup"><span data-stu-id="f4392-169">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f4392-170">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*安全与合规中心除外*）的命令。&amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-170">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="f4392-171">下面是使用“用于图表的 Azure Active Directory PowerShell”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*Exchange Online 除外*）的所有命令。</span><span class="sxs-lookup"><span data-stu-id="f4392-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="f4392-172">“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块</span><span class="sxs-lookup"><span data-stu-id="f4392-172">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="f4392-173">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*安全与合规中心除外*）的所有命令。&amp;</span><span class="sxs-lookup"><span data-stu-id="f4392-173">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="f4392-174">下面是使用“用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块”模块时，在单个块中用于通过多重身份验证连接到多个 Microsoft 365 服务（*Exchange Online 除外*）的所有命令。</span><span class="sxs-lookup"><span data-stu-id="f4392-174">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="f4392-175">关闭 PowerShell 窗口</span><span class="sxs-lookup"><span data-stu-id="f4392-175">Close the PowerShell window</span></span>

<span data-ttu-id="f4392-176">当你准备好关闭 PowerShell 窗口时，请运行以下命令以删除与 Skype for Business Online、SharePoint Online 和 Teams 的活动会话：</span><span class="sxs-lookup"><span data-stu-id="f4392-176">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="f4392-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4392-177">See also</span></span>

- [<span data-ttu-id="f4392-178">使用 PowerShell 连接 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4392-178">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="f4392-179">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4392-179">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f4392-180">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="f4392-180">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
