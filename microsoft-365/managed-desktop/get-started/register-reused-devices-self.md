---
title: 自行注册现有设备
description: 注册重新使用的设备你可能已经有了你自己的设备，以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1ad83dbf323e431e1694b408e09e581ff5b76348
ms.sourcegitcommit: e9f32675061cd1cf4a3e2dada393e10d7c552efe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48279557"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="1afe3-103">自行注册现有设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="1afe3-104">本主题介绍了重新使用已拥有的设备的步骤，并将其注册到 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="1afe3-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1afe3-105">如果您正在使用全新的设备，请按照在 [Microsoft 托管桌面中注册新设备](register-devices-self.md) 中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="1afe3-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="1afe3-106">合作伙伴的过程记录在 [合作伙伴注册设备的步骤](register-devices-partner.md)中。</span><span class="sxs-lookup"><span data-stu-id="1afe3-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="1afe3-107">Microsoft 托管桌面可以与全新设备配合使用，也可以重新使用已有的设备 (这将需要您将其重新映像) 。</span><span class="sxs-lookup"><span data-stu-id="1afe3-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="1afe3-108">你可以在 Microsoft 终结点管理器门户中使用 Microsoft 托管桌面注册设备。</span><span class="sxs-lookup"><span data-stu-id="1afe3-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="1afe3-109">准备注册现有设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-109">Prepare to register existing devices</span></span>


