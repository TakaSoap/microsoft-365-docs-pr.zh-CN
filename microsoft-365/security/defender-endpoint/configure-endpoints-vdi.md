---
title: 载入非持久性虚拟桌面基础结构 (VDI) 设备。
description: 在 VDI (虚拟桌面基础结构) 包，以便它们可以载入到 Microsoft Defender ATP 服务。
keywords: 配置虚拟桌面基础结构 (VDI) 设备， vdi， 设备管理， 配置 Windows ATP 终结点， 为终结点终结点配置 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 167db9b5da841528e95f167b3af6a840b6c71eb4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165557"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="ae0df-104">载入非持久性虚拟桌面基础结构 (VDI) 设备。</span><span class="sxs-lookup"><span data-stu-id="ae0df-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ae0df-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ae0df-105">**Applies to:**</span></span>
- [<span data-ttu-id="ae0df-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ae0df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ae0df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae0df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="ae0df-108">虚拟桌面基础结构 (VDI) 设备</span><span class="sxs-lookup"><span data-stu-id="ae0df-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="ae0df-109">Windows 10、Windows Server 2019、Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="ae0df-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="ae0df-110">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ae0df-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ae0df-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ae0df-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="ae0df-112">载入非持久性虚拟桌面基础结构 (VDI) 设备。</span><span class="sxs-lookup"><span data-stu-id="ae0df-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="ae0df-113">Defender for Endpoint 支持非永久性 VDI 会话载入。</span><span class="sxs-lookup"><span data-stu-id="ae0df-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="ae0df-114">载入 VDIS 时可能存在相关挑战。</span><span class="sxs-lookup"><span data-stu-id="ae0df-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="ae0df-115">以下是此方案的典型挑战：</span><span class="sxs-lookup"><span data-stu-id="ae0df-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="ae0df-116">即时提前载入短期会话，这些会话在实际预配之前必须载入到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="ae0df-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="ae0df-117">设备名称通常重新用于新会话。</span><span class="sxs-lookup"><span data-stu-id="ae0df-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="ae0df-118">VDI 设备可以在 Defender for Endpoint 门户中显示为：</span><span class="sxs-lookup"><span data-stu-id="ae0df-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="ae0df-119">每台设备的单个条目。</span><span class="sxs-lookup"><span data-stu-id="ae0df-119">Single entry for each device.</span></span>  
<span data-ttu-id="ae0df-120">请注意，在这种情况下，创建会话时必须配置相同的设备名称，例如使用无人参与应答文件。</span><span class="sxs-lookup"><span data-stu-id="ae0df-120">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="ae0df-121">每个设备有多个条目 - 每个会话一个条目。</span><span class="sxs-lookup"><span data-stu-id="ae0df-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="ae0df-122">以下步骤将指导你完成载入 VDI 设备，并重点介绍单项和多条目的步骤。</span><span class="sxs-lookup"><span data-stu-id="ae0df-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="ae0df-123">对于资源配置较低的环境，VDI 启动过程可能会减慢 Defender for Endpoint 传感器载入的速度。</span><span class="sxs-lookup"><span data-stu-id="ae0df-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="ae0df-124">对于 Windows 10 或 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="ae0df-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="ae0df-125">打开 VDI 配置包 .zip *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的文件。</span><span class="sxs-lookup"><span data-stu-id="ae0df-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="ae0df-126">还可以从 Microsoft Defender 安全中心 [获取程序包](https://securitycenter.windows.com/)：</span><span class="sxs-lookup"><span data-stu-id="ae0df-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="ae0df-127">在导航窗格中，选择"**设置**  >  **""载入"。**</span><span class="sxs-lookup"><span data-stu-id="ae0df-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="ae0df-128">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="ae0df-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="ae0df-129">在 **"部署方法"** 字段中，选择 **"非永久性终结点的 VDI 载入脚本"。**</span><span class="sxs-lookup"><span data-stu-id="ae0df-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="ae0df-130">单击 **下载程序包** 并保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="ae0df-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="ae0df-131">将文件从从 .zip 文件中提取的 WindowsDefenderATPOnboardingPackage 文件夹复制到路径 `golden/master` 下的映像 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 中。</span><span class="sxs-lookup"><span data-stu-id="ae0df-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="ae0df-132">如果不为每台设备实现单个条目，请复制 WindowsDefenderATPOnboardingScript.cmd。</span><span class="sxs-lookup"><span data-stu-id="ae0df-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="ae0df-133">如果要针对每台设备实现单个条目，请同时复制 Onboard-NonPersistentMachine.ps1 和 WindowsDefenderATPOnboardingScript.cmd。</span><span class="sxs-lookup"><span data-stu-id="ae0df-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae0df-134">如果看不到该文件夹 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ，它可能处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="ae0df-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="ae0df-135">你需要从文件资源管理器中选择显示隐藏 **文件和** 文件夹选项。</span><span class="sxs-lookup"><span data-stu-id="ae0df-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="ae0df-136">打开本地组策略编辑器窗口并导航到计算机 **配置**  >  **Windows 设置**  >  **脚本**  >  **启动**。</span><span class="sxs-lookup"><span data-stu-id="ae0df-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ae0df-137">域组策略还可用于载入非永久性 VDI 设备。</span><span class="sxs-lookup"><span data-stu-id="ae0df-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="ae0df-138">根据你要实现的方法，请按照相应步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ae0df-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span> <br>
   <span data-ttu-id="ae0df-139">**对于每台设备的单个条目**：</span><span class="sxs-lookup"><span data-stu-id="ae0df-139">**For single entry for each device**:</span></span><br>
   
   <span data-ttu-id="ae0df-140">选择 **"PowerShell 脚本**"选项卡，然后单击"添加 (Windows 资源管理器将在你之前复制载入脚本的路径中直接) 。</span><span class="sxs-lookup"><span data-stu-id="ae0df-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="ae0df-141">导航到载入 PowerShell 脚本 `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="ae0df-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="ae0df-142">**对于每台设备的多个条目**：</span><span class="sxs-lookup"><span data-stu-id="ae0df-142">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="ae0df-143">选择" **脚本** "选项卡，然后单击 **"添加** (Windows 资源管理器将在你之前复制载入脚本的路径中直接) 。</span><span class="sxs-lookup"><span data-stu-id="ae0df-143">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="ae0df-144">导航到载入 Bash 脚本 `WindowsDefenderATPOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="ae0df-144">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="ae0df-145">测试解决方案：</span><span class="sxs-lookup"><span data-stu-id="ae0df-145">Test your solution:</span></span>

   1. <span data-ttu-id="ae0df-146">创建具有一台设备的池。</span><span class="sxs-lookup"><span data-stu-id="ae0df-146">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="ae0df-147">登录到设备。</span><span class="sxs-lookup"><span data-stu-id="ae0df-147">Logon to device.</span></span>
      
   1. <span data-ttu-id="ae0df-148">从设备注销。</span><span class="sxs-lookup"><span data-stu-id="ae0df-148">Logoff from device.</span></span>

   1. <span data-ttu-id="ae0df-149">使用其他用户登录到设备。</span><span class="sxs-lookup"><span data-stu-id="ae0df-149">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="ae0df-150">**对于每台设备的单个条目**：在 Microsoft Defender 安全中心中仅检查一个条目。</span><span class="sxs-lookup"><span data-stu-id="ae0df-150">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="ae0df-151">**对于每台设备的多个条目**：在 Microsoft Defender 安全中心中检查多个条目。</span><span class="sxs-lookup"><span data-stu-id="ae0df-151">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="ae0df-152">单击 **导航窗格上的** "设备列表"。</span><span class="sxs-lookup"><span data-stu-id="ae0df-152">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="ae0df-153">通过输入设备名称并选择设备作为搜索类型 **来** 使用搜索函数。</span><span class="sxs-lookup"><span data-stu-id="ae0df-153">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="ae0df-154">对于下层 SKUs</span><span class="sxs-lookup"><span data-stu-id="ae0df-154">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="ae0df-155">以下注册表仅在目标是实现"每个设备的单个条目"时相关。</span><span class="sxs-lookup"><span data-stu-id="ae0df-155">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="ae0df-156">将注册表值设置为：</span><span class="sxs-lookup"><span data-stu-id="ae0df-156">Set registry value to:</span></span>

    ```reg
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="ae0df-157">或者使用命令行：</span><span class="sxs-lookup"><span data-stu-id="ae0df-157">or using command line:</span></span>

    ```
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="ae0df-158">按照 [服务器载入过程操作](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="ae0df-158">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="ae0df-159">使用 VDI 映像更新 (虚拟) 基础结构</span><span class="sxs-lookup"><span data-stu-id="ae0df-159">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="ae0df-160">作为最佳实践，我们建议使用脱机维护工具修补黄金/主映像。</span><span class="sxs-lookup"><span data-stu-id="ae0df-160">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="ae0df-161">例如，可以使用以下命令在映像保持脱机时安装更新：</span><span class="sxs-lookup"><span data-stu-id="ae0df-161">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="ae0df-162">有关 DISM 命令和脱机服务的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="ae0df-162">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="ae0df-163">使用 DISM 修改 Windows 映像</span><span class="sxs-lookup"><span data-stu-id="ae0df-163">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="ae0df-164">DISM 映像管理Command-Line选项</span><span class="sxs-lookup"><span data-stu-id="ae0df-164">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="ae0df-165">减小脱机 Windows 映像中组件存储的大小</span><span class="sxs-lookup"><span data-stu-id="ae0df-165">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="ae0df-166">如果脱机服务不是非永久性 VDI 环境的可行选项，应执行以下步骤以确保一致性和传感器运行状况：</span><span class="sxs-lookup"><span data-stu-id="ae0df-166">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="ae0df-167">启动主映像进行联机维护或修补后，运行载出脚本以关闭 Defender for Endpoint 传感器。</span><span class="sxs-lookup"><span data-stu-id="ae0df-167">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="ae0df-168">有关详细信息，请参阅使用本地 [脚本的载出设备](configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="ae0df-168">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="ae0df-169">在 CMD 窗口中运行以下命令，确保传感器已停止：</span><span class="sxs-lookup"><span data-stu-id="ae0df-169">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="ae0df-170">根据需要为映像提供服务。</span><span class="sxs-lookup"><span data-stu-id="ae0df-170">Service the image as needed.</span></span>

4. <span data-ttu-id="ae0df-171">使用可下载的 PsExec.exe (运行以下命令，以清理传感器自启动后可能累积的网络 https://download.sysinternals.com/files/PSTools.zip) 文件夹内容：</span><span class="sxs-lookup"><span data-stu-id="ae0df-171">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="ae0df-172">像平常一样重新密封黄金/主图像。</span><span class="sxs-lookup"><span data-stu-id="ae0df-172">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae0df-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="ae0df-173">Related topics</span></span>
- [<span data-ttu-id="ae0df-174">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="ae0df-174">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="ae0df-175">使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="ae0df-175">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="ae0df-176">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="ae0df-176">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="ae0df-177">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="ae0df-177">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="ae0df-178">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="ae0df-178">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
