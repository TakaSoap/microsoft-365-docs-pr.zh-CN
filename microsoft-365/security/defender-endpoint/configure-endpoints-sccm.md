---
title: 使用 Configuration Manager 载入 Windows 10 设备
description: 使用 Configuration Manager 在设备上部署配置包，以便它们可以载入服务。
keywords: 使用 sccm 载入设备， 设备管理， 为终结点设备配置 Microsoft Defender
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
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: e919f697048840b0eb7bffd34914328fe233f823
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935157"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="204cb-104">使用 Configuration Manager 载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="204cb-104">Onboard Windows 10 devices using Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="204cb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="204cb-105">**Applies to:**</span></span>

- [<span data-ttu-id="204cb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="204cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="204cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="204cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="204cb-108">Microsoft Endpoint Configuration Manager 当前分支</span><span class="sxs-lookup"><span data-stu-id="204cb-108">Microsoft Endpoint Configuration Manager current branch</span></span>
- <span data-ttu-id="204cb-109">系统中心 2012 R2 配置管理器</span><span class="sxs-lookup"><span data-stu-id="204cb-109">System Center 2012 R2 Configuration Manager</span></span>

><span data-ttu-id="204cb-110">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="204cb-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="204cb-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="204cb-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a><span data-ttu-id="204cb-112">支持的客户端操作系统</span><span class="sxs-lookup"><span data-stu-id="204cb-112">Supported client operating systems</span></span>

<span data-ttu-id="204cb-113">根据正在运行的 Configuration Manager 版本，可以载入以下客户端操作系统：</span><span class="sxs-lookup"><span data-stu-id="204cb-113">Based on the version of Configuration Manager you're running, the following client operating systems can be onboarded:</span></span>

#### <a name="configuration-manager-version-1910-and-prior"></a><span data-ttu-id="204cb-114">Configuration Manager 版本 1910 及之前版本</span><span class="sxs-lookup"><span data-stu-id="204cb-114">Configuration Manager version 1910 and prior</span></span>

- <span data-ttu-id="204cb-115">运行 Windows 10 的客户端计算机</span><span class="sxs-lookup"><span data-stu-id="204cb-115">Clients computers running Windows 10</span></span> 

#### <a name="configuration-manager-version-2002-and-later"></a><span data-ttu-id="204cb-116">Configuration Manager 版本 2002 及更高版本</span><span class="sxs-lookup"><span data-stu-id="204cb-116">Configuration Manager version 2002 and later</span></span>

<span data-ttu-id="204cb-117">从 Configuration Manager 版本 2002 开始，你可以载入以下操作系统：</span><span class="sxs-lookup"><span data-stu-id="204cb-117">Starting in Configuration Manager version 2002, you can onboard the following operating systems:</span></span>

- <span data-ttu-id="204cb-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="204cb-118">Windows 8.1</span></span>
- <span data-ttu-id="204cb-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="204cb-119">Windows 10</span></span>
- <span data-ttu-id="204cb-120">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="204cb-120">Windows Server 2012 R2</span></span>
- <span data-ttu-id="204cb-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="204cb-121">Windows Server 2016</span></span>
- <span data-ttu-id="204cb-122">Windows Server 2016 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="204cb-122">Windows Server 2016, version 1803 or later</span></span>
- <span data-ttu-id="204cb-123">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="204cb-123">Windows Server 2019</span></span>

>[!NOTE]
><span data-ttu-id="204cb-124">若要详细了解如何载入 Windows Server 2012 R2、Windows Server 2016 和 Windows Server 2019，请参阅载入 [Windows 服务器](configure-server-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="204cb-124">For more information on how to onboard Windows Server 2012 R2, Windows Server 2016, and Windows Server 2019, see, [Onboard Windows servers](configure-server-endpoints.md).</span></span>



### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="204cb-125">使用 System Center Configuration Manager 载入设备</span><span class="sxs-lookup"><span data-stu-id="204cb-125">Onboard devices using System Center Configuration Manager</span></span>


<span data-ttu-id="204cb-126">[![显示各种部署路径的 PDF 图像](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="204cb-126">[![Image of the PDF showing the various deployment paths](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span></span>


<span data-ttu-id="204cb-127">请查看 [PDF 或](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 以查看部署 Microsoft Defender for Endpoint 的各种路径。</span><span class="sxs-lookup"><span data-stu-id="204cb-127">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span> 



1. <span data-ttu-id="204cb-128">打开 Configuration Manager 配置包 .zip *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的文件。</span><span class="sxs-lookup"><span data-stu-id="204cb-128">Open the Configuration Manager configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="204cb-129">还可以从 Microsoft Defender 安全中心 [获取程序包](https://securitycenter.windows.com/)：</span><span class="sxs-lookup"><span data-stu-id="204cb-129">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="204cb-130">在导航窗格中，选择"**设置**  >  **""载入"。**</span><span class="sxs-lookup"><span data-stu-id="204cb-130">In the navigation pane, select **Settings** > **Onboarding**.</span></span>
    
    1. <span data-ttu-id="204cb-131">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="204cb-131">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="204cb-132">在"**部署方法"** 字段中，选择 **"System Center Configuration Manager 2012/2012 R2/1511/1602"。**</span><span class="sxs-lookup"><span data-stu-id="204cb-132">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="204cb-133">选择 **"下载程序包**"，然后保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="204cb-133">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="204cb-134">将 .zip 文件的内容提取到将部署包的网络管理员可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="204cb-134">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="204cb-135">你应该有一个名为 *WindowsDefenderATPOnboardingScript.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="204cb-135">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="204cb-136">按照 R2 Configuration Manager 中的程序包System Center 2012 [中的步骤部署](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 程序包。</span><span class="sxs-lookup"><span data-stu-id="204cb-136">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="204cb-137">a.</span><span class="sxs-lookup"><span data-stu-id="204cb-137">a.</span></span> <span data-ttu-id="204cb-138">选择要将程序包部署到的预定义设备集合。</span><span class="sxs-lookup"><span data-stu-id="204cb-138">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="204cb-139">在 [OOBE ](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 体验阶段，Defender for Endpoint 不支持 (载入) 阶段。</span><span class="sxs-lookup"><span data-stu-id="204cb-139">Defender for Endpoint doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="204cb-140">确保用户在运行 Windows 安装或升级后完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="204cb-140">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="204cb-141">载入设备后，你可以选择运行检测测试来验证设备是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="204cb-141">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="204cb-142">有关详细信息，请参阅对新载入的适用于终结点 [设备的 Defender](run-detection-test.md)运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="204cb-142">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>
>
> <span data-ttu-id="204cb-143">请注意，在 Configuration Manager 应用程序上创建检测规则可以持续检查设备是否已载入。</span><span class="sxs-lookup"><span data-stu-id="204cb-143">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="204cb-144">应用程序是一种与包和程序不同的对象类型。</span><span class="sxs-lookup"><span data-stu-id="204cb-144">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="204cb-145">如果由于挂起的 OOBE (或其他任何原因) ，设备尚未载入，Configuration Manager 将重试载入设备，直到规则检测到状态更改。</span><span class="sxs-lookup"><span data-stu-id="204cb-145">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="204cb-146">通过创建检测规则检查"OnboardingState"注册表值是否为 (= 1，REG_DWORD) 实现此行为。</span><span class="sxs-lookup"><span data-stu-id="204cb-146">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="204cb-147">此注册表值位于"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"下。</span><span class="sxs-lookup"><span data-stu-id="204cb-147">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="204cb-148">有关详细信息，请参阅 Configure [Detection Methods in System Center 2012 R2 Configuration Manager。](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="204cb-148">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="204cb-149">配置示例集合设置</span><span class="sxs-lookup"><span data-stu-id="204cb-149">Configure sample collection settings</span></span>

<span data-ttu-id="204cb-150">对于每个设备，你可以设置一个配置值，以指示当通过 Microsoft Defender 安全中心提出提交文件进行深入分析的请求时是否可以从该设备收集示例。</span><span class="sxs-lookup"><span data-stu-id="204cb-150">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="204cb-151">这些配置设置通常通过 Configuration Manager 完成。</span><span class="sxs-lookup"><span data-stu-id="204cb-151">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="204cb-152">可以在 Configuration Manager 中为配置项设置合规性规则，以更改设备上的示例共享设置。</span><span class="sxs-lookup"><span data-stu-id="204cb-152">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="204cb-153">此规则应为 *修正合规性* 规则配置项，用于设置目标设备上注册表项的值，以确保它们有投诉。</span><span class="sxs-lookup"><span data-stu-id="204cb-153">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="204cb-154">通过以下注册表项设置配置：</span><span class="sxs-lookup"><span data-stu-id="204cb-154">The configuration is set through the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

<span data-ttu-id="204cb-155">其中：</span><span class="sxs-lookup"><span data-stu-id="204cb-155">Where:</span></span><br>
<span data-ttu-id="204cb-156">键类型为 D-WORD。</span><span class="sxs-lookup"><span data-stu-id="204cb-156">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="204cb-157">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="204cb-157">Possible values are:</span></span>
- <span data-ttu-id="204cb-158">0 - 不允许从此设备共享示例</span><span class="sxs-lookup"><span data-stu-id="204cb-158">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="204cb-159">1 - 允许从此设备共享所有文件类型</span><span class="sxs-lookup"><span data-stu-id="204cb-159">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="204cb-160">如果注册表项不存在，则默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="204cb-160">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="204cb-161">有关 System Center Configuration Manager 合规性的信息，请参阅 [System Center 2012 R2 Configuration Manager 中的合规性设置简介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。</span><span class="sxs-lookup"><span data-stu-id="204cb-161">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="204cb-162">其他建议的配置设置</span><span class="sxs-lookup"><span data-stu-id="204cb-162">Other recommended configuration settings</span></span>
<span data-ttu-id="204cb-163">将设备载入服务后，必须利用包含的威胁防护功能，通过以下建议的配置设置启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="204cb-163">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="204cb-164">设备集合配置</span><span class="sxs-lookup"><span data-stu-id="204cb-164">Device collection configuration</span></span>
<span data-ttu-id="204cb-165">如果你使用的是 Endpoint Configuration Manager 版本 2002 或更高版本，可以选择扩大部署范围以包括服务器或低级别客户端。</span><span class="sxs-lookup"><span data-stu-id="204cb-165">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="204cb-166">下一代保护配置</span><span class="sxs-lookup"><span data-stu-id="204cb-166">Next generation protection configuration</span></span>
<span data-ttu-id="204cb-167">建议使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="204cb-167">The following configuration settings are recommended:</span></span>

<span data-ttu-id="204cb-168">**扫描**</span><span class="sxs-lookup"><span data-stu-id="204cb-168">**Scan**</span></span> <br>
- <span data-ttu-id="204cb-169">扫描可移动存储设备（如 USB 驱动器）：是</span><span class="sxs-lookup"><span data-stu-id="204cb-169">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="204cb-170">**实时保护**</span><span class="sxs-lookup"><span data-stu-id="204cb-170">**Real-time Protection**</span></span> <br>
- <span data-ttu-id="204cb-171">启用行为监视：是</span><span class="sxs-lookup"><span data-stu-id="204cb-171">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="204cb-172">在下载时和安装之前启用对可能不需要的应用程序的保护：是</span><span class="sxs-lookup"><span data-stu-id="204cb-172">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="204cb-173">**云保护服务**</span><span class="sxs-lookup"><span data-stu-id="204cb-173">**Cloud Protection Service**</span></span>
- <span data-ttu-id="204cb-174">云保护服务成员身份类型：高级成员身份</span><span class="sxs-lookup"><span data-stu-id="204cb-174">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="204cb-175">**攻击面减少** 将所有可用规则配置为审核。</span><span class="sxs-lookup"><span data-stu-id="204cb-175">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="204cb-176">阻止这些活动可能会中断合法的业务流程。</span><span class="sxs-lookup"><span data-stu-id="204cb-176">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="204cb-177">最佳方法是设置要审核的所有内容，确定哪些内容可安全打开，然后在没有误报检测的终结点上启用这些设置。</span><span class="sxs-lookup"><span data-stu-id="204cb-177">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>


<span data-ttu-id="204cb-178">**网络保护**</span><span class="sxs-lookup"><span data-stu-id="204cb-178">**Network protection**</span></span> <br>
<span data-ttu-id="204cb-179">在审核或阻止模式下启用网络保护之前，请确保你已安装反恶意软件平台更新，该更新可以从支持 [页面获取](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)。</span><span class="sxs-lookup"><span data-stu-id="204cb-179">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="204cb-180">**受控文件夹访问**</span><span class="sxs-lookup"><span data-stu-id="204cb-180">**Controlled folder access**</span></span><br>
<span data-ttu-id="204cb-181">在审核模式下启用该功能至少 30 天。</span><span class="sxs-lookup"><span data-stu-id="204cb-181">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="204cb-182">在此时间段后，检查检测并创建允许写入受保护目录的应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="204cb-182">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="204cb-183">有关详细信息，请参阅评估 [受控文件夹访问权限](evaluate-controlled-folder-access.md)。</span><span class="sxs-lookup"><span data-stu-id="204cb-183">For more information, see [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="204cb-184">使用 Configuration Manager 的载出设备</span><span class="sxs-lookup"><span data-stu-id="204cb-184">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="204cb-185">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="204cb-185">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="204cb-186">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="204cb-186">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="204cb-187">下载载出包时，你将收到程序包到期日期的通知，并且该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="204cb-187">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="204cb-188">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="204cb-188">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a><span data-ttu-id="204cb-189">使用 Microsoft Endpoint Manager 当前分支的载出设备</span><span class="sxs-lookup"><span data-stu-id="204cb-189">Offboard devices using Microsoft Endpoint Manager current branch</span></span>

<span data-ttu-id="204cb-190">如果使用 Microsoft Endpoint Manager 当前分支，请参阅 [创建载出配置文件](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="204cb-190">If you use Microsoft Endpoint Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="204cb-191">使用 R2 Configuration Manager System Center 2012载设备</span><span class="sxs-lookup"><span data-stu-id="204cb-191">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="204cb-192">从 Microsoft Defender 安全中心获取载 [出程序包](https://securitycenter.windows.com/)：</span><span class="sxs-lookup"><span data-stu-id="204cb-192">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="204cb-193">在导航窗格中，选择"**设置**  >   **""载出"。**</span><span class="sxs-lookup"><span data-stu-id="204cb-193">In the navigation pane, select **Settings** >  **Offboarding**.</span></span>

    1. <span data-ttu-id="204cb-194">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="204cb-194">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="204cb-195">在"**部署方法"** 字段中，选择 **"System Center Configuration Manager 2012/2012 R2/1511/1602"。**</span><span class="sxs-lookup"><span data-stu-id="204cb-195">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="204cb-196">选择 **"下载程序包**"，然后保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="204cb-196">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="204cb-197">将 .zip 文件的内容提取到将部署包的网络管理员可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="204cb-197">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="204cb-198">你应该有一个名为 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="204cb-198">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="204cb-199">按照 R2 Configuration Manager 中的程序包System Center 2012 [中的步骤部署](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 程序包。</span><span class="sxs-lookup"><span data-stu-id="204cb-199">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="204cb-200">a.</span><span class="sxs-lookup"><span data-stu-id="204cb-200">a.</span></span> <span data-ttu-id="204cb-201">选择要将程序包部署到的预定义设备集合。</span><span class="sxs-lookup"><span data-stu-id="204cb-201">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="204cb-202">"载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="204cb-202">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="204cb-203">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="204cb-203">Monitor device configuration</span></span>

<span data-ttu-id="204cb-204">如果你使用的是 Microsoft Endpoint Manager 当前分支，请使用 Configuration Manager 控制台中的内置 Defender for Endpoint 仪表板。</span><span class="sxs-lookup"><span data-stu-id="204cb-204">If you're using Microsoft Endpoint Manager current branch, use the built-in Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="204cb-205">有关详细信息，请参阅 [Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。</span><span class="sxs-lookup"><span data-stu-id="204cb-205">For more information, see [Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="204cb-206">如果使用 R2 配置System Center 2012，监视由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="204cb-206">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="204cb-207">确认配置包已正确部署，并且正在 (或已成功) 网络中设备上运行配置包。</span><span class="sxs-lookup"><span data-stu-id="204cb-207">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="204cb-208">检查设备是否符合 Defender for Endpoint 服务 (这可确保设备可以完成载入过程，并可以继续将数据报告给服务) 。</span><span class="sxs-lookup"><span data-stu-id="204cb-208">Checking that the devices are compliant with the Defender for Endpoint service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="204cb-209">确认配置包已正确部署</span><span class="sxs-lookup"><span data-stu-id="204cb-209">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="204cb-210">在 Configuration Manager 控制台中 **，单击导航** 窗格底部的"监视"。</span><span class="sxs-lookup"><span data-stu-id="204cb-210">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="204cb-211">选择 **"概述**"，然后选择"**部署"。**</span><span class="sxs-lookup"><span data-stu-id="204cb-211">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="204cb-212">使用程序包名称选择部署。</span><span class="sxs-lookup"><span data-stu-id="204cb-212">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="204cb-213">查看"完成统计信息"和 **"内容** 状态" **下的状态指示器**。</span><span class="sxs-lookup"><span data-stu-id="204cb-213">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="204cb-214">如果设备部署失败 (错误、不满足要求或失败状态) ，你可能需要对设备进行故障排除。 </span><span class="sxs-lookup"><span data-stu-id="204cb-214">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="204cb-215">有关详细信息，请参阅 Microsoft [Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="204cb-215">For more information, see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>

    ![显示成功部署（无错误）的 Configuration Manager](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="204cb-217">检查设备是否符合 Microsoft Defender for Endpoint 服务</span><span class="sxs-lookup"><span data-stu-id="204cb-217">Check that the devices are compliant with the Microsoft Defender for Endpoint service</span></span>

<span data-ttu-id="204cb-218">可以在 R2 Configuration Manager 中为配置项设置System Center 2012规则，以监视部署。</span><span class="sxs-lookup"><span data-stu-id="204cb-218">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

<span data-ttu-id="204cb-219">此规则应为非 *修正* 性合规性规则配置项，用于监视目标设备上注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="204cb-219">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="204cb-220">监视以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="204cb-220">Monitor the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

<span data-ttu-id="204cb-221">有关详细信息，请参阅 System Center 2012 [R2 Configuration Manager 中的合规性设置简介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。</span><span class="sxs-lookup"><span data-stu-id="204cb-221">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="204cb-222">相关主题</span><span class="sxs-lookup"><span data-stu-id="204cb-222">Related topics</span></span>
- [<span data-ttu-id="204cb-223">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="204cb-223">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="204cb-224">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="204cb-224">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="204cb-225">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="204cb-225">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="204cb-226">载入非永久虚拟桌面基础结构 （VDI） 设备</span><span class="sxs-lookup"><span data-stu-id="204cb-226">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="204cb-227">在新载入的 Microsoft Defender 终结点设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="204cb-227">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="204cb-228">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="204cb-228">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
