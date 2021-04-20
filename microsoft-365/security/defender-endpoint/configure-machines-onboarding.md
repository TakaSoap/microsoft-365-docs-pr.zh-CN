---
title: 获取载入到 Microsoft Defender for Endpoint 的设备
description: 跟踪将 Intune 托管的设备载入到 Microsoft Defender for Endpoint 并增加载入率。
keywords: 载入， Intune 管理， MDATP， WDATP， Microsoft Defender， Windows Defender， 高级威胁防护， 配置管理
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
ms.openlocfilehash: 5e20c424f15561c8b6f0544b80aca6e30c56409d
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893325"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="3d68f-104">获取载入到 Microsoft Defender for Endpoint 的设备</span><span class="sxs-lookup"><span data-stu-id="3d68f-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d68f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3d68f-105">**Applies to:**</span></span>
- [<span data-ttu-id="3d68f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3d68f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3d68f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d68f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3d68f-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3d68f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3d68f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3d68f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="3d68f-110">每个载入的设备在 EDR (添加额外的终结点检测和响应) ，并提升对网络中泄露活动的可见性。</span><span class="sxs-lookup"><span data-stu-id="3d68f-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="3d68f-111">载入还确保可以检查设备是否具有易受攻击的组件以及安全配置问题，并可在攻击期间接收关键修正操作。</span><span class="sxs-lookup"><span data-stu-id="3d68f-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="3d68f-112">在你可以跟踪和管理设备的载入之前：</span><span class="sxs-lookup"><span data-stu-id="3d68f-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="3d68f-113">将设备注册到 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="3d68f-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="3d68f-114">确保您具有必要的权限</span><span class="sxs-lookup"><span data-stu-id="3d68f-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="3d68f-115">发现和跟踪未受保护的设备</span><span class="sxs-lookup"><span data-stu-id="3d68f-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="3d68f-116">载入卡通过将已实际载入 Defender for Endpoint 的 Windows 10 设备数与 Intune 管理的 Windows 10 设备的总数进行比较，提供载入率的简要概述。</span><span class="sxs-lookup"><span data-stu-id="3d68f-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="3d68f-117">![设备配置管理载入卡](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="3d68f-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="3d68f-118">*显示已载入设备与 Intune 管理的 Windows 10 设备总数比较的卡片*</span><span class="sxs-lookup"><span data-stu-id="3d68f-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="3d68f-119">如果你使用安全中心配置管理器、载入脚本或其他不使用 Intune 配置文件的载入方法，你可能会遇到数据差异。</span><span class="sxs-lookup"><span data-stu-id="3d68f-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="3d68f-120">若要解决这些差异，请为 Defender for Endpoint 载入创建相应的 Intune 配置文件，并将该配置文件分配给你的设备。</span><span class="sxs-lookup"><span data-stu-id="3d68f-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="3d68f-121">使用 Intune 配置文件载入更多设备</span><span class="sxs-lookup"><span data-stu-id="3d68f-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="3d68f-122">Defender for Endpoint 提供了几个用于载入 [Windows 10 设备的便捷选项](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="3d68f-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="3d68f-123">但是，对于 Intune 托管的设备，你可以利用 Intune 配置文件便捷地部署 Defender for Endpoint 传感器以选择设备，从而有效地将这些设备载入服务。</span><span class="sxs-lookup"><span data-stu-id="3d68f-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="3d68f-124">从 **载入卡中** ， **选择载入更多设备** 以在 Intune 上创建和分配配置文件。</span><span class="sxs-lookup"><span data-stu-id="3d68f-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="3d68f-125">该链接将你指向 Intune 上的设备合规性页面，该页面提供了载入状态类似的概述。</span><span class="sxs-lookup"><span data-stu-id="3d68f-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="3d68f-126">![Intune 设备管理上的 Microsoft Defender ATP 设备合规性页面](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="3d68f-126">![Microsoft Defender ATP device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="3d68f-127">*Intune 设备管理上的 Microsoft Defender ATP 设备合规性页面*</span><span class="sxs-lookup"><span data-stu-id="3d68f-127">*Microsoft Defender ATP device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="3d68f-128">或者，你可以从 [Microsoft Defender](https://portal.azure.com/) ATP 的所有服务 > Intune > 设备合规性> Microsoft Azure 门户中的 Defender for **Endpoint 载入合规性页面**。</span><span class="sxs-lookup"><span data-stu-id="3d68f-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="3d68f-129">如果你想要查看最新的设备数据，请单击没有 **ATP 传感器的设备列表**。</span><span class="sxs-lookup"><span data-stu-id="3d68f-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="3d68f-130">从设备合规性页面，专门为部署 Defender for Endpoint 传感器创建配置文件，并将该配置文件分配给你想要载入的设备。</span><span class="sxs-lookup"><span data-stu-id="3d68f-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="3d68f-131">为此，您可以：</span><span class="sxs-lookup"><span data-stu-id="3d68f-131">To do this, you can either:</span></span>

- <span data-ttu-id="3d68f-132">选择 **"创建设备配置文件"将 ATP 传感器** 配置为从预定义的设备配置文件开始。</span><span class="sxs-lookup"><span data-stu-id="3d68f-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="3d68f-133">从头开始创建设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="3d68f-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="3d68f-134">有关详细信息，请阅读 [有关使用 Intune 设备](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)配置文件将设备载入 Defender for Endpoint 的信息。</span><span class="sxs-lookup"><span data-stu-id="3d68f-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="3d68f-135">想要体验 Microsoft Defender ATP？</span><span class="sxs-lookup"><span data-stu-id="3d68f-135">Want to experience Microsoft Defender ATP?</span></span> [<span data-ttu-id="3d68f-136">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3d68f-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="3d68f-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="3d68f-137">Related topics</span></span>
- [<span data-ttu-id="3d68f-138">确保设备配置正确</span><span class="sxs-lookup"><span data-stu-id="3d68f-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="3d68f-139">提高 Defender for Endpoint 安全基线的合规性</span><span class="sxs-lookup"><span data-stu-id="3d68f-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="3d68f-140">优化 ASR 规则部署和检测</span><span class="sxs-lookup"><span data-stu-id="3d68f-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
