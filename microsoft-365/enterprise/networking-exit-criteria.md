---
title: 第 1 阶段：网络基础结构退出条件
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
description: 确保你的配置符合 Microsoft 365 企业版针对网络基础结构的条件。
ms.openlocfilehash: 8161fa2b92ffb4c7c4713e9356c0bc1bfec39d07
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865388"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="5ae54-103">第 1 阶段：网络基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="5ae54-103">Phase 1: Networking infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="5ae54-104">如果网络基础结构符合以下条件，则可继续第 2 阶段。</span><span class="sxs-lookup"><span data-stu-id="5ae54-104">If your networking infrastructure meets the following conditions, you’re ready to move to Phase 2.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="5ae54-105">必需：网络已准备就绪可供 Microsoft 365 企业版使用</span><span class="sxs-lookup"><span data-stu-id="5ae54-105">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="5ae54-106">办公室具有足够的 Internet 带宽，可用于 Microsoft 365 流量，其中包括 Office 365、Microsoft Intune、Windows 10 企业版安装和更新</span><span class="sxs-lookup"><span data-stu-id="5ae54-106">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="5ae54-107">适用所有常规 Internet 流量的中心办公室</span><span class="sxs-lookup"><span data-stu-id="5ae54-107">Central offices for all general Internet traffic</span></span>
- <span data-ttu-id="5ae54-108">适用“优化”类别终结点流量的分公司</span><span class="sxs-lookup"><span data-stu-id="5ae54-108">Branch offices for Optimize category endpoint traffic</span></span>
- <span data-ttu-id="5ae54-109">Office 365 参考体系结构的整个网络地图</span><span class="sxs-lookup"><span data-stu-id="5ae54-109">Your overall network maps to an Office 365 reference architecture</span></span>

<span data-ttu-id="5ae54-110">如果需要，可在[步骤 1](networking-provide-bandwidth-cloud-services.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="5ae54-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="5ae54-111">必需：本地办公室具有本地 Internet 连接和名称解析</span><span class="sxs-lookup"><span data-stu-id="5ae54-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="5ae54-p101">通过本地 ISP（其 DNS 服务器使用在 Internet 上标识其位置的本地公用 IP 地址）来配置每个本地办公室的 Internet 访问。这可确保访问 Office 365 和 Intune 的用户获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="5ae54-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="5ae54-114">如果每个分支机构不使用本地 ISP，则性能可能会受到影响，因为网络通信必须遍历组织的主干线或由远程前端服务器提供服务的数据请求。</span><span class="sxs-lookup"><span data-stu-id="5ae54-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5ae54-115">如何测试</span><span class="sxs-lookup"><span data-stu-id="5ae54-115">How to test</span></span>
<span data-ttu-id="5ae54-p102">使用该办公室中设备上的工具或网站来确定代理服务器所使用的公用 IP 地址。例如，使用[我的 IP 地址是什么](https://www.whatismypublicip.com/)网页。这个由 ISP 分配的公用 IP 地址在地理位置上应为本地。它不应是来自总部的公用 IP 地址范围或来自基于云的网络安全供应商。</span><span class="sxs-lookup"><span data-stu-id="5ae54-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="5ae54-120">如果需要，可在[步骤 2](networking-dns-resolution-same-location.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="5ae54-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneeded-network-hairpins-are-removed"></a><span data-ttu-id="5ae54-121">可选：删除不需要的网络回流</span><span class="sxs-lookup"><span data-stu-id="5ae54-121">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="5ae54-p103">检查网络回流并为所有办公室确定这些回流对性能的影响。在可能的情况下删除网络回流，或与第三方网络或安全提供商协作，以实现与其网络对等的最优 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5ae54-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="5ae54-124">如果需要，可在[步骤 3](networking-avoid-network-hairpins.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="5ae54-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="5ae54-125">可选：在 Internet 浏览器和边缘设备上配置流量旁路</span><span class="sxs-lookup"><span data-stu-id="5ae54-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="5ae54-126">已向本地 Internet 浏览器部署最新 PAC 文件，以使 Microsoft 365 DNS 域名的流量绕过代理服务器。</span><span class="sxs-lookup"><span data-stu-id="5ae54-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="5ae54-127">配置了网络外围设备（例如，防火墙、SSL 中断和检查以及数据包检查设备）以使用流量旁路或尽量少处理 Microsoft 365 终结点的“优化”和“允许”类别的流量。</span><span class="sxs-lookup"><span data-stu-id="5ae54-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="5ae54-128">如何测试</span><span class="sxs-lookup"><span data-stu-id="5ae54-128">How to test</span></span>

<span data-ttu-id="5ae54-129">使用网络外围设备上的日志记录工具，以确保到 Microsoft 365 目标的流量不遭到检查、解密或阻止。</span><span class="sxs-lookup"><span data-stu-id="5ae54-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="5ae54-130">如果需要，可在[步骤 4](networking-configure-proxies-firewalls.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="5ae54-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="5ae54-131">可选：配置客户端和 Office 365 应用程序以优化性能</span><span class="sxs-lookup"><span data-stu-id="5ae54-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="5ae54-132">已优化客户端设备上的传输控制协议 (TCP) 设置，以及 Exchange Online、Skype for Business Online、SharePoint Online 和 Project Online 服务。</span><span class="sxs-lookup"><span data-stu-id="5ae54-132">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="5ae54-133">如果需要，可在[步骤 5](networking-optimize-tcp-performance.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="5ae54-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="next-phase"></a><span data-ttu-id="5ae54-134">下一阶段</span><span class="sxs-lookup"><span data-stu-id="5ae54-134">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="5ae54-135">Microsoft 365 企业版端到端部署过程中的下一个阶段是[标识](identity-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="5ae54-135">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [identity](identity-infrastructure.md).</span></span> |
