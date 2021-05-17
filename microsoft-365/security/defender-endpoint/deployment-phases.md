---
title: 部署阶段
description: 了解如何通过准备、设置和载入适用于终结点的终结点来部署 Microsoft Defender for Endpoint
keywords: 部署， 准备， 设置， 载入， 阶段， 部署， 部署， 采用， 配置
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165161"
---
# <a name="deployment-phases"></a><span data-ttu-id="bd1aa-104">部署阶段</span><span class="sxs-lookup"><span data-stu-id="bd1aa-104">Deployment phases</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd1aa-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bd1aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd1aa-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd1aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bd1aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd1aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bd1aa-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="bd1aa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bd1aa-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="bd1aa-110">了解如何部署 Microsoft Defender for Endpoint，以便企业可以利用预防性保护、攻破后检测、自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-110">Learn how to deploy Microsoft Defender for Endpoint so that your enterprise can take advantage of preventative protection, post-breach detection, automated investigation, and response.</span></span> 


<span data-ttu-id="bd1aa-111">本指南可帮助你跨利益干系人一起准备环境，然后以有条理的方式载入设备，从评估到有意义的试点，到完全部署。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-111">This guide helps you work across stakeholders to prepare your environment and then onboard devices in a methodical way, moving from evaluation, to a meaningful pilot, to full deployment.</span></span>

<span data-ttu-id="bd1aa-112">每个部分对应于此解决方案中的一篇单独的文章。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-112">Each section corresponds to a separate article in this solution.</span></span>

![包含表中详细信息的部署阶段的图像](images/deployment-guide-phases.png)


![部署阶段摘要：准备、设置、载入](images/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="bd1aa-115">阶段</span><span class="sxs-lookup"><span data-stu-id="bd1aa-115">Phase</span></span> | <span data-ttu-id="bd1aa-116">说明</span><span class="sxs-lookup"><span data-stu-id="bd1aa-116">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="bd1aa-117">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="bd1aa-117">Phase 1: Prepare</span></span>](prepare-deployment.md)| <span data-ttu-id="bd1aa-118">了解部署适用于终结点的 Defender 时需要考虑的问题，例如利益干系人审批、环境注意事项、访问权限和功能采用顺序。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-118">Learn about what you need to consider when deploying Defender for Endpoint such as stakeholder approvals, environment considerations, access permissions, and adoption order of capabilities.</span></span> 
| [<span data-ttu-id="bd1aa-119">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="bd1aa-119">Phase 2: Setup</span></span>](production-deployment.md)|  <span data-ttu-id="bd1aa-120">获取有关需要执行的初始步骤的指导，以便你可以访问门户，例如验证许可、完成安装向导和网络配置。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-120">Get guidance on the initial steps you need to take so that you can access the portal such as validating licensing, completing the setup wizard, and network configuration.</span></span> 
| [<span data-ttu-id="bd1aa-121">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="bd1aa-121">Phase 3: Onboard</span></span>](onboarding.md) | <span data-ttu-id="bd1aa-122">了解如何使用部署圈、基于终结点类型支持的载入工具以及配置可用功能。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-122">Learn how to make use of deployment rings, supported onboarding tools based on the type of endpoint, and configuring available capabilities.</span></span> 


<span data-ttu-id="bd1aa-123">完成本指南后，你将使用正确的访问权限进行设置，你的终结点将载入，并且向服务报告传感器数据，并且下一代保护和攻击面减少等功能将就位。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-123">After you've completed this guide, you'll be setup with the right access permissions, your endpoints will be onboarded and reporting sensor data to the service, and capabilities such as next-generation protection and attack surface reduction will be in place.</span></span>



<span data-ttu-id="bd1aa-124">无论选择的环境体系结构和部署方法如何，规划部署指南中概述，[](deployment-strategy.md)本指南都将在载入终结点方面支持你。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-124">Regardless of the environment architecture and method of deployment you choose outlined in the [Plan deployment](deployment-strategy.md) guidance, this guide is going to support you in onboarding endpoints.</span></span> 








## <a name="key-capabilities"></a><span data-ttu-id="bd1aa-125">关键功能</span><span class="sxs-lookup"><span data-stu-id="bd1aa-125">Key capabilities</span></span>

<span data-ttu-id="bd1aa-126">虽然 Microsoft Defender for Endpoint 提供了许多功能，但此部署指南的主要目的是通过载入设备入门。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-126">While Microsoft Defender for Endpoint provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="bd1aa-127">除了载入之外，本指南还让你开始使用以下功能。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-127">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>



