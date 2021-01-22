---
title: Microsoft 365 Defender 高级搜寻架构中的命名更改
description: 跟踪和查看高级搜寻架构中的命名更改表和列
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 数据， 命名更改， 重命名， Microsoft 威胁防护
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
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932198"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="fa5f3-104">高级搜寻架构 - 命名更改</span><span class="sxs-lookup"><span data-stu-id="fa5f3-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fa5f3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fa5f3-105">**Applies to:**</span></span>
- <span data-ttu-id="fa5f3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa5f3-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="fa5f3-107">高级 [搜寻架构](advanced-hunting-schema-tables.md) 会定期更新以添加新的表和列。</span><span class="sxs-lookup"><span data-stu-id="fa5f3-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="fa5f3-108">在某些情况下，重命名或替换现有列名称以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="fa5f3-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="fa5f3-109">请参阅本文，查看可能会影响查询的命名更改。</span><span class="sxs-lookup"><span data-stu-id="fa5f3-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="fa5f3-110">命名更改将自动应用于保存在安全中心的查询，包括自定义检测规则使用的查询。</span><span class="sxs-lookup"><span data-stu-id="fa5f3-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="fa5f3-111">无需手动更新这些查询。</span><span class="sxs-lookup"><span data-stu-id="fa5f3-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="fa5f3-112">但是，您需要更新以下查询：</span><span class="sxs-lookup"><span data-stu-id="fa5f3-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="fa5f3-113">使用 API 运行的查询</span><span class="sxs-lookup"><span data-stu-id="fa5f3-113">Queries that are run using the API</span></span>
- <span data-ttu-id="fa5f3-114">保存在安全中心外部的其他地方的查询</span><span class="sxs-lookup"><span data-stu-id="fa5f3-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="fa5f3-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="fa5f3-115">December 2020</span></span>

| <span data-ttu-id="fa5f3-116">表名</span><span class="sxs-lookup"><span data-stu-id="fa5f3-116">Table name</span></span> | <span data-ttu-id="fa5f3-117">原始列名称</span><span class="sxs-lookup"><span data-stu-id="fa5f3-117">Original column name</span></span> | <span data-ttu-id="fa5f3-118">新列名称</span><span class="sxs-lookup"><span data-stu-id="fa5f3-118">New column name</span></span> | <span data-ttu-id="fa5f3-119">更改原因</span><span class="sxs-lookup"><span data-stu-id="fa5f3-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="fa5f3-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="fa5f3-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="fa5f3-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="fa5f3-121">FinalEmailAction</span></span> | <span data-ttu-id="fa5f3-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="fa5f3-122">EmailAction</span></span> | <span data-ttu-id="fa5f3-123">客户反馈</span><span class="sxs-lookup"><span data-stu-id="fa5f3-123">Customer feedback</span></span> |
| [<span data-ttu-id="fa5f3-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="fa5f3-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="fa5f3-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="fa5f3-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="fa5f3-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="fa5f3-126">EmailActionPolicy</span></span> | <span data-ttu-id="fa5f3-127">客户反馈</span><span class="sxs-lookup"><span data-stu-id="fa5f3-127">Customer feedback</span></span> |
| [<span data-ttu-id="fa5f3-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="fa5f3-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="fa5f3-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="fa5f3-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="fa5f3-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="fa5f3-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="fa5f3-131">客户反馈</span><span class="sxs-lookup"><span data-stu-id="fa5f3-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fa5f3-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="fa5f3-132">Related topics</span></span>
- [<span data-ttu-id="fa5f3-133">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="fa5f3-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fa5f3-134">了解架构</span><span class="sxs-lookup"><span data-stu-id="fa5f3-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)