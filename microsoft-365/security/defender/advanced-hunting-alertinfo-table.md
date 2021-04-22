---
title: 高级搜寻架构中的 AlertInfo 表
description: 了解高级搜寻架构的 AlertInfo 表中的警报生成事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， AlertInfo， 警报， 严重性， 类别， MITRE， ATT&CK， Microsoft Defender for Endpoint， Microsoft Defender for Office 365， Microsoft Cloud App Security， MCAS， And Microsoft Defender for Identity
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933693"
---
# <a name="alertinfo"></a><span data-ttu-id="75174-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="75174-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75174-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="75174-105">**Applies to:**</span></span>
- <span data-ttu-id="75174-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75174-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="75174-107">高级 `AlertInfo` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的警报的信息。</span><span class="sxs-lookup"><span data-stu-id="75174-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="75174-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="75174-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="75174-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="75174-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="75174-110">列名称</span><span class="sxs-lookup"><span data-stu-id="75174-110">Column name</span></span> | <span data-ttu-id="75174-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="75174-111">Data type</span></span> | <span data-ttu-id="75174-112">说明</span><span class="sxs-lookup"><span data-stu-id="75174-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="75174-113">datetime</span><span class="sxs-lookup"><span data-stu-id="75174-113">datetime</span></span> | <span data-ttu-id="75174-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="75174-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="75174-115">string</span><span class="sxs-lookup"><span data-stu-id="75174-115">string</span></span> | <span data-ttu-id="75174-116">警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="75174-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="75174-117">string</span><span class="sxs-lookup"><span data-stu-id="75174-117">string</span></span> | <span data-ttu-id="75174-118">警报的标题</span><span class="sxs-lookup"><span data-stu-id="75174-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="75174-119">string</span><span class="sxs-lookup"><span data-stu-id="75174-119">string</span></span> | <span data-ttu-id="75174-120">由警报标识的威胁指示器或违反活动的类型</span><span class="sxs-lookup"><span data-stu-id="75174-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="75174-121">string</span><span class="sxs-lookup"><span data-stu-id="75174-121">string</span></span> | <span data-ttu-id="75174-122">指示警报所标识的威胁指示器或违反活动的潜在影响（高、中或低）</span><span class="sxs-lookup"><span data-stu-id="75174-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="75174-123">string</span><span class="sxs-lookup"><span data-stu-id="75174-123">string</span></span> | <span data-ttu-id="75174-124">提供警报信息的产品或服务</span><span class="sxs-lookup"><span data-stu-id="75174-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="75174-125">string</span><span class="sxs-lookup"><span data-stu-id="75174-125">string</span></span> | <span data-ttu-id="75174-126">标识值得注意的组件或活动的检测技术或传感器</span><span class="sxs-lookup"><span data-stu-id="75174-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="75174-127">string</span><span class="sxs-lookup"><span data-stu-id="75174-127">string</span></span> | <span data-ttu-id="75174-128">MITRE ATT&触发警报的活动相关的 CK 技术</span><span class="sxs-lookup"><span data-stu-id="75174-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="75174-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="75174-129">Related topics</span></span>
- [<span data-ttu-id="75174-130">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="75174-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="75174-131">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="75174-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="75174-132">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="75174-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="75174-133">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="75174-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="75174-134">了解架构</span><span class="sxs-lookup"><span data-stu-id="75174-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="75174-135">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="75174-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