<span data-ttu-id="bd1aa-128">功能</span><span class="sxs-lookup"><span data-stu-id="bd1aa-128">Capability</span></span> | <span data-ttu-id="bd1aa-129">说明</span><span class="sxs-lookup"><span data-stu-id="bd1aa-129">Description</span></span> 
:---|:---
<span data-ttu-id="bd1aa-130">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="bd1aa-130">Endpoint detection and response</span></span> | <span data-ttu-id="bd1aa-131">终结点检测和响应功能已到位，以检测、调查和响应入侵尝试和主动泄露。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-131">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span>
<span data-ttu-id="bd1aa-132">下一代保护</span><span class="sxs-lookup"><span data-stu-id="bd1aa-132">Next-generation protection</span></span> | <span data-ttu-id="bd1aa-133">为了进一步强化网络的安全外围，Microsoft Defender for Endpoint 使用旨在捕获所有类型的新兴威胁的下一代保护。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-133">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>
<span data-ttu-id="bd1aa-134">攻击面减少</span><span class="sxs-lookup"><span data-stu-id="bd1aa-134">Attack surface reduction</span></span> |  <span data-ttu-id="bd1aa-135">在堆栈中提供第一道防线。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-135">Provide the first line of defense in the stack.</span></span> <span data-ttu-id="bd1aa-136">通过确保正确设置配置设置并应用攻击缓解技术，这些功能集可抵御攻击和利用。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-136">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

<span data-ttu-id="bd1aa-137">所有这些功能都适用于适用于终结点许可证持有者的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-137">All these capabilities are available for Microsoft Defender for Endpoint license holders.</span></span> <span data-ttu-id="bd1aa-138">有关详细信息，请参阅 [许可要求](minimum-requirements.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="bd1aa-138">For more information, see [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

## <a name="scope"></a><span data-ttu-id="bd1aa-139">范围</span><span class="sxs-lookup"><span data-stu-id="bd1aa-139">Scope</span></span>

### <a name="in-scope"></a><span data-ttu-id="bd1aa-140">在作用域内</span><span class="sxs-lookup"><span data-stu-id="bd1aa-140">In scope</span></span>

-   <span data-ttu-id="bd1aa-141">使用 Microsoft Endpoint Manager 和 Microsoft Endpoint Manager将终结点载入服务并配置功能</span><span class="sxs-lookup"><span data-stu-id="bd1aa-141">Use of Microsoft Endpoint Manager and Microsoft Endpoint Manager to onboard endpoints into the service and configure capabilities</span></span>

-   <span data-ttu-id="bd1aa-142">启用 Defender 终结点检测和响应 (EDR) 功能</span><span class="sxs-lookup"><span data-stu-id="bd1aa-142">Enabling Defender for Endpoint endpoint detection and response (EDR)  capabilities</span></span>

-   <span data-ttu-id="bd1aa-143">启用适用于终结点保护平台的 Defender (EPP) 功能</span><span class="sxs-lookup"><span data-stu-id="bd1aa-143">Enabling Defender for Endpoint endpoint protection platform (EPP) capabilities</span></span>

    -   <span data-ttu-id="bd1aa-144">下一代保护</span><span class="sxs-lookup"><span data-stu-id="bd1aa-144">Next-generation protection</span></span>

    -   <span data-ttu-id="bd1aa-145">攻击面减少</span><span class="sxs-lookup"><span data-stu-id="bd1aa-145">Attack surface reduction</span></span>


### <a name="out-of-scope"></a><span data-ttu-id="bd1aa-146">超出范围</span><span class="sxs-lookup"><span data-stu-id="bd1aa-146">Out of scope</span></span>

<span data-ttu-id="bd1aa-147">以下超出了此部署指南的范围：</span><span class="sxs-lookup"><span data-stu-id="bd1aa-147">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="bd1aa-148">可能与 Defender for Endpoint 集成的第三方解决方案的配置</span><span class="sxs-lookup"><span data-stu-id="bd1aa-148">Configuration of third-party solutions that might integrate with Defender for Endpoint</span></span>

-   <span data-ttu-id="bd1aa-149">生产环境中的渗透测试</span><span class="sxs-lookup"><span data-stu-id="bd1aa-149">Penetration testing in production environment</span></span>




## <a name="see-also"></a><span data-ttu-id="bd1aa-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd1aa-150">See also</span></span>
- [<span data-ttu-id="bd1aa-151">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="bd1aa-151">Phase 1: Prepare</span></span>](prepare-deployment.md)
- [<span data-ttu-id="bd1aa-152">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="bd1aa-152">Phase 2: Set up</span></span>](production-deployment.md)
- [<span data-ttu-id="bd1aa-153">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="bd1aa-153">Phase 3: Onboard</span></span>](onboarding.md)
- [<span data-ttu-id="bd1aa-154">计划部署</span><span class="sxs-lookup"><span data-stu-id="bd1aa-154">Plan deployment</span></span>](deployment-strategy.md)