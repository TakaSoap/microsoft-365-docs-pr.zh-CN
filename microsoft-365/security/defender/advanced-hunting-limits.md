---
title: Microsoft 365 Defender 中的高级搜寻配额和使用参数
description: 了解使高级搜寻服务保持响应 (服务) 的各种配额和使用参数
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构， kusto， CPU 限制， 查询限制， 资源， 最大结果， 配额， 参数， 分配
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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245596"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="28d60-104">高级搜寻配额和使用参数</span><span class="sxs-lookup"><span data-stu-id="28d60-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="28d60-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="28d60-105">**Applies to:**</span></span>
- <span data-ttu-id="28d60-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28d60-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="28d60-107">为保持服务性能高且响应迅速，高级搜寻设置各种配额和使用 (也称为"服务限制") 。</span><span class="sxs-lookup"><span data-stu-id="28d60-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="28d60-108">这些配额和参数分别应用于手动运行的查询和使用自定义检测规则 [运行的查询](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="28d60-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="28d60-109">定期运行多个查询的客户应注意这些限制，并 [应用](advanced-hunting-best-practices.md) 优化最佳做法以最大限度地减少中断。</span><span class="sxs-lookup"><span data-stu-id="28d60-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="28d60-110">请参阅下表以了解现有配额和使用参数。</span><span class="sxs-lookup"><span data-stu-id="28d60-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="28d60-111">配额或参数</span><span class="sxs-lookup"><span data-stu-id="28d60-111">Quota or parameter</span></span> | <span data-ttu-id="28d60-112">Size</span><span class="sxs-lookup"><span data-stu-id="28d60-112">Size</span></span> | <span data-ttu-id="28d60-113">刷新周期</span><span class="sxs-lookup"><span data-stu-id="28d60-113">Refresh cycle</span></span> | <span data-ttu-id="28d60-114">说明</span><span class="sxs-lookup"><span data-stu-id="28d60-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="28d60-115">数据区域</span><span class="sxs-lookup"><span data-stu-id="28d60-115">Data range</span></span> | <span data-ttu-id="28d60-116">30 天</span><span class="sxs-lookup"><span data-stu-id="28d60-116">30 days</span></span> | <span data-ttu-id="28d60-117">每个查询</span><span class="sxs-lookup"><span data-stu-id="28d60-117">Every query</span></span> | <span data-ttu-id="28d60-118">每个查询都可以查找过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="28d60-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="28d60-119">结果集</span><span class="sxs-lookup"><span data-stu-id="28d60-119">Result set</span></span> | <span data-ttu-id="28d60-120">10，000 行</span><span class="sxs-lookup"><span data-stu-id="28d60-120">10,000 rows</span></span> | <span data-ttu-id="28d60-121">每个查询</span><span class="sxs-lookup"><span data-stu-id="28d60-121">Every query</span></span> | <span data-ttu-id="28d60-122">每个查询最多可返回 10，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="28d60-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="28d60-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="28d60-123">Timeout</span></span> | <span data-ttu-id="28d60-124">10 分钟</span><span class="sxs-lookup"><span data-stu-id="28d60-124">10 minutes</span></span> | <span data-ttu-id="28d60-125">每个查询</span><span class="sxs-lookup"><span data-stu-id="28d60-125">Every query</span></span> | <span data-ttu-id="28d60-126">每个查询最多可以运行 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="28d60-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="28d60-127">如果未在 10 分钟内完成，则服务将显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="28d60-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="28d60-128">CPU 资源</span><span class="sxs-lookup"><span data-stu-id="28d60-128">CPU resources</span></span> | <span data-ttu-id="28d60-129">基于租户大小</span><span class="sxs-lookup"><span data-stu-id="28d60-129">Based on tenant size</span></span> | <span data-ttu-id="28d60-130">每 15 分钟</span><span class="sxs-lookup"><span data-stu-id="28d60-130">Every 15 minutes</span></span> | <span data-ttu-id="28d60-131">只要 [查询运行且租户已占用](advanced-hunting-errors.md) 已分配资源的 10% 以上，门户就会显示错误。</span><span class="sxs-lookup"><span data-stu-id="28d60-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="28d60-132">如果租户一直达到 100%， 直到下一个 15 分钟周期之后，查询将被阻止。</span><span class="sxs-lookup"><span data-stu-id="28d60-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="28d60-133">一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="28d60-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="28d60-134">阅读有关高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="28d60-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="28d60-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="28d60-135">Related topics</span></span>

- [<span data-ttu-id="28d60-136">高级搜寻最佳做法</span><span class="sxs-lookup"><span data-stu-id="28d60-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="28d60-137">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="28d60-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="28d60-138">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="28d60-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="28d60-139">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="28d60-139">Custom detections overview</span></span>](custom-detections-overview.md)