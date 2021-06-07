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
ms.openlocfilehash: 7cb2369c9a31210f26db12b0453e7a4228e1cccc
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782437"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="44d32-103">获取有关基本移动性和安全性托管设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="44d32-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="44d32-104">本文演示如何使用 Windows PowerShell获取有关您为基本移动性和安全性设置的组织中设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="44d32-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="44d32-105">以下是可供你使用的设备详细信息的细目。</span><span class="sxs-lookup"><span data-stu-id="44d32-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="44d32-106">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="44d32-106">**Detail**</span></span>|<span data-ttu-id="44d32-107">**在 PowerShell 中查找什么**</span><span class="sxs-lookup"><span data-stu-id="44d32-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="44d32-108">设备已注册基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="44d32-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="44d32-109">有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="44d32-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="44d32-110"> \*isManaged 参数*   的值为：</span><span class="sxs-lookup"><span data-stu-id="44d32-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="44d32-111">**True**= 设备已注册。</span><span class="sxs-lookup"><span data-stu-id="44d32-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="44d32-112">**False**= 设备未注册。</span><span class="sxs-lookup"><span data-stu-id="44d32-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="44d32-113">设备符合设备安全策略。</span><span class="sxs-lookup"><span data-stu-id="44d32-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="44d32-114">有关详细信息，请参阅 [创建设备安全策略](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="44d32-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="44d32-115"> \*isCompliant* 参数   的值为：</span><span class="sxs-lookup"><span data-stu-id="44d32-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="44d32-116">**True**  = 设备符合策略。</span><span class="sxs-lookup"><span data-stu-id="44d32-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="44d32-117">**False**  = 设备不符合策略。</span><span class="sxs-lookup"><span data-stu-id="44d32-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本移动性和安全性 PowerShell 参数":::

>[!NOTE]
><span data-ttu-id="44d32-119">本文中的命令和脚本还返回有关由 Microsoft Intune 管理 [的任何设备的详细信息](https://www.microsoft.com/cloud-platform/microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="44d32-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="44d32-120">准备工作</span><span class="sxs-lookup"><span data-stu-id="44d32-120">Before you begin</span></span>

<span data-ttu-id="44d32-121">需要设置一些操作以运行本文中所述的命令和脚本。</span><span class="sxs-lookup"><span data-stu-id="44d32-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="44d32-122">步骤 1：下载并安装Azure Active Directory模块Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44d32-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="44d32-123">有关这些步骤详细信息，请参阅 连接 [Microsoft 365 PowerShell。](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="44d32-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="44d32-124">转到"Microsoft Online Services Sign-In IT 专业人员 [RTWl"，](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)然后选择   "下载 **Microsoft Online Services登录助手"。**</span><span class="sxs-lookup"><span data-stu-id="44d32-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="44d32-125">安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，具体步骤如下：</span><span class="sxs-lookup"><span data-stu-id="44d32-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="44d32-126">打开管理员级 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="44d32-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="44d32-127">运行 Install-Module MSOnline 命令。</span><span class="sxs-lookup"><span data-stu-id="44d32-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="44d32-128">如果系统提示安装 NuGet 提供程序，请键入 Y，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="44d32-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="44d32-129">如果系统提示从 PSGallery 安装模块，请键入 Y，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="44d32-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="44d32-130">安装完成后，关闭 PowerShell 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="44d32-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="44d32-131">步骤 2：连接订阅Microsoft 365订阅</span><span class="sxs-lookup"><span data-stu-id="44d32-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="44d32-132">在Windows Azure Active Directory模块Windows PowerShell，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="44d32-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="44d32-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="44d32-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="44d32-134">在"Windows PowerShell凭据请求"对话框中，键入您的全局管理员帐户Microsoft 365用户名和密码，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="44d32-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="44d32-135">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="44d32-135">Run the following command.</span></span>

    <span data-ttu-id="44d32-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="44d32-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="44d32-137">步骤 3：确保能够运行 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="44d32-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="44d32-138">如果已设置为运行 PowerShell 脚本，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="44d32-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="44d32-139">若要运行 Get-MsolUserDeviceComplianceStatus.ps1 脚本，需要启用 PowerShell 脚本的运行。</span><span class="sxs-lookup"><span data-stu-id="44d32-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="44d32-140">From your Windows Desktop， select **Start**， and then type Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44d32-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="44d32-141">右键单击"Windows PowerShell"，然后选择"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="44d32-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="44d32-142">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="44d32-142">Run the following command.</span></span>

    <span data-ttu-id="44d32-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="44d32-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="44d32-144">当系统提示时，键入 Y，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="44d32-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="44d32-145">**运行 Get-MsolDevice cmdlet 以显示组织中所有设备的详细信息**</span><span class="sxs-lookup"><span data-stu-id="44d32-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="44d32-146">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="44d32-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="44d32-147">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="44d32-147">Run the following command.</span></span>

    <span data-ttu-id="44d32-148">Get-MsolDevice -All -ReturnRegisteredOwners |Where-Object {$_.RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="44d32-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="44d32-149">有关更多示例，请参阅  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)。</span><span class="sxs-lookup"><span data-stu-id="44d32-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="44d32-150">运行脚本获取设备详细信息</span><span class="sxs-lookup"><span data-stu-id="44d32-150">Run a script to get device details</span></span>

<span data-ttu-id="44d32-151">首先，将脚本保存到计算机。</span><span class="sxs-lookup"><span data-stu-id="44d32-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="44d32-152">将以下文本复制并粘贴到记事本。</span><span class="sxs-lookup"><span data-stu-id="44d32-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="44d32-153">param (</span><span class="sxs-lookup"><span data-stu-id="44d32-153">param (</span></span>

3.  <span data-ttu-id="44d32-154">[PSObject[]]$users = @ () ，</span><span class="sxs-lookup"><span data-stu-id="44d32-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="44d32-155">[Switch]$export，</span><span class="sxs-lookup"><span data-stu-id="44d32-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="44d32-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv"，</span><span class="sxs-lookup"><span data-stu-id="44d32-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="44d32-157">[String]$exportPath = [Environment]：：GetFolderPath ("Desktop") </span><span class="sxs-lookup"><span data-stu-id="44d32-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="44d32-158">)</span><span class="sxs-lookup"><span data-stu-id="44d32-158">)</span></span>

9.  <span data-ttu-id="44d32-159">[System.Collections.IDictionary]$script：schema = @{</span><span class="sxs-lookup"><span data-stu-id="44d32-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="44d32-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="44d32-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="44d32-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="44d32-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="44d32-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="44d32-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="44d32-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="44d32-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="44d32-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="44d32-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="44d32-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="44d32-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="44d32-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="44d32-172">}</span><span class="sxs-lookup"><span data-stu-id="44d32-172">}</span></span>
    

