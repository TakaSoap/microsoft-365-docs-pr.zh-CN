---
title: 载入非持久性虚拟桌面基础结构 (VDI) 设备。
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 在 VDI (虚拟桌面基础结构) 包，以便它们可以载入到 Microsoft 365 终结点数据丢失防护服务。
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917948"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="b5131-103">载入非持久性虚拟桌面基础结构 (VDI) 设备。</span><span class="sxs-lookup"><span data-stu-id="b5131-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="b5131-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b5131-104">**Applies to:**</span></span>
- [<span data-ttu-id="b5131-105">Microsoft 365 终结点数据丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="b5131-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="b5131-106">虚拟桌面基础结构 (VDI) 设备</span><span class="sxs-lookup"><span data-stu-id="b5131-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="b5131-107">Windows 虚拟桌面的 Microsoft 365 终结点数据丢失防护支持支持单个会话方案。</span><span class="sxs-lookup"><span data-stu-id="b5131-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="b5131-108">Windows 虚拟桌面上的多会话方案当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="b5131-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="b5131-109">载入 VDI 设备</span><span class="sxs-lookup"><span data-stu-id="b5131-109">Onboard VDI devices</span></span>

<span data-ttu-id="b5131-110">Microsoft 365 终结点数据丢失防护支持非永久性 VDI 会话载入。</span><span class="sxs-lookup"><span data-stu-id="b5131-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="b5131-111">若要载入非永久性 VDI 会话，VDI 设备必须位于 Windows 10 1809 或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="b5131-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="b5131-112">载入 VDIS 时可能存在相关挑战。</span><span class="sxs-lookup"><span data-stu-id="b5131-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="b5131-113">以下是此方案的典型挑战：</span><span class="sxs-lookup"><span data-stu-id="b5131-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="b5131-114">即时提前载入短期会话，这些会话在实际预配之前必须载入到 Microsoft 365 终结点数据丢失防护。</span><span class="sxs-lookup"><span data-stu-id="b5131-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="b5131-115">设备名称通常重新用于新会话。</span><span class="sxs-lookup"><span data-stu-id="b5131-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="b5131-116">VDI 设备可以在 Microsoft 365 合规中心显示为：</span><span class="sxs-lookup"><span data-stu-id="b5131-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="b5131-117">每台设备的单个条目。</span><span class="sxs-lookup"><span data-stu-id="b5131-117">Single entry for each device.</span></span>  
<span data-ttu-id="b5131-118">请注意，在这种情况下，创建会话时必须配置相同的设备名称，例如使用无人参与应答文件。</span><span class="sxs-lookup"><span data-stu-id="b5131-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="b5131-119">每个设备有多个条目 - 每个会话一个条目。</span><span class="sxs-lookup"><span data-stu-id="b5131-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="b5131-120">以下步骤将指导你完成载入 VDI 设备，并重点介绍单项和多条目的步骤。</span><span class="sxs-lookup"><span data-stu-id="b5131-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="b5131-121">对于资源配置较低的环境，VDI 启动过程可能会减慢 Microsoft 365 终结点数据丢失防护载入的速度。</span><span class="sxs-lookup"><span data-stu-id="b5131-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="b5131-122">打开 VDI 配置包 .zip *(DeviceCompliancePackage.zip)* 从服务载入向导下载的文件。</span><span class="sxs-lookup"><span data-stu-id="b5131-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="b5131-123">在导航窗格中，选择"**设置**  >  **""设备载入**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="b5131-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="b5131-124">在 **"部署方法"** 字段中，选择 **"非永久性终结点的 VDI 载入脚本"。**</span><span class="sxs-lookup"><span data-stu-id="b5131-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="b5131-125">单击 **下载程序包** 并保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="b5131-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="b5131-126">从 .zip 文件提取的 DeviceCompliancePackage 文件夹中的文件复制到路径 `golden/master` 下的映像 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 中。</span><span class="sxs-lookup"><span data-stu-id="b5131-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="b5131-127">如果未针对每台设备实现单个条目，请复制 DeviceComplianceOnboardingScript.cmd。</span><span class="sxs-lookup"><span data-stu-id="b5131-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="b5131-128">如果你要针对每台设备实现单个条目，请复制 Onboard-NonPersistentMachine.ps1 和 DeviceComplianceOnboardingScript.cmd。</span><span class="sxs-lookup"><span data-stu-id="b5131-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5131-129">如果看不到该文件夹 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ，它可能处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="b5131-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="b5131-130">你需要从文件资源管理器中选择显示隐藏 **文件和** 文件夹选项。</span><span class="sxs-lookup"><span data-stu-id="b5131-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="b5131-131">打开本地组策略编辑器窗口并导航到计算机 **配置**  >  **Windows 设置**  >  **脚本**  >  **启动**。</span><span class="sxs-lookup"><span data-stu-id="b5131-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b5131-132">域组策略还可用于载入非永久性 VDI 设备。</span><span class="sxs-lookup"><span data-stu-id="b5131-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="b5131-133">根据你要实现的方法，请按照相应步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b5131-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="b5131-134">**对于每台设备的单个条目**</span><span class="sxs-lookup"><span data-stu-id="b5131-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="b5131-135">选择 **"PowerShell 脚本**"选项卡，然后单击"添加 (Windows 资源管理器将在你之前复制载入脚本的路径中直接) 。</span><span class="sxs-lookup"><span data-stu-id="b5131-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="b5131-136">导航到载入 PowerShell 脚本 `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="b5131-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="b5131-137">**对于每台设备的多个条目**：</span><span class="sxs-lookup"><span data-stu-id="b5131-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="b5131-138">选择" **脚本** "选项卡，然后单击 **"添加** (Windows 资源管理器将在你之前复制载入脚本的路径中直接) 。</span><span class="sxs-lookup"><span data-stu-id="b5131-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="b5131-139">导航到载入 Bash 脚本 `DeviceComplianceOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="b5131-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="b5131-140">测试解决方案：</span><span class="sxs-lookup"><span data-stu-id="b5131-140">Test your solution:</span></span>

   1. <span data-ttu-id="b5131-141">创建具有一台设备的池。</span><span class="sxs-lookup"><span data-stu-id="b5131-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="b5131-142">登录到设备。</span><span class="sxs-lookup"><span data-stu-id="b5131-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="b5131-143">从设备注销。</span><span class="sxs-lookup"><span data-stu-id="b5131-143">Logoff from device.</span></span>

   1. <span data-ttu-id="b5131-144">使用其他用户登录到设备。</span><span class="sxs-lookup"><span data-stu-id="b5131-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="b5131-145">**对于每台设备的单个条目**：在 Microsoft Defender 安全中心中仅检查一个条目。</span><span class="sxs-lookup"><span data-stu-id="b5131-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="b5131-146">**对于每台设备的多个条目**：在 Microsoft Defender 安全中心中检查多个条目。</span><span class="sxs-lookup"><span data-stu-id="b5131-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="b5131-147">单击 **导航窗格上的** "设备列表"。</span><span class="sxs-lookup"><span data-stu-id="b5131-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="b5131-148">通过输入设备名称并选择设备作为搜索类型 **来** 使用搜索函数。</span><span class="sxs-lookup"><span data-stu-id="b5131-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="b5131-149">使用 VDI 映像更新 (虚拟) 基础结构</span><span class="sxs-lookup"><span data-stu-id="b5131-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="b5131-150">作为最佳实践，我们建议使用脱机维护工具修补黄金/主映像。</span><span class="sxs-lookup"><span data-stu-id="b5131-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="b5131-151">例如，可以使用以下命令在映像保持脱机时安装更新：</span><span class="sxs-lookup"><span data-stu-id="b5131-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="b5131-152">有关 DISM 命令和脱机服务的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="b5131-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="b5131-153">使用 DISM 修改 Windows 映像</span><span class="sxs-lookup"><span data-stu-id="b5131-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="b5131-154">DISM 映像管理Command-Line选项</span><span class="sxs-lookup"><span data-stu-id="b5131-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="b5131-155">减小脱机 Windows 映像中组件存储的大小</span><span class="sxs-lookup"><span data-stu-id="b5131-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="b5131-156">如果脱机服务不是非永久性 VDI 环境的可行选项，应执行以下步骤以确保一致性和传感器运行状况：</span><span class="sxs-lookup"><span data-stu-id="b5131-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="b5131-157">启动主映像进行联机维护或修补后，运行载出脚本以关闭 Microsoft 365 终结点数据丢失防护传感器。</span><span class="sxs-lookup"><span data-stu-id="b5131-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="b5131-158">有关详细信息，请参阅使用本地 [脚本的载出设备](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="b5131-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="b5131-159">在 CMD 窗口中运行以下命令，确保传感器已停止：</span><span class="sxs-lookup"><span data-stu-id="b5131-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="b5131-160">根据需要为映像提供服务。</span><span class="sxs-lookup"><span data-stu-id="b5131-160">Service the image as needed.</span></span>

4. <span data-ttu-id="b5131-161">使用可下载的 PsExec.exe (运行以下命令，以清理传感器自启动后可能累积的网络 https://download.sysinternals.com/files/PSTools.zip) 文件夹内容：</span><span class="sxs-lookup"><span data-stu-id="b5131-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="b5131-162">像平常一样重新密封黄金/主图像。</span><span class="sxs-lookup"><span data-stu-id="b5131-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5131-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="b5131-163">Related topics</span></span>
- [<span data-ttu-id="b5131-164">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="b5131-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="b5131-165">使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="b5131-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="b5131-166">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="b5131-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="b5131-167">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="b5131-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="b5131-168">Microsoft Defender 高级威胁防护载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="b5131-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)