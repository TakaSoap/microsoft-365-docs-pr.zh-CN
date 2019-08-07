---
title: 第 1 阶段：Microsoft 365 企业版的网络基础结构
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的网络基础结构的步骤。
ms.openlocfilehash: 4c1ea87e243d72920a3a56df270fab33bd722834
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074312"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="a43dc-103">第 1 阶段：Microsoft 365 企业版的网络基础结构</span><span class="sxs-lookup"><span data-stu-id="a43dc-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="a43dc-104">Microsoft 365 企业版包括 Office 365 和 Microsoft Intune，作为企业管理 + 安全性 (EMS) 一部分。</span><span class="sxs-lookup"><span data-stu-id="a43dc-104">Microsoft 365 Enterprise includes Office 365 and Microsoft Intune as part of Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="a43dc-105">这两种基于云的服务都依赖于来自客户端设备通过 Internet 或专用电路的连接的安全性、性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="a43dc-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="a43dc-106">为了托管这些服务并将其提供给世界各地的客户，Microsoft 设计了一个强调性能和集成的网络基础架构。</span><span class="sxs-lookup"><span data-stu-id="a43dc-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="a43dc-p102">在这个阶段，将遍历创建与 Microsoft 365 企业版云服务的高性能连接的关键注意事项。有关概述，请参阅 [Office 365 网络原则](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。</span><span class="sxs-lookup"><span data-stu-id="a43dc-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="a43dc-109">如果已部署网络基础结构，请查看这一阶段的[退出条件](networking-exit-criteria.md)，以确保其满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="a43dc-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="a43dc-110">计划和部署 Microsoft 365 企业版网络基础结构</span><span class="sxs-lookup"><span data-stu-id="a43dc-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="a43dc-111">使用以下步骤构建满足 Microsoft 365 企业版各项要求和能力的网络基础结构。</span><span class="sxs-lookup"><span data-stu-id="a43dc-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="a43dc-112">准备用于 Microsoft 365 的·网络</span><span class="sxs-lookup"><span data-stu-id="a43dc-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="a43dc-113">配置每个办公室的本地 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="a43dc-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="a43dc-114">避免网络回流</span><span class="sxs-lookup"><span data-stu-id="a43dc-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="a43dc-115">配置流量旁路</span><span class="sxs-lookup"><span data-stu-id="a43dc-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="a43dc-116">优化客户端和 Office 365 服务性能</span><span class="sxs-lookup"><span data-stu-id="a43dc-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="a43dc-117">在完成这些步骤后，请转到这一阶段的[退出条件](networking-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="a43dc-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="a43dc-118">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="a43dc-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="a43dc-119">洞察 Microsoft，了解这家公司如何[针对云服务优化 Microsoft 网络](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR4)。</span><span class="sxs-lookup"><span data-stu-id="a43dc-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="a43dc-120">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="a43dc-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="a43dc-121">了解 Contoso Corporation（有代表性的虚构跨国企业）如何针对 Microsoft 365 云服务[优化自己的网络设备和 Internet 连接](contoso-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="a43dc-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="a43dc-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a43dc-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="a43dc-123">准备用于 Microsoft 365 的·网络</span><span class="sxs-lookup"><span data-stu-id="a43dc-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

