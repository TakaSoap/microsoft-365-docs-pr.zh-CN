---
title: 第 1 阶段：Microsoft 365 企业版的网络基础结构
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的网络基础结构的步骤。
ms.openlocfilehash: d575d8c3156ac1fc1a8a2bca96c875d4587ebf05
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865660"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="c211e-103">第 1 阶段：Microsoft 365 企业版的网络基础结构</span><span class="sxs-lookup"><span data-stu-id="c211e-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="c211e-p101">作为企业管理 + 安全性 (EMS) 的一部分，Microsoft 365 企业版包含了 Office 365 和 Windows Intune。这两个基于云的服务都依赖于通过 Internet 或专用线路进行连接的客户端设备的安全性、性能和可靠性。为了托管这些服务并使其对全球所有客户都可用，Microsoft 设计了侧重于性能和集成的网络基础结构。</span><span class="sxs-lookup"><span data-stu-id="c211e-p101">Microsoft 365 Enterprise includes Office 365 and Windows Intune as part of Enterprise Management + Security (EMS). Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits. To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="c211e-p102">在这个阶段，将遍历创建与 Microsoft 365 企业版云服务的高性能连接的关键注意事项。有关概述，请参阅 [Office 365 网络原则](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。</span><span class="sxs-lookup"><span data-stu-id="c211e-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="c211e-109">如果已部署网络基础结构，请查看这一阶段的[退出条件](networking-exit-criteria.md)，以确保其满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="c211e-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="c211e-110">计划和部署 Microsoft 365 企业版网络基础结构</span><span class="sxs-lookup"><span data-stu-id="c211e-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="c211e-111">使用以下步骤构建满足 Microsoft 365 企业版各项要求和能力的网络基础结构。</span><span class="sxs-lookup"><span data-stu-id="c211e-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="c211e-112">准备用于 Microsoft 365 的·网络</span><span class="sxs-lookup"><span data-stu-id="c211e-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="c211e-113">配置每个办公室的本地 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="c211e-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="c211e-114">避免网络回流</span><span class="sxs-lookup"><span data-stu-id="c211e-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="c211e-115">配置流量旁路</span><span class="sxs-lookup"><span data-stu-id="c211e-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="c211e-116">优化客户端和 Office 365 服务性能</span><span class="sxs-lookup"><span data-stu-id="c211e-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="c211e-117">在完成这些步骤后，请转到这一阶段的[退出条件](networking-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="c211e-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c211e-118">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="c211e-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c211e-119">[针对 Microsoft Office 365 优化网络性能](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)，深入了解 Microsoft，了解公司如何做好准备，针对 Office 365 云服务优化 Microsoft 网络。</span><span class="sxs-lookup"><span data-stu-id="c211e-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c211e-120">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="c211e-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c211e-121">了解 Contoso Corporation（虚构但具代表性的跨国企业）如何针对 Microsoft 365 云服务[优化其网络](contoso-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="c211e-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="c211e-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c211e-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="c211e-123">准备用于 Microsoft 365 的·网络</span><span class="sxs-lookup"><span data-stu-id="c211e-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

