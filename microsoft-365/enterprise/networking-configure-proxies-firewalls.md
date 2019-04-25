---
title: 第 4 步：配置流量旁路
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Web 浏览器和边缘设备，以便流量绕过受信任的 Office 365 位置。
ms.openlocfilehash: 8486b5c0da9e44ed0b9ee42feb7acbfd21445010
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291585"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="3a7ae-103">第 4 步：配置流量旁路</span><span class="sxs-lookup"><span data-stu-id="3a7ae-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="3a7ae-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="3a7ae-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="3a7ae-p101">由于一般的 Internet 流量可能存在风险，因此典型组织网络通过代理服务器、SSL 中断和检查、数据包检查设备和数据丢失防护系统等边缘设备实施安全性。阅读有关使用第三方网络设备或 Office 365 流量解决方案的网络侦听设备的一些问题。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-p101">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span>

<span data-ttu-id="3a7ae-p102">但是，Microsoft 365 基于云的服务使用的 DNS 域名和 IP 地址是众所周知的。此外，流量和服务本身受到许多安全功能的保护。由于已经应用了安全性和保护功能，因此边缘设备无需重复此过程。Microsoft 365 流量的中间目标和重复安全性处理可能会显著降低性能。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="3a7ae-p103">消除中间目标和重复安全性处理的第一步是识别 Microsoft 365 流量。Microsoft 已定义以下类型的 DNS 域名和 IP 地址范围，称为终结点：</span><span class="sxs-lookup"><span data-stu-id="3a7ae-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="3a7ae-113">**优化** - 必需连接到每项 Office 365 服务，并代表超过 75% 的 Microsoft 365 带宽、连接和数据量。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-113">Optimize - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span> <span data-ttu-id="3a7ae-114">这些终结点代表对网络性能、延迟和可用性最敏感的 Microsoft 365 方案。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-114">Optimize - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="3a7ae-115">**允许** - 若要连接到特定 Microsoft 365 服务和功能，但不像“优化”类别终结点那样对网络性能和延迟敏感，必须使用这种类别。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-115">Allow - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="3a7ae-116">**默认** - 代表不需要任何优化的 Microsoft 365 服务和依赖项。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-116">Default - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span> <span data-ttu-id="3a7ae-117">可以将“默认”类别终结点视为正常 Internet 流量。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-117">Default - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="3a7ae-118">可在 [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints) 中查找 DNS 域名和 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-118">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="3a7ae-119">Microsoft 建议：</span><span class="sxs-lookup"><span data-stu-id="3a7ae-119">Microsoft recommends that you:</span></span>

- <span data-ttu-id="3a7ae-p106">使用本地计算机 Internet 浏览器上的代理自动配置 (PAC) 脚本绕过代理服务器以获取 Microsoft 365 基于云的服务的 DNS 域名。有关 Microsoft 365 PAC 脚本的最新信息，请参阅 Get-Pacfile PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-p106">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span>
- <span data-ttu-id="3a7ae-p107">分析边缘设备以确定重复处理，然后对其进行配置以将流量转发到“优化”和“允许”终结点而不进行处理。这称为流量旁路。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="3a7ae-p108">边缘设备包括防火墙、SSL 中断和检查、数据包检查设备和数据丢失防护系统。要配置和更新边缘设备的配置，可以使用脚本或 REST 调用来使用 Office 365 终结点 Web 服务的结构化终结点列表。有关详细信息，请参阅 [Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-p108">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="3a7ae-p109">请注意，你只是绕过了针对 Microsoft 365“优化”和“允许”类别终结点的流量的正常代理和网络安全处理。所有其他常规 Internet 流量都将被代理，并受现有网络安全处理的约束。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="3a7ae-129">作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step4)。</span><span class="sxs-lookup"><span data-stu-id="3a7ae-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="3a7ae-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3a7ae-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="3a7ae-131">优化客户端和 Office 365 服务性能</span><span class="sxs-lookup"><span data-stu-id="3a7ae-131">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



