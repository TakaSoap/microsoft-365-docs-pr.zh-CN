---
title: " (VDI) 设备的板载非永久性虚拟桌面基础结构"
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
description: 在虚拟桌面基础结构 (VDI) 设备上部署配置包，以使其载入到 Microsoft 365 终结点数据丢失防护服务。
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769401"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="d6079-103"> (VDI) 设备的板载非永久性虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="d6079-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="d6079-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d6079-104">**Applies to:**</span></span>
- [<span data-ttu-id="d6079-105">Microsoft 365 Endpoint data 丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="d6079-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="d6079-106"> (VDI) 设备的虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="d6079-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="d6079-107">Windows 虚拟桌面的 Microsoft 365 终结点数据丢失防护支持支持单个会话方案。</span><span class="sxs-lookup"><span data-stu-id="d6079-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="d6079-108">目前，Windows 虚拟桌面上的多会话方案不受支持。</span><span class="sxs-lookup"><span data-stu-id="d6079-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="d6079-109">板载 VDI 设备</span><span class="sxs-lookup"><span data-stu-id="d6079-109">Onboard VDI devices</span></span>

<span data-ttu-id="d6079-110">Microsoft 365 终结点数据丢失防护支持非永久性 VDI 会话载入。</span><span class="sxs-lookup"><span data-stu-id="d6079-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="d6079-111">对于板载非永久性 VDI 会话，VDI 设备必须在 Windows 10 1809 或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="d6079-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="d6079-112">在加入 VDIs 时可能会有相关的挑战。</span><span class="sxs-lookup"><span data-stu-id="d6079-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="d6079-113">以下是此方案的典型难题：</span><span class="sxs-lookup"><span data-stu-id="d6079-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="d6079-114">即时启动短期会话的快速加载，在实际设置之前，必须载入到 Microsoft 365 终结点数据丢失。</span><span class="sxs-lookup"><span data-stu-id="d6079-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="d6079-115">通常为新会话重用设备名称。</span><span class="sxs-lookup"><span data-stu-id="d6079-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="d6079-116">VDI 设备可以在 Microsoft 365 合规性中心中显示，就是：</span><span class="sxs-lookup"><span data-stu-id="d6079-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="d6079-117">每个设备一个条目。</span><span class="sxs-lookup"><span data-stu-id="d6079-117">Single entry for each device.</span></span>  
<span data-ttu-id="d6079-118">请注意，在这种情况下，必须在创建会话时配置 *相同* 的设备名称，例如使用无人参与的应答文件。</span><span class="sxs-lookup"><span data-stu-id="d6079-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="d6079-119">每个设备1个条目-每个会话一个。</span><span class="sxs-lookup"><span data-stu-id="d6079-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="d6079-120">以下步骤将指导您完成加入 VDI 设备的步骤，并将突出显示单个和多个条目的步骤。</span><span class="sxs-lookup"><span data-stu-id="d6079-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="d6079-121">对于资源配置较少的环境，VDI 启动过程可能会降低 Microsoft 365 终结点数据丢失防护的加入速度。</span><span class="sxs-lookup"><span data-stu-id="d6079-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="d6079-122">打开您从 "服务载入" 向导下载 *DeviceCompliancePackage.zip* )  (的 VDI 配置包 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="d6079-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="d6079-123">在导航窗格中，选择 " **设置**  >  **设备** 启动加入"  >  **Onboarding** 。</span><span class="sxs-lookup"><span data-stu-id="d6079-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="d6079-124">在 " **部署方法** " 字段中， **为非持久终结点选择 VDI 载入脚本** 。</span><span class="sxs-lookup"><span data-stu-id="d6079-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="d6079-125">单击 " **下载包** " 并保存该 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="d6079-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="d6079-126">将从 .zip 文件提取的 DeviceCompliancePackage 文件夹中的文件复制到 `golden/master` 路径下的图像中 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。</span><span class="sxs-lookup"><span data-stu-id="d6079-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="d6079-127">如果不是为每个设备实现单个条目，请复制 DeviceComplianceOnboardingScript。</span><span class="sxs-lookup"><span data-stu-id="d6079-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="d6079-128">如果要为每个设备实现单个条目，请复制 Onboard-NonPersistentMachine.ps1 和 DeviceComplianceOnboardingScript。</span><span class="sxs-lookup"><span data-stu-id="d6079-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6079-129">如果看不到该 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 文件夹，则可能已将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="d6079-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="d6079-130">您需要从文件资源管理器中选择 " **显示隐藏文件和文件夹** " 选项。</span><span class="sxs-lookup"><span data-stu-id="d6079-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="d6079-131">打开本地组策略编辑器窗口并导航到 " **计算机配置** " "  >  **Windows 设置**  >  **脚本**  >  **启动** "。</span><span class="sxs-lookup"><span data-stu-id="d6079-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="d6079-132">域组策略也可用于加入非永久性 VDI 设备。</span><span class="sxs-lookup"><span data-stu-id="d6079-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="d6079-133">根据要实现的方法，请执行相应的步骤：</span><span class="sxs-lookup"><span data-stu-id="d6079-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="d6079-134">**对于每个设备的单个条目**</span><span class="sxs-lookup"><span data-stu-id="d6079-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="d6079-135">选择 " **PowerShell 脚本** " 选项卡，然后单击 " **添加** " (Windows 资源管理器将直接在先前复制的载入脚本的路径中打开) 。</span><span class="sxs-lookup"><span data-stu-id="d6079-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="d6079-136">导航到 "载入 PowerShell 脚本" `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="d6079-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="d6079-137">**对于每个设备的多个条目** ：</span><span class="sxs-lookup"><span data-stu-id="d6079-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="d6079-138">选择 " **脚本** " 选项卡，然后单击 " **添加** " (Windows 资源管理器将直接在先前复制的载入脚本的路径中打开) 。</span><span class="sxs-lookup"><span data-stu-id="d6079-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="d6079-139">导航到 "载入 bash" 脚本 `DeviceComplianceOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="d6079-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="d6079-140">测试您的解决方案：</span><span class="sxs-lookup"><span data-stu-id="d6079-140">Test your solution:</span></span>

   1. <span data-ttu-id="d6079-141">创建一个包含一个设备的池。</span><span class="sxs-lookup"><span data-stu-id="d6079-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="d6079-142">登录到设备。</span><span class="sxs-lookup"><span data-stu-id="d6079-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="d6079-143">从设备注销。</span><span class="sxs-lookup"><span data-stu-id="d6079-143">Logoff from device.</span></span>

   1. <span data-ttu-id="d6079-144">使用另一个用户登录到设备。</span><span class="sxs-lookup"><span data-stu-id="d6079-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="d6079-145">**对于每个设备的单个条目** ：仅检查 Microsoft Defender Security Center 中的一个条目。</span><span class="sxs-lookup"><span data-stu-id="d6079-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="d6079-146">**对于每个设备的多个条目** ：检查 Microsoft Defender 安全中心中的多个条目。</span><span class="sxs-lookup"><span data-stu-id="d6079-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="d6079-147">单击导航窗格上的 " **设备列表** "。</span><span class="sxs-lookup"><span data-stu-id="d6079-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="d6079-148">通过输入设备名称并选择 " **设备** " 作为搜索类型来使用搜索功能。</span><span class="sxs-lookup"><span data-stu-id="d6079-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="d6079-149"> (VDI) 映像更新非永久性虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="d6079-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="d6079-150">作为一种最佳做法，我们建议使用脱机服务工具来修补黄金/母版映像。</span><span class="sxs-lookup"><span data-stu-id="d6079-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="d6079-151">例如，您可以使用下面的命令在图像保持脱机的情况下安装更新：</span><span class="sxs-lookup"><span data-stu-id="d6079-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="d6079-152">有关 DISM 命令和离线服务的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="d6079-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="d6079-153">使用 DISM 修改 Windows 映像</span><span class="sxs-lookup"><span data-stu-id="d6079-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="d6079-154">DISM 图像管理 Command-Line 选项</span><span class="sxs-lookup"><span data-stu-id="d6079-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="d6079-155">减小脱机 Windows 映像中组件存储的大小</span><span class="sxs-lookup"><span data-stu-id="d6079-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="d6079-156">如果非持久 VDI 环境中的脱机服务不是可行的选项，则应采取以下步骤来确保一致性和传感器运行状况：</span><span class="sxs-lookup"><span data-stu-id="d6079-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="d6079-157">在启动用于联机服务或修补的主映像之后，运行一个脱离脚本来关闭 Microsoft 365 终结点数据丢失防护传感器。</span><span class="sxs-lookup"><span data-stu-id="d6079-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="d6079-158">有关详细信息，请参阅 [使用本地脚本的分离设备](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="d6079-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="d6079-159">通过在 CMD 窗口中运行下面的命令来确保传感器已停止：</span><span class="sxs-lookup"><span data-stu-id="d6079-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="d6079-160">根据需要为图像服务。</span><span class="sxs-lookup"><span data-stu-id="d6079-160">Service the image as needed.</span></span>

4. <span data-ttu-id="d6079-161">使用 PsExec.exe (可从其下载 https://download.sysinternals.com/files/PSTools.zip) 以清理自启动以来，传感器可能已积累的网络文件夹内容的命令运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d6079-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="d6079-162">按正常方式重新密封黄金/主映像。</span><span class="sxs-lookup"><span data-stu-id="d6079-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d6079-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="d6079-163">Related topics</span></span>
- [<span data-ttu-id="d6079-164">使用组策略的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d6079-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="d6079-165">使用 Microsoft 终结点配置管理器的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d6079-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="d6079-166">使用移动设备管理工具的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d6079-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="d6079-167">使用本地脚本的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d6079-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="d6079-168">解决 Microsoft Defender 高级威胁防护载入问题</span><span class="sxs-lookup"><span data-stu-id="d6079-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
