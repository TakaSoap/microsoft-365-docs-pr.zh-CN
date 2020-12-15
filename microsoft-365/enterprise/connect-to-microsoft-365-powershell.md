---
title: 使用 PowerShell 连接 Microsoft 365
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
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: 使用 PowerShell for Microsoft 365 连接到 Microsoft 365 租户，从命令行执行管理中心任务。
ms.openlocfilehash: 33f9af45418ae8a1f126d2b321e7246201bd1f6e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002401"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="09b7d-103">使用 PowerShell 连接 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="09b7d-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="09b7d-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="09b7d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="09b7d-105">PowerShell for Microsoft 365 可让你从命令行管理您的 Microsoft 365 设置。</span><span class="sxs-lookup"><span data-stu-id="09b7d-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="09b7d-106">要连接到 PowerShell，只需安装所需的软件，然后连接到 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="09b7d-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="09b7d-107">可以使用两种版本的 PowerShell 模块连接至 Microsoft 365 和管理员用户帐户、组和许可证：</span><span class="sxs-lookup"><span data-stu-id="09b7d-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="09b7d-108">Azure Active Directory PowerShell for Graph（其 cmdlet 在其名称中包含 *AzureAD*）</span><span class="sxs-lookup"><span data-stu-id="09b7d-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="09b7d-109">用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块（其 cmdlet 在其名称中包含 *Msol*）</span><span class="sxs-lookup"><span data-stu-id="09b7d-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="09b7d-110">目前，对于用户、组和许可证管理，Azure Active Directory PowerShell for Graph 模块不能完全替代用于 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块的功能。</span><span class="sxs-lookup"><span data-stu-id="09b7d-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="09b7d-111">在某些情况下，需要同时使用两种版本。</span><span class="sxs-lookup"><span data-stu-id="09b7d-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="09b7d-112">可以在同一计算机上安全地安装两种版本。</span><span class="sxs-lookup"><span data-stu-id="09b7d-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="09b7d-113">开始前，需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="09b7d-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="09b7d-114">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="09b7d-114">**Operating system**</span></span>

<span data-ttu-id="09b7d-115">必须使用 64 位版 Windows。</span><span class="sxs-lookup"><span data-stu-id="09b7d-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="09b7d-116">2014 年已终止对 32 位版的用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块的支持。</span><span class="sxs-lookup"><span data-stu-id="09b7d-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="09b7d-117">可以使用下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="09b7d-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="09b7d-118">Windows 10、Windows 8.1、Windows 8 或 Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="09b7d-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="09b7d-119">Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="09b7d-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="09b7d-120">对于 Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 SP1，请下载并安装 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="09b7d-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="09b7d-121">**PowerShell**</span></span>

