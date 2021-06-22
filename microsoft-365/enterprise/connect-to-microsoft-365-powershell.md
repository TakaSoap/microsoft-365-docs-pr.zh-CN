---
title: 使用 PowerShell 连接 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
ms.openlocfilehash: 6b8f98441c7d727984bde8775dea496a9324d50c
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053055"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="60fb8-103">使用 PowerShell 连接 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60fb8-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="60fb8-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="60fb8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="60fb8-105">PowerShell for Microsoft 365 可让你从命令行管理您的 Microsoft 365 设置。</span><span class="sxs-lookup"><span data-stu-id="60fb8-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="60fb8-106">要连接到 PowerShell，只需安装所需的软件，然后连接到 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="60fb8-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="60fb8-107">可以使用两种版本的 PowerShell 模块连接至 Microsoft 365 和管理员用户帐户、组和许可证：</span><span class="sxs-lookup"><span data-stu-id="60fb8-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="60fb8-108">Azure Active Directory PowerShell for Graph（其 cmdlet 在其名称中包含 *AzureAD*）</span><span class="sxs-lookup"><span data-stu-id="60fb8-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="60fb8-109">用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块（其 cmdlet 在其名称中包含 *Msol*）</span><span class="sxs-lookup"><span data-stu-id="60fb8-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="60fb8-110">目前，对于用户、组和许可证管理，Azure Active Directory PowerShell for Graph 模块不能完全替代用于 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块的功能。</span><span class="sxs-lookup"><span data-stu-id="60fb8-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="60fb8-111">在某些情况下，需要同时使用两种版本。</span><span class="sxs-lookup"><span data-stu-id="60fb8-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="60fb8-112">可以在同一计算机上安全地安装两种版本。</span><span class="sxs-lookup"><span data-stu-id="60fb8-112">You can safely install both versions on the same computer.</span></span>

