---
title: 第 3 步：避免网络回流
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
description: 了解并删除网络回流以获得更佳性能。
ms.openlocfilehash: eb233c02d1d4c0198c11d520acca1d680df78a82
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073282"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="e46a3-103">第 3 步：避免网络回流</span><span class="sxs-lookup"><span data-stu-id="e46a3-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="e46a3-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="e46a3-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="e46a3-p101">首次将发往目标的流量定向到其他中间位置（例如本地安全堆栈、云访问代理或基于云的 Web 网关）时，会发生[网络回流](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)。由于网络服务提供商的原因，Internet 上的路由不良也可能导致网络回流。回流会增加延迟，并可能将流量重定向到地理位置较远的位置。</span><span class="sxs-lookup"><span data-stu-id="e46a3-p101">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway. A network hairpin could also be caused by poor routing on the Internet due to network service providers. A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="e46a3-p102">要优化 Microsoft 365 基于云的服务的流量性能，请检查提供本地 Internet 连接的 ISP 是否与该位置附近的 Microsoft 全球网络具有直接对等关系。这些连接中没有回流。</span><span class="sxs-lookup"><span data-stu-id="e46a3-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="e46a3-p103">如果将基于云的网络或安全服务用于 Microsoft 365 流量，请确保评估回流效果并确保了解其对性能的影响。检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="e46a3-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="e46a3-112">服务提供商的数量和位置，通过这些服务提供商将流量转发到分公司和 Microsoft 全球网络对等点</span><span class="sxs-lookup"><span data-stu-id="e46a3-112">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="e46a3-113">服务提供商与 ISP 和 Microsoft 的网络对等关系的质量</span><span class="sxs-lookup"><span data-stu-id="e46a3-113">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="e46a3-114">服务提供商基础结构中回程的性能影响</span><span class="sxs-lookup"><span data-stu-id="e46a3-114">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="e46a3-115">如有可能，配置边缘路由器以直接发送受信任的 Microsoft 365 流量，而不是通过处理 Internet 流量的第三方云或基于云的网络安全供应商进行代理或隧道传输。</span><span class="sxs-lookup"><span data-stu-id="e46a3-115">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

<span data-ttu-id="e46a3-116">作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step3)。</span><span class="sxs-lookup"><span data-stu-id="e46a3-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e46a3-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e46a3-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="e46a3-118">配置流量旁路</span><span class="sxs-lookup"><span data-stu-id="e46a3-118">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
