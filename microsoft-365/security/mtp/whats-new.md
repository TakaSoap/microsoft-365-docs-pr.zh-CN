---
title: Microsoft 威胁防护的新增功能
description: 列出 Microsoft 威胁防护中的新特性和功能
keywords: microsoft 威胁防护中的新增功能、ga、正式发布、功能、可用、新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: da3fd8b97899e302c9b7b24a5c0677534b579981
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947980"
---
# <a name="whats-new-in-microsoft-threat-protection"></a><span data-ttu-id="89d36-104">Microsoft 威胁防护的新增功能</span><span class="sxs-lookup"><span data-stu-id="89d36-104">What's new in Microsoft Threat Protection</span></span>

<span data-ttu-id="89d36-105">以下功能在最新版本的 Microsoft 威胁防护中 () 正式提供。</span><span class="sxs-lookup"><span data-stu-id="89d36-105">The following features are generally available (GA) in the latest release of Microsoft Threat Protection.</span></span>

<span data-ttu-id="89d36-106">RSS 源：通过将以下 URL 复制并粘贴到订阅源阅读器中来更新此页面时收到通知：</span><span class="sxs-lookup"><span data-stu-id="89d36-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a><span data-ttu-id="89d36-107">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="89d36-107">September 2020</span></span>
- [<span data-ttu-id="89d36-108">AssignedIPAddresses ( # A1 函数</span><span class="sxs-lookup"><span data-stu-id="89d36-108">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="89d36-109">在 [高级搜寻](advanced-hunting-overview.md) 查询中使用此函数可以快速获取从指定时间点分配给设备或最近的 ip 地址的最新 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="89d36-109">Use this function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="89d36-110">2020 年 7 月</span><span class="sxs-lookup"><span data-stu-id="89d36-110">July 2020</span></span>
- [<span data-ttu-id="89d36-111">FileProfile ( # A1 函数</span><span class="sxs-lookup"><span data-stu-id="89d36-111">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="89d36-112">在高级搜寻查询中使用此功能，通过全面的文件信息丰富结果。</span><span class="sxs-lookup"><span data-stu-id="89d36-112">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="89d36-113">标识和应用程序表</span><span class="sxs-lookup"><span data-stu-id="89d36-113">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="89d36-114">在高级搜寻架构中获取对 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和 [AppFileEvents](advanced-hunting-appfileevents-table.md) 表的身份验证事件、Active Directory 查询和应用程序相关活动的可见性。</span><span class="sxs-lookup"><span data-stu-id="89d36-114">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="89d36-115">转到查寻</span><span class="sxs-lookup"><span data-stu-id="89d36-115">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="89d36-116">通过使用基于查询的高级搜寻功能，快速透视调查事件以检查特定事件、用户、设备或其他实体类型。</span><span class="sxs-lookup"><span data-stu-id="89d36-116">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based advanced hunting capabilities.</span></span>

## <a name="june-2020"></a><span data-ttu-id="89d36-117">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="89d36-117">June 2020</span></span>
- <span data-ttu-id="89d36-118">Twitter 源</span><span class="sxs-lookup"><span data-stu-id="89d36-118">Twitter feed</span></span> <br> <span data-ttu-id="89d36-119">在仪表板中获取最新的安全研究、威胁智能、产品新闻和更多权限。</span><span class="sxs-lookup"><span data-stu-id="89d36-119">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="89d36-120">EmailPostDeliveryEvents 架构表</span><span class="sxs-lookup"><span data-stu-id="89d36-120">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="89d36-121">将有关在您的高级搜寻查询中对电子邮件执行的送达操作的信息合并在一起。</span><span class="sxs-lookup"><span data-stu-id="89d36-121">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="89d36-122">检查高级搜寻中的记录</span><span class="sxs-lookup"><span data-stu-id="89d36-122">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="89d36-123">使用新的详细信息面板快速检查查询结果中的记录。</span><span class="sxs-lookup"><span data-stu-id="89d36-123">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="89d36-124">2020 年 5 月</span><span class="sxs-lookup"><span data-stu-id="89d36-124">May 2020</span></span>
- [<span data-ttu-id="89d36-125">自定义检测</span><span class="sxs-lookup"><span data-stu-id="89d36-125">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="89d36-126">使用高级搜寻查询创建可自动监视和响应安全事件和系统状态的自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="89d36-126">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="89d36-127">2020 年 2 月</span><span class="sxs-lookup"><span data-stu-id="89d36-127">February 2020</span></span>
- [<span data-ttu-id="89d36-128">事件</span><span class="sxs-lookup"><span data-stu-id="89d36-128">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="89d36-129">确切知道攻击的启动位置和其他详细信息，以帮助您了解攻击的程度。</span><span class="sxs-lookup"><span data-stu-id="89d36-129">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="89d36-130">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="89d36-130">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="89d36-131">AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="89d36-131">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="89d36-132">高级搜寻增强功能</span><span class="sxs-lookup"><span data-stu-id="89d36-132">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="89d36-133">使用 Kusto 查询语言和安全优化架构主动查找整个新式工作区中的威胁。</span><span class="sxs-lookup"><span data-stu-id="89d36-133">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="89d36-134">2019 年 3 月</span><span class="sxs-lookup"><span data-stu-id="89d36-134">March 2019</span></span>
- <span data-ttu-id="89d36-135">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="89d36-135">Advanced hunting</span></span> <br> <span data-ttu-id="89d36-136">登录页面到各种搜索功能，使您能够主动找到影响电子邮件和数据、设备和标识的威胁。</span><span class="sxs-lookup"><span data-stu-id="89d36-136">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="89d36-137">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="89d36-137">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="89d36-138">组织的安全状态的度量值，其数字越高表示执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="89d36-138">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="89d36-139">按照安全得分建议，可以保护您的组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="89d36-139">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="89d36-140">报表</span><span class="sxs-lookup"><span data-stu-id="89d36-140">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="89d36-141">提供一系列涵盖安全分析员和管理员在日常运营中进行跟踪的各种领域的卡片主机。</span><span class="sxs-lookup"><span data-stu-id="89d36-141">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
