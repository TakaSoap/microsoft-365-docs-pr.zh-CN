---
title: 自行注册现有设备
description: 注册你可能已拥有的重复使用的设备，以便它们可以通过 Microsoft 托管桌面进行管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840511"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="93ec7-103">自行注册现有设备</span><span class="sxs-lookup"><span data-stu-id="93ec7-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="93ec7-104">本主题介绍重复使用已有设备的步骤，并在 Microsoft 托管桌面中注册这些设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="93ec7-105">如果你使用全新的设备，请改为按照 Microsoft 托管桌面中的"注册新设备" [中的](register-devices-self.md) 步骤操作。</span><span class="sxs-lookup"><span data-stu-id="93ec7-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="93ec7-106">合作伙伴的流程记录在合作伙伴 [注册设备的步骤中](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="93ec7-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="93ec7-107">Microsoft 托管桌面可以与全新的设备一起使用，或者你可以重复使用你可能已拥有的设备 (这将要求你将它们重新映像) 。</span><span class="sxs-lookup"><span data-stu-id="93ec7-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="93ec7-108">可以在 Microsoft Endpoint Manager 门户中向 Microsoft 托管桌面注册设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="93ec7-109">准备注册现有设备</span><span class="sxs-lookup"><span data-stu-id="93ec7-109">Prepare to register existing devices</span></span>


<span data-ttu-id="93ec7-110">若要注册现有设备，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="93ec7-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="93ec7-111">获取每个设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="93ec7-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="93ec7-112">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="93ec7-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="93ec7-113">[在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="93ec7-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="93ec7-114">仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="93ec7-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="93ec7-115">交付设备</span><span class="sxs-lookup"><span data-stu-id="93ec7-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="93ec7-116">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="93ec7-116">Obtain the hardware hash</span></span>

