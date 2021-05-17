---
title: 规划 Microsoft Defender for Endpoint 部署
description: 选择适用于你的环境的最佳 Microsoft Defender 终结点部署策略
keywords: 部署， 计划， 部署策略， 云本机， 管理， 本地， 评估， 载入， 本地， 组策略， gp， 终结点管理器， mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163571"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="7f655-104">规划 Microsoft Defender for Endpoint 部署</span><span class="sxs-lookup"><span data-stu-id="7f655-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7f655-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7f655-105">**Applies to:**</span></span>
- [<span data-ttu-id="7f655-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7f655-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7f655-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f655-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7f655-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="7f655-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7f655-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7f655-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="7f655-110">规划 Microsoft Defender for Endpoint 部署，以便你可以最大化套件中的安全性功能，并更好地保护你的企业免受网络威胁。</span><span class="sxs-lookup"><span data-stu-id="7f655-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="7f655-111">此解决方案提供了有关如何确定环境体系结构、选择最符合您需求的部署工具类型的指导，以及如何配置功能的指南。</span><span class="sxs-lookup"><span data-stu-id="7f655-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![部署流的图像](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="7f655-113">步骤 1：确定体系结构</span><span class="sxs-lookup"><span data-stu-id="7f655-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="7f655-114">我们知道每个企业环境都是唯一的，因此我们提供了多个选项，让你能够灵活地选择如何部署服务。</span><span class="sxs-lookup"><span data-stu-id="7f655-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="7f655-115">根据你的环境，某些工具更适合某些体系结构。</span><span class="sxs-lookup"><span data-stu-id="7f655-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="7f655-116">使用以下材料选择最适合贵组织的适用于终结点的 Defender 体系结构。</span><span class="sxs-lookup"><span data-stu-id="7f655-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="7f655-117">项目</span><span class="sxs-lookup"><span data-stu-id="7f655-117">Item</span></span> | <span data-ttu-id="7f655-118">说明</span><span class="sxs-lookup"><span data-stu-id="7f655-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="7f655-119">[![适用于终结点部署策略的 Defender 缩略图](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="7f655-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="7f655-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="7f655-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="7f655-121">体系结构资料有助于规划如下体系结构的部署：</span><span class="sxs-lookup"><span data-stu-id="7f655-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="7f655-122">云-本机</span><span class="sxs-lookup"><span data-stu-id="7f655-122">Cloud-native</span></span> </li><li> <span data-ttu-id="7f655-123">协同管理</span><span class="sxs-lookup"><span data-stu-id="7f655-123">Co-management</span></span> </li><li> <span data-ttu-id="7f655-124">本地</span><span class="sxs-lookup"><span data-stu-id="7f655-124">On-premise</span></span></li><li><span data-ttu-id="7f655-125">评估和本地载入</span><span class="sxs-lookup"><span data-stu-id="7f655-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="7f655-126">步骤 2：选择部署方法</span><span class="sxs-lookup"><span data-stu-id="7f655-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="7f655-127">Defender for Endpoint 支持可载入到服务的各种终结点。</span><span class="sxs-lookup"><span data-stu-id="7f655-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="7f655-128">下表列出了受支持的终结点和可使用的相应部署工具，以便可以相应地规划部署。</span><span class="sxs-lookup"><span data-stu-id="7f655-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="7f655-129">终结点</span><span class="sxs-lookup"><span data-stu-id="7f655-129">Endpoint</span></span>     | <span data-ttu-id="7f655-130">部署工具</span><span class="sxs-lookup"><span data-stu-id="7f655-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="7f655-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="7f655-131">**Windows**</span></span>  |  [<span data-ttu-id="7f655-132">本地脚本 (最多 10 台设备) </span><span class="sxs-lookup"><span data-stu-id="7f655-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="7f655-133">组策略</span><span class="sxs-lookup"><span data-stu-id="7f655-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="7f655-134">Microsoft Endpoint Manager/移动设备管理器</span><span class="sxs-lookup"><span data-stu-id="7f655-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="7f655-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7f655-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="7f655-136">VDI 脚本</span><span class="sxs-lookup"><span data-stu-id="7f655-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="7f655-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="7f655-137">**macOS**</span></span>    | [<span data-ttu-id="7f655-138">本地脚本</span><span class="sxs-lookup"><span data-stu-id="7f655-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="7f655-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="7f655-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="7f655-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="7f655-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="7f655-141">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="7f655-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="7f655-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="7f655-142">**Linux Server**</span></span> | [<span data-ttu-id="7f655-143">本地脚本</span><span class="sxs-lookup"><span data-stu-id="7f655-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="7f655-144">百分百</span><span class="sxs-lookup"><span data-stu-id="7f655-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="7f655-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="7f655-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="7f655-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="7f655-146">**iOS**</span></span>      | [<span data-ttu-id="7f655-147">基于应用</span><span class="sxs-lookup"><span data-stu-id="7f655-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="7f655-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="7f655-148">**Android**</span></span>  | [<span data-ttu-id="7f655-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="7f655-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="7f655-150">步骤 3：配置功能</span><span class="sxs-lookup"><span data-stu-id="7f655-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="7f655-151">载入终结点后，在 Defender for Endpoint 中配置安全功能，以便你可以最大化套件中可用的强大安全保护。</span><span class="sxs-lookup"><span data-stu-id="7f655-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="7f655-152">功能包括：</span><span class="sxs-lookup"><span data-stu-id="7f655-152">Capabilities include:</span></span>

- <span data-ttu-id="7f655-153">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="7f655-153">Endpoint detection and response</span></span>
- <span data-ttu-id="7f655-154">下一代保护</span><span class="sxs-lookup"><span data-stu-id="7f655-154">Next-generation protection</span></span>
- <span data-ttu-id="7f655-155">攻击面减少</span><span class="sxs-lookup"><span data-stu-id="7f655-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="7f655-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f655-156">Related topics</span></span>
- [<span data-ttu-id="7f655-157">部署阶段</span><span class="sxs-lookup"><span data-stu-id="7f655-157">Deployment phases</span></span>](deployment-phases.md)
