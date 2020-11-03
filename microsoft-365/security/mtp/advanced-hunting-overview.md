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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 627791e9dc3d4bf18047a05734a4e275152d19da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845028"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="01b08-104">在 Microsoft 365 Defender 中主动查找具有高级搜寻的威胁</span><span class="sxs-lookup"><span data-stu-id="01b08-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01b08-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="01b08-105">**Applies to:**</span></span>
- <span data-ttu-id="01b08-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01b08-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="01b08-107">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="01b08-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="01b08-108">您可以主动检查网络中的事件以查找威胁指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="01b08-108">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="01b08-109">灵活的数据访问可实现已知和潜在威胁的无约束搜寻。</span><span class="sxs-lookup"><span data-stu-id="01b08-109">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="01b08-110">你可以使用相同的威胁搜寻查询来构建自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="01b08-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="01b08-111">这些规则会自动运行以检查并响应可疑的违规活动、错误配置的计算机以及其他发现。</span><span class="sxs-lookup"><span data-stu-id="01b08-111">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="01b08-112">此功能类似于 [Microsoft Defender For Endpoint 中的高级搜寻](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="01b08-112">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="01b08-113">在 Microsoft 365 安全中心中提供，此功能支持通过以下查询检查更广泛的数据集：</span><span class="sxs-lookup"><span data-stu-id="01b08-113">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="01b08-114">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="01b08-114">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="01b08-115">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="01b08-115">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="01b08-116">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="01b08-116">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="01b08-117">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="01b08-117">Microsoft Defender for Identity</span></span>