>[!Note]
><span data-ttu-id="60fb8-113">还可以从 Microsoft 365 管理中心连接 [Azure Cloud Shell](#connect-with-the-azure-cloud-shell)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-113">You can also connect with the [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) from the Microsoft 365 admin center.</span></span>
>


## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="60fb8-114">开始前，需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="60fb8-114">What do you need to know before you begin?</span></span>


<span data-ttu-id="60fb8-115">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="60fb8-115">**Operating system**</span></span>

<span data-ttu-id="60fb8-p103">必须使用 64 位版本的 Windows。2014 年 10 月份已终止对 32 位版本的用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块的支持。</span><span class="sxs-lookup"><span data-stu-id="60fb8-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="60fb8-118">可以使用下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="60fb8-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="60fb8-119">Windows 10、Windows 8.1、Windows 8 或 Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="60fb8-119">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="60fb8-120">Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="60fb8-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="60fb8-121">对于 Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 SP1，请下载并安装 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-121">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="60fb8-122">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="60fb8-122">**PowerShell**</span></span>

- <span data-ttu-id="60fb8-123">对于 Azure Active Directory PowerShell for Graph 模块，必须使用 PowerShell 版本 5.1 或以上版本。</span><span class="sxs-lookup"><span data-stu-id="60fb8-123">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="60fb8-p104">对于用于 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块，必须使用 PowerShell 版本 5.1 或以上版本（最高版本 6）。不能使用 PowerShell 版本 7。</span><span class="sxs-lookup"><span data-stu-id="60fb8-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="60fb8-126">这些步骤适合于属于 Microsoft 365 管理员角色成员的用户。</span><span class="sxs-lookup"><span data-stu-id="60fb8-126">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="60fb8-127">有关详细信息，请参阅[关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-127">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="60fb8-128">连接到 Azure Active Directory PowerShell Graph 模块</span><span class="sxs-lookup"><span data-stu-id="60fb8-128">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="60fb8-129">Azure Active Directory PowerShell Graph 模块中的命令在其 cmdlet 名称中包含 *AzureAD*。</span><span class="sxs-lookup"><span data-stu-id="60fb8-129">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="60fb8-130">可安装[Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) 模块或 [Azure PowerShell](/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-130">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="60fb8-131">有关在 Azure Active Directory PowerShell Graph 模块中需要新 cmdlet 的过程，请按照以下步骤安装该模块并连接到 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="60fb8-131">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="60fb8-132">有关不同版本的 Microsoft Windows 的支持信息，请参阅 [Azure Active Directory PowerShell Graph 模块](/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-132">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="60fb8-133">步骤 1：安装所需软件</span><span class="sxs-lookup"><span data-stu-id="60fb8-133">Step 1: Install the required software</span></span>

<span data-ttu-id="60fb8-134">这些步骤只需在计算机上执行一次。</span><span class="sxs-lookup"><span data-stu-id="60fb8-134">These steps are required only one time on your computer.</span></span> <span data-ttu-id="60fb8-135">但可能需要定期更新软件。</span><span class="sxs-lookup"><span data-stu-id="60fb8-135">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="60fb8-136">打开提升的 Windows PowerShell 命令提示符窗口（以管理员身份运行 Windows PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="60fb8-136">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="60fb8-137">运行此命令：</span><span class="sxs-lookup"><span data-stu-id="60fb8-137">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="60fb8-138">默认情况下，PowerShell 库 (PSGallery) 不会配置为 **PowerShellGet** 受信任的存储库。</span><span class="sxs-lookup"><span data-stu-id="60fb8-138">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="60fb8-139">首次使用 PSGallery 时，你将看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="60fb8-139">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="60fb8-140">回答“**是**”或“**全部是**”以继续安装。</span><span class="sxs-lookup"><span data-stu-id="60fb8-140">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="60fb8-141">步骤 2：连接到 Microsoft 365 订阅的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="60fb8-141">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="60fb8-p109">:若要使用帐户名称和密码或者多重身份验证连接到 Microsoft 365 订阅的 Azure Active Directory (Azure AD)，请在 Windows PowerShell 命令提示符中运行这些命令之一。（不必进行提升。）</span><span class="sxs-lookup"><span data-stu-id="60fb8-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="60fb8-144">Office 365 云</span><span class="sxs-lookup"><span data-stu-id="60fb8-144">Office 365 cloud</span></span> | <span data-ttu-id="60fb8-145">命令</span><span class="sxs-lookup"><span data-stu-id="60fb8-145">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="60fb8-146">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="60fb8-146">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="60fb8-147">由世纪互联运营的 Office 365</span><span class="sxs-lookup"><span data-stu-id="60fb8-147">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="60fb8-148">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="60fb8-148">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="60fb8-149">Office 365 美国政府版 DoD 和 Office 365 美国政府版 GCC 高</span><span class="sxs-lookup"><span data-stu-id="60fb8-149">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="60fb8-150">在“**登录到你的帐户**”对话框中，键入 Microsoft 365 工作或学校帐户用户名和密码，再选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="60fb8-150">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="60fb8-151">如果使用多重身份验证，请按照说明提供其他身份验证信息，例如验证码。</span><span class="sxs-lookup"><span data-stu-id="60fb8-151">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="60fb8-152">连接后，可对 [Azure Active Directory PowerShell Graph 模块](/powershell/module/azuread)使用这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="60fb8-152">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="60fb8-153">与用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块连接</span><span class="sxs-lookup"><span data-stu-id="60fb8-153">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="60fb8-154">用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块中的 cmdlet 名称中具有 *Msol*。</span><span class="sxs-lookup"><span data-stu-id="60fb8-154">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="60fb8-155">PowerShell 版本 7 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="60fb8-155">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="60fb8-156">对于 PowerShell 版本 7 和更高版本，必须使用 Azure Active Directory PowerShell for Graph 模块或 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="60fb8-156">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="60fb8-157">PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="60fb8-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="60fb8-158">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="60fb8-158">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="60fb8-159">步骤 1：安装所需软件</span><span class="sxs-lookup"><span data-stu-id="60fb8-159">Step 1: Install the required software</span></span>

<span data-ttu-id="60fb8-160">这些步骤只需在计算机上执行一次。</span><span class="sxs-lookup"><span data-stu-id="60fb8-160">These steps are required only one time on your computer.</span></span> <span data-ttu-id="60fb8-161">但可能需要定期更新软件。</span><span class="sxs-lookup"><span data-stu-id="60fb8-161">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="60fb8-162">如果您运行的不是 Windows 10，则请安装 64 位版 Microsoft Online Services 登录助手：[适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-162">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="60fb8-163">请按照以下步骤，安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块：</span><span class="sxs-lookup"><span data-stu-id="60fb8-163">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="60fb8-164">打开提升的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="60fb8-164">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="60fb8-165">运行 **Install-Module MSOnline** 命令。</span><span class="sxs-lookup"><span data-stu-id="60fb8-165">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="60fb8-166">如果系统提示安装 NuGet 提供程序，请键入 **Y**，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="60fb8-166">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="60fb8-167">如果系统提示从 PSGallery 安装模块，请键入 **Y**，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="60fb8-167">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="60fb8-168">步骤 2：连接到 Microsoft 365 订阅的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="60fb8-168">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="60fb8-p113">若要使用帐户名称和密码或者多重身份验证连接到 Microsoft 365 订阅的 Azure AD，请在 Windows PowerShell 命令提示符中运行这些命令之一。（不必进行提升。）</span><span class="sxs-lookup"><span data-stu-id="60fb8-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="60fb8-171">Office 365 云</span><span class="sxs-lookup"><span data-stu-id="60fb8-171">Office 365 cloud</span></span> | <span data-ttu-id="60fb8-172">命令</span><span class="sxs-lookup"><span data-stu-id="60fb8-172">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="60fb8-173">Office 365 全球 (+GCC)</span><span class="sxs-lookup"><span data-stu-id="60fb8-173">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="60fb8-174">由世纪互联运营的 Office 365</span><span class="sxs-lookup"><span data-stu-id="60fb8-174">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="60fb8-175">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="60fb8-175">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="60fb8-176">Office 365 美国政府版 DoD 和 Office 365 美国政府版 GCC 高</span><span class="sxs-lookup"><span data-stu-id="60fb8-176">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="60fb8-177">在“**登录到你的帐户**”对话框中，键入 Microsoft 365 工作或学校帐户用户名和密码，再选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="60fb8-177">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="60fb8-178">如果使用多重身份验证，请按照说明提供其他身份验证信息，例如验证码。</span><span class="sxs-lookup"><span data-stu-id="60fb8-178">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="60fb8-179">如何知道它是正常工作的？</span><span class="sxs-lookup"><span data-stu-id="60fb8-179">How do you know it worked?</span></span>

<span data-ttu-id="60fb8-180">如果你没有收到错误消息，则表明你已成功连接。</span><span class="sxs-lookup"><span data-stu-id="60fb8-180">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="60fb8-181">若要快速测试，请运行 Microsoft 365 cmdlet，例如 **Get-MsolUser**，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="60fb8-181">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="60fb8-182">如果收到错误消息，请检查以下问题：</span><span class="sxs-lookup"><span data-stu-id="60fb8-182">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="60fb8-183">**常见问题是密码错误**。</span><span class="sxs-lookup"><span data-stu-id="60fb8-183">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="60fb8-184">再次运行[步骤 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)，并密切注意您输入的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="60fb8-184">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="60fb8-185">**用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块要求在计算机上启用 Microsoft .NET Framework 3.5.* x*。很可能你的计算机已安装了较新的版本（例如 4 或 4.5.\* x\*）。</span><span class="sxs-lookup"><span data-stu-id="60fb8-185">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="60fb8-186">但可以启用或禁用与 .NET Framework 的早期版本的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="60fb8-186">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="60fb8-187">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="60fb8-187">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="60fb8-188">对于 Windows Server 2012 或 Windows Server 2012 R2，请参阅[使用“添加角色和功能”向导启用 .NET Framework 3.5](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10))。</span><span class="sxs-lookup"><span data-stu-id="60fb8-188">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="60fb8-189">对于 Windows 7 或 Windows Server 2008 R2，请参阅[不能打开用于 Windows PowerShell 的 Azure Active Directory 模块](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-189">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="60fb8-190">对于 Windows 10、Windows 8.1 和 Windows 8，请参阅[在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5](/dotnet/framework/install/dotnet-35-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-190">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="60fb8-191">**你的用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块版本可能已过期。**</span><span class="sxs-lookup"><span data-stu-id="60fb8-191">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="60fb8-192">若要进行检查，请在 PowerShell for Microsoft 365 或用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="60fb8-192">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="60fb8-193">如果返回的版本号低于 *1.0.8070.2*，请卸载用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，并通过上述 [第 1 步](#step-1-install-the-required-software)进行安装。</span><span class="sxs-lookup"><span data-stu-id="60fb8-193">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="60fb8-194">**如果收到连接错误，请参阅**[“Connect-MsolService：抛出类型异常”错误](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-194">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="60fb8-195">**如果收到“Get-Item：找不到路径”错误消息**，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="60fb8-195">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a><span data-ttu-id="60fb8-196">与 Azure Cloud Shell 连接</span><span class="sxs-lookup"><span data-stu-id="60fb8-196">Connect with the Azure Cloud Shell</span></span>

<span data-ttu-id="60fb8-197">若要连接并使用 Microsoft 365 管理中心中的 Azure Cloud Shell，请从任务栏右上角选择 PowerShell 窗口图标。</span><span class="sxs-lookup"><span data-stu-id="60fb8-197">To connect with and use the Azure Cloud Shell from the Microsoft 365 admin center, select the PowerShell window icon from the upper-right corner of the task bar.</span></span> <span data-ttu-id="60fb8-198">在 **欢迎使用 Azure Cloud Shell** 窗格中，选择 **PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="60fb8-198">In the **Welcome to Azure Cloud Shell** pane, select **PowerShell**.</span></span>

<span data-ttu-id="60fb8-199">将需要组织有活跃的 Azure 订阅，并与 Microsoft 365 订阅绑定。</span><span class="sxs-lookup"><span data-stu-id="60fb8-199">You will need an active Azure subscription for your organization that is tied to your Microsoft 365 subscription.</span></span> <span data-ttu-id="60fb8-200">如果还没有，可以创建一个。</span><span class="sxs-lookup"><span data-stu-id="60fb8-200">If you don't already have one, you can create one.</span></span> <span data-ttu-id="60fb8-201">一旦拥有了 Azure 订阅，则会打开 PowerShell 窗口，可以从中运行 PowerShell 命令和脚本。</span><span class="sxs-lookup"><span data-stu-id="60fb8-201">Once you have an Azure subscription, a PowerShell window opens from which you can run PowerShell commands and scripts.</span></span>

<span data-ttu-id="60fb8-202">有关详细信息，请参阅 [Azure Cloud Shell](/azure/cloud-shell/overview)。</span><span class="sxs-lookup"><span data-stu-id="60fb8-202">For more information, see [Azure Cloud Shell](/azure/cloud-shell/overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="60fb8-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60fb8-203">See also</span></span>

- [<span data-ttu-id="60fb8-204">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60fb8-204">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="60fb8-205">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="60fb8-205">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="60fb8-206">在单个 Windows PowerShell 窗口中连接所有 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="60fb8-206">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
