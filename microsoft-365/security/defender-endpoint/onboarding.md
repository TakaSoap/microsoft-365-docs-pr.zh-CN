---
title: 载入 Microsoft Defender for Endpoint 服务
description: 了解如何将终结点载入到 Microsoft Defender for Endpoint 服务
keywords: microsoft defender for endpoint， onboard， deploy
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f63b4f81f454fec60a26c7cb063d66bed4a2bead
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933537"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="3a395-104">载入 Microsoft Defender for Endpoint 服务</span><span class="sxs-lookup"><span data-stu-id="3a395-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3a395-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3a395-105">**Applies to:**</span></span>
- [<span data-ttu-id="3a395-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3a395-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3a395-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a395-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="3a395-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3a395-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3a395-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3a395-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3a395-110">了解部署 Microsoft Defender for Endpoint 的各个阶段以及如何在解决方案中配置功能。</span><span class="sxs-lookup"><span data-stu-id="3a395-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="3a395-111">部署适用于终结点的 Defender 的过程分三个阶段：</span><span class="sxs-lookup"><span data-stu-id="3a395-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="3a395-112">[![部署阶段 - 准备](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="3a395-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="3a395-113">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="3a395-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="3a395-114">[![部署阶段 - 设置](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="3a395-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="3a395-115">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="3a395-115">Phase 2: Setup</span></span>](production-deployment.md) | ![部署阶段 - 载入](images/phase-diagrams/onboard.png)<br><span data-ttu-id="3a395-117">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="3a395-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="3a395-118">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="3a395-118">*You are here!*</span></span>|

<span data-ttu-id="3a395-119">你当前处于载入阶段。</span><span class="sxs-lookup"><span data-stu-id="3a395-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="3a395-120">部署适用于终结点的 Defender 需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3a395-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="3a395-121">步骤 1：将终结点载入服务</span><span class="sxs-lookup"><span data-stu-id="3a395-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="3a395-122">步骤 2：配置功能</span><span class="sxs-lookup"><span data-stu-id="3a395-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="3a395-123">步骤 1：使用任何受支持的管理工具载入终结点</span><span class="sxs-lookup"><span data-stu-id="3a395-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="3a395-124">规划 [部署](deployment-strategy.md) 主题概述了部署 Defender for Endpoint 所需的常规步骤。</span><span class="sxs-lookup"><span data-stu-id="3a395-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="3a395-125">观看此视频，快速概览载入过程并了解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="3a395-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="3a395-126">确定体系结构后，需要决定使用哪种部署方法。</span><span class="sxs-lookup"><span data-stu-id="3a395-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="3a395-127">你选择的部署工具会影响将终结点载入到服务中。</span><span class="sxs-lookup"><span data-stu-id="3a395-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="3a395-128">载入工具选项</span><span class="sxs-lookup"><span data-stu-id="3a395-128">Onboarding tool options</span></span>

<span data-ttu-id="3a395-129">下表列出了基于需要载入的终结点的可用工具。</span><span class="sxs-lookup"><span data-stu-id="3a395-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="3a395-130">终结点</span><span class="sxs-lookup"><span data-stu-id="3a395-130">Endpoint</span></span>     | <span data-ttu-id="3a395-131">工具选项</span><span class="sxs-lookup"><span data-stu-id="3a395-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="3a395-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="3a395-132">**Windows**</span></span>  |  [<span data-ttu-id="3a395-133">本地脚本 (最多 10 台设备) </span><span class="sxs-lookup"><span data-stu-id="3a395-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="3a395-134">组策略</span><span class="sxs-lookup"><span data-stu-id="3a395-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="3a395-135">Microsoft Endpoint Manager/移动设备管理器</span><span class="sxs-lookup"><span data-stu-id="3a395-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="3a395-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3a395-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="3a395-137">VDI 脚本</span><span class="sxs-lookup"><span data-stu-id="3a395-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="3a395-138">与 Azure Defender 集成</span><span class="sxs-lookup"><span data-stu-id="3a395-138">Integration with Azure Defender</span></span>](configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="3a395-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="3a395-139">**macOS**</span></span>    | [<span data-ttu-id="3a395-140">本地脚本</span><span class="sxs-lookup"><span data-stu-id="3a395-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="3a395-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="3a395-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="3a395-142">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="3a395-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="3a395-143">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="3a395-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="3a395-144">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="3a395-144">**Linux Server**</span></span> | [<span data-ttu-id="3a395-145">本地脚本</span><span class="sxs-lookup"><span data-stu-id="3a395-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="3a395-146">百分百</span><span class="sxs-lookup"><span data-stu-id="3a395-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="3a395-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="3a395-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="3a395-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="3a395-148">**iOS**</span></span>      | [<span data-ttu-id="3a395-149">基于应用</span><span class="sxs-lookup"><span data-stu-id="3a395-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="3a395-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="3a395-150">**Android**</span></span>  | [<span data-ttu-id="3a395-151">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="3a395-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="3a395-152">步骤 2：配置功能</span><span class="sxs-lookup"><span data-stu-id="3a395-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="3a395-153">载入终结点后，你将配置各种功能，如终结点检测和响应、下一代保护和攻击面减少。</span><span class="sxs-lookup"><span data-stu-id="3a395-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="3a395-154">部署示例</span><span class="sxs-lookup"><span data-stu-id="3a395-154">Example deployments</span></span>
<span data-ttu-id="3a395-155">在此部署指南中，我们将指导你使用两个部署工具载入终结点以及如何配置功能。</span><span class="sxs-lookup"><span data-stu-id="3a395-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="3a395-156">示例部署中的工具包括：</span><span class="sxs-lookup"><span data-stu-id="3a395-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="3a395-157">使用 Microsoft Endpoint Configuration Manager 载入</span><span class="sxs-lookup"><span data-stu-id="3a395-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="3a395-158">使用 Microsoft Endpoint Manager 载入</span><span class="sxs-lookup"><span data-stu-id="3a395-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="3a395-159">然后，使用上面提到的部署工具，指导你配置以下 Defender for Endpoint 功能：</span><span class="sxs-lookup"><span data-stu-id="3a395-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="3a395-160">终结点检测和响应配置</span><span class="sxs-lookup"><span data-stu-id="3a395-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="3a395-161">下一代保护配置</span><span class="sxs-lookup"><span data-stu-id="3a395-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="3a395-162">攻击面减少配置</span><span class="sxs-lookup"><span data-stu-id="3a395-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="3a395-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="3a395-163">Related topics</span></span>
- [<span data-ttu-id="3a395-164">使用 Microsoft Endpoint Configuration Manager 载入</span><span class="sxs-lookup"><span data-stu-id="3a395-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="3a395-165">使用 Microsoft Endpoint Manager 载入</span><span class="sxs-lookup"><span data-stu-id="3a395-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="3a395-166">Microsoft 365 E5 中的安全文档</span><span class="sxs-lookup"><span data-stu-id="3a395-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