<span data-ttu-id="1afe3-110">若要注册现有设备，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1afe3-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="1afe3-111">获取每个设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="1afe3-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="1afe3-112">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="1afe3-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="1afe3-113">[在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="1afe3-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="1afe3-114">请仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="1afe3-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="1afe3-115">传递设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="1afe3-116">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="1afe3-116">Obtain the hardware hash</span></span>

<span data-ttu-id="1afe3-117">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每个设备。</span><span class="sxs-lookup"><span data-stu-id="1afe3-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="1afe3-118">你可以通过四个选项从已在使用的设备中获取此信息：</span><span class="sxs-lookup"><span data-stu-id="1afe3-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="1afe3-119">向 OEM 提供商咨询 AutoPilot 注册文件，其中将包含硬件哈希值。</span><span class="sxs-lookup"><span data-stu-id="1afe3-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="1afe3-120">在 [Microsoft 终结点配置管理器](#microsoft-endpoint-configuration-manager)中收集信息。</span><span class="sxs-lookup"><span data-stu-id="1afe3-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="1afe3-121">在每台设备上使用 [Active Directory](#active-directory-powershell-script-method) 或 [手动](#manual-powershell-script-method) 运行 Windows PowerShell 脚本--并在文件中收集结果。</span><span class="sxs-lookup"><span data-stu-id="1afe3-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="1afe3-122">启动每个设备--但不完成 Windows 安装程序体验，并 [收集可移动闪存驱动器上的哈希值](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="1afe3-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="1afe3-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1afe3-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="1afe3-124">您可以使用 Microsoft 终结点配置管理器收集要使用 Microsoft 托管桌面注册的现有设备的硬件哈希值。</span><span class="sxs-lookup"><span data-stu-id="1afe3-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1afe3-125">要获取此信息的任何设备都必须运行 Windows 10 版本1703或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1afe3-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="1afe3-126">如果你已满足所有这些先决条件，则可以按照以下步骤收集信息：</span><span class="sxs-lookup"><span data-stu-id="1afe3-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="1afe3-127">在 Configuration Manager 控制台中，选择 " **监控**"。</span><span class="sxs-lookup"><span data-stu-id="1afe3-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="1afe3-128">在 "监控" 工作区中，展开 " **报告** " 节点，再展开 " **报告**"，然后选择 " **硬件"-"常规** " 节点。</span><span class="sxs-lookup"><span data-stu-id="1afe3-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="1afe3-129">运行报告、 **Windows Autopilot 设备信息**并查看结果。</span><span class="sxs-lookup"><span data-stu-id="1afe3-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="1afe3-130">在报表查看器中，选择 " **导出** " 图标，然后选择 \*\*CSV (逗号分隔的) \*\* 选项。</span><span class="sxs-lookup"><span data-stu-id="1afe3-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="1afe3-131">保存文件后，您需要筛选结果，使其仅包含计划注册 Microsoft 托管桌面的那些设备，并将数据上传到 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="1afe3-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="1afe3-132">打开 Microsoft 终结点管理器并导航到 " **设备** " 菜单，然后查找 "Microsoft 托管桌面" 部分，然后选择 " **设备**"。</span><span class="sxs-lookup"><span data-stu-id="1afe3-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="1afe3-133">选择 " **+ 注册设备** "，打开飞入的设备以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="1afe3-133">Select **+ Register devices** which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="1afe3-134">有关详细信息，请参阅 [注册设备（使用管理门户](#register-devices-by-using-the-admin-portal) ）。</span><span class="sxs-lookup"><span data-stu-id="1afe3-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="1afe3-135">Active Directory PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="1afe3-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="1afe3-136">在 Active Directory 环境中，您可以使用 `Get-WindowsAutoPilotInfo` PowerShell cmdlet 从 Active Directory 组中的设备远程收集信息，方法是使用 WinRM。</span><span class="sxs-lookup"><span data-stu-id="1afe3-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="1afe3-137">您还可以使用 `Get-AD Computer` cmdlet 并获取目录中包含的特定硬件模型名称的筛选结果。</span><span class="sxs-lookup"><span data-stu-id="1afe3-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="1afe3-138">为此，请首先确认这些先决条件，然后继续执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1afe3-138">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="1afe3-139">启用 WinRM。</span><span class="sxs-lookup"><span data-stu-id="1afe3-139">WinRM is enabled.</span></span>
- <span data-ttu-id="1afe3-140">您要注册的设备在网络 (上是活动的，它们不会断开连接或关闭) 。</span><span class="sxs-lookup"><span data-stu-id="1afe3-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="1afe3-141">请确保您有一个具有在设备上远程执行的权限的域凭据参数。</span><span class="sxs-lookup"><span data-stu-id="1afe3-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="1afe3-142">请确保 Windows 防火墙允许访问 WMI。</span><span class="sxs-lookup"><span data-stu-id="1afe3-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="1afe3-143">为此，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1afe3-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="1afe3-144">打开 **Windows Defender 防火墙** 控制面板，然后选择 " **允许通过 Windows defender 防火墙的应用程序或功能**"。</span><span class="sxs-lookup"><span data-stu-id="1afe3-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="1afe3-145">在列表中查找 \*\*Windows Management Instrumentation (WMI) \*\* ，启用 " **专用" 和 "公共**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1afe3-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="1afe3-146">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="1afe3-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="1afe3-147">运行以下 *任意一个* 脚本：</span><span class="sxs-lookup"><span data-stu-id="1afe3-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="1afe3-148">访问可能包含设备条目的任何目录。</span><span class="sxs-lookup"><span data-stu-id="1afe3-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="1afe3-149">从 *所有* 目录中删除每个设备的条目，包括 Windows Server Active Directory 域服务和 Azure Active directory。</span><span class="sxs-lookup"><span data-stu-id="1afe3-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="1afe3-150">请注意，此删除操作可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="1afe3-150">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="1afe3-151">可能包含设备条目的 Access management services。</span><span class="sxs-lookup"><span data-stu-id="1afe3-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="1afe3-152">从 *所有* 管理服务（包括 Microsoft 终结点配置管理器、microsoft Intune 和 Windows Autopilot）中删除每个设备的条目。</span><span class="sxs-lookup"><span data-stu-id="1afe3-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="1afe3-153">请注意，此删除操作可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="1afe3-153">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="1afe3-154">现在，你可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="1afe3-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="1afe3-155">手动 PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="1afe3-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="1afe3-156">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="1afe3-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="1afe3-157">以 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="1afe3-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="1afe3-158">以 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="1afe3-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="1afe3-159">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="1afe3-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="1afe3-160">闪存驱动器方法</span><span class="sxs-lookup"><span data-stu-id="1afe3-160">Flash drive method</span></span>

1. <span data-ttu-id="1afe3-161">在要注册的设备以外的其他设备上，插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="1afe3-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="1afe3-162">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="1afe3-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="1afe3-163">以 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="1afe3-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="1afe3-164">打开要注册的设备，但 *不要启动安装程序体验*。</span><span class="sxs-lookup"><span data-stu-id="1afe3-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="1afe3-165">如果您意外启动了设置体验，则必须重置或重新映像设备。</span><span class="sxs-lookup"><span data-stu-id="1afe3-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="1afe3-166">插入 u 盘，然后按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="1afe3-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="1afe3-167">打开具有管理权限的 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="1afe3-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="1afe3-168">以 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="1afe3-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="1afe3-169">以 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="1afe3-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="1afe3-170">删除 USB 驱动器，然后通过运行来关闭设备 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="1afe3-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="1afe3-171">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="1afe3-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="1afe3-172">在完成注册后，请不要再打开要注册的设备。</span><span class="sxs-lookup"><span data-stu-id="1afe3-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="1afe3-173">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="1afe3-173">Merge hash data</span></span>

<span data-ttu-id="1afe3-174">如果您通过手动 PowerShell 或闪存驱动器方法收集了硬件哈希数据，则您现在需要将 CSV 文件中的数据组合到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="1afe3-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="1afe3-175">下面是一个示例 PowerShell 脚本，可轻松实现此操作：</span><span class="sxs-lookup"><span data-stu-id="1afe3-175">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="1afe3-176">将哈希数据合并到一个 CSV 文件中，现在就可以继续 [注册设备了](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="1afe3-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="1afe3-177">使用管理门户注册设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="1afe3-178">在 [Microsoft 终结点管理器](https://endpoint.microsoft.com/)中，选择左侧导航窗格中的 " **设备** "。</span><span class="sxs-lookup"><span data-stu-id="1afe3-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="1afe3-179">查找菜单中的 "Microsoft 托管桌面" 部分，然后选择 " **设备**"。</span><span class="sxs-lookup"><span data-stu-id="1afe3-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="1afe3-180">在 "Microsoft 托管桌面设备" 工作区中，选择 " **注册设备** "，打开一个飞入的新设备。</span><span class="sxs-lookup"><span data-stu-id="1afe3-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices** which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="1afe3-181">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1afe3-181">Follow these steps:</span></span>

1. <span data-ttu-id="1afe3-182">在 " **文件上载**" 中，提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="1afe3-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="1afe3-183">选择 " **注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="1afe3-183">Select **Register devices**.</span></span> <span data-ttu-id="1afe3-184">系统会将设备添加到 **设备边栏**上的设备列表中，并标记为 " **注册挂起**"。</span><span class="sxs-lookup"><span data-stu-id="1afe3-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="1afe3-185">注册通常需要不到10分钟的时间，如果成功，设备将显示为 "就绪"，使其可供 **用户** 使用，并等待用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="1afe3-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="1afe3-186">您可以在主页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="1afe3-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="1afe3-187">可能报告的状态包括：</span><span class="sxs-lookup"><span data-stu-id="1afe3-187">Possible states reported there include:</span></span>

| <span data-ttu-id="1afe3-188">状态</span><span class="sxs-lookup"><span data-stu-id="1afe3-188">State</span></span> | <span data-ttu-id="1afe3-189">说明</span><span class="sxs-lookup"><span data-stu-id="1afe3-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="1afe3-190">注册挂起</span><span class="sxs-lookup"><span data-stu-id="1afe3-190">Registration Pending</span></span> | <span data-ttu-id="1afe3-191">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="1afe3-191">Registration is not done yet.</span></span> <span data-ttu-id="1afe3-192">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="1afe3-192">Check back later.</span></span> |
| <span data-ttu-id="1afe3-193">注册失败</span><span class="sxs-lookup"><span data-stu-id="1afe3-193">Registration failed</span></span> | <span data-ttu-id="1afe3-194">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="1afe3-194">Registration could not be completed.</span></span> <span data-ttu-id="1afe3-195">有关详细信息，请参阅 [设备注册故障排除](#troubleshooting-device-registration) 。</span><span class="sxs-lookup"><span data-stu-id="1afe3-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="1afe3-196">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="1afe3-196">Ready for user</span></span> | <span data-ttu-id="1afe3-197">注册成功，现在设备已准备好传递给用户。</span><span class="sxs-lookup"><span data-stu-id="1afe3-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="1afe3-198">Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="1afe3-198">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="1afe3-199">活动</span><span class="sxs-lookup"><span data-stu-id="1afe3-199">Active</span></span> | <span data-ttu-id="1afe3-200">设备已传递给用户，并且已向你的租户注册。</span><span class="sxs-lookup"><span data-stu-id="1afe3-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="1afe3-201">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="1afe3-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="1afe3-202">不再</span><span class="sxs-lookup"><span data-stu-id="1afe3-202">Inactive</span></span> | <span data-ttu-id="1afe3-203">设备已传递给用户，并且已向你的租户注册。</span><span class="sxs-lookup"><span data-stu-id="1afe3-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="1afe3-204">但是，他们在过去7天内未使用最近 (设备) 。</span><span class="sxs-lookup"><span data-stu-id="1afe3-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="1afe3-205">设备注册故障排除</span><span class="sxs-lookup"><span data-stu-id="1afe3-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="1afe3-206">错误消息</span><span class="sxs-lookup"><span data-stu-id="1afe3-206">Error message</span></span> | <span data-ttu-id="1afe3-207">详细信息</span><span class="sxs-lookup"><span data-stu-id="1afe3-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="1afe3-208">找不到设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-208">Device not found</span></span> | <span data-ttu-id="1afe3-209">无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="1afe3-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="1afe3-210">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="1afe3-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="1afe3-211">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="1afe3-211">Hardware hash not valid</span></span> | <span data-ttu-id="1afe3-212">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="1afe3-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="1afe3-213">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="1afe3-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="1afe3-214">已注册设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-214">Device already registered</span></span> | <span data-ttu-id="1afe3-215">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="1afe3-215">This device is already registered to your organization.</span></span> <span data-ttu-id="1afe3-216">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="1afe3-216">No further action required.</span></span> |
| <span data-ttu-id="1afe3-217">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-217">Device claimed by another organization</span></span> | <span data-ttu-id="1afe3-218">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="1afe3-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="1afe3-219">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="1afe3-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="1afe3-220">意外错误</span><span class="sxs-lookup"><span data-stu-id="1afe3-220">Unexpected error</span></span> | <span data-ttu-id="1afe3-221">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="1afe3-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="1afe3-222">联系支持人员并提供请求 ID： <requestId></span><span class="sxs-lookup"><span data-stu-id="1afe3-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="1afe3-223">检查图像</span><span class="sxs-lookup"><span data-stu-id="1afe3-223">Check the image</span></span>

<span data-ttu-id="1afe3-224">如果你的设备来自 Microsoft 托管桌面合作伙伴提供商，则该映像应正确。</span><span class="sxs-lookup"><span data-stu-id="1afe3-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="1afe3-225">如果你愿意，也可以在自己自己应用图像。</span><span class="sxs-lookup"><span data-stu-id="1afe3-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="1afe3-226">若要开始，请联系你正在使用的 Microsoft 代表，他们将为你提供应用此图像的位置和步骤。</span><span class="sxs-lookup"><span data-stu-id="1afe3-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="1afe3-227">传递设备</span><span class="sxs-lookup"><span data-stu-id="1afe3-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1afe3-228">在将设备交给用户之前，请确保已为该用户获取并应用了 [相应的许可证](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="1afe3-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="1afe3-229">如果应用了所有许可证，则可以 [让用户准备好使用设备](get-started-devices.md)，然后你的用户可以启动设备并继续执行 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="1afe3-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









