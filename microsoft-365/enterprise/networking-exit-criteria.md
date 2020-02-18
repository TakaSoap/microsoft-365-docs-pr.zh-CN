---
title: 第 1 阶段：网络基础结构退出条件
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 确保你的配置符合 Microsoft 365 企业版针对网络基础结构的条件。
ms.openlocfilehash: 1ace68fd19c62e4dc389604c1b0c02ddc18b52dc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066616"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="53b01-103">第 1 阶段：网络基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="53b01-103">Phase 1: Networking infrastructure exit criteria</span></span>

![第 1 阶段 - 网络](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="53b01-105">确保你的网络基础结构符合以下必需条件，以及你认为可选的那些条件。</span><span class="sxs-lookup"><span data-stu-id="53b01-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="53b01-106">必需：网络已准备就绪可供 Microsoft 365 企业版使用</span><span class="sxs-lookup"><span data-stu-id="53b01-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="53b01-107">你的办公室有足够的 Internet 带宽来处理 Microsoft 365 流量，包括 Office 365、Microsoft Intune 以及 Windows 10 企业版安装和更新。</span><span class="sxs-lookup"><span data-stu-id="53b01-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates.</span></span>
- <span data-ttu-id="53b01-108">你的整个网络都映射到 [Office 365 参考体系结构](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)。</span><span class="sxs-lookup"><span data-stu-id="53b01-108">Your overall network maps to an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="53b01-109">你的网络更改已经过试用和测试，符合流量延迟要求。</span><span class="sxs-lookup"><span data-stu-id="53b01-109">Your network changes have been piloted and tested and meet with your traffic latency requirements.</span></span>

<span data-ttu-id="53b01-110">如果需要，可在[步骤 1](networking-provide-bandwidth-cloud-services.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="53b01-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="53b01-111">必需：本地办公室具有本地 Internet 连接和名称解析</span><span class="sxs-lookup"><span data-stu-id="53b01-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="53b01-p101">通过本地 ISP（其 DNS 服务器使用在 Internet 上标识其位置的本地公用 IP 地址）来配置每个本地办公室的 Internet 访问。这可确保访问 Microsoft 365 云服务尽可能地获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="53b01-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="53b01-114">如果每个分支机构不使用本地 ISP，则性能可能会受到影响，因为网络通信必须遍历组织的主干线或由远程前端服务器提供服务的数据请求。</span><span class="sxs-lookup"><span data-stu-id="53b01-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="53b01-115">如何测试</span><span class="sxs-lookup"><span data-stu-id="53b01-115">How to test</span></span>
<span data-ttu-id="53b01-p102">使用该办公室中设备上的工具或网站来确定代理服务器所使用的公用 IP 地址。例如，使用[我的 IP 地址是什么](https://www.whatismypublicip.com/)网页。这个由 ISP 分配的公用 IP 地址在地理位置上应为本地。它不应是来自总部的公用 IP 地址范围或来自基于云的网络安全供应商。</span><span class="sxs-lookup"><span data-stu-id="53b01-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="53b01-120">如果需要，可在[步骤 2](networking-dns-resolution-same-location.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="53b01-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a><span data-ttu-id="53b01-121">可选：删除不必要的网络回流</span><span class="sxs-lookup"><span data-stu-id="53b01-121">Optional: Unnecessary network hairpins are removed</span></span>

<span data-ttu-id="53b01-p103">检查网络回流并为所有办公室确定这些回流对性能的影响。在可能的情况下删除网络回流，或与第三方网络或安全提供商协作，以实现与其网络对等的最优 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="53b01-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="53b01-124">如果需要，可在[步骤 3](networking-avoid-network-hairpins.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="53b01-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="53b01-125">可选：在 Internet 浏览器和边缘设备上配置流量旁路</span><span class="sxs-lookup"><span data-stu-id="53b01-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="53b01-126">已向本地 Internet 浏览器部署最新 PAC 文件，以使 Microsoft 365 DNS 域名的流量绕过代理服务器。</span><span class="sxs-lookup"><span data-stu-id="53b01-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="53b01-127">配置了网络外围设备（例如，防火墙、SSL 中断和检查以及数据包检查设备）以使用流量旁路或尽量少处理 Microsoft 365 终结点的“优化”和“允许”类别的流量。</span><span class="sxs-lookup"><span data-stu-id="53b01-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="53b01-128">如何测试</span><span class="sxs-lookup"><span data-stu-id="53b01-128">How to test</span></span>

<span data-ttu-id="53b01-129">使用网络外围设备上的日志记录工具，以确保到 Microsoft 365 目标的流量不遭到检查、解密或阻止。</span><span class="sxs-lookup"><span data-stu-id="53b01-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="53b01-130">如果需要，可在[步骤 4](networking-configure-proxies-firewalls.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="53b01-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="53b01-131">可选：配置客户端和 Office 365 应用程序以优化性能</span><span class="sxs-lookup"><span data-stu-id="53b01-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="53b01-132">已优化客户端设备上的传输控制协议 (TCP) 设置，以及 Exchange Online、Skype for Business Online、SharePoint Online 和 Project Online 服务。</span><span class="sxs-lookup"><span data-stu-id="53b01-132">You have optimized the Transmission Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="53b01-133">如果需要，可在[步骤 5](networking-optimize-tcp-performance.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="53b01-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="53b01-134">结果和后续步骤</span><span class="sxs-lookup"><span data-stu-id="53b01-134">Results and next steps</span></span>

<span data-ttu-id="53b01-135">你的 Intranet 用户已准备好通过有效的网络路径或在 Internet 上使用 Microsoft 365 云服务。</span><span class="sxs-lookup"><span data-stu-id="53b01-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![第 2 阶段 - 标识](../media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="53b01-137">如果你正在执行 Microsoft 365 企业版端到端部署的各个阶段，下一个阶段是[标识](identity-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="53b01-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
