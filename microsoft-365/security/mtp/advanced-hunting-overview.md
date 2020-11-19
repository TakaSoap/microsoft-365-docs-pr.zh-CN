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
ms.openlocfilehash: bab055036a8e7fdcf88329413c9fd86269af2aaa
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357216"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="8288f-104">在 Microsoft 365 Defender 中主动查找具有高级搜寻的威胁</span><span class="sxs-lookup"><span data-stu-id="8288f-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8288f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8288f-105">**Applies to:**</span></span>
- <span data-ttu-id="8288f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8288f-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="8288f-107">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="8288f-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="8288f-108">您可以 [在实验室环境中对其进行评估](https://aka.ms/mtp-trial-lab) ，也可以 [在生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="8288f-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="8288f-109">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="8288f-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="8288f-110">您可以主动检查网络中的事件以查找威胁指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="8288f-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="8288f-111">灵活的数据访问可实现已知和潜在威胁的无约束搜寻。</span><span class="sxs-lookup"><span data-stu-id="8288f-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="8288f-112">你可以使用相同的威胁搜寻查询来构建自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="8288f-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="8288f-113">这些规则会自动运行以检查并响应可疑的违规活动、错误配置的计算机以及其他发现。</span><span class="sxs-lookup"><span data-stu-id="8288f-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="8288f-114">此功能类似于 [Microsoft Defender For Endpoint 中的高级搜寻](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="8288f-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="8288f-115">在 Microsoft 365 安全中心中提供，此功能支持通过以下查询检查更广泛的数据集：</span><span class="sxs-lookup"><span data-stu-id="8288f-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="8288f-116">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8288f-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="8288f-117">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8288f-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="8288f-118">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="8288f-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="8288f-119">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8288f-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="8288f-120">若要使用高级搜寻，请 [打开 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="8288f-120">To use advanced hunting, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="8288f-121">高级搜寻入门</span><span class="sxs-lookup"><span data-stu-id="8288f-121">Get started with advanced hunting</span></span>

<span data-ttu-id="8288f-122">我们建议您通过几个步骤快速开始执行高级搜寻。</span><span class="sxs-lookup"><span data-stu-id="8288f-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="8288f-123">学习目标</span><span class="sxs-lookup"><span data-stu-id="8288f-123">Learning goal</span></span> | <span data-ttu-id="8288f-124">说明</span><span class="sxs-lookup"><span data-stu-id="8288f-124">Description</span></span> | <span data-ttu-id="8288f-125">资源</span><span class="sxs-lookup"><span data-stu-id="8288f-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="8288f-126">**了解语言**</span><span class="sxs-lookup"><span data-stu-id="8288f-126">**Learn the language**</span></span> | <span data-ttu-id="8288f-127">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="8288f-127">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="8288f-128">通过运行第一个查询开始学习查询语言。</span><span class="sxs-lookup"><span data-stu-id="8288f-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="8288f-129">查询语言概述</span><span class="sxs-lookup"><span data-stu-id="8288f-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="8288f-130">**了解如何使用查询结果**</span><span class="sxs-lookup"><span data-stu-id="8288f-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="8288f-131">了解您可以查看或导出结果的各种图表和各种方式。</span><span class="sxs-lookup"><span data-stu-id="8288f-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="8288f-132">了解如何快速调整查询、向下钻取以获取更丰富的信息，并采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="8288f-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="8288f-133">- [处理查询结果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="8288f-134">- [对查询结果执行操作](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="8288f-135">**了解架构**</span><span class="sxs-lookup"><span data-stu-id="8288f-135">**Understand the schema**</span></span> | <span data-ttu-id="8288f-136">更好地大致了解架构及其列中的表。</span><span class="sxs-lookup"><span data-stu-id="8288f-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="8288f-137">了解在构造查询时查找数据的位置。</span><span class="sxs-lookup"><span data-stu-id="8288f-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="8288f-138">- [架构参考](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="8288f-139">- [从 Microsoft Defender for Endpoint 转换](advanced-hunting-migrate-from-mdatp.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)</span></span> |
| <span data-ttu-id="8288f-140">**获取专家提示和示例**</span><span class="sxs-lookup"><span data-stu-id="8288f-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="8288f-141">从 Microsoft 专家处获取免费培训指南。</span><span class="sxs-lookup"><span data-stu-id="8288f-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="8288f-142">浏览涵盖不同威胁搜寻方案的预定义查询集合。</span><span class="sxs-lookup"><span data-stu-id="8288f-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="8288f-143">- [获取专家培训](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="8288f-144">- [使用共享查询](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="8288f-145">- [开始智能寻线](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="8288f-146">- [在设备、电子邮件、应用和标识之间寻找威胁](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="8288f-147">**优化查询和处理错误**</span><span class="sxs-lookup"><span data-stu-id="8288f-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="8288f-148">了解如何创建高效和无错误的查询。</span><span class="sxs-lookup"><span data-stu-id="8288f-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="8288f-149">- [查询最佳实践](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="8288f-150">- [处理错误](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="8288f-151">**创建自定义检测规则**</span><span class="sxs-lookup"><span data-stu-id="8288f-151">**Create custom detection rules**</span></span> | <span data-ttu-id="8288f-152">了解如何使用高级搜寻查询来触发通知并自动采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="8288f-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="8288f-153">- [自定义检测概述](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-153">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="8288f-154">- [自定义检测规则](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="8288f-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="8288f-155">获取访问权限</span><span class="sxs-lookup"><span data-stu-id="8288f-155">Get access</span></span>
<span data-ttu-id="8288f-156">若要使用高级搜寻或其他 [Microsoft 365 Defender](microsoft-threat-protection.md) 功能，您需要在 Azure Active Directory 中使用适当的角色。</span><span class="sxs-lookup"><span data-stu-id="8288f-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-threat-protection.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="8288f-157">此外，您对终结点数据的访问权限由基于角色的访问控制在 Microsoft Defender for Endpoint 中 (RBAC) 设置决定。</span><span class="sxs-lookup"><span data-stu-id="8288f-157">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="8288f-158">阅读有关管理对 Microsoft 365 Defender 的访问权限的信息</span><span class="sxs-lookup"><span data-stu-id="8288f-158">Read about managing access to Microsoft 365 Defender</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="8288f-159">数据刷新和更新频率</span><span class="sxs-lookup"><span data-stu-id="8288f-159">Data freshness and update frequency</span></span>
<span data-ttu-id="8288f-160">高级的搜寻数据可分为两种不同的类型，每种方式都有不同的合并。</span><span class="sxs-lookup"><span data-stu-id="8288f-160">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="8288f-161">**事件或活动数据**—填充有关警报、安全事件、系统事件和常规评估的表。</span><span class="sxs-lookup"><span data-stu-id="8288f-161">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="8288f-162">高级搜寻几乎会在收集这些数据的传感器成功传输到相应的云服务后立即收到。</span><span class="sxs-lookup"><span data-stu-id="8288f-162">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="8288f-163">例如，您可以在工作站或域控制器上的正常传感器中立即查询事件数据，这些数据在 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 中可用后几乎会立即查询。</span><span class="sxs-lookup"><span data-stu-id="8288f-163">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="8288f-164">**实体数据**—使用有关用户和设备的信息填充表。</span><span class="sxs-lookup"><span data-stu-id="8288f-164">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="8288f-165">这些数据来自相对静态数据源和动态源，如 Active Directory 条目和事件日志。</span><span class="sxs-lookup"><span data-stu-id="8288f-165">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="8288f-166">为了提供新数据，每15分钟更新一次表中的所有新信息，添加可能未完全填充的行。</span><span class="sxs-lookup"><span data-stu-id="8288f-166">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="8288f-167">每隔24小时，合并数据以插入包含有关每个实体的最新、最全面的数据集的记录。</span><span class="sxs-lookup"><span data-stu-id="8288f-167">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="8288f-168">时区</span><span class="sxs-lookup"><span data-stu-id="8288f-168">Time zone</span></span>
<span data-ttu-id="8288f-169">高级搜寻中的时间信息位于 UTC 时区中。</span><span class="sxs-lookup"><span data-stu-id="8288f-169">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8288f-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="8288f-170">Related topics</span></span>
- [<span data-ttu-id="8288f-171">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="8288f-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8288f-172">获取专家培训</span><span class="sxs-lookup"><span data-stu-id="8288f-172">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="8288f-173">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="8288f-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8288f-174">了解架构</span><span class="sxs-lookup"><span data-stu-id="8288f-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8288f-175">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="8288f-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8288f-176">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="8288f-176">Custom detections overview</span></span>](custom-detections-overview.md)

