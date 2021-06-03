---
title: 支持的 Microsoft 365 Defender API
description: 支持的 Microsoft 365 Defender API
keywords: Microsoft 365Defender， API， api
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
ms.openlocfilehash: c10b2863503a5bda829cbf67379a606b687ac2e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730938"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="745b6-104">支持的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="745b6-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="745b6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="745b6-105">**Applies to:**</span></span>
- <span data-ttu-id="745b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="745b6-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="745b6-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="745b6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="745b6-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="745b6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="745b6-109">可用 API 列表</span><span class="sxs-lookup"><span data-stu-id="745b6-109">List of available APIs</span></span>

<span data-ttu-id="745b6-110">文章</span><span class="sxs-lookup"><span data-stu-id="745b6-110">Article</span></span> | <span data-ttu-id="745b6-111">说明</span><span class="sxs-lookup"><span data-stu-id="745b6-111">Description</span></span>
-|-
[<span data-ttu-id="745b6-112">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="745b6-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="745b6-113">运行高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="745b6-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="745b6-114">事件 API</span><span class="sxs-lookup"><span data-stu-id="745b6-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="745b6-115">列出和更新事件以及其他实际任务。</span><span class="sxs-lookup"><span data-stu-id="745b6-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="745b6-116">[流式 API](../defender-endpoint/raw-data-export.md) (预览) </span><span class="sxs-lookup"><span data-stu-id="745b6-116">[Streaming API](../defender-endpoint/raw-data-export.md) (Preview)</span></span> | <span data-ttu-id="745b6-117">在单个数据流中发生时发送实时事件和警报。</span><span class="sxs-lookup"><span data-stu-id="745b6-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="745b6-118">终结点 URI</span><span class="sxs-lookup"><span data-stu-id="745b6-118">Endpoint URIs</span></span>

<span data-ttu-id="745b6-119">这两个主要 API 的基本 URI 是 https://api.security.microsoft.com ：。</span><span class="sxs-lookup"><span data-stu-id="745b6-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="745b6-120">为了提高性能，请使用距离地理位置更近的服务器：</span><span class="sxs-lookup"><span data-stu-id="745b6-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="745b6-121">美国：api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="745b6-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="745b6-122">欧洲：api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="745b6-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="745b6-123">英国：api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="745b6-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="745b6-124">可以通过访问 获取令牌 https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="745b6-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="745b6-125">路径上的所有 `/api` API 都使用 [OData](/odata/overview) 协议;例如， https://api.security.microsoft.com/api/incidents 。</span><span class="sxs-lookup"><span data-stu-id="745b6-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="745b6-126">相关文章</span><span class="sxs-lookup"><span data-stu-id="745b6-126">Related articles</span></span>

- [<span data-ttu-id="745b6-127">Microsoft 365Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="745b6-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="745b6-128">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="745b6-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="745b6-129">流式处理 API</span><span class="sxs-lookup"><span data-stu-id="745b6-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="745b6-130">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="745b6-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="745b6-131">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="745b6-131">Understand error codes</span></span>](api-error-codes.md)
