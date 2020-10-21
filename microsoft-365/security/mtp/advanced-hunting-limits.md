---
title: Microsoft 威胁防护中的高级搜寻配额和使用参数
description: '了解 (服务限制的各种配额和使用参数，以确保高级搜寻服务响应速度) '
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构、kusto、CPU 限制、查询限制、资源、最大结果、配额、参数、分配
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 192fb47aafdd20bd5e1f0774a64ec3215f1203d1
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636901"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="ca4e9-104">高级搜寻配额和使用参数</span><span class="sxs-lookup"><span data-stu-id="ca4e9-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ca4e9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ca4e9-105">**Applies to:**</span></span>
- <span data-ttu-id="ca4e9-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="ca4e9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ca4e9-107">为了保持服务的性能和响应能力，高级搜寻设置各种配额和使用参数 (也称为 "服务限制" ) 。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="ca4e9-108">这些配额和参数适用于手动运行的查询和 [自定义检测规则](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="ca4e9-109">定期运行多个查询的客户应跟踪消耗量并 [应用优化最佳实践](advanced-hunting-best-practices.md) 以最大限度地减少中断。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="ca4e9-110">请参阅下表，了解现有的配额和使用参数。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="ca4e9-111">配额或参数</span><span class="sxs-lookup"><span data-stu-id="ca4e9-111">Quota or parameter</span></span> | <span data-ttu-id="ca4e9-112">Size</span><span class="sxs-lookup"><span data-stu-id="ca4e9-112">Size</span></span> | <span data-ttu-id="ca4e9-113">刷新周期</span><span class="sxs-lookup"><span data-stu-id="ca4e9-113">Refresh cycle</span></span> | <span data-ttu-id="ca4e9-114">说明</span><span class="sxs-lookup"><span data-stu-id="ca4e9-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="ca4e9-115">数据区域</span><span class="sxs-lookup"><span data-stu-id="ca4e9-115">Data range</span></span> | <span data-ttu-id="ca4e9-116">30 天</span><span class="sxs-lookup"><span data-stu-id="ca4e9-116">30 days</span></span> | <span data-ttu-id="ca4e9-117">每个查询</span><span class="sxs-lookup"><span data-stu-id="ca4e9-117">Every query</span></span> | <span data-ttu-id="ca4e9-118">每个查询最长可查找过去30天的数据。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="ca4e9-119">结果集</span><span class="sxs-lookup"><span data-stu-id="ca4e9-119">Result set</span></span> | <span data-ttu-id="ca4e9-120">10000行</span><span class="sxs-lookup"><span data-stu-id="ca4e9-120">10,000 rows</span></span> | <span data-ttu-id="ca4e9-121">每个查询</span><span class="sxs-lookup"><span data-stu-id="ca4e9-121">Every query</span></span> | <span data-ttu-id="ca4e9-122">每个查询最长可返回10000条记录。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="ca4e9-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="ca4e9-123">Timeout</span></span> | <span data-ttu-id="ca4e9-124">10 分钟</span><span class="sxs-lookup"><span data-stu-id="ca4e9-124">10 minutes</span></span> | <span data-ttu-id="ca4e9-125">每个查询</span><span class="sxs-lookup"><span data-stu-id="ca4e9-125">Every query</span></span> | <span data-ttu-id="ca4e9-126">每个查询最长可运行10分钟。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="ca4e9-127">如果未在10分钟内完成，则服务将显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="ca4e9-128">CPU 资源</span><span class="sxs-lookup"><span data-stu-id="ca4e9-128">CPU resources</span></span> | <span data-ttu-id="ca4e9-129">基于租户大小</span><span class="sxs-lookup"><span data-stu-id="ca4e9-129">Based on tenant size</span></span> | <span data-ttu-id="ca4e9-130">-在每小时，然后每15分钟</span><span class="sxs-lookup"><span data-stu-id="ca4e9-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="ca4e9-131">-每日午夜12点</span><span class="sxs-lookup"><span data-stu-id="ca4e9-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="ca4e9-132">该服务分别强制实施每日和15分钟的配额。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="ca4e9-133">对于每个配额，只要查询运行且租户已消耗10% 以上的已分配资源，门户就会 [显示错误](advanced-hunting-errors.md) 。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="ca4e9-134">如果租户在下一天或15分钟周期中已达到100%，则会阻止查询。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="ca4e9-135">一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="ca4e9-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="ca4e9-136">阅读有关高级搜寻 Api 的信息</span><span class="sxs-lookup"><span data-stu-id="ca4e9-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="ca4e9-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="ca4e9-137">Related topics</span></span>

- [<span data-ttu-id="ca4e9-138">高级的求职最佳实践</span><span class="sxs-lookup"><span data-stu-id="ca4e9-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ca4e9-139">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="ca4e9-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="ca4e9-140">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="ca4e9-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ca4e9-141">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="ca4e9-141">Custom detections overview</span></span>](custom-detections-overview.md)