---
title: 评估 Microsoft 365 网络连接
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 旨在允许全球客户使用 Internet 连接连接到服务。 随着服务的发展，Microsoft 365 的安全性、性能和可靠性会基于客户使用 Internet 与服务建立连接而得到改进。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905472"
---
# <a name="assessing-microsoft-365-network-connectivity"></a><span data-ttu-id="1b06b-104">评估 Microsoft 365 网络连接</span><span class="sxs-lookup"><span data-stu-id="1b06b-104">Assessing Microsoft 365 network connectivity</span></span>

<span data-ttu-id="1b06b-105">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="1b06b-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1b06b-106">Microsoft 365 旨在允许全球客户使用 Internet 连接连接到服务。</span><span class="sxs-lookup"><span data-stu-id="1b06b-106">Microsoft 365 is designed to enable customers all over the world to connect to the service using an internet connection.</span></span> <span data-ttu-id="1b06b-107">随着服务的发展，Microsoft 365 的安全性、性能和可靠性会基于客户使用 Internet 与服务建立连接而得到改进。</span><span class="sxs-lookup"><span data-stu-id="1b06b-107">As the service evolves, the security, performance, and reliability of Microsoft 365 are improved based on customers using the internet to establish a connection to the service.</span></span>
  
<span data-ttu-id="1b06b-108">作为部署项目的一部分，计划使用 Microsoft 365 的客户应评估其现有和预测的 Internet 连接需求。</span><span class="sxs-lookup"><span data-stu-id="1b06b-108">Customers planning to use Microsoft 365 should assess their existing and forecasted internet connectivity needs as a part of the deployment project.</span></span> <span data-ttu-id="1b06b-109">对于企业级部署，可靠且大小合适的 Internet 连接是使用 Microsoft 365 功能和方案的关键部分。</span><span class="sxs-lookup"><span data-stu-id="1b06b-109">For enterprise class deployments reliable and appropriately sized internet connectivity is a critical part of consuming Microsoft 365 features and scenarios.</span></span>
  
<span data-ttu-id="1b06b-110">网络评估可以由许多不同的人员和组织执行，具体取决于你的大小和首选项。</span><span class="sxs-lookup"><span data-stu-id="1b06b-110">Network evaluations can be performed by many different people and organizations depending on your size and preferences.</span></span> <span data-ttu-id="1b06b-111">评估的网络范围也可能有所不同，具体取决于你在部署过程中处于何处。</span><span class="sxs-lookup"><span data-stu-id="1b06b-111">The network scope of the assessment can also vary depending on where you're at in your deployment process.</span></span> <span data-ttu-id="1b06b-112">为了帮助你更好地了解执行网络评估需要执行的操作，我们生成了一个网络评估指南，可帮助你了解可用的选项。</span><span class="sxs-lookup"><span data-stu-id="1b06b-112">To help you get a better understanding of what it takes to perform a network assessment, we've produced a network assessment guide to help you understand the options available to you.</span></span> <span data-ttu-id="1b06b-113">此评估将确定需要向部署项目添加哪些步骤和资源，以便成功采用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="1b06b-113">This assessment will determine what steps and resources need to be added to the deployment project to enable you to successfully adopt Microsoft 365.</span></span>
  
<span data-ttu-id="1b06b-114">全面的网络评估将提供可能的网络设计挑战解决方案以及实施详细信息。</span><span class="sxs-lookup"><span data-stu-id="1b06b-114">A comprehensive network assessment will provide possible solutions to networking design challenges along with implementation details.</span></span> <span data-ttu-id="1b06b-115">一些网络评估将显示，通过对现有网络和 Internet 出口基础结构进行细微的配置或设计更改，可以适应与 Microsoft 365 的最佳网络连接。</span><span class="sxs-lookup"><span data-stu-id="1b06b-115">Some network assessments will show that optimal network connectivity to Microsoft 365 can be accommodated with minor configuration or design changes to the existing network and internet egress infrastructure.</span></span>

