---
title: Microsoft 365 Defender 的新增功能
description: 列出 Microsoft 365 Defender 中的新特性和功能
keywords: Microsoft 威胁防护的新增功能， ga， 通用， 功能， 可用， 新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 5de805784b2772b0169b2ad2a503e9378b82fda7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927092"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="40647-104">Microsoft 365 Defender 的新增功能</span><span class="sxs-lookup"><span data-stu-id="40647-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="40647-105">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="40647-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="40647-106">可以在[实验室环境中评估它或在](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab)[生产中运行你的试验项目](./mtp-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="40647-106">You can [evaluate it in a lab environment](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](./mtp-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="40647-107">在最新版本的 Microsoft 365 defender (GA) 通常提供以下功能。</span><span class="sxs-lookup"><span data-stu-id="40647-107">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="40647-108">RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中：</span><span class="sxs-lookup"><span data-stu-id="40647-108">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="march-2021"></a><span data-ttu-id="40647-109">2021 年 3 月</span><span class="sxs-lookup"><span data-stu-id="40647-109">March 2021</span></span>
- [<span data-ttu-id="40647-110">CloudAppEvents 表</span><span class="sxs-lookup"><span data-stu-id="40647-110">CloudAppEvents table</span></span>](advanced-hunting-cloudappevents-table.md) <br><span data-ttu-id="40647-111">查找有关 Microsoft Cloud App Security 涵盖的各种云应用和服务中的事件的信息。</span><span class="sxs-lookup"><span data-stu-id="40647-111">Find information about events in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="40647-112">此表还包括之前在 中提供的信息 `AppFileEvents` 。</span><span class="sxs-lookup"><span data-stu-id="40647-112">This table also includes information previously available in `AppFileEvents`.</span></span>
## <a name="february-2021"></a><span data-ttu-id="40647-113">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="40647-113">February 2021</span></span>
- <span data-ttu-id="40647-114"> (预览) 增强[的 Microsoft https://security.microsoft.com) 365](https://security.microsoft.com)安全中心 (现在提供公共预览版。</span><span class="sxs-lookup"><span data-stu-id="40647-114">(Preview) The enhanced [Microsoft 365 security center (https://security.microsoft.com)](https://security.microsoft.com) is now available in public preview.</span></span> <span data-ttu-id="40647-115">这一新体验将 Defender for Endpoint 和 Defender for Office 365 引入中心。</span><span class="sxs-lookup"><span data-stu-id="40647-115">This new experience brings Defender for Endpoint and Defender for Office 365 to the center.</span></span> <span data-ttu-id="40647-116">[详细了解更改了哪些功能](./overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="40647-116">[Learn more about what's changed](./overview-security-center.md).</span></span>

## <a name="september-2020"></a><span data-ttu-id="40647-117">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="40647-117">September 2020</span></span>
- [<span data-ttu-id="40647-118">IdentityDirectoryEvents 表</span><span class="sxs-lookup"><span data-stu-id="40647-118">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="40647-119">查找涉及本地域控制器的事件，该域控制器运行 Active Directory (AD) 。</span><span class="sxs-lookup"><span data-stu-id="40647-119">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="40647-120">此 [高级搜寻](advanced-hunting-overview.md) 架构表涵盖域控制器上一系列与标识相关的事件和系统事件。</span><span class="sxs-lookup"><span data-stu-id="40647-120">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="40647-121">AssignedIPAddresses () 函数</span><span class="sxs-lookup"><span data-stu-id="40647-121">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="40647-122">在高级搜寻查询中使用此函数可快速获取分配给设备的最新 IP 地址或特定时间的最新 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="40647-122">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="40647-123">2020 年 7 月</span><span class="sxs-lookup"><span data-stu-id="40647-123">July 2020</span></span>
- [<span data-ttu-id="40647-124">FileProfile () 函数</span><span class="sxs-lookup"><span data-stu-id="40647-124">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="40647-125">在高级搜寻查询中使用此函数，通过综合文件信息丰富结果。</span><span class="sxs-lookup"><span data-stu-id="40647-125">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="40647-126">标识表和应用表</span><span class="sxs-lookup"><span data-stu-id="40647-126">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="40647-127">通过高级搜寻架构中的[IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)表，了解身份验证事件、Active [Directory](advanced-hunting-identityqueryevents-table.md)查询和与应用相关的活动。</span><span class="sxs-lookup"><span data-stu-id="40647-127">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="40647-128">转到查寻</span><span class="sxs-lookup"><span data-stu-id="40647-128">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="40647-129">快速透视从调查事件到检查特定事件、用户、设备或高级搜寻上的其他实体类型。</span><span class="sxs-lookup"><span data-stu-id="40647-129">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="40647-130">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="40647-130">June 2020</span></span>
- <span data-ttu-id="40647-131">Twitter 源</span><span class="sxs-lookup"><span data-stu-id="40647-131">Twitter feed</span></span> <br> <span data-ttu-id="40647-132">直接在仪表板内获取最新的安全研究、威胁情报、产品新闻等。</span><span class="sxs-lookup"><span data-stu-id="40647-132">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="40647-133">EmailPostDeliveryEvents 架构表</span><span class="sxs-lookup"><span data-stu-id="40647-133">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="40647-134">在高级搜寻查询中纳入有关对电子邮件执行传递后操作的信息。</span><span class="sxs-lookup"><span data-stu-id="40647-134">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="40647-135">检查高级搜寻中的记录</span><span class="sxs-lookup"><span data-stu-id="40647-135">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="40647-136">使用新的详细信息面板快速检查查询结果中的记录。</span><span class="sxs-lookup"><span data-stu-id="40647-136">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="40647-137">2020 年 5 月</span><span class="sxs-lookup"><span data-stu-id="40647-137">May 2020</span></span>
- [<span data-ttu-id="40647-138">自定义检测</span><span class="sxs-lookup"><span data-stu-id="40647-138">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="40647-139">使用高级搜寻查询创建自定义检测规则，以自动监视和响应安全事件和系统状态。</span><span class="sxs-lookup"><span data-stu-id="40647-139">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="40647-140">2020 年 2 月</span><span class="sxs-lookup"><span data-stu-id="40647-140">February 2020</span></span>
- [<span data-ttu-id="40647-141">事件</span><span class="sxs-lookup"><span data-stu-id="40647-141">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="40647-142">准确了解攻击的开始位置和其他详细信息，以帮助你查看攻击的范围。</span><span class="sxs-lookup"><span data-stu-id="40647-142">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="40647-143">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="40647-143">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="40647-144">AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="40647-144">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="40647-145">高级搜寻增强功能</span><span class="sxs-lookup"><span data-stu-id="40647-145">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="40647-146">使用 Kusto 查询语言和安全优化架构，在新式工作区中主动搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="40647-146">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="40647-147">2019 年 3 月</span><span class="sxs-lookup"><span data-stu-id="40647-147">March 2019</span></span>
- <span data-ttu-id="40647-148">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="40647-148">Advanced hunting</span></span> <br> <span data-ttu-id="40647-149">各种搜寻功能的登陆页面，可让你主动查找影响电子邮件和数据、设备和标识的威胁。</span><span class="sxs-lookup"><span data-stu-id="40647-149">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="40647-150">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="40647-150">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="40647-151">衡量组织的安全状态，较高的数字表示采取更多改进措施。</span><span class="sxs-lookup"><span data-stu-id="40647-151">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="40647-152">遵循安全分数建议可保护组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="40647-152">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="40647-153">报表</span><span class="sxs-lookup"><span data-stu-id="40647-153">Reports</span></span>](./overview-security-center.md) <br>  <span data-ttu-id="40647-154">功能一系列卡片，涵盖安全分析师和管理员在日常操作中跟踪的一系列领域。</span><span class="sxs-lookup"><span data-stu-id="40647-154">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>