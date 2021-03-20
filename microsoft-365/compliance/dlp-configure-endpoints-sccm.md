---
title: 使用 Configuration Manager 载入 Windows 10 设备
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
description: 使用 Configuration Manager 在设备上部署配置包，以便它们可以载入服务。
ms.openlocfilehash: a84222d7654c6fb9ccab4275273e9e9c2c189790
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917998"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="70a0a-103">使用 Configuration Manager 载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="70a0a-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="70a0a-104">**Applies to:**</span></span>

- [<span data-ttu-id="70a0a-105">Microsoft 365 终结点数据丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="70a0a-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="70a0a-106">系统中心 2012 R2 配置管理器</span><span class="sxs-lookup"><span data-stu-id="70a0a-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="70a0a-107">使用 System Center Configuration Manager 载入设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="70a0a-108">打开 Configuration Manager 配置包 .zip *(DeviceComplianceOnboardingPackage.zip)* 从服务载入向导下载的文件。</span><span class="sxs-lookup"><span data-stu-id="70a0a-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="70a0a-109">您还可以从 Microsoft 合规性中心 [获取程序包](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="70a0a-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="70a0a-110">在导航窗格中，选择"**设置**  >  **设备载入**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="70a0a-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="70a0a-111">在"**部署方法"** 字段中，选择 **"Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602"。**</span><span class="sxs-lookup"><span data-stu-id="70a0a-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="70a0a-112">选择 **"下载程序包**"，然后保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="70a0a-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="70a0a-113">将 .zip 文件的内容提取到将部署包的网络管理员可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="70a0a-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="70a0a-114">你应该有一个名为 *DeviceComplianceOnboardingScript.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="70a0a-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="70a0a-115">按照 R2 Configuration Manager 中的程序包System Center 2012 [中的步骤部署](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) 程序包。</span><span class="sxs-lookup"><span data-stu-id="70a0a-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="70a0a-116">选择要将程序包部署到的预定义设备集合。</span><span class="sxs-lookup"><span data-stu-id="70a0a-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="70a0a-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-of-Box Experience (OOBE) ](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span><span class="sxs-lookup"><span data-stu-id="70a0a-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="70a0a-118">确保用户在运行 Windows 安装或升级后完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="70a0a-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="70a0a-119">载入设备后，你可以选择运行检测测试来验证设备是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="70a0a-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="70a0a-120">有关详细信息，请参阅对新载入的 [Microsoft Defender ATP](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)设备运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="70a0a-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="70a0a-121">请注意，在 Configuration Manager 应用程序上创建检测规则可以持续检查设备是否已载入。</span><span class="sxs-lookup"><span data-stu-id="70a0a-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="70a0a-122">应用程序是一种与包和程序不同的对象类型。</span><span class="sxs-lookup"><span data-stu-id="70a0a-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="70a0a-123">如果由于挂起的 OOBE (或其他任何原因) ，设备尚未载入，Configuration Manager 将重试载入设备，直到规则检测到状态更改。</span><span class="sxs-lookup"><span data-stu-id="70a0a-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="70a0a-124">通过创建检测规则检查"OnboardingState"注册表值是否为 (= 1，REG_DWORD) 实现此行为。</span><span class="sxs-lookup"><span data-stu-id="70a0a-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="70a0a-125">此注册表值位于"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"下。</span><span class="sxs-lookup"><span data-stu-id="70a0a-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="70a0a-126">有关详细信息，请参阅 Configure [Detection Methods in System Center 2012 R2 Configuration Manager。](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="70a0a-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="70a0a-127">配置示例集合设置</span><span class="sxs-lookup"><span data-stu-id="70a0a-127">Configure sample collection settings</span></span>

<span data-ttu-id="70a0a-128">对于每个设备，你可以设置一个配置值，以指示当通过 Microsoft Defender 安全中心提出提交文件进行深入分析的请求时是否可以从该设备收集示例。</span><span class="sxs-lookup"><span data-stu-id="70a0a-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="70a0a-129">这些配置设置通常通过 Configuration Manager 完成。</span><span class="sxs-lookup"><span data-stu-id="70a0a-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="70a0a-130">可以在 Configuration Manager 中为配置项设置合规性规则，以更改设备上的示例共享设置。</span><span class="sxs-lookup"><span data-stu-id="70a0a-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="70a0a-131">此规则应为 *修正合规性* 规则配置项，用于设置目标设备上注册表项的值，以确保它们有投诉。</span><span class="sxs-lookup"><span data-stu-id="70a0a-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="70a0a-132">通过以下注册表项设置配置：</span><span class="sxs-lookup"><span data-stu-id="70a0a-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="70a0a-133">其中：</span><span class="sxs-lookup"><span data-stu-id="70a0a-133">Where:</span></span><br>
<span data-ttu-id="70a0a-134">键类型为 D-WORD。</span><span class="sxs-lookup"><span data-stu-id="70a0a-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="70a0a-135">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="70a0a-135">Possible values are:</span></span>
- <span data-ttu-id="70a0a-136">0 - 不允许从此设备共享示例</span><span class="sxs-lookup"><span data-stu-id="70a0a-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="70a0a-137">1 - 允许从此设备共享所有文件类型</span><span class="sxs-lookup"><span data-stu-id="70a0a-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="70a0a-138">如果注册表项不存在，则默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="70a0a-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="70a0a-139">有关 System Center Configuration Manager 合规性的信息，请参阅 [System Center 2012 R2 Configuration Manager 中的合规性设置简介](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="70a0a-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="70a0a-140">其他建议的配置设置</span><span class="sxs-lookup"><span data-stu-id="70a0a-140">Other recommended configuration settings</span></span>
<span data-ttu-id="70a0a-141">将设备载入服务后，必须利用包含的威胁防护功能，通过以下建议的配置设置启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="70a0a-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="70a0a-142">设备集合配置</span><span class="sxs-lookup"><span data-stu-id="70a0a-142">Device collection configuration</span></span>
<span data-ttu-id="70a0a-143">如果你使用的是 Endpoint Configuration Manager 版本 2002 或更高版本，可以选择扩大部署范围以包括服务器或低级别客户端。</span><span class="sxs-lookup"><span data-stu-id="70a0a-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="70a0a-144">下一代保护配置</span><span class="sxs-lookup"><span data-stu-id="70a0a-144">Next generation protection configuration</span></span>

<span data-ttu-id="70a0a-145">建议使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="70a0a-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="70a0a-146">**扫描**</span><span class="sxs-lookup"><span data-stu-id="70a0a-146">**Scan**</span></span>

- <span data-ttu-id="70a0a-147">扫描可移动存储设备（如 USB 驱动器）：是</span><span class="sxs-lookup"><span data-stu-id="70a0a-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="70a0a-148">**实时保护**</span><span class="sxs-lookup"><span data-stu-id="70a0a-148">**Real-time Protection**</span></span>

- <span data-ttu-id="70a0a-149">启用行为监视：是</span><span class="sxs-lookup"><span data-stu-id="70a0a-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="70a0a-150">在下载时和安装之前启用对可能不需要的应用程序的保护：是</span><span class="sxs-lookup"><span data-stu-id="70a0a-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="70a0a-151">**云保护服务**</span><span class="sxs-lookup"><span data-stu-id="70a0a-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="70a0a-152">云保护服务成员身份类型：高级成员身份</span><span class="sxs-lookup"><span data-stu-id="70a0a-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="70a0a-153">**攻击面减少** 将所有可用规则配置为审核。</span><span class="sxs-lookup"><span data-stu-id="70a0a-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="70a0a-154">阻止这些活动可能会中断合法的业务流程。</span><span class="sxs-lookup"><span data-stu-id="70a0a-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="70a0a-155">最佳方法是设置要审核的所有内容，确定哪些内容可安全打开，然后在没有误报检测的终结点上启用这些设置。</span><span class="sxs-lookup"><span data-stu-id="70a0a-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="70a0a-156">**网络保护**</span><span class="sxs-lookup"><span data-stu-id="70a0a-156">**Network protection**</span></span>

<span data-ttu-id="70a0a-157">在审核或阻止模式下启用网络保护之前，请确保你已安装反恶意软件平台更新，该更新可以从支持 [页面获取](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)。</span><span class="sxs-lookup"><span data-stu-id="70a0a-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="70a0a-158">**受控文件夹访问权限**</span><span class="sxs-lookup"><span data-stu-id="70a0a-158">**Controlled folder access**</span></span>

<span data-ttu-id="70a0a-159">在审核模式下启用该功能至少 30 天。</span><span class="sxs-lookup"><span data-stu-id="70a0a-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="70a0a-160">在此时间段后，检查检测并创建允许写入受保护目录的应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="70a0a-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="70a0a-161">有关详细信息，请参阅评估 [受控文件夹访问权限](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)。</span><span class="sxs-lookup"><span data-stu-id="70a0a-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="70a0a-162">使用 Configuration Manager 的载出设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="70a0a-163">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="70a0a-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="70a0a-164">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="70a0a-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="70a0a-165">下载载出包时，你将收到程序包到期日期的通知，并且该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="70a0a-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="70a0a-166">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="70a0a-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="70a0a-167">使用 Microsoft Endpoint Configuration Manager 当前分支的载出设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="70a0a-168">如果使用 Microsoft Endpoint Configuration Manager 当前分支，请参阅 [创建载出配置文件](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="70a0a-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="70a0a-169">使用 R2 Configuration Manager System Center 2012载设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="70a0a-170">从 Microsoft 合规性中心获取载 [出包](https://compliance.microsoft.com/)：</span><span class="sxs-lookup"><span data-stu-id="70a0a-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="70a0a-171">在导航窗格中，选择"**设置**  >   **""设备载入** >  **""载出"。**</span><span class="sxs-lookup"><span data-stu-id="70a0a-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="70a0a-172">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="70a0a-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="70a0a-173">在"**部署方法"** 字段中，选择 **"Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602"。**</span><span class="sxs-lookup"><span data-stu-id="70a0a-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="70a0a-174">选择 **"下载程序包**"，然后保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="70a0a-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="70a0a-175">将 .zip 文件的内容提取到将部署包的网络管理员可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="70a0a-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="70a0a-176">你应该有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="70a0a-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="70a0a-177">按照 R2 Configuration Manager 中的程序包System Center 2012 [中的步骤部署](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) 程序包。</span><span class="sxs-lookup"><span data-stu-id="70a0a-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="70a0a-178">选择要将程序包部署到的预定义设备集合。</span><span class="sxs-lookup"><span data-stu-id="70a0a-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70a0a-179">"载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="70a0a-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="70a0a-180">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="70a0a-180">Monitor device configuration</span></span>

<span data-ttu-id="70a0a-181">如果你使用的是 Microsoft Endpoint Configuration Manager 当前分支，请使用 Configuration Manager 控制台中的内置 Microsoft Defender ATP 仪表板。</span><span class="sxs-lookup"><span data-stu-id="70a0a-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="70a0a-182">有关详细信息，请参阅 [Microsoft Defender 高级威胁防护 - 监视](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。</span><span class="sxs-lookup"><span data-stu-id="70a0a-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="70a0a-183">如果使用 R2 配置System Center 2012，监视由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="70a0a-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="70a0a-184">确认配置包已正确部署，并且正在 (或已成功) 网络中设备上运行配置包。</span><span class="sxs-lookup"><span data-stu-id="70a0a-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="70a0a-185">检查设备是否符合 Microsoft 365 终结点数据丢失防护服务 (这可确保设备可以完成载入过程，并可以继续将数据报告给服务) 。</span><span class="sxs-lookup"><span data-stu-id="70a0a-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="70a0a-186">确认配置包已正确部署</span><span class="sxs-lookup"><span data-stu-id="70a0a-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="70a0a-187">在 Configuration Manager 控制台中 **，单击导航** 窗格底部的"监视"。</span><span class="sxs-lookup"><span data-stu-id="70a0a-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="70a0a-188">选择 **"概述**"，然后选择"**部署"。**</span><span class="sxs-lookup"><span data-stu-id="70a0a-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="70a0a-189">使用程序包名称选择部署。</span><span class="sxs-lookup"><span data-stu-id="70a0a-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="70a0a-190">查看"完成统计信息"和 **"内容** 状态" **下的状态指示器**。</span><span class="sxs-lookup"><span data-stu-id="70a0a-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="70a0a-191">如果设备部署失败 (错误、不满足要求或失败状态) ，你可能需要对设备进行故障排除。 </span><span class="sxs-lookup"><span data-stu-id="70a0a-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="70a0a-192">有关详细信息，请参阅 Microsoft [Defender 高级威胁防护载入问题疑难解答](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="70a0a-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![显示成功部署（无错误）的 Configuration Manager](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="70a0a-194">检查设备是否符合 Microsoft 365 终结点数据丢失防护服务</span><span class="sxs-lookup"><span data-stu-id="70a0a-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="70a0a-195">可以在 R2 Configuration Manager 中为配置项设置System Center 2012规则，以监视部署。</span><span class="sxs-lookup"><span data-stu-id="70a0a-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="70a0a-196">此过程和注册表项适用于 Endpoint DLP 以及高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="70a0a-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="70a0a-197">此规则应为非 *修正* 性合规性规则配置项，用于监视目标设备上注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="70a0a-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="70a0a-198">监视以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="70a0a-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="70a0a-199">有关详细信息，请参阅 System Center 2012 [R2 Configuration Manager 中的合规性设置简介](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="70a0a-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="70a0a-200">相关主题</span><span class="sxs-lookup"><span data-stu-id="70a0a-200">Related topics</span></span>
- [<span data-ttu-id="70a0a-201">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="70a0a-202">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="70a0a-203">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="70a0a-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="70a0a-204">载入非持久性虚拟桌面基础结构 (VDI) 设备。</span><span class="sxs-lookup"><span data-stu-id="70a0a-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="70a0a-205">在新载入的 Microsoft Defender ATP 设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="70a0a-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="70a0a-206">Microsoft Defender 高级威胁防护载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="70a0a-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)