<span data-ttu-id="01b08-118">若要使用高级搜寻，请 [打开 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="01b08-118">To use advanced hunting, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="01b08-119">高级搜寻入门</span><span class="sxs-lookup"><span data-stu-id="01b08-119">Get started with advanced hunting</span></span>

<span data-ttu-id="01b08-120">我们建议您通过几个步骤快速开始执行高级搜寻。</span><span class="sxs-lookup"><span data-stu-id="01b08-120">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="01b08-121">学习目标</span><span class="sxs-lookup"><span data-stu-id="01b08-121">Learning goal</span></span> | <span data-ttu-id="01b08-122">说明</span><span class="sxs-lookup"><span data-stu-id="01b08-122">Description</span></span> | <span data-ttu-id="01b08-123">资源</span><span class="sxs-lookup"><span data-stu-id="01b08-123">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="01b08-124">**了解语言**</span><span class="sxs-lookup"><span data-stu-id="01b08-124">**Learn the language**</span></span> | <span data-ttu-id="01b08-125">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="01b08-125">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="01b08-126">通过运行第一个查询开始学习查询语言。</span><span class="sxs-lookup"><span data-stu-id="01b08-126">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="01b08-127">查询语言概述</span><span class="sxs-lookup"><span data-stu-id="01b08-127">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="01b08-128">**了解如何使用查询结果**</span><span class="sxs-lookup"><span data-stu-id="01b08-128">**Learn how to use the query results**</span></span> | <span data-ttu-id="01b08-129">了解您可以查看或导出结果的各种图表和各种方式。</span><span class="sxs-lookup"><span data-stu-id="01b08-129">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="01b08-130">了解如何快速调整查询、向下钻取以获取更丰富的信息，并采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="01b08-130">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="01b08-131">- [处理查询结果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-131">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="01b08-132">- [对查询结果执行操作](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-132">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="01b08-133">**了解架构**</span><span class="sxs-lookup"><span data-stu-id="01b08-133">**Understand the schema**</span></span> | <span data-ttu-id="01b08-134">更好地大致了解架构及其列中的表。</span><span class="sxs-lookup"><span data-stu-id="01b08-134">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="01b08-135">了解在构造查询时查找数据的位置。</span><span class="sxs-lookup"><span data-stu-id="01b08-135">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="01b08-136">- [架构参考](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-136">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="01b08-137">- [从 Microsoft Defender for Endpoint 转换](advanced-hunting-migrate-from-mdatp.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-137">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)</span></span> |
| <span data-ttu-id="01b08-138">**获取专家提示和示例**</span><span class="sxs-lookup"><span data-stu-id="01b08-138">**Get expert tips and examples**</span></span> | <span data-ttu-id="01b08-139">从 Microsoft 专家处获取免费培训指南。</span><span class="sxs-lookup"><span data-stu-id="01b08-139">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="01b08-140">浏览涵盖不同威胁搜寻方案的预定义查询集合。</span><span class="sxs-lookup"><span data-stu-id="01b08-140">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="01b08-141">- [获取专家培训](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-141">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="01b08-142">- [使用共享查询](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-142">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="01b08-143">- [开始智能寻线](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-143">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="01b08-144">- [在设备、电子邮件、应用和标识之间寻找威胁](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-144">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="01b08-145">**优化查询和处理错误**</span><span class="sxs-lookup"><span data-stu-id="01b08-145">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="01b08-146">了解如何创建高效和无错误的查询。</span><span class="sxs-lookup"><span data-stu-id="01b08-146">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="01b08-147">- [查询最佳实践](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-147">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="01b08-148">- [处理错误](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-148">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="01b08-149">**创建自定义检测规则**</span><span class="sxs-lookup"><span data-stu-id="01b08-149">**Create custom detection rules**</span></span> | <span data-ttu-id="01b08-150">了解如何使用高级搜寻查询来触发通知并自动采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="01b08-150">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="01b08-151">- [自定义检测概述](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-151">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="01b08-152">- [自定义检测规则](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="01b08-152">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="01b08-153">获取访问权限</span><span class="sxs-lookup"><span data-stu-id="01b08-153">Get access</span></span>
<span data-ttu-id="01b08-154">若要使用高级搜寻或其他 [Microsoft 365 Defender](microsoft-threat-protection.md) 功能，您需要在 Azure Active Directory 中使用适当的角色。</span><span class="sxs-lookup"><span data-stu-id="01b08-154">To use advanced hunting or other [Microsoft 365 Defender](microsoft-threat-protection.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="01b08-155">此外，您对终结点数据的访问权限由基于角色的访问控制在 Microsoft Defender for Endpoint 中 (RBAC) 设置决定。</span><span class="sxs-lookup"><span data-stu-id="01b08-155">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="01b08-156">阅读有关管理对 Microsoft 365 Defender 的访问权限的信息</span><span class="sxs-lookup"><span data-stu-id="01b08-156">Read about managing access to Microsoft 365 Defender</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="01b08-157">数据刷新和更新频率</span><span class="sxs-lookup"><span data-stu-id="01b08-157">Data freshness and update frequency</span></span>
<span data-ttu-id="01b08-158">高级的搜寻数据可分为两种不同的类型，每种方式都有不同的合并。</span><span class="sxs-lookup"><span data-stu-id="01b08-158">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="01b08-159">**事件或活动数据** —填充有关警报、安全事件、系统事件和常规评估的表。</span><span class="sxs-lookup"><span data-stu-id="01b08-159">**Event or activity data** —populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="01b08-160">高级搜寻几乎会在收集这些数据的传感器成功传输到相应的云服务后立即收到。</span><span class="sxs-lookup"><span data-stu-id="01b08-160">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="01b08-161">例如，您可以在工作站或域控制器上的正常传感器中立即查询事件数据，这些数据在 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 中可用后几乎会立即查询。</span><span class="sxs-lookup"><span data-stu-id="01b08-161">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="01b08-162">**实体数据** —使用有关用户和设备的信息填充表。</span><span class="sxs-lookup"><span data-stu-id="01b08-162">**Entity data** —populates tables with information about users and devices.</span></span> <span data-ttu-id="01b08-163">这些数据来自相对静态数据源和动态源，如 Active Directory 条目和事件日志。</span><span class="sxs-lookup"><span data-stu-id="01b08-163">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="01b08-164">为了提供新数据，每15分钟更新一次表中的所有新信息，添加可能未完全填充的行。</span><span class="sxs-lookup"><span data-stu-id="01b08-164">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="01b08-165">每隔24小时，合并数据以插入包含有关每个实体的最新、最全面的数据集的记录。</span><span class="sxs-lookup"><span data-stu-id="01b08-165">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="01b08-166">时区</span><span class="sxs-lookup"><span data-stu-id="01b08-166">Time zone</span></span>
<span data-ttu-id="01b08-167">高级搜寻中的时间信息位于 UTC 时区中。</span><span class="sxs-lookup"><span data-stu-id="01b08-167">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01b08-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="01b08-168">Related topics</span></span>
- [<span data-ttu-id="01b08-169">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="01b08-169">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01b08-170">获取专家培训</span><span class="sxs-lookup"><span data-stu-id="01b08-170">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="01b08-171">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="01b08-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01b08-172">了解架构</span><span class="sxs-lookup"><span data-stu-id="01b08-172">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01b08-173">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="01b08-173">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="01b08-174">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="01b08-174">Custom detections overview</span></span>](custom-detections-overview.md)

