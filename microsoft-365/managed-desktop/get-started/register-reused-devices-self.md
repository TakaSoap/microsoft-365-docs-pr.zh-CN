---
title: 自行注册现有设备
description: 注册你可能已拥有的重复使用的设备，以便它们可以通过 Microsoft 托管桌面进行管理
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445562"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="210f7-104">自行注册现有设备</span><span class="sxs-lookup"><span data-stu-id="210f7-104">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="210f7-105">本主题介绍重复使用已有设备的步骤，并在 Microsoft 托管桌面中注册这些设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-105">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="210f7-106">如果你使用全新的设备，请改为按照在 Microsoft 托管桌面中注册新 [设备中的步骤](register-devices-self.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="210f7-106">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="210f7-107">合作伙伴过程记录在合作伙伴 [注册设备的步骤中](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="210f7-107">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="210f7-108">Microsoft 托管桌面可以与全新的设备一起工作，或者你可以重复使用你可能已有的设备 (这将要求你重新映像它们) 。</span><span class="sxs-lookup"><span data-stu-id="210f7-108">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="210f7-109">可以在 Microsoft Endpoint Manager 门户中向 Microsoft 托管桌面注册设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-109">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="210f7-110">准备注册现有设备</span><span class="sxs-lookup"><span data-stu-id="210f7-110">Prepare to register existing devices</span></span>


<span data-ttu-id="210f7-111">若要注册现有设备，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="210f7-111">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="210f7-112">获取每台设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="210f7-112">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="210f7-113">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="210f7-113">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="210f7-114">[在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="210f7-114">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="210f7-115">仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="210f7-115">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="210f7-116">交付设备</span><span class="sxs-lookup"><span data-stu-id="210f7-116">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="210f7-117">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="210f7-117">Obtain the hardware hash</span></span>

<span data-ttu-id="210f7-118">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-118">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="210f7-119">有四个选项用于从你已在使用的设备获取此信息：</span><span class="sxs-lookup"><span data-stu-id="210f7-119">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="210f7-120">请你的 OEM 供应商提供 AutoPilot 注册文件，该文件将包含硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="210f7-120">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="210f7-121">在 [Microsoft Endpoint Configuration Manager 中收集信息](#microsoft-endpoint-configuration-manager)。</span><span class="sxs-lookup"><span data-stu-id="210f7-121">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="210f7-122">运行Windows PowerShell脚本（通过使用[Active Directory](#active-directory-powershell-script-method)或在每台设备上[](#manual-powershell-script-method)手动运行）并收集文件中的结果。</span><span class="sxs-lookup"><span data-stu-id="210f7-122">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="210f7-123">启动每台设备（但不完成 Windows 设置体验）并收集可移动闪存 [驱动器上的哈希](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="210f7-123">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="210f7-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="210f7-124">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="210f7-125">可以使用 Microsoft Endpoint Configuration Manager 从要注册到 Microsoft 托管桌面的现有设备收集硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="210f7-125">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="210f7-126">要获取此信息的任何设备都必须运行 Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="210f7-126">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="210f7-127">如果满足所有这些先决条件，就可以按照以下步骤收集信息：</span><span class="sxs-lookup"><span data-stu-id="210f7-127">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="210f7-128">在 Configuration Manager 控制台中，选择"监视 **"。**</span><span class="sxs-lookup"><span data-stu-id="210f7-128">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="210f7-129">在"监控"工作区中，展开" **报告"** 节点，展开" **报告**"，然后选择" **硬件 - 常规"** 节点。</span><span class="sxs-lookup"><span data-stu-id="210f7-129">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="210f7-130">运行报告 **、Windows Autopilot 设备信息**，并查看结果。</span><span class="sxs-lookup"><span data-stu-id="210f7-130">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="210f7-131">在报告查看器中， **选择"导出** "图标，然后选择"CSV (**逗号分隔**) 选项。</span><span class="sxs-lookup"><span data-stu-id="210f7-131">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="210f7-132">保存文件后，你需要仅筛选结果到计划向 Microsoft 托管桌面注册的设备，并将数据上载到 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="210f7-132">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="210f7-133">打开 Microsoft Endpoint Manager 并导航到 **"设备**"菜单，然后查找"Microsoft 托管桌面"部分并选择 **"设备"。**</span><span class="sxs-lookup"><span data-stu-id="210f7-133">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="210f7-134">选择 **+ 注册设备**，这将打开一个飞入以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-134">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="210f7-135">有关详细信息 [，请参阅使用管理门户注册](#register-devices-by-using-the-admin-portal) 设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-135">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="210f7-136">Active Directory PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="210f7-136">Active Directory PowerShell script method</span></span>

<span data-ttu-id="210f7-137">在 Active Directory 环境中，可以使用 `Get-WindowsAutoPilotInfo` PowerShell cmdlet 通过 WinRM 远程收集 Active Directory 组中设备的信息。</span><span class="sxs-lookup"><span data-stu-id="210f7-137">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="210f7-138">您还可以使用 cmdlet 并获取目录中包含的特定 `Get-AD Computer` 硬件型号名称的筛选结果。</span><span class="sxs-lookup"><span data-stu-id="210f7-138">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="210f7-139">在继续之前，首先确认这些先决条件，然后继续执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="210f7-139">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="210f7-140">WinRM 已启用。</span><span class="sxs-lookup"><span data-stu-id="210f7-140">WinRM is enabled.</span></span>
- <span data-ttu-id="210f7-141">你想要注册的设备在网络设备上处于活动状态 (也就是说，它们未断开连接或) 。</span><span class="sxs-lookup"><span data-stu-id="210f7-141">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="210f7-142">确保你有一个域凭据参数，该参数有权在设备上远程执行。</span><span class="sxs-lookup"><span data-stu-id="210f7-142">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="210f7-143">确保 Windows 防火墙允许访问 WMI。</span><span class="sxs-lookup"><span data-stu-id="210f7-143">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="210f7-144">为此，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="210f7-144">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="210f7-145">打开 **"Windows Defender防火墙**"控制面板，然后选择"允许应用或功能通过Windows Defender **防火墙"。**</span><span class="sxs-lookup"><span data-stu-id="210f7-145">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="210f7-146">在列表中查找 Windows Management Instrumentation (**WMI**) ，同时启用 **"** 专用"和"公用"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="210f7-146">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="210f7-147">使用管理权限打开 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="210f7-147">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="210f7-148">运行 *以下任* 一脚本：</span><span class="sxs-lookup"><span data-stu-id="210f7-148">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="210f7-149">访问可能有设备条目的任何目录。</span><span class="sxs-lookup"><span data-stu-id="210f7-149">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="210f7-150">从所有目录（包括 Windows  Server Active Directory 域服务和 Azure Active Directory）中删除每台设备的条目。</span><span class="sxs-lookup"><span data-stu-id="210f7-150">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="210f7-151">请注意，删除可能需要几个小时才能完全完成。</span><span class="sxs-lookup"><span data-stu-id="210f7-151">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="210f7-152">访问管理服务，其中可能有设备条目。</span><span class="sxs-lookup"><span data-stu-id="210f7-152">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="210f7-153">从所有管理服务（包括 Microsoft  Endpoint Configuration Manager、Microsoft Intune 和 Windows Autopilot）中删除每个设备的条目。</span><span class="sxs-lookup"><span data-stu-id="210f7-153">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="210f7-154">请注意，删除可能需要几个小时才能完全完成。</span><span class="sxs-lookup"><span data-stu-id="210f7-154">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="210f7-155">现在，你可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="210f7-155">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="210f7-156">手动 PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="210f7-156">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="210f7-157">使用管理权限打开 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="210f7-157">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="210f7-158">运行 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="210f7-158">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="210f7-159">运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="210f7-159">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="210f7-160">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="210f7-160">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="210f7-161">Flash drive 方法</span><span class="sxs-lookup"><span data-stu-id="210f7-161">Flash drive method</span></span>

1. <span data-ttu-id="210f7-162">在注册设备外的其他设备上，插入 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="210f7-162">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="210f7-163">使用管理权限打开 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="210f7-163">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="210f7-164">运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="210f7-164">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="210f7-165">打开你要注册的设备， *但不启动设置体验*。</span><span class="sxs-lookup"><span data-stu-id="210f7-165">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="210f7-166">如果意外启动设置体验，必须重置或重置设备映像。</span><span class="sxs-lookup"><span data-stu-id="210f7-166">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="210f7-167">插入 USB 驱动器，然后按 Shift + F10。</span><span class="sxs-lookup"><span data-stu-id="210f7-167">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="210f7-168">使用管理权限打开 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="210f7-168">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="210f7-169">运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="210f7-169">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="210f7-170">运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="210f7-170">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="210f7-171">删除 USB 驱动器，然后通过运行来关闭设备 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="210f7-171">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="210f7-172">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="210f7-172">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="210f7-173">完成注册之前，请勿再次打开要注册的设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-173">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="210f7-174">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="210f7-174">Merge hash data</span></span>

<span data-ttu-id="210f7-175">如果你通过手动 PowerShell 或闪存驱动器方法收集了硬件哈希数据，你现在需要将 CSV 文件中的数据合并到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="210f7-175">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="210f7-176">下面是一个简单易行的示例 PowerShell 脚本：</span><span class="sxs-lookup"><span data-stu-id="210f7-176">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="210f7-177">将哈希数据合并到一个 CSV 文件中后，现在可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="210f7-177">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="210f7-178">使用管理门户注册设备</span><span class="sxs-lookup"><span data-stu-id="210f7-178">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="210f7-179">在[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)中，选择左侧导航窗格中的"设备"。 </span><span class="sxs-lookup"><span data-stu-id="210f7-179">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="210f7-180">查找菜单的"Microsoft 托管桌面"部分，然后选择"**设备"。**</span><span class="sxs-lookup"><span data-stu-id="210f7-180">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="210f7-181">在 Microsoft 托管桌面设备工作区中，选择 **+ 注册设备**，这将打开一个飞入以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-181">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="210f7-182">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="210f7-182">Follow these steps:</span></span>

1. <span data-ttu-id="210f7-183">在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="210f7-183">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="210f7-184">选择 **注册设备**。</span><span class="sxs-lookup"><span data-stu-id="210f7-184">Select **Register devices**.</span></span> <span data-ttu-id="210f7-185">系统将设备添加到设备边栏选项卡上的设备列表，标记为 **注册挂起**。 </span><span class="sxs-lookup"><span data-stu-id="210f7-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="210f7-186">注册通常少于 10 分钟，并且成功后，设备将显示为"为用户准备就绪"，这意味着它已准备好并等待用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="210f7-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="210f7-187">你可以监视主页上的设备注册进度。</span><span class="sxs-lookup"><span data-stu-id="210f7-187">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="210f7-188">其中报告的可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="210f7-188">Possible states reported there include:</span></span>

| <span data-ttu-id="210f7-189">状态</span><span class="sxs-lookup"><span data-stu-id="210f7-189">State</span></span> | <span data-ttu-id="210f7-190">说明</span><span class="sxs-lookup"><span data-stu-id="210f7-190">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="210f7-191">Registration Pending</span><span class="sxs-lookup"><span data-stu-id="210f7-191">Registration Pending</span></span> | <span data-ttu-id="210f7-192">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="210f7-192">Registration is not done yet.</span></span> <span data-ttu-id="210f7-193">请稍后再查看。</span><span class="sxs-lookup"><span data-stu-id="210f7-193">Check back later.</span></span> |
| <span data-ttu-id="210f7-194">注册失败</span><span class="sxs-lookup"><span data-stu-id="210f7-194">Registration failed</span></span> | <span data-ttu-id="210f7-195">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="210f7-195">Registration could not be completed.</span></span> <span data-ttu-id="210f7-196">有关详细信息 [，请参阅设备](#troubleshooting-device-registration) 注册疑难解答。</span><span class="sxs-lookup"><span data-stu-id="210f7-196">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="210f7-197">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="210f7-197">Ready for user</span></span> | <span data-ttu-id="210f7-198">注册成功，设备现在已准备好传递给用户。</span><span class="sxs-lookup"><span data-stu-id="210f7-198">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="210f7-199">Microsoft 托管桌面将指导用户完成首次设置，因此无需执行任何进一步准备。</span><span class="sxs-lookup"><span data-stu-id="210f7-199">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="210f7-200">活动</span><span class="sxs-lookup"><span data-stu-id="210f7-200">Active</span></span> | <span data-ttu-id="210f7-201">设备已传递给用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="210f7-201">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="210f7-202">这还指示他们定期使用设备。</span><span class="sxs-lookup"><span data-stu-id="210f7-202">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="210f7-203">非活动</span><span class="sxs-lookup"><span data-stu-id="210f7-203">Inactive</span></span> | <span data-ttu-id="210f7-204">设备已传递给用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="210f7-204">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="210f7-205">但是，他们在最近 7 天内 (使用过该设备) 。</span><span class="sxs-lookup"><span data-stu-id="210f7-205">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="210f7-206">设备注册疑难解答</span><span class="sxs-lookup"><span data-stu-id="210f7-206">Troubleshooting device registration</span></span>

| <span data-ttu-id="210f7-207">错误消息</span><span class="sxs-lookup"><span data-stu-id="210f7-207">Error message</span></span> | <span data-ttu-id="210f7-208">详细信息</span><span class="sxs-lookup"><span data-stu-id="210f7-208">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="210f7-209">未找到设备</span><span class="sxs-lookup"><span data-stu-id="210f7-209">Device not found</span></span> | <span data-ttu-id="210f7-210">我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="210f7-210">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="210f7-211">与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="210f7-211">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="210f7-212">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="210f7-212">Hardware hash not valid</span></span> | <span data-ttu-id="210f7-213">你为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="210f7-213">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="210f7-214">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="210f7-214">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="210f7-215">设备已注册</span><span class="sxs-lookup"><span data-stu-id="210f7-215">Device already registered</span></span> | <span data-ttu-id="210f7-216">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="210f7-216">This device is already registered to your organization.</span></span> <span data-ttu-id="210f7-217">无需执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="210f7-217">No further action required.</span></span> |
| <span data-ttu-id="210f7-218">由另一个组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="210f7-218">Device claimed by another organization</span></span> | <span data-ttu-id="210f7-219">此设备已被另一个组织声明。</span><span class="sxs-lookup"><span data-stu-id="210f7-219">This device has already been claimed by another organization.</span></span> <span data-ttu-id="210f7-220">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="210f7-220">Check with your device supplier.</span></span> |
| <span data-ttu-id="210f7-221">意外错误</span><span class="sxs-lookup"><span data-stu-id="210f7-221">Unexpected error</span></span> | <span data-ttu-id="210f7-222">您的请求无法自动处理。</span><span class="sxs-lookup"><span data-stu-id="210f7-222">Your request could not be automatically processed.</span></span> <span data-ttu-id="210f7-223">联系支持人员并提供请求 ID： <requestId></span><span class="sxs-lookup"><span data-stu-id="210f7-223">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="210f7-224">检查图像</span><span class="sxs-lookup"><span data-stu-id="210f7-224">Check the image</span></span>

<span data-ttu-id="210f7-225">如果你的设备来自 Microsoft 托管桌面合作伙伴供应商，则映像应该正确。</span><span class="sxs-lookup"><span data-stu-id="210f7-225">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="210f7-226">如果愿意，也欢迎您自行应用该图像。</span><span class="sxs-lookup"><span data-stu-id="210f7-226">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="210f7-227">To get started， contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="210f7-227">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="210f7-228">交付设备</span><span class="sxs-lookup"><span data-stu-id="210f7-228">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="210f7-229">在将设备交还给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="210f7-229">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="210f7-230">如果应用所有许可证，你可以让用户准备好使用[](get-started-devices.md)设备，然后你的用户可以启动设备并继续 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="210f7-230">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









