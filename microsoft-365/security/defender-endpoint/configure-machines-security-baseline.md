---
title: 提高 Microsoft Defender 终结点安全基线的合规性
description: Microsoft Defender for Endpoint 安全基线设置安全控件以提供最佳保护。
keywords: Intune 管理， Microsoft Defender for Endpoint， Microsoft Defender， Microsoft Defender for Endpoint ASR， 安全基线
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fbdc0d02d4c5ba5cfda9773e62082217ba4f8c4e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933597"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="49159-104">提高 Microsoft Defender 终结点安全基线的合规性</span><span class="sxs-lookup"><span data-stu-id="49159-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="49159-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="49159-105">**Applies to:**</span></span>
- [<span data-ttu-id="49159-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="49159-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="49159-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49159-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="49159-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="49159-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="49159-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="49159-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="49159-110">安全基线可确保根据安全专家和专家 Windows 系统管理员的指导配置安全功能。</span><span class="sxs-lookup"><span data-stu-id="49159-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="49159-111">部署后，Defender for Endpoint 安全基线将设置 Defender for Endpoint 安全控件以提供最佳保护。</span><span class="sxs-lookup"><span data-stu-id="49159-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="49159-112">若要了解安全基线以及如何使用配置文件在 Intune 上分配这些基线， [请阅读此常见问题](https://docs.microsoft.com/intune/security-baselines#q--a)解答。</span><span class="sxs-lookup"><span data-stu-id="49159-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="49159-113">在部署和跟踪安全基线的合规性之前：</span><span class="sxs-lookup"><span data-stu-id="49159-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="49159-114">将设备注册到 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="49159-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="49159-115">确保您具有必要的权限</span><span class="sxs-lookup"><span data-stu-id="49159-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="49159-116">比较 Microsoft Defender for Endpoint 和 Windows Intune 安全基线</span><span class="sxs-lookup"><span data-stu-id="49159-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="49159-117">Windows Intune 安全基线提供了一组全面的建议设置，用于安全配置运行 Windows 的设备，包括浏览器设置、PowerShell 设置以及某些安全功能（如 Microsoft Defender 防病毒）的设置。</span><span class="sxs-lookup"><span data-stu-id="49159-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="49159-118">相比之下，Defender for Endpoint 基线提供了优化 Defender for Endpoint 堆栈中所有安全控件的设置，包括终结点检测和响应 (EDR) 的设置以及 Windows Intune 安全基线中的设置。</span><span class="sxs-lookup"><span data-stu-id="49159-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="49159-119">有关每个基线详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="49159-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="49159-120">Intune 的 Windows 安全基线设置</span><span class="sxs-lookup"><span data-stu-id="49159-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="49159-121">Intune 的 Microsoft Defender for Endpoint 基线设置</span><span class="sxs-lookup"><span data-stu-id="49159-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="49159-122">理想情况下，已载入 Defender for Endpoint 的设备同时部署两个基线：Windows Intune 安全基线最初用于保护 Windows，然后是分层分层的 Defender for Endpoint 安全基线，以最佳方式配置 Defender for Endpoint 安全控件。</span><span class="sxs-lookup"><span data-stu-id="49159-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="49159-123">若要从有关风险和威胁的最新数据中获益，并随着基线的不断发展最大程度地减少冲突，请始终在发布所有产品后对所有产品应用基线的最新版本。</span><span class="sxs-lookup"><span data-stu-id="49159-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="49159-124">Defender for Endpoint 安全基线已针对物理设备进行了优化，当前不建议在虚拟机 (VM 或 VDI) 使用。</span><span class="sxs-lookup"><span data-stu-id="49159-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="49159-125">某些基线设置可能会影响虚拟化环境的远程交互式会话。</span><span class="sxs-lookup"><span data-stu-id="49159-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="49159-126">监视对 Defender for Endpoint 安全基线的合规性</span><span class="sxs-lookup"><span data-stu-id="49159-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="49159-127">设备 **配置** 管理上的安全基线 [卡](configure-machines.md) 概述了分配了 Defender for Endpoint 安全基线的 Windows 10 设备的合规性。</span><span class="sxs-lookup"><span data-stu-id="49159-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="49159-128">![安全基线卡](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="49159-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="49159-129">*显示 Defender for Endpoint 安全基线合规性的卡片*</span><span class="sxs-lookup"><span data-stu-id="49159-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="49159-130">每台设备都给定以下状态类型之一：</span><span class="sxs-lookup"><span data-stu-id="49159-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="49159-131">**匹配基线**- 设备设置与基线中的所有设置匹配</span><span class="sxs-lookup"><span data-stu-id="49159-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="49159-132">**与基线不匹配**— 至少一个设备设置与基线不匹配</span><span class="sxs-lookup"><span data-stu-id="49159-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="49159-133">**配置错误**— 设备上未正确配置至少一个基线设置，并且处于冲突、错误或挂起状态</span><span class="sxs-lookup"><span data-stu-id="49159-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="49159-134">**不适用**— 设备上至少有一个基线设置不适用</span><span class="sxs-lookup"><span data-stu-id="49159-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="49159-135">若要查看特定设备，请选择 **"在卡上** 配置安全基线"。</span><span class="sxs-lookup"><span data-stu-id="49159-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="49159-136">这会将你带去 Intune 设备管理。</span><span class="sxs-lookup"><span data-stu-id="49159-136">This takes you to Intune device management.</span></span> <span data-ttu-id="49159-137">从其中， **为设备的** 名称和状态选择设备状态。</span><span class="sxs-lookup"><span data-stu-id="49159-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="49159-138">在设备配置管理页面上显示的聚合数据以及 Intune 中的概述屏幕上显示的聚合数据中，你可能会遇到差异。</span><span class="sxs-lookup"><span data-stu-id="49159-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="49159-139">查看并分配 Microsoft Defender for Endpoint 安全基线</span><span class="sxs-lookup"><span data-stu-id="49159-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="49159-140">设备配置管理仅监视专门分配了 Microsoft Defender 终结点安全基线的 Windows 10 设备的基线合规性。</span><span class="sxs-lookup"><span data-stu-id="49159-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="49159-141">你可以方便地查看基线并将其分配给 Intune 设备管理上的设备。</span><span class="sxs-lookup"><span data-stu-id="49159-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="49159-142">选择 **安全基线卡** 上的配置 **安全基线** 以转到 Intune 设备管理。</span><span class="sxs-lookup"><span data-stu-id="49159-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="49159-143">显示比较基准合规性的类似概述。</span><span class="sxs-lookup"><span data-stu-id="49159-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="49159-144">或者，你可以从所有服务 > Intune > 设备安全 > 安全基线 > **Microsoft Defender ATP** 基线导航到 Microsoft Azure 门户中的 Defender for Endpoint 安全基线。</span><span class="sxs-lookup"><span data-stu-id="49159-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="49159-145">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="49159-145">Create a new profile.</span></span>

   <span data-ttu-id="49159-146">![Intune 上的 Microsoft Defender for Endpoint 安全基线概述](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="49159-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="49159-147">*Intune 上的 Microsoft Defender for Endpoint 安全基线概述*</span><span class="sxs-lookup"><span data-stu-id="49159-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="49159-148">创建配置文件期间，你可以查看和调整基线上的特定设置。</span><span class="sxs-lookup"><span data-stu-id="49159-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="49159-149">![在 Intune 上创建配置文件期间的安全基线选项](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="49159-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="49159-150">*在 Intune 上创建配置文件期间的安全基线选项*</span><span class="sxs-lookup"><span data-stu-id="49159-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="49159-151">将配置文件分配给相应的设备组。</span><span class="sxs-lookup"><span data-stu-id="49159-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="49159-152">![Intune 上的安全基线配置文件](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="49159-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="49159-153">*在 Intune 上分配安全基线配置文件*</span><span class="sxs-lookup"><span data-stu-id="49159-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="49159-154">创建配置文件以保存它并将其部署到分配的设备组。</span><span class="sxs-lookup"><span data-stu-id="49159-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="49159-155">![在 Intune 上分配安全基线](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="49159-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="49159-156">*在 Intune 上创建安全基线配置文件*</span><span class="sxs-lookup"><span data-stu-id="49159-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="49159-157">Intune 上的安全基线提供了一种全面保护设备的便捷方式。</span><span class="sxs-lookup"><span data-stu-id="49159-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="49159-158">[详细了解 Intune 上的安全基线](https://docs.microsoft.com/intune/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="49159-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="49159-159">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="49159-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="49159-160">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="49159-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="49159-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="49159-161">Related topics</span></span>
- [<span data-ttu-id="49159-162">确保设备配置正确</span><span class="sxs-lookup"><span data-stu-id="49159-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="49159-163">获取载入到 Microsoft Defender for Endpoint 的设备</span><span class="sxs-lookup"><span data-stu-id="49159-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="49159-164">优化 ASR 规则部署和检测</span><span class="sxs-lookup"><span data-stu-id="49159-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
