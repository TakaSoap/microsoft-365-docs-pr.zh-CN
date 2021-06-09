---
title: 确保设备配置正确
description: 正确配置设备以提升抵御威胁的整体复原能力，并增强检测和响应攻击的能力。
keywords: 载入， Intune 管理， Microsoft Defender for Endpoint， Microsoft Defender， Windows Defender， 攻击面减少， ASR， 安全基线
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dccc623bfa6c3f5e8fe4d88ccfafd66d3e53482a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840894"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="6f5c4-104">确保设备配置正确</span><span class="sxs-lookup"><span data-stu-id="6f5c4-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f5c4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6f5c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f5c4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f5c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6f5c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f5c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6f5c4-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6f5c4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f5c4-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="6f5c4-110">借助正确配置的设备，你可以提升抵御威胁的整体复原能力，并增强检测和响应攻击的能力。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="6f5c4-111">安全配置管理有助于确保你的设备：</span><span class="sxs-lookup"><span data-stu-id="6f5c4-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="6f5c4-112">载入到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f5c4-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="6f5c4-113">满足或超过 Defender for Endpoint 安全基线配置</span><span class="sxs-lookup"><span data-stu-id="6f5c4-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="6f5c4-114">已制定战略攻击面缓解措施</span><span class="sxs-lookup"><span data-stu-id="6f5c4-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="6f5c4-115">单击 **导航菜单中** 的"配置管理"以打开"设备配置管理"页。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="6f5c4-116">![安全配置管理页](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="6f5c4-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="6f5c4-117">*设备配置管理页*</span><span class="sxs-lookup"><span data-stu-id="6f5c4-117">*Device configuration management page*</span></span>

<span data-ttu-id="6f5c4-118">可以通过指向 Microsoft Intune 和 Microsoft 365 安全中心上的设备管理页面的直接深层链接，在组织级别跟踪配置状态并快速采取措施，以响应载入范围不佳、合规性问题以及攻击面缓解的不优化情况。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="6f5c4-119">在执行此操作时，您将受益于：</span><span class="sxs-lookup"><span data-stu-id="6f5c4-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="6f5c4-120">设备上事件的全面可见性</span><span class="sxs-lookup"><span data-stu-id="6f5c4-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="6f5c4-121">用于处理原始事件和识别泄露活动和威胁指示器的强大威胁情报和强大的设备学习技术</span><span class="sxs-lookup"><span data-stu-id="6f5c4-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="6f5c4-122">配置为有效停止安装恶意攻击、劫持系统文件和进程、数据外脏及其他威胁活动的完整安全功能堆栈</span><span class="sxs-lookup"><span data-stu-id="6f5c4-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="6f5c4-123">优化了攻击面缓解，最大程度地提高了威胁活动的战略防御能力，同时最大限度地减少了对工作效率的影响</span><span class="sxs-lookup"><span data-stu-id="6f5c4-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="6f5c4-124">将设备注册到 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="6f5c4-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="6f5c4-125">设备配置管理与 Intune 设备管理密切合作，以建立组织中设备的清单和基线安全配置。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="6f5c4-126">你将能够在 Intune 托管的设备上跟踪和管理Windows 10问题。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="6f5c4-127">在确保设备配置正确之前，请将其注册到 Intune 管理。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="6f5c4-128">Intune 注册很可靠，并且具有多个适用于Windows 10注册选项。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="6f5c4-129">有关 Intune 注册选项的详细信息，请阅读有关为设备Windows[注册的信息](/intune/windows-enroll)。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="6f5c4-130">若要Windows设备注册到 Intune，管理员必须已分配有许可证。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="6f5c4-131">[阅读有关分配设备注册许可证的信息](/intune/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-131">[Read about assigning licenses for device enrollment](/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="6f5c4-132">若要通过 Intune 优化设备管理， [请将 Intune 连接到 Defender for Endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="6f5c4-133">获取所需权限</span><span class="sxs-lookup"><span data-stu-id="6f5c4-133">Obtain required permissions</span></span>
<span data-ttu-id="6f5c4-134">默认情况下，只有已分配有 Azure AD 上的全局管理员或 Intune 服务管理员角色的用户才能管理和分配载入设备和部署安全基线所需的设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="6f5c4-135">如果已分配有其他角色，请确保你拥有必要的权限：</span><span class="sxs-lookup"><span data-stu-id="6f5c4-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="6f5c4-136">设备配置的完整权限</span><span class="sxs-lookup"><span data-stu-id="6f5c4-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="6f5c4-137">对安全基线的完全权限</span><span class="sxs-lookup"><span data-stu-id="6f5c4-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="6f5c4-138">读取设备合规性策略的权限</span><span class="sxs-lookup"><span data-stu-id="6f5c4-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="6f5c4-139">读取对组织的权限</span><span class="sxs-lookup"><span data-stu-id="6f5c4-139">Read permissions to the organization</span></span>

<span data-ttu-id="6f5c4-140">![intune 上所需的权限](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="6f5c4-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="6f5c4-141">*Intune 上的设备配置权限*</span><span class="sxs-lookup"><span data-stu-id="6f5c4-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="6f5c4-142">若要了解有关在 Intune 上分配权限有关详细信息，[请阅读有关创建自定义角色。](/intune/create-custom-role#to-create-a-custom-role)</span><span class="sxs-lookup"><span data-stu-id="6f5c4-142">To learn more about assigning permissions on Intune, [read about creating custom roles](/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6f5c4-143">本节内容</span><span class="sxs-lookup"><span data-stu-id="6f5c4-143">In this section</span></span>
<span data-ttu-id="6f5c4-144">主题</span><span class="sxs-lookup"><span data-stu-id="6f5c4-144">Topic</span></span> | <span data-ttu-id="6f5c4-145">说明</span><span class="sxs-lookup"><span data-stu-id="6f5c4-145">Description</span></span>
:---|:---
[<span data-ttu-id="6f5c4-146">将设备载入到 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f5c4-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="6f5c4-147">跟踪 Intune 托管设备的载入状态，并通过 Intune 载入更多设备。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="6f5c4-148">提高 Defender for Endpoint 安全基线的合规性</span><span class="sxs-lookup"><span data-stu-id="6f5c4-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="6f5c4-149">跟踪基线合规性和不符合情况。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="6f5c4-150">将安全基线部署到更多 Intune 托管的设备。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="6f5c4-151">优化 ASR 规则部署和检测</span><span class="sxs-lookup"><span data-stu-id="6f5c4-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="6f5c4-152">查看规则部署，然后使用安全中心内的影响分析工具Microsoft 365检测。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="6f5c4-153">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6f5c4-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f5c4-154">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6f5c4-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
