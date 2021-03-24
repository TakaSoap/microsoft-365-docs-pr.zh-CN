---
title: 使用本地脚本载入 Windows 10 设备
description: 使用本地脚本在设备上部署配置包，以便它们可以载入服务。
keywords: 使用本地脚本配置设备， 设备管理， 配置 Windows ATP 设备， 为终结点设备配置 Microsoft Defender
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
ms.technology: mde
ms.openlocfilehash: 77473df9cc3e0e98efac8eaacd0a51b551bc3258
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056359"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="7d636-104">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="7d636-104">Onboard Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="7d636-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d636-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="7d636-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="7d636-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7d636-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7d636-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="7d636-108">还可以手动将个别设备载入到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="7d636-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="7d636-109">在承诺载入网络内的所有设备之前，你可能希望先在测试服务时这样做。</span><span class="sxs-lookup"><span data-stu-id="7d636-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d636-110">此脚本已优化为在最多 10 台设备上使用。</span><span class="sxs-lookup"><span data-stu-id="7d636-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="7d636-111">若要大规模部署，请使用 [其他部署选项](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="7d636-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="7d636-112">例如，可以使用使用组策略载入 Windows 10 设备中提供的脚本，将载入脚本部署到生产中的 [10 多个设备](configure-endpoints-gp.md)。</span><span class="sxs-lookup"><span data-stu-id="7d636-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="7d636-113">载入设备</span><span class="sxs-lookup"><span data-stu-id="7d636-113">Onboard devices</span></span> 

<span data-ttu-id="7d636-114">[![显示各种部署路径的 PDF 图像](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7d636-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="7d636-115">请查看 [PDF 或](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 以查看部署 Defender for Endpoint 中的各个路径。</span><span class="sxs-lookup"><span data-stu-id="7d636-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="7d636-116">打开 GP 配置包 .zip *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的文件。</span><span class="sxs-lookup"><span data-stu-id="7d636-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="7d636-117">还可以从 Microsoft Defender 安全中心 [获取程序包](https://securitycenter.windows.com/)：</span><span class="sxs-lookup"><span data-stu-id="7d636-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="7d636-118">在导航窗格中，选择"**设置**  >  **""载入"。**</span><span class="sxs-lookup"><span data-stu-id="7d636-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="7d636-119">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="7d636-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="7d636-120">在"**部署方法"** 字段中，选择"**本地脚本"。**</span><span class="sxs-lookup"><span data-stu-id="7d636-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="7d636-121">单击 **下载程序包** 并保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="7d636-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="7d636-122">将配置包的内容解压缩到你想要载入 (的位置，例如桌面) 。</span><span class="sxs-lookup"><span data-stu-id="7d636-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="7d636-123">你应该有一个名为 *WindowsDefenderATPOnboardingScript.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="7d636-123">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="7d636-124">在设备上打开提升的命令行提示符并运行脚本：</span><span class="sxs-lookup"><span data-stu-id="7d636-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="7d636-125">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="7d636-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="7d636-126">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="7d636-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![指向"以管理员模式运行"的"窗口开始"菜单](images/run-as-admin.png)

4.  <span data-ttu-id="7d636-128">键入脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7d636-128">Type the location of the script file.</span></span> <span data-ttu-id="7d636-129">如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="7d636-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="7d636-130">按 **Enter 键** 或单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="7d636-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="7d636-131">若要了解如何手动验证设备是否合规并正确报告传感器数据，请参阅 Microsoft [Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="7d636-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="7d636-132">载入设备后，你可以选择运行检测测试来验证设备是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="7d636-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="7d636-133">有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint 终结点](run-detection-test.md)运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="7d636-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="7d636-134">配置示例集合设置</span><span class="sxs-lookup"><span data-stu-id="7d636-134">Configure sample collection settings</span></span>
<span data-ttu-id="7d636-135">对于每个设备，你可以设置一个配置值，以指示当通过 Microsoft Defender 安全中心提出提交文件进行深入分析的请求时是否可以从该设备收集示例。</span><span class="sxs-lookup"><span data-stu-id="7d636-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="7d636-136">可以使用 *regedit* 或创建并运行 *.reg* 文件，在设备上手动配置示例共享设置。</span><span class="sxs-lookup"><span data-stu-id="7d636-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="7d636-137">通过以下注册表项设置配置：</span><span class="sxs-lookup"><span data-stu-id="7d636-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="7d636-138">其中：</span><span class="sxs-lookup"><span data-stu-id="7d636-138">Where:</span></span><br>
<span data-ttu-id="7d636-139">名称类型为 D-WORD。</span><span class="sxs-lookup"><span data-stu-id="7d636-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="7d636-140">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="7d636-140">Possible values are:</span></span>
- <span data-ttu-id="7d636-141">0 - 不允许从此设备共享示例</span><span class="sxs-lookup"><span data-stu-id="7d636-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="7d636-142">1 - 允许从此设备共享所有文件类型</span><span class="sxs-lookup"><span data-stu-id="7d636-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="7d636-143">如果注册表项不存在，则默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="7d636-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="7d636-144">使用本地脚本的载出设备</span><span class="sxs-lookup"><span data-stu-id="7d636-144">Offboard devices using a local script</span></span>
<span data-ttu-id="7d636-145">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="7d636-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="7d636-146">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="7d636-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="7d636-147">下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="7d636-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="7d636-148">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="7d636-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="7d636-149">从 Microsoft Defender 安全中心获取载 [出程序包](https://securitycenter.windows.com/)：</span><span class="sxs-lookup"><span data-stu-id="7d636-149">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="7d636-150">在导航窗格中，选择"**设置**  >  **""载出"。**</span><span class="sxs-lookup"><span data-stu-id="7d636-150">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="7d636-151">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="7d636-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="7d636-152">在"**部署方法"** 字段中，选择"**本地脚本"。**</span><span class="sxs-lookup"><span data-stu-id="7d636-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="7d636-153">单击 **下载程序包** 并保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="7d636-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="7d636-154">将 .zip 文件的内容提取到设备可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="7d636-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="7d636-155">你应该有一个名为 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="7d636-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="7d636-156">在设备上打开提升的命令行提示符并运行脚本：</span><span class="sxs-lookup"><span data-stu-id="7d636-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="7d636-157">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="7d636-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="7d636-158">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="7d636-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![指向"以管理员模式运行"的"窗口开始"菜单](images/run-as-admin.png)

4.  <span data-ttu-id="7d636-160">键入脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7d636-160">Type the location of the script file.</span></span> <span data-ttu-id="7d636-161">如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="7d636-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="7d636-162">按 **Enter 键** 或单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="7d636-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d636-163">"载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="7d636-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="7d636-164">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="7d636-164">Monitor device configuration</span></span>
<span data-ttu-id="7d636-165">可以按照载入问题疑难解答中的不同[](troubleshoot-onboarding.md)验证步骤验证脚本是否成功完成以及代理是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="7d636-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="7d636-166">也可以直接在门户上或使用不同的部署工具进行监视。</span><span class="sxs-lookup"><span data-stu-id="7d636-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="7d636-167">使用门户监视设备</span><span class="sxs-lookup"><span data-stu-id="7d636-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="7d636-168">转到 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="7d636-168">Go to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="7d636-169">单击 **"设备列表"。**</span><span class="sxs-lookup"><span data-stu-id="7d636-169">Click **Devices list**.</span></span>

3. <span data-ttu-id="7d636-170">验证设备是否显示。</span><span class="sxs-lookup"><span data-stu-id="7d636-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7d636-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="7d636-171">Related topics</span></span>
- [<span data-ttu-id="7d636-172">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="7d636-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="7d636-173">使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="7d636-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="7d636-174">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="7d636-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="7d636-175">载入非持久性虚拟桌面基础结构 (VDI) 设备。</span><span class="sxs-lookup"><span data-stu-id="7d636-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="7d636-176">在新载入的 Microsoft Defender 终结点设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="7d636-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="7d636-177">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="7d636-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