- <span data-ttu-id="09b7d-122">对于 Azure Active Directory PowerShell for Graph 模块，必须使用 PowerShell 版本 5.1 或以上版本。</span><span class="sxs-lookup"><span data-stu-id="09b7d-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="09b7d-123">对于用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，必须使用 PowerShell 版本 5.1 或以上版本（最高版本 6）。</span><span class="sxs-lookup"><span data-stu-id="09b7d-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="09b7d-124">你无法使用 PowerShell 版本 7。</span><span class="sxs-lookup"><span data-stu-id="09b7d-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="09b7d-125">这些步骤适合于属于 Microsoft 365 管理员角色成员的用户。</span><span class="sxs-lookup"><span data-stu-id="09b7d-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="09b7d-126">有关详细信息，请参阅[关于管理员角色](https://go.microsoft.com/fwlink/p/?LinkId=532367)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-126">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="09b7d-127">连接到 Azure Active Directory PowerShell Graph 模块</span><span class="sxs-lookup"><span data-stu-id="09b7d-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="09b7d-128">Azure Active Directory PowerShell Graph 模块中的命令在其 cmdlet 名称中包含 *AzureAD*。</span><span class="sxs-lookup"><span data-stu-id="09b7d-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="09b7d-129">可安装[Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 模块或 [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-129">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="09b7d-130">有关在 Azure Active Directory PowerShell Graph 模块中需要新 cmdlet 的过程，请按照以下步骤安装该模块并连接到 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="09b7d-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="09b7d-131">有关不同版本的 Microsoft Windows 的支持信息，请参阅 [Azure Active Directory PowerShell Graph 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="09b7d-132">步骤 1：安装所需软件</span><span class="sxs-lookup"><span data-stu-id="09b7d-132">Step 1: Install the required software</span></span>

<span data-ttu-id="09b7d-133">这些步骤只需在计算机上执行一次。</span><span class="sxs-lookup"><span data-stu-id="09b7d-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="09b7d-134">但可能需要定期更新软件。</span><span class="sxs-lookup"><span data-stu-id="09b7d-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="09b7d-135">打开提升的 Windows PowerShell 命令提示符窗口（以管理员身份运行 Windows PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="09b7d-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="09b7d-136">运行此命令：</span><span class="sxs-lookup"><span data-stu-id="09b7d-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="09b7d-137">如果系统提示从不受信任的存储库安装模块，请键入 **Y** 并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="09b7d-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="09b7d-138">步骤 2：连接到 Microsoft 365 订阅的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="09b7d-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="09b7d-139">若要使用帐户名称和密码或者多重身份验证连接到 Microsoft 365 订阅的 Azure Active Directory (Azure AD)，请在 Windows PowerShell 命令提示符中运行这些命令之一。</span><span class="sxs-lookup"><span data-stu-id="09b7d-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="09b7d-140">（无需提升。）</span><span class="sxs-lookup"><span data-stu-id="09b7d-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="09b7d-141">Office 365 云</span><span class="sxs-lookup"><span data-stu-id="09b7d-141">Office 365 cloud</span></span> | <span data-ttu-id="09b7d-142">命令</span><span class="sxs-lookup"><span data-stu-id="09b7d-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="09b7d-143">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="09b7d-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="09b7d-144">由世纪互联运营的 Office 365</span><span class="sxs-lookup"><span data-stu-id="09b7d-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="09b7d-145">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="09b7d-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="09b7d-146">Office 365 美国政府版 DoD 和 Office 365 美国政府版 GCC 高</span><span class="sxs-lookup"><span data-stu-id="09b7d-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="09b7d-147">在“**登录到你的帐户**”对话框中，键入 Microsoft 365 工作或学校帐户用户名和密码，再选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="09b7d-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="09b7d-148">如果使用多重身份验证，请按照说明提供其他身份验证信息，例如验证码。</span><span class="sxs-lookup"><span data-stu-id="09b7d-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="09b7d-149">连接后，可对 [Azure Active Directory PowerShell Graph 模块](https://docs.microsoft.com/powershell/module/azuread)使用这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="09b7d-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="09b7d-150">与用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块连接</span><span class="sxs-lookup"><span data-stu-id="09b7d-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="09b7d-151">用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块中的 cmdlet 名称中具有 *Msol*。</span><span class="sxs-lookup"><span data-stu-id="09b7d-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="09b7d-152">PowerShell 版本 7 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="09b7d-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="09b7d-153">对于 PowerShell 版本 7 和更高版本，必须使用 Azure Active Directory PowerShell for Graph 模块或 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="09b7d-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="09b7d-154">PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="09b7d-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="09b7d-155">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="09b7d-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="09b7d-156">步骤 1：安装所需软件</span><span class="sxs-lookup"><span data-stu-id="09b7d-156">Step 1: Install the required software</span></span>

<span data-ttu-id="09b7d-157">这些步骤只需在计算机上执行一次。</span><span class="sxs-lookup"><span data-stu-id="09b7d-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="09b7d-158">但可能需要定期更新软件。</span><span class="sxs-lookup"><span data-stu-id="09b7d-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="09b7d-159">如果您运行的不是 Windows 10，则请安装 64 位版 Microsoft Online Services 登录助手：[适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手](https://go.microsoft.com/fwlink/p/?LinkId=286152)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="09b7d-160">请按照以下步骤，安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块：</span><span class="sxs-lookup"><span data-stu-id="09b7d-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="09b7d-161">打开提升的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="09b7d-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="09b7d-162">运行 **Install-Module MSOnline** 命令。</span><span class="sxs-lookup"><span data-stu-id="09b7d-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="09b7d-163">如果系统提示安装 NuGet 提供程序，请键入 **Y**，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="09b7d-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="09b7d-164">如果系统提示从 PSGallery 安装模块，请键入 **Y**，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="09b7d-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="09b7d-165">步骤 2：连接到 Microsoft 365 订阅的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="09b7d-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="09b7d-166">若要使用帐户名称和密码或者多重身份验证连接到 Microsoft 365 订阅的 Azure AD，请在 Windows PowerShell 命令提示符中运行这些命令之一。</span><span class="sxs-lookup"><span data-stu-id="09b7d-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="09b7d-167">（无需提升。）</span><span class="sxs-lookup"><span data-stu-id="09b7d-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="09b7d-168">Office 365 云</span><span class="sxs-lookup"><span data-stu-id="09b7d-168">Office 365 cloud</span></span> | <span data-ttu-id="09b7d-169">命令</span><span class="sxs-lookup"><span data-stu-id="09b7d-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="09b7d-170">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="09b7d-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="09b7d-171">由世纪互联运营的 Office 365</span><span class="sxs-lookup"><span data-stu-id="09b7d-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="09b7d-172">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="09b7d-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="09b7d-173">Office 365 美国政府版 DoD 和 Office 365 美国政府版 GCC 高</span><span class="sxs-lookup"><span data-stu-id="09b7d-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="09b7d-174">在“**登录到你的帐户**”对话框中，键入 Microsoft 365 工作或学校帐户用户名和密码，再选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="09b7d-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="09b7d-175">如果使用多重身份验证，请按照说明提供其他身份验证信息，例如验证码。</span><span class="sxs-lookup"><span data-stu-id="09b7d-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="09b7d-176">如何知道它是正常工作的？</span><span class="sxs-lookup"><span data-stu-id="09b7d-176">How do you know it worked?</span></span>

<span data-ttu-id="09b7d-177">如果你没有收到错误消息，则表明你已成功连接。</span><span class="sxs-lookup"><span data-stu-id="09b7d-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="09b7d-178">若要快速测试，请运行 Microsoft 365 cmdlet，例如 **Get-MsolUser**，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="09b7d-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="09b7d-179">如果收到错误消息，请检查以下问题：</span><span class="sxs-lookup"><span data-stu-id="09b7d-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="09b7d-180">**常见问题是密码错误**。</span><span class="sxs-lookup"><span data-stu-id="09b7d-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="09b7d-181">再次运行[步骤 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)，并密切注意您输入的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="09b7d-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="09b7d-182">**用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块要求在计算机上启用 Microsoft .NET Framework 3.5.* x*。很可能你的计算机已安装了较新的版本（例如 4 或 4.5.\* x\*）。</span><span class="sxs-lookup"><span data-stu-id="09b7d-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="09b7d-183">但可以启用或禁用与 .NET Framework 的早期版本的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="09b7d-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="09b7d-184">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="09b7d-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="09b7d-185">对于 Windows Server 2012 或 Windows Server 2012 R2，请参阅[使用“添加角色和功能”向导启用 .NET Framework 3.5](https://go.microsoft.com/fwlink/p/?LinkId=532368)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span></span>
    
  - <span data-ttu-id="09b7d-186">对于 Windows 7 或 Windows Server 2008 R2，请参阅[不能打开用于 Windows PowerShell 的 Azure Active Directory 模块](https://go.microsoft.com/fwlink/p/?LinkId=532370)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span></span>

  - <span data-ttu-id="09b7d-187">对于 Windows 10、Windows 8.1 和 Windows 8，请参阅[在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="09b7d-188">**你的用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块版本可能已过期。**</span><span class="sxs-lookup"><span data-stu-id="09b7d-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="09b7d-189">若要进行检查，请在 PowerShell for Microsoft 365 或用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="09b7d-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="09b7d-190">如果返回的版本号低于 *1.0.8070.2*，请卸载用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，并通过上述[第 1 步](#step-1-install-the-required-software)进行安装。</span><span class="sxs-lookup"><span data-stu-id="09b7d-190">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="09b7d-191">**如果收到连接错误，请参阅**[“Connect-MsolService：抛出类型异常”错误](https://go.microsoft.com/fwlink/p/?LinkId=532377)。</span><span class="sxs-lookup"><span data-stu-id="09b7d-191">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="09b7d-192">**如果收到“Get-Item：找不到路径”错误消息**，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="09b7d-192">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="09b7d-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09b7d-193">See also</span></span>

- [<span data-ttu-id="09b7d-194">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="09b7d-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="09b7d-195">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="09b7d-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="09b7d-196">在单个 Windows PowerShell 窗口中连接所有 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="09b7d-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
