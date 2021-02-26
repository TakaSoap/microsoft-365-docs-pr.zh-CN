---
title: Microsoft 365 终结点
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 对于 Microsoft 365 流量的目标 IP 地址和 URL，请针对不同 Microsoft 365 云的 Internet 终结点使用此文章列表。
ms.openlocfilehash: 159c8e7dea6fe241ab44b283b1193397c3ad70e3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787899"
---
# <a name="microsoft-365-endpoints"></a><span data-ttu-id="57183-103">Microsoft 365 终结点</span><span class="sxs-lookup"><span data-stu-id="57183-103">Microsoft 365 endpoints</span></span>

<span data-ttu-id="57183-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="57183-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="57183-105">终结点是 Internet 上 Microsoft 365 通信流的目标 IP 地址、DNS 域名和 URL 集合。</span><span class="sxs-lookup"><span data-stu-id="57183-105">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Microsoft 365 traffic on the Internet.</span></span> 

<span data-ttu-id="57183-106">若要优化 Microsoft 365 基于云的服务的性能，这些终结点需要通过客户端浏览器和边缘网络中的设备执行特殊处理。</span><span class="sxs-lookup"><span data-stu-id="57183-106">To optimize performance to Microsoft 365 cloud-based services, these endpoints need special handling by your client browsers and the devices in your edge network.</span></span> <span data-ttu-id="57183-107">这些设备包括防火墙、SSL 中断和检查和包检查设备以及数据丢失防护系统。</span><span class="sxs-lookup"><span data-stu-id="57183-107">These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="57183-108">请参阅 [管理 Microsoft 365 终结点](managing-office-365-endpoints.md) 详细信息。</span><span class="sxs-lookup"><span data-stu-id="57183-108">See [Managing Microsoft 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="57183-109">当前有五个不同的 Microsoft 365 云。</span><span class="sxs-lookup"><span data-stu-id="57183-109">There are currently five different Microsoft 365 clouds.</span></span> <span data-ttu-id="57183-110">此表将让你查看每个终结点的终结点列表。</span><span class="sxs-lookup"><span data-stu-id="57183-110">This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="57183-111">云</span><span class="sxs-lookup"><span data-stu-id="57183-111">Cloud</span></span> | <span data-ttu-id="57183-112">说明</span><span class="sxs-lookup"><span data-stu-id="57183-112">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="57183-113">全球终结点</span><span class="sxs-lookup"><span data-stu-id="57183-113">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="57183-114">全球 Microsoft 365 订阅的终结点，包括美国政府社区云 （GCC）。</span><span class="sxs-lookup"><span data-stu-id="57183-114">The endpoints for worldwide Microsoft 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="57183-115">美国政府 DoD 端点</span><span class="sxs-lookup"><span data-stu-id="57183-115">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="57183-116">针对美国国防部 (DoD) 订阅的端点。</span><span class="sxs-lookup"><span data-stu-id="57183-116">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="57183-117">美国政府 GCC 高端点</span><span class="sxs-lookup"><span data-stu-id="57183-117">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="57183-118">针对美国政府社区云高（GCC 高）订阅的端点。</span><span class="sxs-lookup"><span data-stu-id="57183-118">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="57183-119">由世纪互联运营的 Microsoft 365 终结点</span><span class="sxs-lookup"><span data-stu-id="57183-119">Microsoft 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="57183-120">由世纪互联运营的 Microsoft 365 的终结点，旨在满足中国 Microsoft 365 的需求。</span><span class="sxs-lookup"><span data-stu-id="57183-120">The endpoints for Microsoft 365 operated by 21Vianet, which is designed to meet the needs for Microsoft 365 in China.</span></span> |
| [<span data-ttu-id="57183-121">Microsoft 365 Germany 终结点</span><span class="sxs-lookup"><span data-stu-id="57183-121">Microsoft 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="57183-122">为德国、欧盟 (EU) 和欧洲自由贸易协会 (EFTA) 中监管最严格的客户在欧洲建立的独立云的端点。</span><span class="sxs-lookup"><span data-stu-id="57183-122">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="57183-123">若要自动获取 Microsoft 365 云的最新终结点列表，请参阅 [Office 365 IP 地址和 URL Web 服务](microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="57183-123">To automate getting the latest list of endpoints for your Microsoft 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="57183-124">有关额外的端点，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="57183-124">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="57183-125">Web 服务中未包含的其他端点</span><span class="sxs-lookup"><span data-stu-id="57183-125">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="57183-126">Office 2016 for Mac 中的网络请求</span><span class="sxs-lookup"><span data-stu-id="57183-126">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)

<span data-ttu-id="57183-127">如果是网络设备供应商，请加入 [Office 365 网络合作伙伴计划](microsoft-365-networking-partner-program.md)。</span><span class="sxs-lookup"><span data-stu-id="57183-127">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="57183-128">注册该计划，在产品和解决方案中构建 Microsoft 365 网络连接原则。</span><span class="sxs-lookup"><span data-stu-id="57183-128">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 
