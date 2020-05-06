---
title: 概述-高级搜寻
description: 了解 Microsoft 365 中的高级搜寻查询以及如何使用它们来主动查找网络中的威胁和弱点
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、microsoft 365、Microsoft 威胁防护
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4b5d58a006591da23d37aaeccf72cfccc6d1c43
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033970"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="95792-104">通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="95792-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="95792-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="95792-105">**Applies to:**</span></span>
- <span data-ttu-id="95792-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="95792-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="95792-107">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="95792-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="95792-108">你可以主动检查网络中的事件来找到感兴趣的指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="95792-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="95792-109">灵活访问数据有助于无约束搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="95792-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="95792-110">您可以使用相同的威胁搜寻查询来生成自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="95792-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="95792-111">这些规则会自动运行以检查和响应各种事件和系统状态，包括可疑的入侵活动和误配置的计算机。</span><span class="sxs-lookup"><span data-stu-id="95792-111">These rules run automatically to check for and respond to various events and system states, including suspected breach activity and misconfigured machines.</span></span>

<span data-ttu-id="95792-112">在 Microsoft 365 安全中心中，高级搜索支持从各种工作区查看数据的查询，其中包括有关设备、电子邮件、应用程序和 Microsoft Defender ATP、Office 365 ATP、Microsoft 云应用安全性和 Azure ATP 等标识的数据。</span><span class="sxs-lookup"><span data-stu-id="95792-112">In the Microsoft 365 security center, advanced hunting supports queries that look into data from various workspaces, including data about devices, emails, apps, and identities from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="95792-113">若要使用高级搜寻，请[打开 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="95792-113">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="95792-114">高级搜寻入门</span><span class="sxs-lookup"><span data-stu-id="95792-114">Get started with advanced hunting</span></span>

<span data-ttu-id="95792-115">我们建议执行几个步骤来通过高级搜寻快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="95792-115">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="95792-116">学习目标</span><span class="sxs-lookup"><span data-stu-id="95792-116">Learning goal</span></span> | <span data-ttu-id="95792-117">说明</span><span class="sxs-lookup"><span data-stu-id="95792-117">Description</span></span> | <span data-ttu-id="95792-118">资源</span><span class="sxs-lookup"><span data-stu-id="95792-118">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="95792-119">**了解语言**</span><span class="sxs-lookup"><span data-stu-id="95792-119">**Get a feel for the language**</span></span> | <span data-ttu-id="95792-120">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="95792-120">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="95792-121">通过运行第一个查询开始学习查询语言。</span><span class="sxs-lookup"><span data-stu-id="95792-121">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="95792-122">查询语言概述</span><span class="sxs-lookup"><span data-stu-id="95792-122">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="95792-123">**了解如何使用查询结果**</span><span class="sxs-lookup"><span data-stu-id="95792-123">**Learn how to use the query results**</span></span> | <span data-ttu-id="95792-124">了解您可以查看或导出结果的各种图表和各种方式。</span><span class="sxs-lookup"><span data-stu-id="95792-124">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="95792-125">了解如何快速调整查询和向下钻取以获取更丰富的信息。</span><span class="sxs-lookup"><span data-stu-id="95792-125">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="95792-126">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="95792-126">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="95792-127">**了解架构**</span><span class="sxs-lookup"><span data-stu-id="95792-127">**Understand the schema**</span></span> | <span data-ttu-id="95792-128">更好地大致了解架构及其列中的表。</span><span class="sxs-lookup"><span data-stu-id="95792-128">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="95792-129">这将帮助你确定在何处查找数据以及如何构建查询。</span><span class="sxs-lookup"><span data-stu-id="95792-129">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="95792-130">架构参考</span><span class="sxs-lookup"><span data-stu-id="95792-130">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="95792-131">**利用预定义查询**</span><span class="sxs-lookup"><span data-stu-id="95792-131">**Leverage predefined queries**</span></span> | <span data-ttu-id="95792-132">浏览涵盖不同威胁搜寻方案的预定义查询集合。</span><span class="sxs-lookup"><span data-stu-id="95792-132">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="95792-133">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="95792-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="95792-134">**优化查询**</span><span class="sxs-lookup"><span data-stu-id="95792-134">**Optimize queries**</span></span> | <span data-ttu-id="95792-135">了解如何创建高效查询以及组合电子邮件和设备中的数据的查询。</span><span class="sxs-lookup"><span data-stu-id="95792-135">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="95792-136">- [查询最佳实践](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="95792-136">- [Query best practices](advanced-hunting-shared-queries.md)</span></span> <br><span data-ttu-id="95792-137">- [跨设备和电子邮件的智能寻线](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="95792-137">- [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span> |
| <span data-ttu-id="95792-138">**创建自定义检测规则**</span><span class="sxs-lookup"><span data-stu-id="95792-138">**Create custom detection rules**</span></span> | <span data-ttu-id="95792-139">了解如何使用高级搜寻查询来触发通知并自动应用响应操作。</span><span class="sxs-lookup"><span data-stu-id="95792-139">Understand how you can use advanced hunting queries to trigger alerts and apply response actions automatically.</span></span> | <span data-ttu-id="95792-140">- [自定义检测概述](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="95792-140">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="95792-141">- [自定义检测规则](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="95792-141">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="related-topics"></a><span data-ttu-id="95792-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="95792-142">Related topics</span></span>
- [<span data-ttu-id="95792-143">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="95792-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="95792-144">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="95792-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="95792-145">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="95792-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="95792-146">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="95792-146">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="95792-147">了解架构</span><span class="sxs-lookup"><span data-stu-id="95792-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="95792-148">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="95792-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="95792-149">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="95792-149">Custom detections overview</span></span>](custom-detections-overview.md)