<span data-ttu-id="1b06b-116">一些评估将指示与 Microsoft 365 的网络连接将需要在网络组件方面进行额外投资。</span><span class="sxs-lookup"><span data-stu-id="1b06b-116">Some assessments will indicate network connectivity to Microsoft 365 will require additional investments in networking components.</span></span> <span data-ttu-id="1b06b-117">例如，跨分支机构和多个地理区域的企业网络可能需要投资 SD-WAN 解决方案或优化的路由基础结构以支持到 Microsoft 365 的 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="1b06b-117">For example, enterprise networks that span branch offices and multiple geographic regions may require investments in SD-WAN solutions or optimized routing infrastructure to support internet connectivity to Microsoft 365.</span></span> <span data-ttu-id="1b06b-118">有时，评估将指示与 Microsoft 365 的网络连接受 Skype for Business Online 媒体质量等方案的法规或性能 [要求的影响](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)。</span><span class="sxs-lookup"><span data-stu-id="1b06b-118">Occasionally an assessment will indicate network connectivity to Microsoft 365 is influenced by regulation or performance requirements for scenarios such as [Skype for Business Online media quality](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).</span></span> <span data-ttu-id="1b06b-119">这些额外的要求可能会导致 Internet 连接基础结构、路由优化和专门的直接连接方面的投资。</span><span class="sxs-lookup"><span data-stu-id="1b06b-119">These additional requirements may lead to investments in internet connectivity infrastructure, routing optimization, and specialized direct connectivity.</span></span>

<span data-ttu-id="1b06b-120">帮助您评估网络的一些资源：</span><span class="sxs-lookup"><span data-stu-id="1b06b-120">Some resources to help you assess your network:</span></span>

