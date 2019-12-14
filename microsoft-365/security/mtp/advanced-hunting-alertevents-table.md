---
title: 高级搜寻架构中的 AlertEvents 表
description: 在高级搜寻架构的 AlertEvents 表中，了解警报生成事件
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 列, 数据类型, 说明, alertevents, 警报, 严重性, 类别
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910818"
---
# <a name="alertevents"></a><span data-ttu-id="95aff-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="95aff-104">AlertEvents</span></span>

<span data-ttu-id="95aff-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="95aff-105">**Applies to:**</span></span>
- <span data-ttu-id="95aff-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="95aff-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="95aff-107">[高级搜寻](advanced-hunting-overview.md)架构中的 `AlertEvents` 表包含有关 Microsoft Defender ATP 警报的信息。</span><span class="sxs-lookup"><span data-stu-id="95aff-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="95aff-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="95aff-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="95aff-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="95aff-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="95aff-110">列名称</span><span class="sxs-lookup"><span data-stu-id="95aff-110">Column name</span></span> | <span data-ttu-id="95aff-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="95aff-111">Data type</span></span> | <span data-ttu-id="95aff-112">说明</span><span class="sxs-lookup"><span data-stu-id="95aff-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="95aff-113">string</span><span class="sxs-lookup"><span data-stu-id="95aff-113">string</span></span> | <span data-ttu-id="95aff-114">警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="95aff-114">Unique identifier for the bucket.</span></span> |
| `EventTime` | <span data-ttu-id="95aff-115">datetime</span><span class="sxs-lookup"><span data-stu-id="95aff-115">dateTime</span></span> | <span data-ttu-id="95aff-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="95aff-116">Date and time the report was recorded.</span></span> |
| `MachineId` | <span data-ttu-id="95aff-117">string</span><span class="sxs-lookup"><span data-stu-id="95aff-117">string</span></span> | <span data-ttu-id="95aff-118">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="95aff-118">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="95aff-119">string</span><span class="sxs-lookup"><span data-stu-id="95aff-119">string</span></span> | <span data-ttu-id="95aff-120">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="95aff-120">Fully qualified domain name (FQDN) of the pool</span></span> |
| `Severity` | <span data-ttu-id="95aff-121">string</span><span class="sxs-lookup"><span data-stu-id="95aff-121">string</span></span> | <span data-ttu-id="95aff-122">指示警报所标识的威胁指示器或违反活动的潜在影响（高、中或低）</span><span class="sxs-lookup"><span data-stu-id="95aff-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="95aff-123">string</span><span class="sxs-lookup"><span data-stu-id="95aff-123">string</span></span> | <span data-ttu-id="95aff-124">由警报标识的威胁指示器或违反活动的类型</span><span class="sxs-lookup"><span data-stu-id="95aff-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="95aff-125">string</span><span class="sxs-lookup"><span data-stu-id="95aff-125">string</span></span> | <span data-ttu-id="95aff-126">警报的标题</span><span class="sxs-lookup"><span data-stu-id="95aff-126">Title of the alert.</span></span> |
| `FileName` | <span data-ttu-id="95aff-127">string</span><span class="sxs-lookup"><span data-stu-id="95aff-127">string</span></span> | <span data-ttu-id="95aff-128">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="95aff-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="95aff-129">string</span><span class="sxs-lookup"><span data-stu-id="95aff-129">string</span></span> | <span data-ttu-id="95aff-130">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="95aff-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="95aff-131">string</span><span class="sxs-lookup"><span data-stu-id="95aff-131">string</span></span> | <span data-ttu-id="95aff-132">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="95aff-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="95aff-133">string</span><span class="sxs-lookup"><span data-stu-id="95aff-133">string</span></span> | <span data-ttu-id="95aff-134">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="95aff-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="95aff-135">long</span><span class="sxs-lookup"><span data-stu-id="95aff-135">long</span></span> | <span data-ttu-id="95aff-136">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="95aff-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="95aff-137">要标识唯一事件，此列必须与 ComputerName 和 EventTime 列一起使用</span><span class="sxs-lookup"><span data-stu-id="95aff-137">To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns</span></span> |
| `Table` | <span data-ttu-id="95aff-138">string</span><span class="sxs-lookup"><span data-stu-id="95aff-138">string</span></span> | <span data-ttu-id="95aff-139">包含事件详细信息的表</span><span class="sxs-lookup"><span data-stu-id="95aff-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="95aff-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="95aff-140">Related topics</span></span>
- [<span data-ttu-id="95aff-141">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="95aff-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="95aff-142">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="95aff-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="95aff-143">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="95aff-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="95aff-144">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="95aff-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="95aff-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="95aff-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="95aff-146">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="95aff-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
