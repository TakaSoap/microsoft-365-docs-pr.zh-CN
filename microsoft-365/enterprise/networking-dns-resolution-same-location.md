---
title: 第 2 步：配置每个办公室的本地 Internet 连接
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
description: 理解并配置 DNS 解析，以获得更好的性能。
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066651"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="3e5f5-103">第 2 步：配置每个办公室的本地 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="3e5f5-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="3e5f5-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="3e5f5-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![阶段 1：网络](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="3e5f5-p101">在第 2 步中，确保每个办公室都具有本地 Internet 连接并使用本地 DNS 服务器。要求这两个元素均降低连接延迟，并确保本地客户端计算机与 Microsoft 365 基于云的服务的最近入口点建立连接。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="3e5f5-108">在大型组织的传统网络中，Internet 流量通过网络主干网传输到中央 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="3e5f5-109">这不适用于优化全局分布式软件即服务 (SaaS) 基础结构的性能，该基础结构包含 Microsoft 365 中的 Office 365 和 Intune 产品。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="3e5f5-110">Microsoft 全局网络包括*分布式服务前端*基础结构，后者是具有异地分布位置的高可用性和可扩展网络边缘。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="3e5f5-111">它将终止前端服务器上的最终用户连接，并高效地在 Microsoft 全局网络中路由最终用户流量。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![Microsoft 全局网络](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="3e5f5-113">为了获得最佳性能，本地客户端应访问地理位置最靠近它们的前端位置，而不是通过网络主干网发送流量并将流量发送到最靠近组织中央 Internet 连接的前端。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="3e5f5-114">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-114">Here’s an example.</span></span>

![使用 Microsoft 全局网络的示例](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="3e5f5-116">当巴黎分支机构中的用户想要访问 SharePoint Online 网站时：</span><span class="sxs-lookup"><span data-stu-id="3e5f5-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="3e5f5-117">它将发送 DNS 查询来解析名称，例如 contoso.sharepoint.com。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="3e5f5-118">ISP 提供的 DNS 服务器会将此查询转发到 Microsoft DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="3e5f5-119">Microsoft DNS 服务器会将转发的 DNS 查询的源 IP 地址与分配该地址的世界区域相匹配。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="3e5f5-120">Microsoft DNS 服务器将使用欧洲最近的 Microsoft 网络前端的 IP 地址进行响应。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="3e5f5-121">ISP DNS 服务器将该 IP 地址发送给用户。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="3e5f5-122">用户通过欧洲前端启动与 SharePoint 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="3e5f5-123">为了将客户端请求定向到地理位置最近的前端，Microsoft DNS 服务器使用与客户端初始连接请求相对应的 DNS 查询。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="3e5f5-124">因此，为了实现最低网络延迟：</span><span class="sxs-lookup"><span data-stu-id="3e5f5-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="3e5f5-125">组织的所有办公室都应具有本地 Internet 连接，以便[优化](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)类别网络流量。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="3e5f5-126">每个本地 Internet 连接应使用地区本地 DNS 服务器来处理来自该位置的出站 Internet 流量。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="3e5f5-127">有关详细信息，请参阅[本地出口网络连接](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="3e5f5-128">作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step2)。</span><span class="sxs-lookup"><span data-stu-id="3e5f5-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="3e5f5-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3e5f5-129">Next step</span></span>

|||
|:-------|:-----|
|![第 3 步](../media/stepnumbers/Step3.png)|[<span data-ttu-id="3e5f5-131">避免网络回流</span><span class="sxs-lookup"><span data-stu-id="3e5f5-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
