---
title: 使用本地脚本的板载 Windows 10 设备
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
description: 使用本地脚本在设备上部署配置包，以使其载入服务。
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769406"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="48ec6-103">使用本地脚本的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="48ec6-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="48ec6-104">**Applies to:**</span></span>

- [<span data-ttu-id="48ec6-105">Microsoft 365 Endpoint data 丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="48ec6-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="48ec6-106">此外，还可以将单个设备手动集成到 Microsoft 365 终结点数据丢失防护中。</span><span class="sxs-lookup"><span data-stu-id="48ec6-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="48ec6-107">在您提交以在网络中加入所有设备之前测试服务时，您可能需要先执行此操作。</span><span class="sxs-lookup"><span data-stu-id="48ec6-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48ec6-108">此脚本已经过优化，可在最多10台设备上使用。</span><span class="sxs-lookup"><span data-stu-id="48ec6-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="48ec6-109">若要在扩展时部署，请使用 [其他部署选项](dlp-configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="48ec6-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="48ec6-110">例如，您可以使用组策略将载入脚本部署到生产环境中的10个以上的设备，并在 [Windows 10 的板载 Windows 10 设备](dlp-configure-endpoints-gp.md)中提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="48ec6-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="48ec6-111">板载设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="48ec6-112">打开您从 "服务载入" 向导下载 *DeviceComplianceOnboardingPackage.zip* )  (的 GP configuration 包 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="48ec6-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="48ec6-113">你也可以从[Microsoft 合规性中心](https://compliance.microsoft.com)获取程序包</span><span class="sxs-lookup"><span data-stu-id="48ec6-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="48ec6-114">在导航窗格中，选择 " **设置**  >  **设备载入** "。</span><span class="sxs-lookup"><span data-stu-id="48ec6-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="48ec6-115">在 " **部署方法** " 字段中，选择 " **本地脚本** "。</span><span class="sxs-lookup"><span data-stu-id="48ec6-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="48ec6-116">单击 " **下载包** " 并保存该 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="48ec6-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="48ec6-117">将配置包的内容解压缩到设备上要板载 (的位置。例如，桌面) 。</span><span class="sxs-lookup"><span data-stu-id="48ec6-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="48ec6-118">您应该具有一个名为 *DeviceOnboardingScript* 的文件。</span><span class="sxs-lookup"><span data-stu-id="48ec6-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="48ec6-119">在设备上打开提升的命令行提示符并运行脚本：</span><span class="sxs-lookup"><span data-stu-id="48ec6-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="48ec6-120">转到 " **开始** " 并键入 **cmd** 。</span><span class="sxs-lookup"><span data-stu-id="48ec6-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="48ec6-121">右键单击 " **命令提示符** "，然后选择 " **以管理员身份运行** "。</span><span class="sxs-lookup"><span data-stu-id="48ec6-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![指向 "以管理员身份运行" 窗口的 "开始" 菜单](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="48ec6-123">键入脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="48ec6-123">Type the location of the script file.</span></span> <span data-ttu-id="48ec6-124">如果将文件复制到桌面，请键入： *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="48ec6-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="48ec6-125">按 **enter** 键或单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="48ec6-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="48ec6-126">有关如何手动验证设备是否合规并正确报告传感器数据的信息，请参阅 [解决 Microsoft Defender 高级威胁防护的载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="48ec6-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="48ec6-127">使用本地脚本的分离设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-127">Offboard devices using a local script</span></span>
<span data-ttu-id="48ec6-128">出于安全考虑，用于分离设备的包将在下载后的30天后过期。</span><span class="sxs-lookup"><span data-stu-id="48ec6-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="48ec6-129">发送到设备的已过期的脱离程序包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="48ec6-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="48ec6-130">下载一个脱离程序包时，系统会通知你提供程序包到期日期，并且它也将包含在包名称中。</span><span class="sxs-lookup"><span data-stu-id="48ec6-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="48ec6-131">无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。</span><span class="sxs-lookup"><span data-stu-id="48ec6-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="48ec6-132">从[Microsoft 合规性中心](https://compliance.microsoft.com)获取脱离程序包</span><span class="sxs-lookup"><span data-stu-id="48ec6-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="48ec6-133">在导航窗格中，选择 " **设置**  >  **设备脱离** "。</span><span class="sxs-lookup"><span data-stu-id="48ec6-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="48ec6-134">在 " **部署方法** " 字段中，选择 " **本地脚本** "。</span><span class="sxs-lookup"><span data-stu-id="48ec6-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="48ec6-135">单击 " **下载包** " 并保存该 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="48ec6-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="48ec6-136">将 .zip 文件的内容提取到可由设备访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="48ec6-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="48ec6-137">您应具有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的文件。</span><span class="sxs-lookup"><span data-stu-id="48ec6-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="48ec6-138">在设备上打开提升的命令行提示符并运行脚本：</span><span class="sxs-lookup"><span data-stu-id="48ec6-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="48ec6-139">转到 " **开始** " 并键入 **cmd** 。</span><span class="sxs-lookup"><span data-stu-id="48ec6-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="48ec6-140">右键单击 " **命令提示符** "，然后选择 " **以管理员身份运行** "。</span><span class="sxs-lookup"><span data-stu-id="48ec6-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![指向 "以管理员身份运行" 窗口的 "开始" 菜单](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="48ec6-142">键入脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="48ec6-142">Type the location of the script file.</span></span> <span data-ttu-id="48ec6-143">如果将文件复制到桌面，请键入： *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd*</span><span class="sxs-lookup"><span data-stu-id="48ec6-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="48ec6-144">按 **enter** 键或单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="48ec6-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48ec6-145">脱离将导致设备停止将传感器数据发送到门户。</span><span class="sxs-lookup"><span data-stu-id="48ec6-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="48ec6-146">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="48ec6-146">Monitor device configuration</span></span>
<span data-ttu-id="48ec6-147">您可以按照 [解决载入问题] ( # B1 中的不同验证步骤操作， https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 以验证脚本是否已成功完成且代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="48ec6-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="48ec6-148">还可以直接在门户或使用不同的部署工具进行监视。</span><span class="sxs-lookup"><span data-stu-id="48ec6-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="48ec6-149">使用门户监视设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="48ec6-150">转到 [Microsoft 365 合规性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="48ec6-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="48ec6-151">选择 " **设置**  >  **设备加入**  >  **设备"** 。</span><span class="sxs-lookup"><span data-stu-id="48ec6-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="48ec6-152">验证设备是否显示。</span><span class="sxs-lookup"><span data-stu-id="48ec6-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="48ec6-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="48ec6-153">Related topics</span></span>
- [<span data-ttu-id="48ec6-154">使用组策略的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="48ec6-155">使用 Microsoft 终结点配置管理器的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="48ec6-156">使用移动设备管理工具的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="48ec6-157"> (VDI) 设备的板载非永久性虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="48ec6-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="48ec6-158">在新载入上运行检测测试 Microsoft Defender ATP 设备</span><span class="sxs-lookup"><span data-stu-id="48ec6-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="48ec6-159">解决 Microsoft Defender 高级威胁防护载入问题</span><span class="sxs-lookup"><span data-stu-id="48ec6-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
