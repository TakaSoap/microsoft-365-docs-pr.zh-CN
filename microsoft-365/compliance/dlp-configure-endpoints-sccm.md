---
title: 使用配置管理器的板载 Windows 10 设备
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
description: 使用 Configuration Manager 在设备上部署配置包，以使其载入服务。
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769407"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="d95ba-103">使用配置管理器的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="d95ba-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d95ba-104">**Applies to:**</span></span>

- [<span data-ttu-id="d95ba-105">Microsoft 365 Endpoint data 丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="d95ba-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="d95ba-106">系统中心 2012 R2 配置管理器</span><span class="sxs-lookup"><span data-stu-id="d95ba-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="d95ba-107">使用 System Center Configuration Manager 的板载设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="d95ba-108">打开您从 "服务载入" 向导下载 *DeviceComplianceOnboardingPackage.zip* )  (的 configuration Manager 配置包 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="d95ba-108">Open the Configuration Manager configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="d95ba-109">你也可以从 [Microsoft 合规性中心](https://compliance.microsoft.com/)获取该包。</span><span class="sxs-lookup"><span data-stu-id="d95ba-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="d95ba-110">在导航窗格中，选择 " **设置**  >  **设备** 启动加入"  >  **Onboarding** 。</span><span class="sxs-lookup"><span data-stu-id="d95ba-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="d95ba-111">在 " **部署方法** " 字段中，选择 " **Microsoft 终结点配置管理器 2012/2012 R2/1511/1602** "。</span><span class="sxs-lookup"><span data-stu-id="d95ba-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
 
4. <span data-ttu-id="d95ba-112">选择 " **下载包** "，并保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="d95ba-112">Select **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="d95ba-113">将 .zip 文件的内容提取到一个共享的只读位置，该位置可供将部署该包的网络管理员访问。</span><span class="sxs-lookup"><span data-stu-id="d95ba-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="d95ba-114">您应该具有一个名为 *DeviceComplianceOnboardingScript* 的文件。</span><span class="sxs-lookup"><span data-stu-id="d95ba-114">You should have a file named *DeviceComplianceOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="d95ba-115">按照 [System Center 2012 R2 Configuration Manager 一文中的程序包和程序](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 中的步骤部署程序包。</span><span class="sxs-lookup"><span data-stu-id="d95ba-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="d95ba-116">选择要将程序包部署到的预定义设备集合。</span><span class="sxs-lookup"><span data-stu-id="d95ba-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="d95ba-117">Microsoft 365 终结点数据丢失防护不支持在 [OOBE) 阶段 (的开箱 ](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 即用期间的载入。</span><span class="sxs-lookup"><span data-stu-id="d95ba-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="d95ba-118">确保在运行 Windows 安装或升级后，用户完成了 OOBE。</span><span class="sxs-lookup"><span data-stu-id="d95ba-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="d95ba-119">在载入设备后，您可以选择运行检测测试来验证设备是否已正确载入服务。</span><span class="sxs-lookup"><span data-stu-id="d95ba-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="d95ba-120">有关详细信息，请参阅 [在新载入上运行检测测试 Microsoft DEFENDER ATP 设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="d95ba-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="d95ba-121">请注意，可以在 Configuration Manager 应用程序上创建一个检测规则，以连续检查设备是否已载入。</span><span class="sxs-lookup"><span data-stu-id="d95ba-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="d95ba-122">应用程序是与包和程序不同的对象类型。</span><span class="sxs-lookup"><span data-stu-id="d95ba-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="d95ba-123">如果设备尚未载入 (由于挂起的 OOBE 完成或任何其他原因) ，配置管理器将重试设备板载，直到规则检测到状态更改。</span><span class="sxs-lookup"><span data-stu-id="d95ba-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="d95ba-124">如果 "OnboardingState" 注册表值 (的类型 REG_DWORD) = 1，则可以通过创建检测规则检查来实现此行为。</span><span class="sxs-lookup"><span data-stu-id="d95ba-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="d95ba-125">此注册表值位于 "HKLM\SOFTWARE\Microsoft\Windows 高级威胁 Protection\Status" 下。</span><span class="sxs-lookup"><span data-stu-id="d95ba-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="d95ba-126">有关详细信息，请参阅 [在 System Center 2012 R2 配置管理器中配置检测方法](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)。</span><span class="sxs-lookup"><span data-stu-id="d95ba-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="d95ba-127">配置示例集合设置</span><span class="sxs-lookup"><span data-stu-id="d95ba-127">Configure sample collection settings</span></span>

<span data-ttu-id="d95ba-128">对于每个设备，您可以设置一个配置值以表明通过 Microsoft Defender 安全中心发出请求以提交文件进行深入分析时，能否从设备收集示例。</span><span class="sxs-lookup"><span data-stu-id="d95ba-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="d95ba-129">这些配置设置通常通过配置管理器完成。</span><span class="sxs-lookup"><span data-stu-id="d95ba-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="d95ba-130">您可以为 Configuration Manager 中的配置项目设置符合性规则，以更改设备上的示例共享设置。</span><span class="sxs-lookup"><span data-stu-id="d95ba-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="d95ba-131">此规则应为 *补救* 合规性规则配置项，它在目标设备上设置注册表项的值，以确保它们是投诉。</span><span class="sxs-lookup"><span data-stu-id="d95ba-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="d95ba-132">通过以下注册表项设置配置：</span><span class="sxs-lookup"><span data-stu-id="d95ba-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="d95ba-133">其中：</span><span class="sxs-lookup"><span data-stu-id="d95ba-133">Where:</span></span><br>
<span data-ttu-id="d95ba-134">键类型为 D-字。</span><span class="sxs-lookup"><span data-stu-id="d95ba-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="d95ba-135">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="d95ba-135">Possible values are:</span></span>
- <span data-ttu-id="d95ba-136">0-不允许从此设备共享示例</span><span class="sxs-lookup"><span data-stu-id="d95ba-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="d95ba-137">1-允许共享此设备的所有文件类型</span><span class="sxs-lookup"><span data-stu-id="d95ba-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="d95ba-138">如果注册表项不存在，则默认值为1。</span><span class="sxs-lookup"><span data-stu-id="d95ba-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="d95ba-139">有关 System Center Configuration Manager 合规性的详细信息，请参阅 [System center 2012 R2 Configuration Manager 中的合规性设置简介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。</span><span class="sxs-lookup"><span data-stu-id="d95ba-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="d95ba-140">其他建议的配置设置</span><span class="sxs-lookup"><span data-stu-id="d95ba-140">Other recommended configuration settings</span></span>
<span data-ttu-id="d95ba-141">在将设备载入服务后，请务必充分利用包含的威胁防护功能，方法是使用以下建议的配置设置来启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="d95ba-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="d95ba-142">设备集合配置</span><span class="sxs-lookup"><span data-stu-id="d95ba-142">Device collection configuration</span></span>
<span data-ttu-id="d95ba-143">如果使用的是终结点配置管理器，版本2002或更高版本，则可以选择扩大部署以包含服务器或下层客户端。</span><span class="sxs-lookup"><span data-stu-id="d95ba-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="d95ba-144">下一代保护配置</span><span class="sxs-lookup"><span data-stu-id="d95ba-144">Next generation protection configuration</span></span>

<span data-ttu-id="d95ba-145">建议使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="d95ba-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="d95ba-146">**扫描**</span><span class="sxs-lookup"><span data-stu-id="d95ba-146">**Scan**</span></span>

- <span data-ttu-id="d95ba-147">扫描可移动存储设备（如 USB 驱动器）：是</span><span class="sxs-lookup"><span data-stu-id="d95ba-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="d95ba-148">**实时保护**</span><span class="sxs-lookup"><span data-stu-id="d95ba-148">**Real-time Protection**</span></span>

- <span data-ttu-id="d95ba-149">启用行为监视：是</span><span class="sxs-lookup"><span data-stu-id="d95ba-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="d95ba-150">在下载和安装之前针对可能不需要的应用程序启用保护：是</span><span class="sxs-lookup"><span data-stu-id="d95ba-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="d95ba-151">**云保护服务**</span><span class="sxs-lookup"><span data-stu-id="d95ba-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="d95ba-152">云保护服务成员身份类型：高级成员身份</span><span class="sxs-lookup"><span data-stu-id="d95ba-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="d95ba-153">**攻击面减少** 将所有可用的规则配置为 "审核"。</span><span class="sxs-lookup"><span data-stu-id="d95ba-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="d95ba-154">阻止这些活动可能会中断合法业务流程。</span><span class="sxs-lookup"><span data-stu-id="d95ba-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="d95ba-155">最佳方法是设置要审核的所有内容，确定哪些内容是安全的，然后在不具有误报检测的终结点上启用这些设置。</span><span class="sxs-lookup"><span data-stu-id="d95ba-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="d95ba-156">**网络保护**</span><span class="sxs-lookup"><span data-stu-id="d95ba-156">**Network protection**</span></span>

<span data-ttu-id="d95ba-157">在 "审核" 或 "阻止" 模式下启用网络保护之前，请确保已安装反恶意软件平台更新（可从 " [支持" 页面](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)获取）。</span><span class="sxs-lookup"><span data-stu-id="d95ba-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="d95ba-158">**受控文件夹访问**</span><span class="sxs-lookup"><span data-stu-id="d95ba-158">**Controlled folder access**</span></span>

<span data-ttu-id="d95ba-159">在审核模式下启用至少30天的功能。</span><span class="sxs-lookup"><span data-stu-id="d95ba-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="d95ba-160">在此时间段后，检查检测项并创建允许写入受保护目录的应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="d95ba-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="d95ba-161">有关详细信息，请参阅 [评估受控文件夹访问权限](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)。</span><span class="sxs-lookup"><span data-stu-id="d95ba-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="d95ba-162">使用配置管理器的分离设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="d95ba-163">出于安全考虑，用于分离设备的包将在下载后的30天后过期。</span><span class="sxs-lookup"><span data-stu-id="d95ba-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="d95ba-164">发送到设备的已过期的脱离程序包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="d95ba-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="d95ba-165">下载一个脱离程序包时，系统会通知你数据包到期日期，并且它也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="d95ba-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="d95ba-166">无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。</span><span class="sxs-lookup"><span data-stu-id="d95ba-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="d95ba-167">使用 Microsoft 终结点配置管理器的分离设备当前分支</span><span class="sxs-lookup"><span data-stu-id="d95ba-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="d95ba-168">如果使用 Microsoft 终结点配置管理器的当前分支，请参阅 [创建脱离配置文件](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="d95ba-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="d95ba-169">使用 System Center 2012 R2 配置管理器的分离设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="d95ba-170">从 [Microsoft 合规性中心](https://compliance.microsoft.com/)获取脱离包：</span><span class="sxs-lookup"><span data-stu-id="d95ba-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="d95ba-171">在导航窗格中，选择 " **设置**  >   **设备加入** >  **脱离** "。</span><span class="sxs-lookup"><span data-stu-id="d95ba-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding** .</span></span>

3. <span data-ttu-id="d95ba-172">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="d95ba-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="d95ba-173">在 " **部署方法** " 字段中，选择 " **Microsoft 终结点配置管理器 2012/2012 R2/1511/1602** "。</span><span class="sxs-lookup"><span data-stu-id="d95ba-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
    
5. <span data-ttu-id="d95ba-174">选择 " **下载包** "，并保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="d95ba-174">Select **Download package** , and save the .zip file.</span></span>

6. <span data-ttu-id="d95ba-175">将 .zip 文件的内容提取到一个共享的只读位置，该位置可供将部署该包的网络管理员访问。</span><span class="sxs-lookup"><span data-stu-id="d95ba-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="d95ba-176">您应具有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的文件。</span><span class="sxs-lookup"><span data-stu-id="d95ba-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

7. <span data-ttu-id="d95ba-177">按照 [System Center 2012 R2 Configuration Manager 一文中的程序包和程序](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 中的步骤部署程序包。</span><span class="sxs-lookup"><span data-stu-id="d95ba-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="d95ba-178">选择要将程序包部署到的预定义设备集合。</span><span class="sxs-lookup"><span data-stu-id="d95ba-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d95ba-179">脱离将导致设备停止向门户发送传感器数据，但设备中的数据（包括对其已有的任何警报的引用）将保留最长6个月。</span><span class="sxs-lookup"><span data-stu-id="d95ba-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="d95ba-180">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="d95ba-180">Monitor device configuration</span></span>

<span data-ttu-id="d95ba-181">如果使用的是 Microsoft 终结点配置管理器的当前分支，请使用 Configuration Manager 控制台中的内置 Microsoft Defender ATP 仪表板。</span><span class="sxs-lookup"><span data-stu-id="d95ba-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="d95ba-182">有关详细信息，请参阅 [Microsoft Defender 高级威胁防护-Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。</span><span class="sxs-lookup"><span data-stu-id="d95ba-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="d95ba-183">如果您使用的是 System Center 2012 R2 配置管理器，则监控由以下两部分组成：</span><span class="sxs-lookup"><span data-stu-id="d95ba-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="d95ba-184">确认配置包已正确部署，并且正在运行 (或已在网络中的设备上成功运行) 。</span><span class="sxs-lookup"><span data-stu-id="d95ba-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="d95ba-185">检查设备是否符合 Microsoft 365 终结点数据丢失防护服务 (这可确保设备能够完成载入过程，并可继续向服务) 报告数据。</span><span class="sxs-lookup"><span data-stu-id="d95ba-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="d95ba-186">确认配置包已正确部署</span><span class="sxs-lookup"><span data-stu-id="d95ba-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="d95ba-187">在 Configuration Manager 控制台中，单击导航窗格底部的 " **监视** "。</span><span class="sxs-lookup"><span data-stu-id="d95ba-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="d95ba-188">依次选择 " **概述** " 和 " **部署** "。</span><span class="sxs-lookup"><span data-stu-id="d95ba-188">Select **Overview** and then **Deployments** .</span></span>

3. <span data-ttu-id="d95ba-189">在部署中选择包名称。</span><span class="sxs-lookup"><span data-stu-id="d95ba-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="d95ba-190">查看 " **完成统计信息** " 和 " **内容状态** " 下的状态指示器。</span><span class="sxs-lookup"><span data-stu-id="d95ba-190">Review the status indicators under **Completion Statistics** and **Content Status** .</span></span>

    <span data-ttu-id="d95ba-191">如果有失败的部署 (设备出现 **错误** 、 **未满足要求** 或 **故障状态** ) ，则可能需要对设备进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="d95ba-191">If there are failed deployments (devices with **Error** , **Requirements Not Met** , or **Failed statuses** ), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="d95ba-192">有关详细信息，请参阅 [解决 Microsoft Defender 高级威胁防护载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="d95ba-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![显示无任何错误的成功部署的配置管理器](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="d95ba-194">检查设备是否符合 Microsoft 365 终结点数据丢失防护服务</span><span class="sxs-lookup"><span data-stu-id="d95ba-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="d95ba-195">您可以为 System Center 2012 R2 配置管理器中的配置项目设置符合性规则，以监视您的部署。</span><span class="sxs-lookup"><span data-stu-id="d95ba-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="d95ba-196">此过程和注册表项适用于终结点 DLP 以及高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="d95ba-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="d95ba-197">此规则应 *是非补救* 性规则配置项目，用于监视目标设备上的注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="d95ba-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="d95ba-198">监视以下注册表项项：</span><span class="sxs-lookup"><span data-stu-id="d95ba-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="d95ba-199">有关详细信息，请参阅 [System Center 2012 R2 Configuration Manager 中的合规性设置简介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。</span><span class="sxs-lookup"><span data-stu-id="d95ba-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d95ba-200">相关主题</span><span class="sxs-lookup"><span data-stu-id="d95ba-200">Related topics</span></span>
- [<span data-ttu-id="d95ba-201">使用组策略的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="d95ba-202">使用移动设备管理工具的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="d95ba-203">使用本地脚本的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="d95ba-204"> (VDI) 设备的板载非永久性虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="d95ba-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="d95ba-205">在新载入上运行检测测试 Microsoft Defender ATP 设备</span><span class="sxs-lookup"><span data-stu-id="d95ba-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="d95ba-206">解决 Microsoft Defender 高级威胁防护载入问题</span><span class="sxs-lookup"><span data-stu-id="d95ba-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
