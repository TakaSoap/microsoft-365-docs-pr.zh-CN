---
title: Microsoft 365网络连接位置服务
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365网络连接位置服务
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470444"
---
# <a name="microsoft-365-network-connectivity-location-services"></a><span data-ttu-id="c49df-103">Microsoft 365网络连接位置服务</span><span class="sxs-lookup"><span data-stu-id="c49df-103">Microsoft 365 Network Connectivity Location Services</span></span>

<span data-ttu-id="c49df-104">管理Microsoft 365中心现在显示 **Network Insights** 和性能建议，这些建议是实时性能指标，收集自你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="c49df-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics that are collected from your Microsoft 365 tenant.</span></span> <span data-ttu-id="c49df-105">这些指标仅能由租户中的管理用户查看。</span><span class="sxs-lookup"><span data-stu-id="c49df-105">These metrics can be viewed only by administrative users in your tenant.</span></span> <span data-ttu-id="c49df-106">组织网络连接是通过网络出口位置到 Internet 按办公室位置设计的。</span><span class="sxs-lookup"><span data-stu-id="c49df-106">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="c49df-107">Microsoft 365客户端连接使用该路由，然后通过 Internet 连接到 Microsoft 服务前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c49df-107">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="c49df-108">标识办公地点是显示这些网络见解的关键。</span><span class="sxs-lookup"><span data-stu-id="c49df-108">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="c49df-109">网络测量中的位置</span><span class="sxs-lookup"><span data-stu-id="c49df-109">Location in network measurements</span></span>

<span data-ttu-id="c49df-110">组织的管理员可以选择将位置包含在此功能所使用的网络度量中。</span><span class="sxs-lookup"><span data-stu-id="c49df-110">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="c49df-111">这允许自动发现每个办公室所在的城市。</span><span class="sxs-lookup"><span data-stu-id="c49df-111">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="c49df-112">位置信息并不精确，并模糊处理为 300m，并按城市分类。</span><span class="sxs-lookup"><span data-stu-id="c49df-112">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="c49df-113">在设备上捕获位置Windows时，设备将在工具托盘中显示"位置使用中"图标。 </span><span class="sxs-lookup"><span data-stu-id="c49df-113">At the time when location is captured on a Windows device, the device will show a **Location In-Use** icon in the tool tray.</span></span> <span data-ttu-id="c49df-114">管理员可能需要通知用户此图标的外观。</span><span class="sxs-lookup"><span data-stu-id="c49df-114">Administrators may want to notify users of the appearance of this icon.</span></span> <span data-ttu-id="c49df-115">通过此处理，该位置将被视为组织办公地点，而不是人员或设备的位置。</span><span class="sxs-lookup"><span data-stu-id="c49df-115">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="c49df-116">可以在这些发现的办公地点城市显示网络见解。</span><span class="sxs-lookup"><span data-stu-id="c49df-116">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="c49df-117">如果希望建议的准确性更高，可以输入特定的办公地点地址。</span><span class="sxs-lookup"><span data-stu-id="c49df-117">If you want higher accuracy in the recommendations, you can enter specific office location addresses.</span></span> <span data-ttu-id="c49df-118">网络见解将聚合到这些位置。</span><span class="sxs-lookup"><span data-stu-id="c49df-118">The network insights will be aggregated to those locations instead.</span></span> <span data-ttu-id="c49df-119">Office聚合的位置不能超过 300 米。</span><span class="sxs-lookup"><span data-stu-id="c49df-119">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c49df-120">管理中心Microsoft 365位置</span><span class="sxs-lookup"><span data-stu-id="c49df-120">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="c49df-121">在Microsoft 365中心，必应地图控件来显示组织办公地点。</span><span class="sxs-lookup"><span data-stu-id="c49df-121">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are.</span></span> <span data-ttu-id="c49df-122">这些控件还显示选定办公地点的网络外围拓扑。</span><span class="sxs-lookup"><span data-stu-id="c49df-122">The controls also show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="c49df-123">当管理员为办公地点添加特定地址详细信息时，必应地图还用于建议地址，以便更轻松地输入数据。</span><span class="sxs-lookup"><span data-stu-id="c49df-123">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="c49df-124">使用条款</span><span class="sxs-lookup"><span data-stu-id="c49df-124">Terms of Use</span></span>

<span data-ttu-id="c49df-125">通过网站必应地图（包括地理代码）只能在提供内容的产品内使用。</span><span class="sxs-lookup"><span data-stu-id="c49df-125">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="c49df-126">客户对 Microsoft 365 管理中心位置服务功能（由 必应地图 支持）的使用受 必应地图 End-User _使用条款_ 和 <https://go.microsoft.com/?linkid=9710837> Microsoft [隐私声明的约束](https://go.microsoft.com/fwlink/?LinkID=248686)。</span><span class="sxs-lookup"><span data-stu-id="c49df-126">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End-User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkID=248686).</span></span>

<span data-ttu-id="c49df-127">此功能通过 必应地图，也受 **TomTom 支持**。</span><span class="sxs-lookup"><span data-stu-id="c49df-127">This feature, provided through Bing Maps, is also supported by **TomTom**.</span></span> <span data-ttu-id="c49df-128">有关 TomTom 产品和服务的更多信息，请参阅 [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 。</span><span class="sxs-lookup"><span data-stu-id="c49df-128">More information about TomTom's products and services may be found at [https://www.tomtom.com/legal](https://www.tomtom.com/legal).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c49df-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="c49df-129">Related topics</span></span>

[<span data-ttu-id="c49df-130">Microsoft 365 管理中心 (预览) </span><span class="sxs-lookup"><span data-stu-id="c49df-130">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="c49df-131">Microsoft 365预览版 (网络性能) </span><span class="sxs-lookup"><span data-stu-id="c49df-131">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="c49df-132">Microsoft 365网络评估 (预览) </span><span class="sxs-lookup"><span data-stu-id="c49df-132">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="c49df-133">Microsoft 365管理中心中Microsoft 365预览 (连接) </span><span class="sxs-lookup"><span data-stu-id="c49df-133">Microsoft 365 connectivity test in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
