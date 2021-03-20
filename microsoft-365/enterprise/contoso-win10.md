---
title: Contoso Windows 10 企业版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 来部署 Windows 10 企业版的就地升级。
ms.openlocfilehash: 7907bf64acce3af8b21459202cb6f5cbc1e9f990
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907682"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="9fd2d-103">Contoso Windows 10 企业版部署</span><span class="sxs-lookup"><span data-stu-id="9fd2d-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="9fd2d-104">在广泛推出 Microsoft 365 企业版之前，Contoso 具有运行混合 Windows 7 (10%) 、Windows 8.1 (65%) 和 Windows 10 (25%) 的 Windows 兼容电脑和设备。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-104">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%).</span></span> <span data-ttu-id="9fd2d-105">Contoso 想要升级 Windows 10 企业版电脑，以利用高级安全性并降低自动部署更新的 IT 开销。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-105">Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="9fd2d-106">在评估其基础结构和业务需求之后，Contoso 确定了这些部署的关键要求：</span><span class="sxs-lookup"><span data-stu-id="9fd2d-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="9fd2d-107">应有尽可能多的电脑和设备运行 Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="9fd2d-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="9fd2d-108">就地升级的推广利用了现有的 Configuration Manager 基础结构</span><span class="sxs-lookup"><span data-stu-id="9fd2d-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="9fd2d-109">控制哪些版本的 Windows 10 企业版的部署和更新是通过环来完成的</span><span class="sxs-lookup"><span data-stu-id="9fd2d-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="9fd2d-110">电脑和设备应保持最新的更新、使用最低的 IT 管理成本，并尽量减少对最终用户带来的影响</span><span class="sxs-lookup"><span data-stu-id="9fd2d-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="9fd2d-111">最新更新定义为满足 Contoso 业务需求的受支持的 Windows 10 企业版，这可能不同于使所有 Windows 兼容的电脑运行最新版本的 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="9fd2d-112">部署工具</span><span class="sxs-lookup"><span data-stu-id="9fd2d-112">Deployment tools</span></span>

<span data-ttu-id="9fd2d-113">在 Windows 10 企业版就地升级之前和升级期间，Contoso 使用下列 Windows Analytics 解决方案：</span><span class="sxs-lookup"><span data-stu-id="9fd2d-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="9fd2d-114">升级就绪情况</span><span class="sxs-lookup"><span data-stu-id="9fd2d-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="9fd2d-115">收集系统、应用程序和驱动程序数据进行分析，然后识别可能阻止升级的兼容性问题，并建议修复 Microsoft 已知问题。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="9fd2d-116">更新合规性</span><span class="sxs-lookup"><span data-stu-id="9fd2d-116">Update Compliance</span></span>  

  <span data-ttu-id="9fd2d-117">显示有关 Windows 更新的设备状态，以便你可以根据需要确保它们位于最新的更新中。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="9fd2d-118">设备运行状况</span><span class="sxs-lookup"><span data-stu-id="9fd2d-118">Device Health</span></span>  

  <span data-ttu-id="9fd2d-119">识别由于经常崩溃而可能需要重新生成或替换的设备以及导致设备崩溃的设备驱动程序，还包括有关这些驱动程序的可减少崩溃次数的替代版本建议。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="9fd2d-120">提供 Windows 信息保护错误配置的通知，向最终用户发送相关提示。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="9fd2d-p103">Contoso 具有一个现有的 Configuration Manager (Current Branch) 基础结构。Configuration Manager 针对大型环境进行扩展，并在安装、更新和设置过程中提供广泛的控制。它还具有内置功能，能够更为轻松和高效地部署和管理 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="9fd2d-124">规划过程</span><span class="sxs-lookup"><span data-stu-id="9fd2d-124">Planning process</span></span>

<span data-ttu-id="9fd2d-125">Contoso 使用 Windows Analytics 中的升级就绪情况来确定已安装的应用集及其与 Windows 10 企业版之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="9fd2d-126">部署过程</span><span class="sxs-lookup"><span data-stu-id="9fd2d-126">Deployment process</span></span>

<span data-ttu-id="9fd2d-127">若要完成 Windows 10 企业版的就地升级部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：</span><span class="sxs-lookup"><span data-stu-id="9fd2d-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="9fd2d-128">为 Configuration Manager 启用对等缓存。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="9fd2d-129">基于来自批量许可服务中心的图像创建自定义 Windows 程序包。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="9fd2d-130">使用 Configuration Manager 将 Windows 程序包部署到跨其网络的分发点，将内部版本部署到三个验证和部署暂存组。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="9fd2d-131">使用 Windows Analytics 的设备运行状况和更新合规性解决方案，为三个验证和部署暂存环中的电脑和设备执行成功评估。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="9fd2d-132">根据 Windows Analytics 信息，Contoso 确定了要部署到广泛部署组的 Windows 10 企业版的版本。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="9fd2d-133">运行 Configuration Manager 部署任务序列，将选定的 Windows 程序包部署到广泛部署组。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="9fd2d-134">使用设备运行状况和更新合规性解决方案来解决问题，监视广泛部署组中电脑和设备。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="9fd2d-135">下面是 Contoso 的就地升级和持续更新部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contoso 的 Windows 10 企业版部署基础结构](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="9fd2d-137">此基础结构的组成部分：</span><span class="sxs-lookup"><span data-stu-id="9fd2d-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="9fd2d-138">Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="9fd2d-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="9fd2d-139">从 Microsoft 网络的 Microsoft 批量许可中心获取 Windows 10 企业版包的图像。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="9fd2d-140">是用于部署包的集中管理点。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="9fd2d-141">通常位于 Contoso 区域中心办事处的区域分发点。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="9fd2d-142">不同位置接收和安装部署包的 Windows 电脑和设备，用于根据组成员身份进行就地升级或持续更新。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="9fd2d-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9fd2d-143">Next step</span></span>

<span data-ttu-id="9fd2d-144">了解 Contoso 如何利用其 Configuration Manager 基础结构在整个组织中部署和保持最新的 [Microsoft 365](contoso-o365pp.md) 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="9fd2d-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fd2d-145">See also</span></span>

[<span data-ttu-id="9fd2d-146">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="9fd2d-146">Windows 10 Enterprise</span></span>](/windows/deployment/)

[<span data-ttu-id="9fd2d-147">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="9fd2d-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9fd2d-148">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="9fd2d-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)