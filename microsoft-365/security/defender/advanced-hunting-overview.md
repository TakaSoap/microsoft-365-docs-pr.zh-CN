---
title: 概述 - 高级搜寻
description: 了解 Microsoft 365 中的高级搜寻查询以及如何使用它们来主动查找网络中的威胁和弱点
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: df48ec921dee7d8f3b441ed3f68ed148c5c6c857
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932973"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="1f858-104">在 Microsoft 365 Defender 中通过高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="1f858-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1f858-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1f858-105">**Applies to:**</span></span>
- <span data-ttu-id="1f858-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f858-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="1f858-107">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="1f858-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="1f858-108">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="1f858-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="1f858-109">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="1f858-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="1f858-110">你可以主动检查网络中事件，以查找威胁指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="1f858-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="1f858-111">通过灵活的数据访问，可以不受限制地搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="1f858-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="1f858-112">你可以使用相同的威胁搜寻查询来构建自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="1f858-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="1f858-113">这些规则将自动运行，以检查并响应可疑的泄露活动、错误配置的计算机和其他发现。</span><span class="sxs-lookup"><span data-stu-id="1f858-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="1f858-114">此功能类似于 Microsoft [Defender for Endpoint 中的高级搜寻](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="1f858-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="1f858-115">此功能在 Microsoft 365 安全中心中可用，它支持从检查更广泛的数据集的查询：</span><span class="sxs-lookup"><span data-stu-id="1f858-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="1f858-116">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1f858-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="1f858-117">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1f858-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="1f858-118">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="1f858-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1f858-119">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1f858-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="1f858-120">若要使用高级搜寻， [请打开 Microsoft 365 Defender](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="1f858-120">To use advanced hunting, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="1f858-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="1f858-121">Before you begin</span></span>

<span data-ttu-id="1f858-122">用户需要以下权限级别之一才能访问 Microsoft Defender：</span><span class="sxs-lookup"><span data-stu-id="1f858-122">Users need one of the following levels of permissions to access Microsoft Defender:</span></span>

- <span data-ttu-id="1f858-123">可读写 (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="1f858-123">Full access (read and write)</span></span>
- <span data-ttu-id="1f858-124">只读访问</span><span class="sxs-lookup"><span data-stu-id="1f858-124">Read-only access</span></span>

<span data-ttu-id="1f858-125">**完全访问权限**：具有完全访问权限的用户可以保存、修改和共享查询。</span><span class="sxs-lookup"><span data-stu-id="1f858-125">**Full access**: Users with full access can save, modify, and share a query.</span></span> <span data-ttu-id="1f858-126">分配完全访问权限需要将用户添加到 Azure Active Directory 中的"安全管理员"或"全局管理员"内置角色 (AAD) 。</span><span class="sxs-lookup"><span data-stu-id="1f858-126">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" built-in roles in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="1f858-127">**只读访问**：具有只读访问权限的用户可以登录并查看所有警报和相关信息。</span><span class="sxs-lookup"><span data-stu-id="1f858-127">**Read-only access**: Users with read-only access can log in and view all alerts and related information.</span></span> <span data-ttu-id="1f858-128">他们将无法保存、修改或共享查询。</span><span class="sxs-lookup"><span data-stu-id="1f858-128">They will not be able to save, modify, or share a query.</span></span> <span data-ttu-id="1f858-129">分配只读访问权限需要将用户添加到 AAD 中的"安全读者"内置角色。</span><span class="sxs-lookup"><span data-stu-id="1f858-129">Assigning read-only access rights requires adding the users to the "Security Reader" built-in role in AAD.</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="1f858-130">高级搜寻入门</span><span class="sxs-lookup"><span data-stu-id="1f858-130">Get started with advanced hunting</span></span>

<span data-ttu-id="1f858-131">我们建议执行几个步骤以快速开始使用高级搜寻。</span><span class="sxs-lookup"><span data-stu-id="1f858-131">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="1f858-132">学习目标</span><span class="sxs-lookup"><span data-stu-id="1f858-132">Learning goal</span></span> | <span data-ttu-id="1f858-133">说明</span><span class="sxs-lookup"><span data-stu-id="1f858-133">Description</span></span> | <span data-ttu-id="1f858-134">资源</span><span class="sxs-lookup"><span data-stu-id="1f858-134">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="1f858-135">**了解语言**</span><span class="sxs-lookup"><span data-stu-id="1f858-135">**Learn the language**</span></span> | <span data-ttu-id="1f858-136">高级搜寻基于 [Kusto 查询语言](/azure/kusto/query/)，支持相同的语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="1f858-136">Advanced hunting is based on [Kusto query language](/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="1f858-137">通过运行第一个查询开始学习查询语言。</span><span class="sxs-lookup"><span data-stu-id="1f858-137">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="1f858-138">查询语言概述</span><span class="sxs-lookup"><span data-stu-id="1f858-138">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="1f858-139">**了解如何使用查询结果**</span><span class="sxs-lookup"><span data-stu-id="1f858-139">**Learn how to use the query results**</span></span> | <span data-ttu-id="1f858-140">了解图表以及查看或导出结果的各种方法。</span><span class="sxs-lookup"><span data-stu-id="1f858-140">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="1f858-141">了解如何快速调整查询、向下钻取以获取更丰富的信息以及执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="1f858-141">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="1f858-142">- [使用查询结果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-142">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="1f858-143">- [对查询结果采取措施](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-143">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="1f858-144">**了解架构**</span><span class="sxs-lookup"><span data-stu-id="1f858-144">**Understand the schema**</span></span> | <span data-ttu-id="1f858-145">更好地大致了解架构及其列中的表。</span><span class="sxs-lookup"><span data-stu-id="1f858-145">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="1f858-146">了解在构造查询时在何处查找数据。</span><span class="sxs-lookup"><span data-stu-id="1f858-146">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="1f858-147">- [架构参考](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-147">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="1f858-148">- [从 Microsoft Defender for Endpoint 转换](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-148">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)</span></span> |
| <span data-ttu-id="1f858-149">**获取专家提示和示例**</span><span class="sxs-lookup"><span data-stu-id="1f858-149">**Get expert tips and examples**</span></span> | <span data-ttu-id="1f858-150">通过 Microsoft 专家的指南免费培训。</span><span class="sxs-lookup"><span data-stu-id="1f858-150">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="1f858-151">浏览涵盖不同威胁搜寻方案的预定义查询集合。</span><span class="sxs-lookup"><span data-stu-id="1f858-151">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="1f858-152">- [获取专家培训](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-152">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="1f858-153">- [使用共享查询](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-153">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="1f858-154">- [去寻线](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-154">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="1f858-155">- [跨设备、电子邮件、应用和标识搜寻威胁](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-155">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="1f858-156">**优化查询和处理错误**</span><span class="sxs-lookup"><span data-stu-id="1f858-156">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="1f858-157">了解如何创建高效且无错误的查询。</span><span class="sxs-lookup"><span data-stu-id="1f858-157">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="1f858-158">- [查询最佳做法](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-158">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="1f858-159">- [处理错误](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-159">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="1f858-160">**创建自定义检测规则**</span><span class="sxs-lookup"><span data-stu-id="1f858-160">**Create custom detection rules**</span></span> | <span data-ttu-id="1f858-161">了解如何使用高级搜寻查询来触发警报并自动执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="1f858-161">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="1f858-162">- [自定义检测概述](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-162">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="1f858-163">- [自定义检测规则](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="1f858-163">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="1f858-164">获取访问权限</span><span class="sxs-lookup"><span data-stu-id="1f858-164">Get access</span></span>
<span data-ttu-id="1f858-165">若要使用高级搜寻或其他 [Microsoft 365 Defender](microsoft-365-defender.md) 功能，你需要在 Azure Active Directory 中担任适当的角色。</span><span class="sxs-lookup"><span data-stu-id="1f858-165">To use advanced hunting or other [Microsoft 365 Defender](microsoft-365-defender.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="1f858-166">此外，对终结点数据的访问由基于角色的访问控制 (Microsoft Defender for Endpoint) RBAC 设置确定。</span><span class="sxs-lookup"><span data-stu-id="1f858-166">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="1f858-167">阅读有关管理对 Microsoft 365 Defender 的访问权限</span><span class="sxs-lookup"><span data-stu-id="1f858-167">Read about managing access to Microsoft 365 Defender</span></span>](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="1f858-168">数据新鲜度和更新频率</span><span class="sxs-lookup"><span data-stu-id="1f858-168">Data freshness and update frequency</span></span>
<span data-ttu-id="1f858-169">高级搜寻数据可以分为两种不同的类型，每种类型合并的方式不同。</span><span class="sxs-lookup"><span data-stu-id="1f858-169">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="1f858-170">**事件或活动数据**- 填充有关警报、安全事件、系统事件和例程评估的表。</span><span class="sxs-lookup"><span data-stu-id="1f858-170">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="1f858-171">高级搜寻在收集它们传感器将其成功传输到相应的云服务后，几乎会立即收到此数据。</span><span class="sxs-lookup"><span data-stu-id="1f858-171">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="1f858-172">例如，在 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 上提供事件数据后，你几乎可以在工作站或域控制器上立即查询来自正常传感器的事件数据。</span><span class="sxs-lookup"><span data-stu-id="1f858-172">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="1f858-173">**实体** 数据 - 使用有关用户和设备的信息填充表。</span><span class="sxs-lookup"><span data-stu-id="1f858-173">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="1f858-174">此数据来自相对静态数据源和动态源，如 Active Directory 条目和事件日志。</span><span class="sxs-lookup"><span data-stu-id="1f858-174">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="1f858-175">为了提供最新数据，表格每 15 分钟更新一次任何新信息，并添加可能未完全填充的行。</span><span class="sxs-lookup"><span data-stu-id="1f858-175">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="1f858-176">每 24 小时合并一次数据，以插入包含有关每个实体的最新、最全面的数据集的记录。</span><span class="sxs-lookup"><span data-stu-id="1f858-176">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="1f858-177">时区</span><span class="sxs-lookup"><span data-stu-id="1f858-177">Time zone</span></span>
<span data-ttu-id="1f858-178">高级搜寻中的时间信息采用 UTC 时区。</span><span class="sxs-lookup"><span data-stu-id="1f858-178">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1f858-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="1f858-179">Related topics</span></span>
- [<span data-ttu-id="1f858-180">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="1f858-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1f858-181">获取专家培训</span><span class="sxs-lookup"><span data-stu-id="1f858-181">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="1f858-182">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="1f858-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1f858-183">了解架构</span><span class="sxs-lookup"><span data-stu-id="1f858-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1f858-184">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="1f858-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1f858-185">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="1f858-185">Custom detections overview</span></span>](custom-detections-overview.md)
