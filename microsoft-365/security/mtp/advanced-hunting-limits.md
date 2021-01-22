---
title: Microsoft 365 Defender 中的高级搜寻配额和使用参数
description: 了解用于保持高级搜寻 (响应) 服务限制的各种配额和使用参数
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构， kusto， CPU 限制， 查询限制， 资源， 最大结果， 配额， 参数， 分配
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929786"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="974a3-104">高级搜寻配额和使用参数</span><span class="sxs-lookup"><span data-stu-id="974a3-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="974a3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="974a3-105">**Applies to:**</span></span>
- <span data-ttu-id="974a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="974a3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="974a3-107">为保持服务性能高且响应迅速，高级搜寻设置各种配额和使用 (也称为"服务限制") 。</span><span class="sxs-lookup"><span data-stu-id="974a3-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="974a3-108">这些配额和参数适用于手动运行的查询和自定义 [检测规则](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="974a3-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="974a3-109">定期运行多个查询的客户应跟踪使用情况，并 [应用优化](advanced-hunting-best-practices.md) 最佳实践以最大限度地减少中断。</span><span class="sxs-lookup"><span data-stu-id="974a3-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="974a3-110">请参阅下表以了解现有配额和使用参数。</span><span class="sxs-lookup"><span data-stu-id="974a3-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="974a3-111">配额或参数</span><span class="sxs-lookup"><span data-stu-id="974a3-111">Quota or parameter</span></span> | <span data-ttu-id="974a3-112">Size</span><span class="sxs-lookup"><span data-stu-id="974a3-112">Size</span></span> | <span data-ttu-id="974a3-113">刷新周期</span><span class="sxs-lookup"><span data-stu-id="974a3-113">Refresh cycle</span></span> | <span data-ttu-id="974a3-114">说明</span><span class="sxs-lookup"><span data-stu-id="974a3-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="974a3-115">数据区域</span><span class="sxs-lookup"><span data-stu-id="974a3-115">Data range</span></span> | <span data-ttu-id="974a3-116">30 天</span><span class="sxs-lookup"><span data-stu-id="974a3-116">30 days</span></span> | <span data-ttu-id="974a3-117">每个查询</span><span class="sxs-lookup"><span data-stu-id="974a3-117">Every query</span></span> | <span data-ttu-id="974a3-118">每个查询都可以查找过去 30 天内的数据。</span><span class="sxs-lookup"><span data-stu-id="974a3-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="974a3-119">结果集</span><span class="sxs-lookup"><span data-stu-id="974a3-119">Result set</span></span> | <span data-ttu-id="974a3-120">10，000 行</span><span class="sxs-lookup"><span data-stu-id="974a3-120">10,000 rows</span></span> | <span data-ttu-id="974a3-121">每个查询</span><span class="sxs-lookup"><span data-stu-id="974a3-121">Every query</span></span> | <span data-ttu-id="974a3-122">每个查询最多可返回 10，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="974a3-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="974a3-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="974a3-123">Timeout</span></span> | <span data-ttu-id="974a3-124">10 分钟</span><span class="sxs-lookup"><span data-stu-id="974a3-124">10 minutes</span></span> | <span data-ttu-id="974a3-125">每个查询</span><span class="sxs-lookup"><span data-stu-id="974a3-125">Every query</span></span> | <span data-ttu-id="974a3-126">每个查询最多可以运行 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="974a3-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="974a3-127">如果在 10 分钟内未完成，则服务将显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="974a3-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="974a3-128">CPU 资源</span><span class="sxs-lookup"><span data-stu-id="974a3-128">CPU resources</span></span> | <span data-ttu-id="974a3-129">基于租户大小</span><span class="sxs-lookup"><span data-stu-id="974a3-129">Based on tenant size</span></span> | <span data-ttu-id="974a3-130">- 每小时，然后每 15 分钟</span><span class="sxs-lookup"><span data-stu-id="974a3-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="974a3-131">- 每日午夜 12 点</span><span class="sxs-lookup"><span data-stu-id="974a3-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="974a3-132">该服务单独强制执行每日和 15 分钟配额。</span><span class="sxs-lookup"><span data-stu-id="974a3-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="974a3-133">对于每个配额，只要查询 [运行](advanced-hunting-errors.md) 且租户已占用已分配资源的 10% 以上，门户就会显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="974a3-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="974a3-134">如果租户达到 100%，直到下一个每日或 15 分钟周期之后，查询将被阻止。</span><span class="sxs-lookup"><span data-stu-id="974a3-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="974a3-135">一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="974a3-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="974a3-136">阅读有关高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="974a3-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="974a3-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="974a3-137">Related topics</span></span>

- [<span data-ttu-id="974a3-138">高级搜寻最佳做法</span><span class="sxs-lookup"><span data-stu-id="974a3-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="974a3-139">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="974a3-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="974a3-140">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="974a3-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="974a3-141">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="974a3-141">Custom detections overview</span></span>](custom-detections-overview.md)