- <span data-ttu-id="1b06b-121">有关 [Microsoft 365 网络](microsoft-365-networking-overview.md) 的概念信息，请参阅 Microsoft 365 网络连接概述。</span><span class="sxs-lookup"><span data-stu-id="1b06b-121">See [Microsoft 365 network connectivity overview](microsoft-365-networking-overview.md) for conceptual information about Microsoft 365 networking.</span></span>
- <span data-ttu-id="1b06b-122">请参阅 [Microsoft 365](./microsoft-365-network-connectivity-principles.md) 网络连接原则，了解安全管理 Microsoft 365 流量和获得最佳性能的连接原则。</span><span class="sxs-lookup"><span data-stu-id="1b06b-122">See [Microsoft 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Microsoft 365 traffic and getting the best possible performance.</span></span>
- <span data-ttu-id="1b06b-123">注册 [Microsoft FastTrack，](https://www.microsoft.com/fasttrack) 获得 Microsoft 365 规划、设计和部署指导协助。</span><span class="sxs-lookup"><span data-stu-id="1b06b-123">Sign up for [Microsoft FastTrack](https://www.microsoft.com/fasttrack) for guided assistance with Microsoft 365 planning, design and deployment.</span></span> 
- <span data-ttu-id="1b06b-124">请参阅下面的 [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) 连接测试部分，以运行基本连接测试，这些测试提供有关可在给定用户位置和 Microsoft 365 之间进行网络连接改进的特定指南。</span><span class="sxs-lookup"><span data-stu-id="1b06b-124">See the [Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) section below to run basic connectivity tests that provide specific guidance about networking connectivity improvements that can be made between a given user location and Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="1b06b-125">需要 Microsoft 授权才能使用适用于 Office 365 的 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="1b06b-125">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="1b06b-126">当客户的法规要求要求直接连接时，Microsoft 将审核每个客户请求，并仅授权 ExpressRoute for Office 365 使用。</span><span class="sxs-lookup"><span data-stu-id="1b06b-126">Microsoft reviews every customer request and only authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="1b06b-127">如果你有此类要求，请提供文本摘录和指向法规的 Web 链接，您解释该法规意味着 [ExpressRoute for Office 365](https://aka.ms/O365ERReview) 请求表单中需要直接连接才能开始 Microsoft 审查。</span><span class="sxs-lookup"><span data-stu-id="1b06b-127">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="1b06b-128">尝试为 Office 365 创建路由筛选器的未经授权的订阅将收到 [一条错误消息](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="1b06b-128">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>
  
<span data-ttu-id="1b06b-129">规划 Microsoft 365 网络评估时要考虑的要点：</span><span class="sxs-lookup"><span data-stu-id="1b06b-129">Key points to consider when planning your network assessment for Microsoft 365:</span></span>
  
- <span data-ttu-id="1b06b-130">Microsoft 365 是一种通过公共 Internet 运行的安全、可靠、高性能服务。</span><span class="sxs-lookup"><span data-stu-id="1b06b-130">Microsoft 365 is a secure, reliable, high performance service that runs over the public internet.</span></span> <span data-ttu-id="1b06b-131">我们将继续投资以增强服务的这些方面。</span><span class="sxs-lookup"><span data-stu-id="1b06b-131">We continue to invest to enhance these aspects of the service.</span></span> <span data-ttu-id="1b06b-132">所有 Microsoft 365 服务均通过 Internet 连接提供。</span><span class="sxs-lookup"><span data-stu-id="1b06b-132">All Microsoft 365 services are available via internet connectivity.</span></span>

- <span data-ttu-id="1b06b-133">我们正在不断优化 Microsoft 365 的核心方面，例如可用性、全球范围和基于 Internet 的连接的性能。</span><span class="sxs-lookup"><span data-stu-id="1b06b-133">We are continually optimizing core aspects of Microsoft 365 such as availability, global reach, and performance for internet based connectivity.</span></span> <span data-ttu-id="1b06b-134">例如，许多 Microsoft 365 服务利用一组扩展的面向 Internet 的边缘节点。</span><span class="sxs-lookup"><span data-stu-id="1b06b-134">For example, many Microsoft 365 services leverage an expanding set of internet facing edge nodes.</span></span> <span data-ttu-id="1b06b-135">此边缘网络为通过 Internet 的连接提供最佳邻近感应和性能。</span><span class="sxs-lookup"><span data-stu-id="1b06b-135">This edge network offers the best proximity and performance to connections coming over the internet.</span></span>

- <span data-ttu-id="1b06b-136">当考虑将 Microsoft 365 用于任何包含的服务（如 Teams 或 Skype for Business Online 语音、视频或会议功能）时，客户应该使用 [Microsoft FastTrack](https://www.microsoft.com/fasttrack)完成端到端网络评估并满足连接要求。</span><span class="sxs-lookup"><span data-stu-id="1b06b-136">When considering using Microsoft 365 for any of the included services such as Teams or Skype for Business Online voice, video, or meeting capabilities, customers should complete an end to end network assessment and meet connectivity requirements using [Microsoft FastTrack](https://www.microsoft.com/fasttrack).</span></span>

<span data-ttu-id="1b06b-137">如果你正在评估 Microsoft 365，并且不确定从何处开始进行网络评估，或发现需要协助解决的网络设计挑战，请与你的 Microsoft 帐户团队合作。</span><span class="sxs-lookup"><span data-stu-id="1b06b-137">If you're evaluating Microsoft 365 and aren't sure where to begin with your network assessment or have found network design challenges that you need assistance to overcome, please work with your Microsoft account team.</span></span>

## <a name="the-microsoft-365-connectivity-test"></a><span data-ttu-id="1b06b-138">Microsoft 365 连接测试</span><span class="sxs-lookup"><span data-stu-id="1b06b-138">The Microsoft 365 connectivity test</span></span>

<span data-ttu-id="1b06b-139">[Microsoft 365](https://aka.ms/netonboard)连接测试是概念证明 (POC) 网络评估工具，该工具针对 Microsoft 365 租户运行基本连接测试，并针对最佳 Microsoft 365 性能提供特定的网络设计建议。</span><span class="sxs-lookup"><span data-stu-id="1b06b-139">The [Microsoft 365 connectivity test](https://aka.ms/netonboard) is a proof of concept (POC) network assessment tool that runs basic connectivity tests against your Microsoft 365 tenant and makes specific network design recommendations for optimal Microsoft 365 performance.</span></span> <span data-ttu-id="1b06b-140">该工具重点介绍常见的大型企业网络外围设计选择，这些选项对于 Internet Web 浏览很有用，但会影响大型 SaaS 应用程序（如 Microsoft 365）的性能。</span><span class="sxs-lookup"><span data-stu-id="1b06b-140">The tool highlights common large enterprise network perimeter design choices which are useful for Internet web browsing but impact the performance of large SaaS applications such as Microsoft 365.</span></span>

<span data-ttu-id="1b06b-141">网络载入工具执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1b06b-141">The Network Onboarding tool does the following:</span></span>

- <span data-ttu-id="1b06b-142">检测位置，也可以指定要测试的位置</span><span class="sxs-lookup"><span data-stu-id="1b06b-142">Detects your location, or you can specify a location to test</span></span>
- <span data-ttu-id="1b06b-143">检查网络出口的位置</span><span class="sxs-lookup"><span data-stu-id="1b06b-143">Checks the location of your network egress</span></span>
- <span data-ttu-id="1b06b-144">测试到最近的 Microsoft 365 服务前端的网络路径</span><span class="sxs-lookup"><span data-stu-id="1b06b-144">Tests the network path to the nearest Microsoft 365 service front door</span></span>
- <span data-ttu-id="1b06b-145">使用可下载的 Windows 10 应用程序提供高级测试，该应用程序提供与代理服务器、防火墙和 DNS 相关的外围网络设计建议。</span><span class="sxs-lookup"><span data-stu-id="1b06b-145">Provides advanced tests using a downloadable Windows 10 application that makes perimeter network design recommendations related to proxy servers, firewalls, and DNS.</span></span> <span data-ttu-id="1b06b-146">该工具还运行 Skype for Business Online、Microsoft Teams、SharePoint Online 和 Exchange Online 的性能测试。</span><span class="sxs-lookup"><span data-stu-id="1b06b-146">The tool also runs performance tests for Skype for Business Online, Microsoft Teams, SharePoint Online and Exchange Online.</span></span>

<span data-ttu-id="1b06b-147">该工具包含两个组件：一个收集基本连接信息的基于浏览器的 UI，以及一个可下载的运行高级测试并返回其他评估数据的 Windows 10 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b06b-147">The tool has two components: a browser-based UI that collects basic connectivity information, and a downloadable Windows 10 application that runs advanced tests and returns additional assessment data.</span></span>

<span data-ttu-id="1b06b-148">基于浏览器的工具显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b06b-148">The browser-based tool displays the following information:</span></span>

- <span data-ttu-id="1b06b-149">结果和影响选项卡</span><span class="sxs-lookup"><span data-stu-id="1b06b-149">Results and impact tab</span></span>
  - <span data-ttu-id="1b06b-150">使用中的服务前端在地图上的位置</span><span class="sxs-lookup"><span data-stu-id="1b06b-150">The location on a map of the in-use service front door</span></span>
  - <span data-ttu-id="1b06b-151">可提供最佳连接的其他服务前门地图上的位置</span><span class="sxs-lookup"><span data-stu-id="1b06b-151">The location on a map of other service front doors that would provide optimal connectivity</span></span>
  - <span data-ttu-id="1b06b-152">相对于你附近的其他 Microsoft 365 客户的性能</span><span class="sxs-lookup"><span data-stu-id="1b06b-152">Relative performance compared to other Microsoft 365 customers near you</span></span>
- <span data-ttu-id="1b06b-153">"详细信息和解决方案"选项卡</span><span class="sxs-lookup"><span data-stu-id="1b06b-153">Details and solutions tab</span></span>
  - <span data-ttu-id="1b06b-154">按城市的国家/地区的用户位置</span><span class="sxs-lookup"><span data-stu-id="1b06b-154">User location by city and country</span></span>
  - <span data-ttu-id="1b06b-155">按城市、省/市/市/地区和国家/地区表示的网络出口位置</span><span class="sxs-lookup"><span data-stu-id="1b06b-155">Network egress location by city, state and country</span></span>
  - <span data-ttu-id="1b06b-156">用户到网络出口的距离</span><span class="sxs-lookup"><span data-stu-id="1b06b-156">User to network egress distance</span></span>
  - <span data-ttu-id="1b06b-157">Microsoft 365 Exchange Online 服务前端位置</span><span class="sxs-lookup"><span data-stu-id="1b06b-157">Microsoft 365 Exchange Online service front door location</span></span>
  - <span data-ttu-id="1b06b-158">用户位置的最佳 Microsoft 365 Exchange Online () 配置</span><span class="sxs-lookup"><span data-stu-id="1b06b-158">Optimal Microsoft 365 Exchange Online service front door(s) for user location</span></span>
  - <span data-ttu-id="1b06b-159">拥有更佳性能的你区中的客户</span><span class="sxs-lookup"><span data-stu-id="1b06b-159">Customers in your metro area with better performance</span></span>

<span data-ttu-id="1b06b-160">高级测试可下载应用程序提供以下附加信息：</span><span class="sxs-lookup"><span data-stu-id="1b06b-160">The Advanced Tests downloadable application provides the following additional information:</span></span>

- <span data-ttu-id="1b06b-161">详细信息和解决方案选项卡 (附加) </span><span class="sxs-lookup"><span data-stu-id="1b06b-161">Details and solutions tab (appended)</span></span>
  - <span data-ttu-id="1b06b-162">用户的默认网关</span><span class="sxs-lookup"><span data-stu-id="1b06b-162">User's default gateway</span></span>
  - <span data-ttu-id="1b06b-163">客户端 DNS 服务器</span><span class="sxs-lookup"><span data-stu-id="1b06b-163">Client DNS Server</span></span>
  - <span data-ttu-id="1b06b-164">客户端 DNS 递归解析程序</span><span class="sxs-lookup"><span data-stu-id="1b06b-164">Client DNS Recursive Resolver</span></span>
  - <span data-ttu-id="1b06b-165">Exchange Online DNS 服务器</span><span class="sxs-lookup"><span data-stu-id="1b06b-165">Exchange Online DNS server</span></span>
  - <span data-ttu-id="1b06b-166">SharePoint Online DNS 服务器</span><span class="sxs-lookup"><span data-stu-id="1b06b-166">SharePoint Online DNS server</span></span>
  - <span data-ttu-id="1b06b-167">代理服务器标识</span><span class="sxs-lookup"><span data-stu-id="1b06b-167">Proxy server identification</span></span>
  - <span data-ttu-id="1b06b-168">媒体连接检查</span><span class="sxs-lookup"><span data-stu-id="1b06b-168">Media connectivity check</span></span>
  - <span data-ttu-id="1b06b-169">媒体质量数据包丢失</span><span class="sxs-lookup"><span data-stu-id="1b06b-169">Media quality packet loss</span></span>
  - <span data-ttu-id="1b06b-170">媒体质量延迟</span><span class="sxs-lookup"><span data-stu-id="1b06b-170">Media quality latency</span></span>
  - <span data-ttu-id="1b06b-171">媒体质量抖动</span><span class="sxs-lookup"><span data-stu-id="1b06b-171">Media quality jitter</span></span>
  - <span data-ttu-id="1b06b-172">媒体质量数据包重新排序</span><span class="sxs-lookup"><span data-stu-id="1b06b-172">Media quality packet reorder</span></span>
- <span data-ttu-id="1b06b-173">与多个特定于功能终结点的连接测试</span><span class="sxs-lookup"><span data-stu-id="1b06b-173">Connectivity tests to multiple feature-specific endpoints</span></span>
- <span data-ttu-id="1b06b-174">包括 Exchange Online、SharePoint Online 和 Teams 服务的 tracert 和延迟数据的网络路径诊断</span><span class="sxs-lookup"><span data-stu-id="1b06b-174">Network path diagnostics that include tracert and latency data for the Exchange Online, SharePoint Online and Teams services</span></span>

<span data-ttu-id="1b06b-175">你可以阅读有关 Microsoft 365 连接测试的信息，并可在更新 [后的 Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) 连接测试 POC 和新的网络设计建议博客文章提供反馈。</span><span class="sxs-lookup"><span data-stu-id="1b06b-175">You can read about the Microsoft 365 connectivity test and provide feedback at the [Updated Microsoft 365 connectivity test POC with new network design recommendations](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) blog post.</span></span> <span data-ttu-id="1b06b-176">有关此工具和其他 Microsoft 365 网络更新的未来更新的信息将发布至 Office [365 网络](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) 博客。</span><span class="sxs-lookup"><span data-stu-id="1b06b-176">Information about future updates to this tool and other Microsoft 365 networking updates will be posted to the [Office 365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) blog.</span></span>
  
<span data-ttu-id="1b06b-177">以下是可用于返回的简短链接[ https://aka.ms/o365networkconnectivity ：。](./microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="1b06b-177">Here's a short link you can use to come back: [https://aka.ms/o365networkconnectivity.](./microsoft-365-network-connectivity-principles.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1b06b-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b06b-178">Related topics</span></span>

[<span data-ttu-id="1b06b-179">Microsoft 365 网络连接概述</span><span class="sxs-lookup"><span data-stu-id="1b06b-179">Microsoft 365 Network Connectivity Overview</span></span>](microsoft-365-networking-overview.md)

[<span data-ttu-id="1b06b-180">Microsoft 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="1b06b-180">Microsoft 365 Network Connectivity Principles</span></span>](./microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="1b06b-181">管理 Office 365 终结点</span><span class="sxs-lookup"><span data-stu-id="1b06b-181">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="1b06b-182">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="1b06b-182">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="1b06b-183">Office 365 IP 地址和 URL Web 服务</span><span class="sxs-lookup"><span data-stu-id="1b06b-183">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="1b06b-184">Microsoft 365 网络和性能调整</span><span class="sxs-lookup"><span data-stu-id="1b06b-184">Microsoft 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="1b06b-185">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="1b06b-185">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)