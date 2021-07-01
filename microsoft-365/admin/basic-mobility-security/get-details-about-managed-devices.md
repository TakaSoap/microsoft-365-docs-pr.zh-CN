---
title: 获取有关基本移动性和安全性托管设备的详细信息
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用Windows PowerShell获取有关组织中基本移动和安全设备的详细信息。
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228167"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="270e6-103">获取有关基本移动性和安全性托管设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="270e6-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="270e6-104">本文演示如何使用 Windows PowerShell获取有关您为基本移动性和安全性设置的组织中设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="270e6-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="270e6-105">以下是可供你使用的设备详细信息的细目。</span><span class="sxs-lookup"><span data-stu-id="270e6-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="270e6-106">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="270e6-106">**Detail**</span></span>|<span data-ttu-id="270e6-107">**在 PowerShell 中查找什么**</span><span class="sxs-lookup"><span data-stu-id="270e6-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="270e6-108">设备已注册基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="270e6-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="270e6-109">有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="270e6-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="270e6-110"> \*isManaged 参数*   的值为：</span><span class="sxs-lookup"><span data-stu-id="270e6-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="270e6-111">**True**= 设备已注册。</span><span class="sxs-lookup"><span data-stu-id="270e6-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="270e6-112">**False**= 设备未注册。</span><span class="sxs-lookup"><span data-stu-id="270e6-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="270e6-113">设备符合设备安全策略。</span><span class="sxs-lookup"><span data-stu-id="270e6-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="270e6-114">有关详细信息，请参阅 [创建设备安全策略](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="270e6-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="270e6-115"> \*isCompliant* 参数   的值为：</span><span class="sxs-lookup"><span data-stu-id="270e6-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="270e6-116">**True**  = 设备符合策略。</span><span class="sxs-lookup"><span data-stu-id="270e6-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="270e6-117">**False**  = 设备不符合策略。</span><span class="sxs-lookup"><span data-stu-id="270e6-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本移动性和安全性 PowerShell 参数":::

> [!NOTE]
> <span data-ttu-id="270e6-119">本文中的命令和脚本还返回有关由 Microsoft Intune 管理 [的任何设备的详细信息](https://www.microsoft.com/cloud-platform/microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="270e6-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="270e6-120">准备工作</span><span class="sxs-lookup"><span data-stu-id="270e6-120">Before you begin</span></span>

<span data-ttu-id="270e6-121">需要设置一些操作以运行本文中所述的命令和脚本。</span><span class="sxs-lookup"><span data-stu-id="270e6-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="270e6-122">步骤 1：下载并安装Azure Active Directory模块Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="270e6-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="270e6-123">有关这些步骤详细信息，请参阅 连接 [Microsoft 365 PowerShell。](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="270e6-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="270e6-124">转到"Microsoft Online Services Sign-In IT 专业人员 [RTWl"，](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)然后选择   "下载 **Microsoft Online Services登录助手"。**</span><span class="sxs-lookup"><span data-stu-id="270e6-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="270e6-125">安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，具体步骤如下：</span><span class="sxs-lookup"><span data-stu-id="270e6-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="270e6-126">打开管理员级 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="270e6-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="270e6-127">运行 `Install-Module MSOnline` 命令。</span><span class="sxs-lookup"><span data-stu-id="270e6-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="270e6-128">如果系统提示安装 NuGet 提供程序，请键入 Y，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="270e6-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="270e6-129">如果系统提示从 PSGallery 安装模块，请键入 Y，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="270e6-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="270e6-130">安装完成后，关闭 PowerShell 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="270e6-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="270e6-131">步骤 2：连接订阅Microsoft 365订阅</span><span class="sxs-lookup"><span data-stu-id="270e6-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="270e6-132">在Windows Azure Active Directory模块Windows PowerShell，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="270e6-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="270e6-133">在"Windows PowerShell凭据请求"对话框中，键入您的全局管理员帐户Microsoft 365用户名和密码，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="270e6-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="270e6-134">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="270e6-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="270e6-135">步骤 3：确保能够运行 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="270e6-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="270e6-136">如果已设置为运行 PowerShell 脚本，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="270e6-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="270e6-137">若要运行 Get-MsolUserDeviceComplianceStatus.ps1 脚本，需要启用 PowerShell 脚本的运行。</span><span class="sxs-lookup"><span data-stu-id="270e6-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="270e6-138">From your Windows Desktop， select **Start**， and then type Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270e6-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="270e6-139">右键单击"Windows PowerShell"，然后选择"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="270e6-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="270e6-140">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="270e6-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="270e6-141">当系统提示时，键入 Y，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="270e6-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="270e6-142">运行 Get-MsolDevice cmdlet 以显示组织中所有设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="270e6-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="270e6-143">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="270e6-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="270e6-144">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="270e6-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="270e6-145">有关更多示例，请参阅  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)。</span><span class="sxs-lookup"><span data-stu-id="270e6-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="270e6-146">运行脚本获取设备详细信息</span><span class="sxs-lookup"><span data-stu-id="270e6-146">Run a script to get device details</span></span>

<span data-ttu-id="270e6-147">首先，将脚本保存到计算机。</span><span class="sxs-lookup"><span data-stu-id="270e6-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="270e6-148">将以下文本复制并粘贴到记事本。</span><span class="sxs-lookup"><span data-stu-id="270e6-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="270e6-149">使用文件扩展Windows PowerShell文件，将其另存为脚本.ps1;例如，Get-MsolUserDeviceComplianceStatus.ps1。</span><span class="sxs-lookup"><span data-stu-id="270e6-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="270e6-150">运行脚本获取单个用户帐户的设备信息</span><span class="sxs-lookup"><span data-stu-id="270e6-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="270e6-151">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="270e6-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="270e6-152">转到保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="270e6-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="270e6-153">例如，如果已保存到 C：\PS-Scripts，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="270e6-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="270e6-154">运行以下命令以标识要获取其设备详细信息的用户。</span><span class="sxs-lookup"><span data-stu-id="270e6-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="270e6-155">此示例获取 bar@example.com。</span><span class="sxs-lookup"><span data-stu-id="270e6-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="270e6-156">运行以下命令以启动脚本。</span><span class="sxs-lookup"><span data-stu-id="270e6-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="270e6-157">信息作为 CSV 文件导出Windows桌面。</span><span class="sxs-lookup"><span data-stu-id="270e6-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="270e6-158">可以使用其他参数指定 CSV 的文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="270e6-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="270e6-159">运行脚本获取一组用户的设备信息</span><span class="sxs-lookup"><span data-stu-id="270e6-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="270e6-160">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="270e6-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="270e6-161">转到保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="270e6-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="270e6-162">例如，如果已保存到 C：\PS-Scripts，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="270e6-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="270e6-163">运行以下命令以标识要获取其设备详细信息的组。</span><span class="sxs-lookup"><span data-stu-id="270e6-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="270e6-164">此示例获取 FinanceStaff 组中用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="270e6-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="270e6-165">运行以下命令以启动脚本。</span><span class="sxs-lookup"><span data-stu-id="270e6-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="270e6-166">信息作为 CSV 文件导出Windows桌面。</span><span class="sxs-lookup"><span data-stu-id="270e6-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="270e6-167">可以使用其他参数指定 CSV 的文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="270e6-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="270e6-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="270e6-168">Related topics</span></span>

[<span data-ttu-id="270e6-169">Microsoft 连接已停用</span><span class="sxs-lookup"><span data-stu-id="270e6-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="270e6-170">基本移动性和安全性概览</span><span class="sxs-lookup"><span data-stu-id="270e6-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="270e6-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="270e6-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