<span data-ttu-id="93ec7-117">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="93ec7-118">有四个选项用于从你已使用的设备获取此信息：</span><span class="sxs-lookup"><span data-stu-id="93ec7-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="93ec7-119">向 OEM 供应商询问 AutoPilot 注册文件，该文件将包含硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="93ec7-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="93ec7-120">在 [Microsoft Endpoint Configuration Manager 中收集信息](#microsoft-endpoint-configuration-manager)。</span><span class="sxs-lookup"><span data-stu-id="93ec7-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="93ec7-121">运行Windows PowerShell脚本（通过使用[Active Directory](#active-directory-powershell-script-method)或在每台设备上[](#manual-powershell-script-method)手动运行）并收集文件中的结果。</span><span class="sxs-lookup"><span data-stu-id="93ec7-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="93ec7-122">启动每台设备（但不完成 Windows 设置体验）并收集可移动闪存驱动器 [上的哈希](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="93ec7-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="93ec7-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93ec7-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="93ec7-124">可以使用 Microsoft Endpoint Configuration Manager 从要注册到 Microsoft 托管桌面的现有设备收集硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="93ec7-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93ec7-125">要获取此信息的任何设备都必须运行 Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="93ec7-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="93ec7-126">如果满足所有这些先决条件，就可以按照以下步骤收集信息：</span><span class="sxs-lookup"><span data-stu-id="93ec7-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="93ec7-127">在 Configuration Manager 控制台中，选择"监控 **"。**</span><span class="sxs-lookup"><span data-stu-id="93ec7-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="93ec7-128">在"监控"工作区中，展开 **"报告** "节点，展开 **"报告**"，然后选择 **"硬件 - 常规"** 节点。</span><span class="sxs-lookup"><span data-stu-id="93ec7-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="93ec7-129">运行报告 **、Windows Autopilot 设备信息** 并查看结果。</span><span class="sxs-lookup"><span data-stu-id="93ec7-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="93ec7-130">在报告查看器中 **，选择"** 导出"图标，然后选择 **"CSV** (逗号分隔的) 选项。</span><span class="sxs-lookup"><span data-stu-id="93ec7-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="93ec7-131">保存文件后，你需要仅筛选出计划向 Microsoft 托管桌面注册的设备的结果，并将数据上载到 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="93ec7-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="93ec7-132">打开 Microsoft Endpoint Manager 并导航到 **"设备**"菜单，然后查找"Microsoft 托管桌面"部分并选择 **"设备"。**</span><span class="sxs-lookup"><span data-stu-id="93ec7-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="93ec7-133">选择 **+ 注册设备**，这将打开一个飞入以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="93ec7-134">有关详细信息 [，请参阅使用管理门户注册](#register-devices-by-using-the-admin-portal) 设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="93ec7-135">Active Directory PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="93ec7-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="93ec7-136">在 Active Directory 环境中，可以使用 `Get-WindowsAutoPilotInfo` PowerShell cmdlet 通过 WinRM 从 Active Directory 组的设备远程收集信息。</span><span class="sxs-lookup"><span data-stu-id="93ec7-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="93ec7-137">您还可以使用该 cmdlet，并获取目录中包含的特定 `Get-AD Computer` 硬件型号名称的筛选结果。</span><span class="sxs-lookup"><span data-stu-id="93ec7-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="93ec7-138">在继续之前，首先确认这些先决条件，然后继续执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="93ec7-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="93ec7-139">WinRM 已启用。</span><span class="sxs-lookup"><span data-stu-id="93ec7-139">WinRM is enabled.</span></span>
- <span data-ttu-id="93ec7-140">要注册的设备在网络设备上处于活动状态 (也就是说，它们未断开连接或) 。</span><span class="sxs-lookup"><span data-stu-id="93ec7-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="93ec7-141">请确保你拥有一个域凭据参数，该参数具有在设备上远程执行的权限。</span><span class="sxs-lookup"><span data-stu-id="93ec7-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="93ec7-142">确保 Windows 防火墙允许访问 WMI。</span><span class="sxs-lookup"><span data-stu-id="93ec7-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="93ec7-143">为此，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="93ec7-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="93ec7-144">打开 **Windows Defender防火墙** 控制面板，然后选择"允许应用或功能Windows Defender **防火墙"。**</span><span class="sxs-lookup"><span data-stu-id="93ec7-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="93ec7-145">在 **列表中查找 Windows Management Instrumentation (WMI**) ，同时启用 **"** 专用"和"公用"，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="93ec7-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="93ec7-146">打开具有管理权限的 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="93ec7-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="93ec7-147">运行 *以下任* 一脚本：</span><span class="sxs-lookup"><span data-stu-id="93ec7-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="93ec7-148">访问设备可能有条目的任何目录。</span><span class="sxs-lookup"><span data-stu-id="93ec7-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="93ec7-149">从所有目录（包括 Windows  Server Active Directory 域服务和 Azure Active Directory）中删除每台设备的条目。</span><span class="sxs-lookup"><span data-stu-id="93ec7-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="93ec7-150">请注意，删除可能需要几个小时才能完全完成。</span><span class="sxs-lookup"><span data-stu-id="93ec7-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="93ec7-151">可能有设备条目的访问管理服务。</span><span class="sxs-lookup"><span data-stu-id="93ec7-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="93ec7-152">从所有管理服务（包括 Microsoft  Endpoint Configuration Manager、Microsoft Intune 和 Windows Autopilot）中删除每个设备的条目。</span><span class="sxs-lookup"><span data-stu-id="93ec7-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="93ec7-153">请注意，删除可能需要几个小时才能完全完成。</span><span class="sxs-lookup"><span data-stu-id="93ec7-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="93ec7-154">现在你可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="93ec7-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="93ec7-155">手动 PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="93ec7-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="93ec7-156">打开具有管理权限的 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="93ec7-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="93ec7-157">运行 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="93ec7-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="93ec7-158">运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="93ec7-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="93ec7-159">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="93ec7-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="93ec7-160">Flash 驱动器方法</span><span class="sxs-lookup"><span data-stu-id="93ec7-160">Flash drive method</span></span>

1. <span data-ttu-id="93ec7-161">在除要注册的设备外的其他设备上，插入 U 盘。</span><span class="sxs-lookup"><span data-stu-id="93ec7-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="93ec7-162">打开具有管理权限的 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="93ec7-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="93ec7-163">运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="93ec7-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="93ec7-164">打开要注册的设备，但不 *启动安装体验*。</span><span class="sxs-lookup"><span data-stu-id="93ec7-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="93ec7-165">如果意外启动设置体验，必须重置或重置设备映像。</span><span class="sxs-lookup"><span data-stu-id="93ec7-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="93ec7-166">插入 U 盘，然后按 Shift + F10。</span><span class="sxs-lookup"><span data-stu-id="93ec7-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="93ec7-167">打开具有管理权限的 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="93ec7-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="93ec7-168">运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="93ec7-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="93ec7-169">运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="93ec7-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="93ec7-170">删除 U 盘，然后通过运行关闭设备 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="93ec7-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="93ec7-171">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="93ec7-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="93ec7-172">在注册完设备之前，请勿再次打开要注册的设备的电源。</span><span class="sxs-lookup"><span data-stu-id="93ec7-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="93ec7-173">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="93ec7-173">Merge hash data</span></span>

<span data-ttu-id="93ec7-174">如果通过手动 PowerShell 或闪存驱动器方法收集硬件哈希数据，则现在需要将 CSV 文件中的数据合并到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="93ec7-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="93ec7-175">下面是一个示例 PowerShell 脚本，可轻松实现：</span><span class="sxs-lookup"><span data-stu-id="93ec7-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="93ec7-176">将哈希数据合并到一个 CSV 文件中后，现在可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="93ec7-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="93ec7-177">使用管理门户注册设备</span><span class="sxs-lookup"><span data-stu-id="93ec7-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="93ec7-178">在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)中， **选择** 左侧导航窗格中的设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="93ec7-179">查找菜单的"Microsoft 托管桌面"部分，然后选择 **"设备"。**</span><span class="sxs-lookup"><span data-stu-id="93ec7-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="93ec7-180">在 Microsoft 托管桌面设备工作区中，选择 **+ 注册** 设备，这将打开一个飞入以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="93ec7-181">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="93ec7-181">Follow these steps:</span></span>

