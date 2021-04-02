---
title: Microsoft 365 Defender 中的高级搜寻配额和使用参数
description: 了解使高级搜寻服务保持响应 (服务) 的各种配额和使用参数
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构， kusto， CPU 限制， 查询限制， 资源， 最大结果， 配额， 参数， 分配
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ca79abfa95feb65f98ec32ae8dbc0093e34d58e6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498433"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="f5305-104">高级搜寻配额和使用参数</span><span class="sxs-lookup"><span data-stu-id="f5305-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5305-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f5305-105">**Applies to:**</span></span>
- <span data-ttu-id="f5305-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5305-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f5305-107">为保持服务性能高且响应迅速，高级搜寻设置各种配额和使用 (也称为"服务限制") 。</span><span class="sxs-lookup"><span data-stu-id="f5305-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="f5305-108">这些配额和参数适用于手动和自定义检测规则 [运行的查询](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="f5305-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="f5305-109">定期运行多个查询的客户应跟踪使用情况， [并应用](advanced-hunting-best-practices.md) 优化最佳做法以最大限度地减少中断。</span><span class="sxs-lookup"><span data-stu-id="f5305-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="f5305-110">请参阅下表以了解现有配额和使用参数。</span><span class="sxs-lookup"><span data-stu-id="f5305-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="f5305-111">配额或参数</span><span class="sxs-lookup"><span data-stu-id="f5305-111">Quota or parameter</span></span> | <span data-ttu-id="f5305-112">Size</span><span class="sxs-lookup"><span data-stu-id="f5305-112">Size</span></span> | <span data-ttu-id="f5305-113">刷新周期</span><span class="sxs-lookup"><span data-stu-id="f5305-113">Refresh cycle</span></span> | <span data-ttu-id="f5305-114">说明</span><span class="sxs-lookup"><span data-stu-id="f5305-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="f5305-115">数据区域</span><span class="sxs-lookup"><span data-stu-id="f5305-115">Data range</span></span> | <span data-ttu-id="f5305-116">30 天</span><span class="sxs-lookup"><span data-stu-id="f5305-116">30 days</span></span> | <span data-ttu-id="f5305-117">每个查询</span><span class="sxs-lookup"><span data-stu-id="f5305-117">Every query</span></span> | <span data-ttu-id="f5305-118">每个查询都可以查找过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="f5305-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="f5305-119">结果集</span><span class="sxs-lookup"><span data-stu-id="f5305-119">Result set</span></span> | <span data-ttu-id="f5305-120">10，000 行</span><span class="sxs-lookup"><span data-stu-id="f5305-120">10,000 rows</span></span> | <span data-ttu-id="f5305-121">每个查询</span><span class="sxs-lookup"><span data-stu-id="f5305-121">Every query</span></span> | <span data-ttu-id="f5305-122">每个查询最多可返回 10，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="f5305-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="f5305-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="f5305-123">Timeout</span></span> | <span data-ttu-id="f5305-124">10 分钟</span><span class="sxs-lookup"><span data-stu-id="f5305-124">10 minutes</span></span> | <span data-ttu-id="f5305-125">每个查询</span><span class="sxs-lookup"><span data-stu-id="f5305-125">Every query</span></span> | <span data-ttu-id="f5305-126">每个查询最多可以运行 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="f5305-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="f5305-127">如果未在 10 分钟内完成，则服务将显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="f5305-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="f5305-128">CPU 资源</span><span class="sxs-lookup"><span data-stu-id="f5305-128">CPU resources</span></span> | <span data-ttu-id="f5305-129">基于租户大小</span><span class="sxs-lookup"><span data-stu-id="f5305-129">Based on tenant size</span></span> | <span data-ttu-id="f5305-130">- 每小时，然后每 15 分钟</span><span class="sxs-lookup"><span data-stu-id="f5305-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="f5305-131">- 每天午夜 12 点</span><span class="sxs-lookup"><span data-stu-id="f5305-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="f5305-132">该服务单独强制执行每日和 15 分钟配额。</span><span class="sxs-lookup"><span data-stu-id="f5305-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="f5305-133">对于每个配额，只要 [查询运行](advanced-hunting-errors.md) 且租户已占用已分配资源的 10% 以上，门户就会显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="f5305-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="f5305-134">如果直到下一个每日或 15 分钟周期之后租户一直达到 100%，将阻止查询。</span><span class="sxs-lookup"><span data-stu-id="f5305-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="f5305-135">一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="f5305-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="f5305-136">阅读有关高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="f5305-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="f5305-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="f5305-137">Related topics</span></span>

- [<span data-ttu-id="f5305-138">高级搜寻最佳做法</span><span class="sxs-lookup"><span data-stu-id="f5305-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f5305-139">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="f5305-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="f5305-140">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="f5305-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5305-141">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="f5305-141">Custom detections overview</span></span>](custom-detections-overview.md)