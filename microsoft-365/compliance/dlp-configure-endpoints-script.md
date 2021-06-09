---
title: 使用本地脚本载入 Windows 10 设备
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
description: 使用本地脚本在设备上部署配置包，以便它们可以载入服务。
ms.openlocfilehash: 55109d8fda52db6651d4398cd84ffd6668b4d871
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843442"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="10177-103">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="10177-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="10177-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="10177-104">**Applies to:**</span></span>

- [<span data-ttu-id="10177-105">Microsoft 365DLP (终结点数据丢失) </span><span class="sxs-lookup"><span data-stu-id="10177-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="10177-106">还可以手动载入各个设备，Microsoft 365终结点数据丢失防护。</span><span class="sxs-lookup"><span data-stu-id="10177-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="10177-107">在承诺载入网络内的所有设备之前，你可能希望先在测试服务时这样做。</span><span class="sxs-lookup"><span data-stu-id="10177-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10177-108">此脚本已优化为在最多 10 台设备上使用。</span><span class="sxs-lookup"><span data-stu-id="10177-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="10177-109">若要大规模部署，请使用 [其他部署选项](dlp-configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="10177-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="10177-110">例如，可以使用在使用组策略载入 Windows 10 设备中提供的脚本，将载入脚本部署到生产中的 10[多个设备](dlp-configure-endpoints-gp.md)。</span><span class="sxs-lookup"><span data-stu-id="10177-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="10177-111">载入设备</span><span class="sxs-lookup"><span data-stu-id="10177-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="10177-112">打开 GP 配置包.zip文件 *(DeviceComplianceOnboardingPackage.zip)* 从服务载入向导下载的内容。</span><span class="sxs-lookup"><span data-stu-id="10177-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="10177-113">您还可以从 Microsoft 合规性中心 [获取程序包](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="10177-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="10177-114">在导航窗格中，选择 **"设置**  >  **载入"。**</span><span class="sxs-lookup"><span data-stu-id="10177-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="10177-115">在"**部署方法"** 字段中，选择"**本地脚本"。**</span><span class="sxs-lookup"><span data-stu-id="10177-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="10177-116">单击 **下载程序包** 并保存.zip文件。</span><span class="sxs-lookup"><span data-stu-id="10177-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="10177-117">将配置包的内容解压缩到你想要载入 (的位置，例如桌面) 。</span><span class="sxs-lookup"><span data-stu-id="10177-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="10177-118">你应该有一个名为 *DeviceOnboardingScript.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="10177-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="10177-119">在设备上打开提升的命令行提示符并运行脚本：</span><span class="sxs-lookup"><span data-stu-id="10177-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="10177-120">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="10177-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="10177-121">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="10177-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![指向"以管理员模式运行"的"窗口开始"菜单](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="10177-123">键入脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="10177-123">Type the location of the script file.</span></span> <span data-ttu-id="10177-124">如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="10177-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="10177-125">按 **Enter 键** 或单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="10177-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="10177-126">若要了解如何手动验证设备是否合规并正确报告传感器数据，请参阅载入Microsoft Defender 高级威胁防护[疑难解答](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="10177-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="10177-127">使用本地脚本的载出设备</span><span class="sxs-lookup"><span data-stu-id="10177-127">Offboard devices using a local script</span></span>
<span data-ttu-id="10177-128">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="10177-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="10177-129">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="10177-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="10177-130">下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="10177-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="10177-131">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="10177-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="10177-132">从 Microsoft 合规性中心获取 [载出包](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="10177-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="10177-133">在导航窗格中，选择 **"设置**  >  **设备载出"。**</span><span class="sxs-lookup"><span data-stu-id="10177-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="10177-134">在"**部署方法"** 字段中，选择"**本地脚本"。**</span><span class="sxs-lookup"><span data-stu-id="10177-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="10177-135">单击 **下载程序包** 并保存.zip文件。</span><span class="sxs-lookup"><span data-stu-id="10177-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="10177-136">将文件.zip到设备可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="10177-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="10177-137">你应该有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="10177-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="10177-138">在设备上打开提升的命令行提示符并运行脚本：</span><span class="sxs-lookup"><span data-stu-id="10177-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="10177-139">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="10177-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="10177-140">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="10177-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![指向"以管理员模式运行"的"窗口开始"菜单](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="10177-142">键入脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="10177-142">Type the location of the script file.</span></span> <span data-ttu-id="10177-143">如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="10177-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="10177-144">按 **Enter 键** 或单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="10177-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10177-145">载出导致设备停止向门户发送传感器数据。</span><span class="sxs-lookup"><span data-stu-id="10177-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="10177-146">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="10177-146">Monitor device configuration</span></span>
<span data-ttu-id="10177-147">你可以按照 [载入问题疑难解答] ( (/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 中的不同验证步骤来验证脚本是否成功完成且代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="10177-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="10177-148">也可以直接在门户上或使用不同的部署工具进行监视。</span><span class="sxs-lookup"><span data-stu-id="10177-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="10177-149">使用门户监视设备</span><span class="sxs-lookup"><span data-stu-id="10177-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="10177-150">转到Microsoft 365[合规中心。](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="10177-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="10177-151">选择 **设置**  >  **设备**  >  **载入设备"。**</span><span class="sxs-lookup"><span data-stu-id="10177-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="10177-152">验证设备是否显示。</span><span class="sxs-lookup"><span data-stu-id="10177-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="10177-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="10177-153">Related topics</span></span>
- [<span data-ttu-id="10177-154">使用Windows 10载入设备</span><span class="sxs-lookup"><span data-stu-id="10177-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="10177-155">使用Windows 10载入Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="10177-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="10177-156">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="10177-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="10177-157">载入非永久虚拟桌面基础结构 （VDI） 设备</span><span class="sxs-lookup"><span data-stu-id="10177-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="10177-158">在新载入的 Microsoft Defender 终结点设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="10177-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="10177-159">载入Microsoft Defender 高级威胁防护疑难解答</span><span class="sxs-lookup"><span data-stu-id="10177-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)