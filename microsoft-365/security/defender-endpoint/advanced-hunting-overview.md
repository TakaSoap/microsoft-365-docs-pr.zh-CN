---
title: Microsoft Defender ATP 中的高级搜寻概述
description: 使用 Microsoft Defender ATP 中的威胁搜寻功能生成查找网络中的威胁和弱点的查询
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， 时区， UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9e5f29874ae42f2b82906a5ac0d2e615009d499f
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615479"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a><span data-ttu-id="4220b-104">使用高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="4220b-104">Proactively hunt for threats with advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4220b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4220b-105">**Applies to:**</span></span>
- [<span data-ttu-id="4220b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4220b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="4220b-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4220b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4220b-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4220b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="4220b-109">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="4220b-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="4220b-110">你可以主动检查网络中事件，以查找威胁指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="4220b-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="4220b-111">通过灵活的数据访问，可以不受限制地搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="4220b-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="4220b-112">观看此视频，快速概览高级搜寻和快速入门的简短教程。</span><span class="sxs-lookup"><span data-stu-id="4220b-112">Watch this video for a quick overview of advanced hunting and a short tutorial that will get you started fast.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

<span data-ttu-id="4220b-113">你可以使用相同的威胁搜寻查询来构建自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="4220b-113">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="4220b-114">这些规则将自动运行，以检查并响应可疑的泄露活动、错误配置的计算机和其他发现。</span><span class="sxs-lookup"><span data-stu-id="4220b-114">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

>[!TIP]
><span data-ttu-id="4220b-115">使用 [Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) 中的高级搜寻，使用来自 Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的数据搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="4220b-115">Use [advanced hunting in Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) to hunt for threats using data from Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="4220b-116">[打开 Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)。</span><span class="sxs-lookup"><span data-stu-id="4220b-116">[Turn on Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).</span></span><br><br>
<span data-ttu-id="4220b-117">在从 Microsoft Defender for Endpoint 迁移高级搜寻查询中，详细了解如何将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到 Microsoft 365 [Defender。](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)</span><span class="sxs-lookup"><span data-stu-id="4220b-117">Learn more about how to move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="4220b-118">高级搜寻入门</span><span class="sxs-lookup"><span data-stu-id="4220b-118">Get started with advanced hunting</span></span>

<span data-ttu-id="4220b-119">执行以下步骤以提升高级搜寻知识。</span><span class="sxs-lookup"><span data-stu-id="4220b-119">Go through the following steps to ramp up your advanced hunting knowledge.</span></span>

<span data-ttu-id="4220b-120">我们建议执行几个步骤来通过高级搜寻快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="4220b-120">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="4220b-121">学习目标</span><span class="sxs-lookup"><span data-stu-id="4220b-121">Learning goal</span></span> | <span data-ttu-id="4220b-122">说明</span><span class="sxs-lookup"><span data-stu-id="4220b-122">Description</span></span> | <span data-ttu-id="4220b-123">资源</span><span class="sxs-lookup"><span data-stu-id="4220b-123">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="4220b-124">**了解语言**</span><span class="sxs-lookup"><span data-stu-id="4220b-124">**Learn the language**</span></span> | <span data-ttu-id="4220b-125">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="4220b-125">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="4220b-126">通过运行第一个查询开始学习查询语言。</span><span class="sxs-lookup"><span data-stu-id="4220b-126">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="4220b-127">查询语言概述</span><span class="sxs-lookup"><span data-stu-id="4220b-127">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="4220b-128">**了解如何使用查询结果**</span><span class="sxs-lookup"><span data-stu-id="4220b-128">**Learn how to use the query results**</span></span> | <span data-ttu-id="4220b-129">了解图表以及查看或导出结果的各种方法。</span><span class="sxs-lookup"><span data-stu-id="4220b-129">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="4220b-130">了解如何快速调整查询并向下钻取以获取更丰富的信息。</span><span class="sxs-lookup"><span data-stu-id="4220b-130">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="4220b-131">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="4220b-131">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="4220b-132">**了解架构**</span><span class="sxs-lookup"><span data-stu-id="4220b-132">**Understand the schema**</span></span> | <span data-ttu-id="4220b-133">更好地大致了解架构及其列中的表。</span><span class="sxs-lookup"><span data-stu-id="4220b-133">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="4220b-134">了解在构造查询时在何处查找数据。</span><span class="sxs-lookup"><span data-stu-id="4220b-134">Learn where to look for data when constructing your queries.</span></span> | [<span data-ttu-id="4220b-135">架构参考</span><span class="sxs-lookup"><span data-stu-id="4220b-135">Schema reference</span></span>](advanced-hunting-schema-reference.md) |
| <span data-ttu-id="4220b-136">**使用预定义查询**</span><span class="sxs-lookup"><span data-stu-id="4220b-136">**Use predefined queries**</span></span> | <span data-ttu-id="4220b-137">浏览涵盖不同威胁搜寻方案的预定义查询集合。</span><span class="sxs-lookup"><span data-stu-id="4220b-137">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="4220b-138">共享查询</span><span class="sxs-lookup"><span data-stu-id="4220b-138">Shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="4220b-139">**优化查询和处理错误**</span><span class="sxs-lookup"><span data-stu-id="4220b-139">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="4220b-140">了解如何创建高效且无错误的查询。</span><span class="sxs-lookup"><span data-stu-id="4220b-140">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="4220b-141">- [查询最佳做法](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="4220b-141">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="4220b-142">- [处理错误](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="4220b-142">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="4220b-143">**获得最完整的覆盖范围**</span><span class="sxs-lookup"><span data-stu-id="4220b-143">**Get the most complete coverage**</span></span> | <span data-ttu-id="4220b-144">使用审核设置为组织提供更好的数据覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="4220b-144">Use audit settings to provide better data coverage for your organization.</span></span> | <span data-ttu-id="4220b-145">- [扩展高级搜寻范围](advanced-hunting-extend-data.md)</span><span class="sxs-lookup"><span data-stu-id="4220b-145">- [Extend advanced hunting coverage](advanced-hunting-extend-data.md)</span></span> |
| <span data-ttu-id="4220b-146">**运行快速调查**</span><span class="sxs-lookup"><span data-stu-id="4220b-146">**Run a quick investigation**</span></span> | <span data-ttu-id="4220b-147">快速运行高级搜寻查询以调查可疑活动。</span><span class="sxs-lookup"><span data-stu-id="4220b-147">Quickly run an advanced hunting query to investigate suspicious activity.</span></span> | <span data-ttu-id="4220b-148">- [使用 go hunt 快速搜寻实体或 *事件信息*](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="4220b-148">- [Quickly hunt for entity or event information with *go hunt*](advanced-hunting-go-hunt.md)</span></span> |
| <span data-ttu-id="4220b-149">**包含威胁和地址泄露**</span><span class="sxs-lookup"><span data-stu-id="4220b-149">**Contain threats and address compromises**</span></span> | <span data-ttu-id="4220b-150">通过隔离文件、限制应用执行和其他操作来响应攻击</span><span class="sxs-lookup"><span data-stu-id="4220b-150">Respond to attacks by quarantining files, restricting app execution, and other actions</span></span> | <span data-ttu-id="4220b-151">- [对高级搜寻查询结果采取措施](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="4220b-151">- [Take action on advanced hunting query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="4220b-152">**创建自定义检测规则**</span><span class="sxs-lookup"><span data-stu-id="4220b-152">**Create custom detection rules**</span></span> | <span data-ttu-id="4220b-153">了解如何使用高级搜寻查询来触发警报并自动执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="4220b-153">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="4220b-154">- [自定义检测概述](overview-custom-detections.md)</span><span class="sxs-lookup"><span data-stu-id="4220b-154">- [Custom detections overview](overview-custom-detections.md)</span></span><br><span data-ttu-id="4220b-155">- [自定义检测规则](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="4220b-155">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="4220b-156">数据新鲜度和更新频率</span><span class="sxs-lookup"><span data-stu-id="4220b-156">Data freshness and update frequency</span></span>

<span data-ttu-id="4220b-157">高级搜寻数据可以分为两种不同的类型，每种类型合并的方式不同。</span><span class="sxs-lookup"><span data-stu-id="4220b-157">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="4220b-158">**事件或活动数据**- 填充有关警报、安全事件、系统事件和例程评估的表。</span><span class="sxs-lookup"><span data-stu-id="4220b-158">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="4220b-159">高级搜寻在收集它们传感器将其成功传输到 Defender for Endpoint 后，几乎会立即收到此数据。</span><span class="sxs-lookup"><span data-stu-id="4220b-159">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to Defender for Endpoint.</span></span>
- <span data-ttu-id="4220b-160">**实体数据**- 使用有关用户和设备的综合信息填充表。</span><span class="sxs-lookup"><span data-stu-id="4220b-160">**Entity data**—populates tables with consolidated information about users and devices.</span></span> <span data-ttu-id="4220b-161">此数据来自相对静态数据源和动态源，如 Active Directory 条目和事件日志。</span><span class="sxs-lookup"><span data-stu-id="4220b-161">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="4220b-162">为了提供最新数据，表格每 15 分钟更新一次任何新信息，并添加可能未完全填充的行。</span><span class="sxs-lookup"><span data-stu-id="4220b-162">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="4220b-163">每 24 小时合并一次数据，以插入包含有关每个实体的最新、最全面的数据集的记录。</span><span class="sxs-lookup"><span data-stu-id="4220b-163">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="4220b-164">时区</span><span class="sxs-lookup"><span data-stu-id="4220b-164">Time zone</span></span>

<span data-ttu-id="4220b-165">高级搜寻中的时间信息当前处于 UTC 时区。</span><span class="sxs-lookup"><span data-stu-id="4220b-165">Time information in advanced hunting is currently in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4220b-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="4220b-166">Related topics</span></span>

- [<span data-ttu-id="4220b-167">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="4220b-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4220b-168">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="4220b-168">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4220b-169">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="4220b-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4220b-170">了解架构</span><span class="sxs-lookup"><span data-stu-id="4220b-170">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="4220b-171">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="4220b-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="4220b-172">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="4220b-172">Custom detections overview</span></span>](overview-custom-detections.md)
