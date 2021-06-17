---
title: 支持的 Microsoft 365 Defender API
description: 支持的 Microsoft 365 Defender API
keywords: Microsoft 365 Defender、API、api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985080"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="1d1e0-104">支持的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1d1e0-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1d1e0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1d1e0-105">**Applies to:**</span></span>
- <span data-ttu-id="1d1e0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d1e0-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d1e0-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1d1e0-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="1d1e0-109">可用 API 列表</span><span class="sxs-lookup"><span data-stu-id="1d1e0-109">List of available APIs</span></span>

<span data-ttu-id="1d1e0-110">文章</span><span class="sxs-lookup"><span data-stu-id="1d1e0-110">Article</span></span> | <span data-ttu-id="1d1e0-111">说明</span><span class="sxs-lookup"><span data-stu-id="1d1e0-111">Description</span></span>
-|-
[<span data-ttu-id="1d1e0-112">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="1d1e0-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="1d1e0-113">运行高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="1d1e0-114">事件 API</span><span class="sxs-lookup"><span data-stu-id="1d1e0-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="1d1e0-115">列出和更新事件以及其他实际任务。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="1d1e0-116">[流式 API](streaming-api.md) (预览) </span><span class="sxs-lookup"><span data-stu-id="1d1e0-116">[Streaming API](streaming-api.md) (Preview)</span></span> | <span data-ttu-id="1d1e0-117">在单个数据流中发生时发送实时事件和警报。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="1d1e0-118">终结点 URI</span><span class="sxs-lookup"><span data-stu-id="1d1e0-118">Endpoint URIs</span></span>

<span data-ttu-id="1d1e0-119">这两个主要 API 的基本 URI 是 https://api.security.microsoft.com ：。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="1d1e0-120">为了提高性能，请使用距离地理位置更近的服务器：</span><span class="sxs-lookup"><span data-stu-id="1d1e0-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="1d1e0-121">美国：api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1d1e0-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="1d1e0-122">欧洲：api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1d1e0-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="1d1e0-123">英国：api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1d1e0-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="1d1e0-124">可以通过访问 获取令牌 https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="1d1e0-125">路径上的所有 `/api` API 都使用 [OData](/odata/overview) 协议;例如， https://api.security.microsoft.com/api/incidents 。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1d1e0-126">相关文章</span><span class="sxs-lookup"><span data-stu-id="1d1e0-126">Related articles</span></span>

- [<span data-ttu-id="1d1e0-127">Microsoft 365 DefenderAPI 概述</span><span class="sxs-lookup"><span data-stu-id="1d1e0-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1d1e0-128">访问Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1d1e0-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1d1e0-129">Streaming API</span><span class="sxs-lookup"><span data-stu-id="1d1e0-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="1d1e0-130">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="1d1e0-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1d1e0-131">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="1d1e0-131">Understand error codes</span></span>](api-error-codes.md)
