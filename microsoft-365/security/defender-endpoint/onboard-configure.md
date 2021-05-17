---
title: 将设备载入到 Microsoft Defender for Endpoint 服务
description: 载入Windows 10设备、服务器、Windows设备，并了解如何运行检测测试。
keywords: 载入， Microsoft Defender for Endpoint onboarding， sccm， 组策略， mdm， 本地脚本， 检测测试
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933549"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="2f182-104">将设备载入到 Microsoft Defender for Endpoint 服务</span><span class="sxs-lookup"><span data-stu-id="2f182-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f182-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2f182-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f182-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2f182-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f182-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f182-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="2f182-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="2f182-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f182-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2f182-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="2f182-110">你需要转到 Defender for Endpoint 门户的载入部分，以载入任何受支持的设备。</span><span class="sxs-lookup"><span data-stu-id="2f182-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="2f182-111">根据设备，将指导你执行相应步骤，并提供适当的适用于设备的管理和部署工具选项。</span><span class="sxs-lookup"><span data-stu-id="2f182-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="2f182-112">通常，若要将设备载入服务：</span><span class="sxs-lookup"><span data-stu-id="2f182-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="2f182-113">验证设备是否满足 [最低要求](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="2f182-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="2f182-114">根据设备，按照 Defender for Endpoint 门户的载入部分中提供的配置步骤操作</span><span class="sxs-lookup"><span data-stu-id="2f182-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="2f182-115">为设备使用适当的管理工具和部署方法</span><span class="sxs-lookup"><span data-stu-id="2f182-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="2f182-116">运行检测测试，验证设备是否正确载入并报告给服务</span><span class="sxs-lookup"><span data-stu-id="2f182-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="2f182-117">载入工具选项</span><span class="sxs-lookup"><span data-stu-id="2f182-117">Onboarding tool options</span></span>
<span data-ttu-id="2f182-118">下表列出了基于需要载入的终结点的可用工具。</span><span class="sxs-lookup"><span data-stu-id="2f182-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="2f182-119">终结点</span><span class="sxs-lookup"><span data-stu-id="2f182-119">Endpoint</span></span>     | <span data-ttu-id="2f182-120">工具选项</span><span class="sxs-lookup"><span data-stu-id="2f182-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="2f182-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2f182-121">**Windows**</span></span>  |  [<span data-ttu-id="2f182-122">本地脚本 (最多 10 台设备) </span><span class="sxs-lookup"><span data-stu-id="2f182-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="2f182-123">组策略</span><span class="sxs-lookup"><span data-stu-id="2f182-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="2f182-124">Microsoft Endpoint Manager/移动设备管理器</span><span class="sxs-lookup"><span data-stu-id="2f182-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="2f182-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2f182-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="2f182-126">VDI 脚本</span><span class="sxs-lookup"><span data-stu-id="2f182-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="2f182-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="2f182-127">**macOS**</span></span>    | [<span data-ttu-id="2f182-128">本地脚本</span><span class="sxs-lookup"><span data-stu-id="2f182-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="2f182-129">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2f182-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="2f182-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="2f182-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="2f182-131">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="2f182-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="2f182-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="2f182-132">**Linux Server**</span></span> | [<span data-ttu-id="2f182-133">本地脚本</span><span class="sxs-lookup"><span data-stu-id="2f182-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="2f182-134">百分百</span><span class="sxs-lookup"><span data-stu-id="2f182-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="2f182-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="2f182-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="2f182-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2f182-136">**iOS**</span></span>      | [<span data-ttu-id="2f182-137">基于应用</span><span class="sxs-lookup"><span data-stu-id="2f182-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="2f182-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="2f182-138">**Android**</span></span>  | [<span data-ttu-id="2f182-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2f182-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="2f182-140">本节内容</span><span class="sxs-lookup"><span data-stu-id="2f182-140">In this section</span></span>
<span data-ttu-id="2f182-141">主题</span><span class="sxs-lookup"><span data-stu-id="2f182-141">Topic</span></span> | <span data-ttu-id="2f182-142">说明</span><span class="sxs-lookup"><span data-stu-id="2f182-142">Description</span></span>
:---|:---
[<span data-ttu-id="2f182-143">载入以前版本的 Windows</span><span class="sxs-lookup"><span data-stu-id="2f182-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="2f182-144">将 Windows 7 和 Windows 8.1设备载入到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="2f182-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="2f182-145">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="2f182-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="2f182-146">你需要载入设备，以向 Defender for Endpoint 服务报告。</span><span class="sxs-lookup"><span data-stu-id="2f182-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="2f182-147">了解可用于在企业中配置设备的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="2f182-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="2f182-148">载入服务器</span><span class="sxs-lookup"><span data-stu-id="2f182-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="2f182-149">将 Windows Server 2008 R2 SP1、Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) 版本 1803 及更高版本、Windows Server 2019 及更高版本以及 Windows Server 2019 核心版本载入 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="2f182-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="2f182-150">载入非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="2f182-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="2f182-151">Defender for Endpoint 为用户和非 Windows平台提供了集中式安全Windows体验。</span><span class="sxs-lookup"><span data-stu-id="2f182-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="2f182-152">你将能够查看来自各种支持的操作系统和操作系统警报 (操作系统) Microsoft Defender 安全中心更好地保护组织的网络。</span><span class="sxs-lookup"><span data-stu-id="2f182-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="2f182-153">此体验利用第三方安全产品的传感器数据。</span><span class="sxs-lookup"><span data-stu-id="2f182-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="2f182-154">在新载入的设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="2f182-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="2f182-155">在新载入的设备上运行脚本，验证它是否正确报告给 Defender for Endpoint 服务。</span><span class="sxs-lookup"><span data-stu-id="2f182-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="2f182-156">配置代理和 Internet 设置</span><span class="sxs-lookup"><span data-stu-id="2f182-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="2f182-157">通过配置代理和 Internet 连接设置，启用与 Defender for Endpoint 云服务的通信。</span><span class="sxs-lookup"><span data-stu-id="2f182-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="2f182-158">解决载入问题</span><span class="sxs-lookup"><span data-stu-id="2f182-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="2f182-159">了解如何解决载入期间可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="2f182-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="2f182-160">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="2f182-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f182-161">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2f182-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