25.  <span data-ttu-id="44d32-173">函数 createResultObject</span><span class="sxs-lookup"><span data-stu-id="44d32-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="44d32-174">{</span><span class="sxs-lookup"><span data-stu-id="44d32-174">{</span></span>
    

28.  <span data-ttu-id="44d32-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script：schema</span><span class="sxs-lookup"><span data-stu-id="44d32-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="44d32-176">返回$resultObject</span><span class="sxs-lookup"><span data-stu-id="44d32-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="44d32-177">}</span><span class="sxs-lookup"><span data-stu-id="44d32-177">}</span></span>
    

33.  <span data-ttu-id="44d32-178">如果 ($users。Count -eq 0) </span><span class="sxs-lookup"><span data-stu-id="44d32-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="44d32-179">{</span><span class="sxs-lookup"><span data-stu-id="44d32-179">{</span></span>
    

35.  <span data-ttu-id="44d32-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="44d32-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="44d32-181">}</span><span class="sxs-lookup"><span data-stu-id="44d32-181">}</span></span>
    

38.  <span data-ttu-id="44d32-182">[PSObject[]]$result = foreach ($u in $users) </span><span class="sxs-lookup"><span data-stu-id="44d32-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="44d32-183">{</span><span class="sxs-lookup"><span data-stu-id="44d32-183">{</span></span>
    

41.  <span data-ttu-id="44d32-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="44d32-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="44d32-185">foreach ($d in $devices) </span><span class="sxs-lookup"><span data-stu-id="44d32-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="44d32-186">{</span><span class="sxs-lookup"><span data-stu-id="44d32-186">{</span></span>
    

