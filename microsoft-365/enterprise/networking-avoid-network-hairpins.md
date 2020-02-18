---
title: 第 3 步：避免网络回流
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
description: 了解并删除网络回流以获得更佳性能。
ms.openlocfilehash: f9499fdb8e8c3f7b77e3349d6cc99f6dbf465870
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066701"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="52b55-103">第 3 步：避免网络回流</span><span class="sxs-lookup"><span data-stu-id="52b55-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="52b55-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="52b55-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![阶段 1：网络](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="52b55-106">当绑定到目标的流量先定向到另一个中间位置（例如本地安全堆栈、云访问代理或基于云的 Web 网关）时，会出现[网络发夹](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)。</span><span class="sxs-lookup"><span data-stu-id="52b55-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="52b55-107">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="52b55-107">Here is an example.</span></span>

![网络发夹示例](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="52b55-109">网络发夹也可能是由于网络服务提供商在 Internet 上路由不畅所致。</span><span class="sxs-lookup"><span data-stu-id="52b55-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="52b55-110">发夹会增加延迟，并且可能会将流量重定向到地理位置较远的位置。</span><span class="sxs-lookup"><span data-stu-id="52b55-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="52b55-p102">要优化 Microsoft 365 基于云的服务的流量性能，请检查提供本地 Internet 连接的 ISP 是否与该位置附近的 Microsoft 全球网络具有直接对等关系。这些连接中没有回流。</span><span class="sxs-lookup"><span data-stu-id="52b55-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="52b55-p103">如果将基于云的网络或安全服务用于 Microsoft 365 流量，请确保评估回流效果并确保了解其对性能的影响。检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="52b55-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="52b55-115">服务提供商的数量和位置，通过这些服务提供商将流量转发到分公司和 Microsoft 全球网络对等点</span><span class="sxs-lookup"><span data-stu-id="52b55-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="52b55-116">服务提供商与 ISP 和 Microsoft 的网络对等关系的质量</span><span class="sxs-lookup"><span data-stu-id="52b55-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="52b55-117">服务提供商基础结构中回程的性能影响</span><span class="sxs-lookup"><span data-stu-id="52b55-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="52b55-118">如有可能，配置边缘路由器以直接发送受信任的 Microsoft 365 流量，而不是通过处理 Internet 流量的第三方云或基于云的网络安全供应商进行代理或隧道传输。</span><span class="sxs-lookup"><span data-stu-id="52b55-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![绕过网络发夹的示例](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="52b55-120">作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step3)。</span><span class="sxs-lookup"><span data-stu-id="52b55-120">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="52b55-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="52b55-121">Next step</span></span>

|||
|:-------|:-----|
|![第 4 步](../media/stepnumbers/Step4.png)|[<span data-ttu-id="52b55-123">配置流量旁路</span><span class="sxs-lookup"><span data-stu-id="52b55-123">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