1. <span data-ttu-id="93ec7-182">在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="93ec7-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="93ec7-183">选择 **"注册设备"。**</span><span class="sxs-lookup"><span data-stu-id="93ec7-183">Select **Register devices**.</span></span> <span data-ttu-id="93ec7-184">系统会将设备添加到"设备"边栏选项卡上的设备列表，标记为 **"注册挂起"。**</span><span class="sxs-lookup"><span data-stu-id="93ec7-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="93ec7-185">注册通常少于 10 分钟，并且当成功时，设备将显示为"为用户准备就绪"，这意味着它已准备好并等待用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="93ec7-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="93ec7-186">你可以监视主页上的设备注册进度。</span><span class="sxs-lookup"><span data-stu-id="93ec7-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="93ec7-187">报告可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="93ec7-187">Possible states reported there include:</span></span>

| <span data-ttu-id="93ec7-188">状态</span><span class="sxs-lookup"><span data-stu-id="93ec7-188">State</span></span> | <span data-ttu-id="93ec7-189">说明</span><span class="sxs-lookup"><span data-stu-id="93ec7-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="93ec7-190">注册挂起</span><span class="sxs-lookup"><span data-stu-id="93ec7-190">Registration Pending</span></span> | <span data-ttu-id="93ec7-191">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="93ec7-191">Registration is not done yet.</span></span> <span data-ttu-id="93ec7-192">请稍后再回来查看。</span><span class="sxs-lookup"><span data-stu-id="93ec7-192">Check back later.</span></span> |
| <span data-ttu-id="93ec7-193">注册失败</span><span class="sxs-lookup"><span data-stu-id="93ec7-193">Registration failed</span></span> | <span data-ttu-id="93ec7-194">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="93ec7-194">Registration could not be completed.</span></span> <span data-ttu-id="93ec7-195">有关详细信息 [，请参阅设备注册](#troubleshooting-device-registration) 疑难解答。</span><span class="sxs-lookup"><span data-stu-id="93ec7-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="93ec7-196">为用户做好准备</span><span class="sxs-lookup"><span data-stu-id="93ec7-196">Ready for user</span></span> | <span data-ttu-id="93ec7-197">注册成功，设备现在已准备好传递给用户。</span><span class="sxs-lookup"><span data-stu-id="93ec7-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="93ec7-198">Microsoft 托管桌面将指导用户完成首次设置，因此无需执行任何进一步准备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="93ec7-199">活动文件</span><span class="sxs-lookup"><span data-stu-id="93ec7-199">Active</span></span> | <span data-ttu-id="93ec7-200">设备已传递到用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="93ec7-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="93ec7-201">这还指示他们定期使用设备。</span><span class="sxs-lookup"><span data-stu-id="93ec7-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="93ec7-202">非活动</span><span class="sxs-lookup"><span data-stu-id="93ec7-202">Inactive</span></span> | <span data-ttu-id="93ec7-203">设备已传递到用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="93ec7-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="93ec7-204">但是，他们最近 7 天内 (使用过) 。</span><span class="sxs-lookup"><span data-stu-id="93ec7-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="93ec7-205">设备注册疑难解答</span><span class="sxs-lookup"><span data-stu-id="93ec7-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="93ec7-206">错误消息</span><span class="sxs-lookup"><span data-stu-id="93ec7-206">Error message</span></span> | <span data-ttu-id="93ec7-207">详细信息</span><span class="sxs-lookup"><span data-stu-id="93ec7-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="93ec7-208">未找到设备</span><span class="sxs-lookup"><span data-stu-id="93ec7-208">Device not found</span></span> | <span data-ttu-id="93ec7-209">我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="93ec7-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="93ec7-210">与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="93ec7-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="93ec7-211">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="93ec7-211">Hardware hash not valid</span></span> | <span data-ttu-id="93ec7-212">你为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="93ec7-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="93ec7-213">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="93ec7-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="93ec7-214">设备已注册</span><span class="sxs-lookup"><span data-stu-id="93ec7-214">Device already registered</span></span> | <span data-ttu-id="93ec7-215">此设备已注册到组织。</span><span class="sxs-lookup"><span data-stu-id="93ec7-215">This device is already registered to your organization.</span></span> <span data-ttu-id="93ec7-216">无需执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="93ec7-216">No further action required.</span></span> |
| <span data-ttu-id="93ec7-217">由另一个组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="93ec7-217">Device claimed by another organization</span></span> | <span data-ttu-id="93ec7-218">此设备已被另一个组织声明。</span><span class="sxs-lookup"><span data-stu-id="93ec7-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="93ec7-219">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="93ec7-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="93ec7-220">意外错误</span><span class="sxs-lookup"><span data-stu-id="93ec7-220">Unexpected error</span></span> | <span data-ttu-id="93ec7-221">您的请求无法自动处理。</span><span class="sxs-lookup"><span data-stu-id="93ec7-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="93ec7-222">联系支持人员并提供请求 ID： <requestId></span><span class="sxs-lookup"><span data-stu-id="93ec7-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="93ec7-223">检查图像</span><span class="sxs-lookup"><span data-stu-id="93ec7-223">Check the image</span></span>

<span data-ttu-id="93ec7-224">如果你的设备来自 Microsoft 托管桌面合作伙伴供应商，则映像应该正确。</span><span class="sxs-lookup"><span data-stu-id="93ec7-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="93ec7-225">如果愿意，也欢迎您自行应用该图像。</span><span class="sxs-lookup"><span data-stu-id="93ec7-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="93ec7-226">To get started， contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="93ec7-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="93ec7-227">交付设备</span><span class="sxs-lookup"><span data-stu-id="93ec7-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93ec7-228">在将设备上交给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="93ec7-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="93ec7-229">如果应用了所有许可证，你可以让用户准备好[](get-started-devices.md)使用设备，然后你的用户可以启动设备并继续 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="93ec7-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









