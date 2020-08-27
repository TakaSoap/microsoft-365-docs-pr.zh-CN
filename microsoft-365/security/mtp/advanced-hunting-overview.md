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
ms.openlocfilehash: 75d709cc1f98a12bb6f5a5b6539583a33be500b6
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255741"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="99304-104">通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="99304-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="99304-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="99304-105">**Applies to:**</span></span>
- <span data-ttu-id="99304-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="99304-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="99304-107">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="99304-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="99304-108">你可以主动检查网络中的事件来找到感兴趣的指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="99304-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="99304-109">灵活访问数据有助于无约束搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="99304-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="99304-110">你可以使用相同的威胁搜寻查询来构建自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="99304-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="99304-111">这些规则会自动运行以检查和响应各种事件和系统状态，包括可疑的违规活动和配置错误的计算机。</span><span class="sxs-lookup"><span data-stu-id="99304-111">These rules run automatically to check for and respond to various events and system states, including suspected breach activity and misconfigured machines.</span></span>

<span data-ttu-id="99304-112">该功能与 [Microsoft DEFENDER atp 中的高级](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)搜索类似，不同之处在于，在 microsoft 365 安全中心中，高级搜索功能支持从各种工作区查看数据的查询，其中包括有关 MICROSOFT Defender ATP、OFFICE 365 ATP、Microsoft 云应用安全性和 Azure atp 中的设备、电子邮件、应用和标识的数据。</span><span class="sxs-lookup"><span data-stu-id="99304-112">The feature is similar to [advanced hunting in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview), except that in the Microsoft 365 security center, advanced hunting supports queries that look into data from various workspaces, including data about devices, emails, apps, and identities from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="99304-113">若要使用高级搜寻，请[打开 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="99304-113">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="99304-114">高级搜寻入门</span><span class="sxs-lookup"><span data-stu-id="99304-114">Get started with advanced hunting</span></span>

<span data-ttu-id="99304-115">我们建议执行几个步骤来通过高级搜寻快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="99304-115">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="99304-116">学习目标</span><span class="sxs-lookup"><span data-stu-id="99304-116">Learning goal</span></span> | <span data-ttu-id="99304-117">说明</span><span class="sxs-lookup"><span data-stu-id="99304-117">Description</span></span> | <span data-ttu-id="99304-118">资源</span><span class="sxs-lookup"><span data-stu-id="99304-118">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="99304-119">**了解语言**</span><span class="sxs-lookup"><span data-stu-id="99304-119">**Get a feel for the language**</span></span> | <span data-ttu-id="99304-120">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="99304-120">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="99304-121">通过运行第一个查询开始学习查询语言。</span><span class="sxs-lookup"><span data-stu-id="99304-121">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="99304-122">查询语言概述</span><span class="sxs-lookup"><span data-stu-id="99304-122">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="99304-123">**了解如何使用查询结果**</span><span class="sxs-lookup"><span data-stu-id="99304-123">**Learn how to use the query results**</span></span> | <span data-ttu-id="99304-124">了解您可以查看或导出结果的各种图表和各种方式。</span><span class="sxs-lookup"><span data-stu-id="99304-124">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="99304-125">了解如何快速调整查询、向下钻取以获取更丰富的信息，并采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="99304-125">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="99304-126">- [处理查询结果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="99304-126">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="99304-127">- [对查询结果执行操作](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="99304-127">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="99304-128">**了解架构**</span><span class="sxs-lookup"><span data-stu-id="99304-128">**Understand the schema**</span></span> | <span data-ttu-id="99304-129">更好地大致了解架构及其列中的表。</span><span class="sxs-lookup"><span data-stu-id="99304-129">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="99304-130">这将帮助你确定在何处查找数据以及如何构建查询。</span><span class="sxs-lookup"><span data-stu-id="99304-130">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="99304-131">架构参考</span><span class="sxs-lookup"><span data-stu-id="99304-131">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="99304-132">**利用预定义查询**</span><span class="sxs-lookup"><span data-stu-id="99304-132">**Leverage predefined queries**</span></span> | <span data-ttu-id="99304-133">浏览涵盖不同威胁搜寻方案的预定义查询集合。</span><span class="sxs-lookup"><span data-stu-id="99304-133">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="99304-134">- [使用共享查询](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="99304-134">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="99304-135">- [开始智能寻线](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="99304-135">- [Go hunt](advanced-hunting-go-hunt.md)</span></span> |
| <span data-ttu-id="99304-136">**优化查询**</span><span class="sxs-lookup"><span data-stu-id="99304-136">**Optimize queries**</span></span> | <span data-ttu-id="99304-137">了解如何创建高效查询以及组合电子邮件和设备中的数据的查询。</span><span class="sxs-lookup"><span data-stu-id="99304-137">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="99304-138">- [查询最佳实践](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="99304-138">- [Query best practices](advanced-hunting-best-practices.md)</span></span> <br><span data-ttu-id="99304-139">- [跨设备和电子邮件的智能寻线](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="99304-139">- [Hunt across devices and emails](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="99304-140">**创建自定义检测规则**</span><span class="sxs-lookup"><span data-stu-id="99304-140">**Create custom detection rules**</span></span> | <span data-ttu-id="99304-141">了解如何使用高级搜寻查询来触发通知并自动应用响应操作。</span><span class="sxs-lookup"><span data-stu-id="99304-141">Understand how you can use advanced hunting queries to trigger alerts and apply response actions automatically.</span></span> | <span data-ttu-id="99304-142">- [自定义检测概述](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="99304-142">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="99304-143">- [自定义检测规则](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="99304-143">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="99304-144">获取访问权限</span><span class="sxs-lookup"><span data-stu-id="99304-144">Get access</span></span>
<span data-ttu-id="99304-145">若要使用高级搜寻或其他 [Microsoft 威胁防护](microsoft-threat-protection.md) 功能，您需要在 Azure AD 中为其分配一个适当的角色。</span><span class="sxs-lookup"><span data-stu-id="99304-145">To use advanced hunting or other [Microsoft Threat Protection](microsoft-threat-protection.md) capabilities, you need to be assigned an appropriate role in Azure AD.</span></span> <span data-ttu-id="99304-146">请注意，对终结点数据的访问受 Microsoft Defender ATP 中基于角色的访问控制设置的影响。</span><span class="sxs-lookup"><span data-stu-id="99304-146">Note that your access to endpoint data is influenced by role-based access control settings in Microsoft Defender ATP.</span></span> [<span data-ttu-id="99304-147">阅读有关管理 Microsoft 威胁防护的访问权限</span><span class="sxs-lookup"><span data-stu-id="99304-147">Read about managing access to Microsoft Threat Protection</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="99304-148">数据刷新和更新频率</span><span class="sxs-lookup"><span data-stu-id="99304-148">Data freshness and update frequency</span></span>
<span data-ttu-id="99304-149">高级的搜寻数据可分为两种不同的类型，每种方式都有不同的合并。</span><span class="sxs-lookup"><span data-stu-id="99304-149">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="99304-150">**事件或活动数据** —填充有关警报、安全事件、系统事件和常规评估的表。</span><span class="sxs-lookup"><span data-stu-id="99304-150">**Event or activity data** — populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="99304-151">高级搜寻几乎会在收集这些数据的传感器成功传输到相应的云服务后立即收到。</span><span class="sxs-lookup"><span data-stu-id="99304-151">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="99304-152">例如，您可以开始在工作站或域控制器上的正常传感器中查询事件数据，这些数据在 Microsoft Defender ATP 和 Azure ATP 上可用后几乎可以立即开始。</span><span class="sxs-lookup"><span data-stu-id="99304-152">For example, you can start to query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender ATP and Azure ATP.</span></span>
- <span data-ttu-id="99304-153">**实体数据** —使用有关用户和设备的统一信息填充表。</span><span class="sxs-lookup"><span data-stu-id="99304-153">**Entity data** — populates tables with consolidated information about users and devices.</span></span> <span data-ttu-id="99304-154">此类数据来自相对静态数据源（如 Active Directory 条目）和动态源（如事件日志）。</span><span class="sxs-lookup"><span data-stu-id="99304-154">This data comes from both relatively static data sources, such as Active Directory entries, and dynamic sources, such as event logs.</span></span> <span data-ttu-id="99304-155">为了提供最新数据，每15分钟更新一次表格，以添加任何新信息，添加可能未完全填充的行。</span><span class="sxs-lookup"><span data-stu-id="99304-155">To provide fresh data, tables are updated every 15 minutes with any new information, adding rows that might not be fully populated.</span></span> <span data-ttu-id="99304-156">每隔24小时，合并数据以插入包含有关每个实体的最新、最全面的数据集的记录。</span><span class="sxs-lookup"><span data-stu-id="99304-156">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="99304-157">时区</span><span class="sxs-lookup"><span data-stu-id="99304-157">Time zone</span></span>
<span data-ttu-id="99304-158">高级搜寻中的所有时间信息都在 UTC 时区中。</span><span class="sxs-lookup"><span data-stu-id="99304-158">All time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="99304-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="99304-159">Related topics</span></span>
- [<span data-ttu-id="99304-160">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="99304-160">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="99304-161">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="99304-161">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="99304-162">对查询结果执行操作</span><span class="sxs-lookup"><span data-stu-id="99304-162">Take action on query results</span></span>](advanced-hunting-take-action.md)
- [<span data-ttu-id="99304-163">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="99304-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="99304-164">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="99304-164">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="99304-165">了解架构</span><span class="sxs-lookup"><span data-stu-id="99304-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="99304-166">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="99304-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="99304-167">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="99304-167">Custom detections overview</span></span>](custom-detections-overview.md)
