---
title: Microsoft Defender ATP 中的高级搜寻限制
description: 了解使高级搜寻服务保持响应的各种服务限制
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp， 搜索， 查询， 遥测， 架构， kusto， CPU 限制， 查询限制， 资源， 最大结果
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056379"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="61511-104">高级搜寻服务限制</span><span class="sxs-lookup"><span data-stu-id="61511-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61511-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="61511-105">**Applies to:**</span></span>
- [<span data-ttu-id="61511-106">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61511-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="61511-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="61511-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61511-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="61511-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="61511-109">为保持服务的可执行性和响应性，高级搜寻为手动和自定义检测规则运行的查询 [设置各种限制](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="61511-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="61511-110">请参阅下表以了解这些限制。</span><span class="sxs-lookup"><span data-stu-id="61511-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="61511-111">限制</span><span class="sxs-lookup"><span data-stu-id="61511-111">Limit</span></span> | <span data-ttu-id="61511-112">Size</span><span class="sxs-lookup"><span data-stu-id="61511-112">Size</span></span> | <span data-ttu-id="61511-113">刷新周期</span><span class="sxs-lookup"><span data-stu-id="61511-113">Refresh cycle</span></span> | <span data-ttu-id="61511-114">说明</span><span class="sxs-lookup"><span data-stu-id="61511-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="61511-115">数据区域</span><span class="sxs-lookup"><span data-stu-id="61511-115">Data range</span></span> | <span data-ttu-id="61511-116">30 天</span><span class="sxs-lookup"><span data-stu-id="61511-116">30 days</span></span> | <span data-ttu-id="61511-117">每个查询</span><span class="sxs-lookup"><span data-stu-id="61511-117">Every query</span></span> | <span data-ttu-id="61511-118">每个查询都可以查找过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="61511-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="61511-119">结果集</span><span class="sxs-lookup"><span data-stu-id="61511-119">Result set</span></span> | <span data-ttu-id="61511-120">10，000 行</span><span class="sxs-lookup"><span data-stu-id="61511-120">10,000 rows</span></span> | <span data-ttu-id="61511-121">每个查询</span><span class="sxs-lookup"><span data-stu-id="61511-121">Every query</span></span> | <span data-ttu-id="61511-122">每个查询最多可返回 10，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="61511-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="61511-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="61511-123">Timeout</span></span> | <span data-ttu-id="61511-124">10 分钟</span><span class="sxs-lookup"><span data-stu-id="61511-124">10 minutes</span></span> | <span data-ttu-id="61511-125">每个查询</span><span class="sxs-lookup"><span data-stu-id="61511-125">Every query</span></span> | <span data-ttu-id="61511-126">每个查询最多可以运行 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="61511-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="61511-127">如果未在 10 分钟内完成，则服务将显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="61511-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="61511-128">CPU 资源</span><span class="sxs-lookup"><span data-stu-id="61511-128">CPU resources</span></span> | <span data-ttu-id="61511-129">基于租户大小</span><span class="sxs-lookup"><span data-stu-id="61511-129">Based on tenant size</span></span> | <span data-ttu-id="61511-130">- 每小时，然后每 15 分钟</span><span class="sxs-lookup"><span data-stu-id="61511-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="61511-131">- 每天午夜 12 点</span><span class="sxs-lookup"><span data-stu-id="61511-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="61511-132">该服务单独强制执行每日和 15 分钟的限制。</span><span class="sxs-lookup"><span data-stu-id="61511-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="61511-133">对于每个限制，只要 [查询运行](advanced-hunting-errors.md) 且租户已占用已分配资源的 10% 以上，门户就会显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="61511-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="61511-134">如果直到下一个每日或 15 分钟周期之后租户一直达到 100%，将阻止查询。</span><span class="sxs-lookup"><span data-stu-id="61511-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="61511-135">一组单独的限制适用于通过 API 执行的高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="61511-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="61511-136">阅读有关高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="61511-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="61511-137">定期运行多个查询的客户应跟踪消耗情况，并应用[](advanced-hunting-best-practices.md)优化最佳做法，以最大限度地减少超出这些限制造成的中断。</span><span class="sxs-lookup"><span data-stu-id="61511-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="61511-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="61511-138">Related topics</span></span>

- [<span data-ttu-id="61511-139">高级搜寻最佳做法</span><span class="sxs-lookup"><span data-stu-id="61511-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="61511-140">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="61511-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="61511-141">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="61511-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="61511-142">自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="61511-142">Custom detections rules</span></span>](custom-detection-rules.md)
