---
title: Microsoft 威胁防护中的高级搜寻限制
description: 了解保持高级搜寻服务响应性的各种服务限制
keywords: 高级搜索、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构、kusto、CPU 限制、查询限制、资源和最大结果
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aaba01f5970c9abf55f5fae760d1ba1fed8ba914
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199873"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="e01dd-104">高级搜寻服务限制</span><span class="sxs-lookup"><span data-stu-id="e01dd-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e01dd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e01dd-105">**Applies to:**</span></span>
- <span data-ttu-id="e01dd-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="e01dd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e01dd-107">为保持服务的性能和响应能力，高级搜寻设置了对查询手动运行和 [自定义检测规则](custom-detection-rules.md)的各种限制。</span><span class="sxs-lookup"><span data-stu-id="e01dd-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="e01dd-108">若要了解这些限制，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e01dd-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="e01dd-109">限制</span><span class="sxs-lookup"><span data-stu-id="e01dd-109">Limit</span></span> | <span data-ttu-id="e01dd-110">Size</span><span class="sxs-lookup"><span data-stu-id="e01dd-110">Size</span></span> | <span data-ttu-id="e01dd-111">刷新周期</span><span class="sxs-lookup"><span data-stu-id="e01dd-111">Refresh cycle</span></span> | <span data-ttu-id="e01dd-112">说明</span><span class="sxs-lookup"><span data-stu-id="e01dd-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="e01dd-113">数据区域</span><span class="sxs-lookup"><span data-stu-id="e01dd-113">Data range</span></span> | <span data-ttu-id="e01dd-114">30 天</span><span class="sxs-lookup"><span data-stu-id="e01dd-114">30 days</span></span> | <span data-ttu-id="e01dd-115">每个查询</span><span class="sxs-lookup"><span data-stu-id="e01dd-115">Every query</span></span> | <span data-ttu-id="e01dd-116">每个查询最长可查找过去30天的数据。</span><span class="sxs-lookup"><span data-stu-id="e01dd-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="e01dd-117">结果集</span><span class="sxs-lookup"><span data-stu-id="e01dd-117">Result set</span></span> | <span data-ttu-id="e01dd-118">10000行</span><span class="sxs-lookup"><span data-stu-id="e01dd-118">10,000 rows</span></span> | <span data-ttu-id="e01dd-119">每个查询</span><span class="sxs-lookup"><span data-stu-id="e01dd-119">Every query</span></span> | <span data-ttu-id="e01dd-120">每个查询最长可返回10000条记录。</span><span class="sxs-lookup"><span data-stu-id="e01dd-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="e01dd-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="e01dd-121">Timeout</span></span> | <span data-ttu-id="e01dd-122">10 分钟</span><span class="sxs-lookup"><span data-stu-id="e01dd-122">10 minutes</span></span> | <span data-ttu-id="e01dd-123">每个查询</span><span class="sxs-lookup"><span data-stu-id="e01dd-123">Every query</span></span> | <span data-ttu-id="e01dd-124">每个查询最长可运行10分钟。</span><span class="sxs-lookup"><span data-stu-id="e01dd-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="e01dd-125">如果未在10分钟内完成，则服务将显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="e01dd-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="e01dd-126">CPU 资源</span><span class="sxs-lookup"><span data-stu-id="e01dd-126">CPU resources</span></span> | <span data-ttu-id="e01dd-127">基于租户大小</span><span class="sxs-lookup"><span data-stu-id="e01dd-127">Based on tenant size</span></span> | <span data-ttu-id="e01dd-128">-在每小时，然后每15分钟</span><span class="sxs-lookup"><span data-stu-id="e01dd-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="e01dd-129">-每日午夜12点</span><span class="sxs-lookup"><span data-stu-id="e01dd-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="e01dd-130">该服务分别强制实施每日和15分钟的限制。</span><span class="sxs-lookup"><span data-stu-id="e01dd-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="e01dd-131">对于每个限制，无论何时运行查询以及租户使用了10% 以上的已分配资源， [门户都会显示错误](advanced-hunting-errors.md) 。</span><span class="sxs-lookup"><span data-stu-id="e01dd-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="e01dd-132">如果租户在下一天或15分钟周期中已达到100%，则会阻止查询。</span><span class="sxs-lookup"><span data-stu-id="e01dd-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="e01dd-133">一组单独的限制适用于通过 API 执行的高级搜索查询。</span><span class="sxs-lookup"><span data-stu-id="e01dd-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="e01dd-134">阅读有关高级搜寻 Api 的信息</span><span class="sxs-lookup"><span data-stu-id="e01dd-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="e01dd-135">定期运行多个查询的客户应跟踪消耗量并 [应用优化最佳实践](advanced-hunting-best-practices.md) ，以最大限度地减少超出这些限制导致的中断。</span><span class="sxs-lookup"><span data-stu-id="e01dd-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e01dd-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="e01dd-136">Related topics</span></span>

- [<span data-ttu-id="e01dd-137">高级的求职最佳实践</span><span class="sxs-lookup"><span data-stu-id="e01dd-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e01dd-138">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="e01dd-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="e01dd-139">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="e01dd-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e01dd-140">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="e01dd-140">Custom detections overview</span></span>](custom-detections-overview.md)