44.  <span data-ttu-id="44d32-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="44d32-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="44d32-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="44d32-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="44d32-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="44d32-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="44d32-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="44d32-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="44d32-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="44d32-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="44d32-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="44d32-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="44d32-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="44d32-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="44d32-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="44d32-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="44d32-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="44d32-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="44d32-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="44d32-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="44d32-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="44d32-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="44d32-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="44d32-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="44d32-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="44d32-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="44d32-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="44d32-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="44d32-201">}</span><span class="sxs-lookup"><span data-stu-id="44d32-201">}</span></span>
    

61.  <span data-ttu-id="44d32-202">}</span><span class="sxs-lookup"><span data-stu-id="44d32-202">}</span></span>
    

63.  <span data-ttu-id="44d32-203">如果 ($export) </span><span class="sxs-lookup"><span data-stu-id="44d32-203">If ($export)</span></span>
    

64.  <span data-ttu-id="44d32-204">{</span><span class="sxs-lookup"><span data-stu-id="44d32-204">{</span></span>
    

65.  <span data-ttu-id="44d32-205">$result |Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="44d32-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="44d32-206">}</span><span class="sxs-lookup"><span data-stu-id="44d32-206">}</span></span>
    

67.  <span data-ttu-id="44d32-207">Else</span><span class="sxs-lookup"><span data-stu-id="44d32-207">Else</span></span>
    

68.  <span data-ttu-id="44d32-208">{</span><span class="sxs-lookup"><span data-stu-id="44d32-208">{</span></span>
    

69.  <span data-ttu-id="44d32-209">$result</span><span class="sxs-lookup"><span data-stu-id="44d32-209">$result</span></span>
    

70.  <span data-ttu-id="44d32-210">}</span><span class="sxs-lookup"><span data-stu-id="44d32-210">}</span></span>
    

71.  <span data-ttu-id="44d32-211">使用文件扩展Windows PowerShell文件，将其另存为脚本.ps1;例如，Get-MsolUserDeviceComplianceStatus.ps1。</span><span class="sxs-lookup"><span data-stu-id="44d32-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="44d32-212">运行脚本获取单个用户帐户的设备信息</span><span class="sxs-lookup"><span data-stu-id="44d32-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="44d32-213">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="44d32-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="44d32-214">转到保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="44d32-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="44d32-215">例如，如果已保存到 C：\PS-Scripts，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="44d32-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="44d32-216">cd C：\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="44d32-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="44d32-217">运行以下命令以标识要获取其设备详细信息的用户。</span><span class="sxs-lookup"><span data-stu-id="44d32-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="44d32-218">此示例获取 bar@example.com。</span><span class="sxs-lookup"><span data-stu-id="44d32-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="44d32-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="44d32-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="44d32-220">运行以下命令以启动脚本。</span><span class="sxs-lookup"><span data-stu-id="44d32-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="44d32-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="44d32-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="44d32-222">信息作为 CSV 文件导出Windows桌面。</span><span class="sxs-lookup"><span data-stu-id="44d32-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="44d32-223">可以使用其他参数指定 CSV 的文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="44d32-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="44d32-224">运行脚本获取一组用户的设备信息</span><span class="sxs-lookup"><span data-stu-id="44d32-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="44d32-225">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="44d32-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="44d32-226">转到保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="44d32-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="44d32-227">例如，如果已保存到 C：\PS-Scripts，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="44d32-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="44d32-228">cd C：\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="44d32-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="44d32-229">运行以下命令以标识要获取其设备详细信息的组。</span><span class="sxs-lookup"><span data-stu-id="44d32-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="44d32-230">此示例获取 FinanceStaff 组中用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="44d32-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="44d32-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" |% { Get-MsolUser -ObjectId $_。ObjectId }</span><span class="sxs-lookup"><span data-stu-id="44d32-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="44d32-232">运行以下命令以启动脚本。</span><span class="sxs-lookup"><span data-stu-id="44d32-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="44d32-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="44d32-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="44d32-234">信息作为 CSV 文件导出Windows桌面。</span><span class="sxs-lookup"><span data-stu-id="44d32-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="44d32-235">可以使用其他参数指定 CSV 的文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="44d32-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="44d32-236">相关主题</span><span class="sxs-lookup"><span data-stu-id="44d32-236">Related topics</span></span>

[<span data-ttu-id="44d32-237">Microsoft 连接已停用</span><span class="sxs-lookup"><span data-stu-id="44d32-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="44d32-238">基本移动性和安全性概览</span><span class="sxs-lookup"><span data-stu-id="44d32-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="44d32-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="44d32-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)