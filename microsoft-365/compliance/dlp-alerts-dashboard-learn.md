---
title: 了解数据丢失防护警报仪表板
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解数据丢失防护警报和警报仪表板。
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760703"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a><span data-ttu-id="89f40-103">了解数据丢失防护警报仪表板</span><span class="sxs-lookup"><span data-stu-id="89f40-103">Learn about the data loss prevention Alerts dashboard</span></span>

<span data-ttu-id="89f40-104">当 DLP (数据丢失防护) 策略中的条件与用户对敏感项目采取的操作匹配时，该策略可能会生成警报。</span><span class="sxs-lookup"><span data-stu-id="89f40-104">When the criteria in a Data loss prevention (DLP) policy is matched by the actions a user is taking on a sensitive item, the policy can generate an alert.</span></span> <span data-ttu-id="89f40-105">这可能会导致大量警报。</span><span class="sxs-lookup"><span data-stu-id="89f40-105">This can result in a high volume of alerts.</span></span> <span data-ttu-id="89f40-106">DLP 警报收集在警报仪表板中。</span><span class="sxs-lookup"><span data-stu-id="89f40-106">DLP alerts are collected in the alerts dashboard.</span></span> <span data-ttu-id="89f40-107">警报仪表板为您提供了一个可以深入调查与策略匹配有关的所有详细信息的位置。</span><span class="sxs-lookup"><span data-stu-id="89f40-107">The alerts dashboard gives you a single place to go to perform a deep investigation of all the details regarding the policy match.</span></span>  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a><span data-ttu-id="89f40-108">工作负载</span><span class="sxs-lookup"><span data-stu-id="89f40-108">Workloads</span></span>

<span data-ttu-id="89f40-109">Microsoft [365](https://compliance.microsoft.com/)合规中心中的[DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)警报管理仪表板显示有关这些工作负载的 DLP 策略警报：</span><span class="sxs-lookup"><span data-stu-id="89f40-109">The [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), shows alerts for DLP policies on these workloads:</span></span>

- <span data-ttu-id="89f40-110">Exchange</span><span class="sxs-lookup"><span data-stu-id="89f40-110">Exchange</span></span>
- <span data-ttu-id="89f40-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="89f40-111">SharePoint</span></span>
- <span data-ttu-id="89f40-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="89f40-112">OneDrive</span></span>
- <span data-ttu-id="89f40-113">Teams</span><span class="sxs-lookup"><span data-stu-id="89f40-113">Teams</span></span>
- <span data-ttu-id="89f40-114">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="89f40-114">Windows 10 devices</span></span> 

> [!TIP]
> <span data-ttu-id="89f40-115">使用符合[Teams DLP](endpoint-dlp-learn-about.md)条件的客户将在[](dlp-microsoft-teams.md)DLP 警报管理仪表板中查看其终结点 DLP 策略警报和 Teams DLP 策略警报。</span><span class="sxs-lookup"><span data-stu-id="89f40-115">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

## <a name="single-alert-and-aggregate-alert"></a><span data-ttu-id="89f40-116">单个警报和聚合警报</span><span class="sxs-lookup"><span data-stu-id="89f40-116">Single alert and aggregate alert</span></span>

<span data-ttu-id="89f40-117">可以在 DLP 策略中配置两种类型的警报。</span><span class="sxs-lookup"><span data-stu-id="89f40-117">There are two types of alerts that can be configured in DLP policies.</span></span>

<span data-ttu-id="89f40-118">单事件警报通常用于监视低量发生的高度敏感事件的策略，例如，在组织外发送一封包含 10 个或 10 多个客户信用卡号的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="89f40-118">**Single-event alerts** are typically used in policies that monitor for highly sensitive events that occur in a low volume, like a single email with 10 or more customer credit card numbers being sent outside your organization.</span></span>

<span data-ttu-id="89f40-119">**聚合事件警报** 通常用于监视在一段时间内发生较高容量的事件的策略。</span><span class="sxs-lookup"><span data-stu-id="89f40-119">**Aggregate-event alerts** are typically used in policies that monitor for events that occur in a higher volume over a period of time.</span></span> <span data-ttu-id="89f40-120">例如，在 48 小时内向组织外发送 10 封单独电子邮件（每封电子邮件包含一个客户信用卡号）时，可能会触发聚合警报。</span><span class="sxs-lookup"><span data-stu-id="89f40-120">For example, an aggregate alert can be triggered when 10 individual emails each with one customer credit card number is sent outside your org over 48 hours.</span></span>

## <a name="types-of-events"></a><span data-ttu-id="89f40-121">事件类型</span><span class="sxs-lookup"><span data-stu-id="89f40-121">Types of events</span></span>

<span data-ttu-id="89f40-122">下面是与警报关联的一些事件。</span><span class="sxs-lookup"><span data-stu-id="89f40-122">Here are some of the events associated with an alert.</span></span> <span data-ttu-id="89f40-123">在 UI 中，你可以选择一个特定的事件来查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="89f40-123">In the UI, you can choose a particular event to view its details.</span></span> 

### <a name="event-details"></a><span data-ttu-id="89f40-124">事件详情</span><span class="sxs-lookup"><span data-stu-id="89f40-124">Event details</span></span>

|<span data-ttu-id="89f40-125">属性名</span><span class="sxs-lookup"><span data-stu-id="89f40-125">Property name</span></span>  |<span data-ttu-id="89f40-126">描述</span><span class="sxs-lookup"><span data-stu-id="89f40-126">Description</span></span>  |<span data-ttu-id="89f40-127">事件类型</span><span class="sxs-lookup"><span data-stu-id="89f40-127">Event types</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="89f40-128">ID</span><span class="sxs-lookup"><span data-stu-id="89f40-128">ID</span></span> |<span data-ttu-id="89f40-129">与事件关联的唯一 ID</span><span class="sxs-lookup"><span data-stu-id="89f40-129">unique ID associated with the event</span></span> |<span data-ttu-id="89f40-130">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-130">all events</span></span> |
|<span data-ttu-id="89f40-131">位置</span><span class="sxs-lookup"><span data-stu-id="89f40-131">Location</span></span> |<span data-ttu-id="89f40-132">检测到事件的工作负荷</span><span class="sxs-lookup"><span data-stu-id="89f40-132">workload where the event was detected</span></span>|<span data-ttu-id="89f40-133">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-133">all events</span></span> |
|<span data-ttu-id="89f40-134">活动时间</span><span class="sxs-lookup"><span data-stu-id="89f40-134">time of activity</span></span>     |<span data-ttu-id="89f40-135">符合 DLP 策略条件的用户活动时间</span><span class="sxs-lookup"><span data-stu-id="89f40-135">time of the user activity that matched the criteria of the DLP policy</span></span> |

### <a name="impacted-entities"></a><span data-ttu-id="89f40-136">影响的实体</span><span class="sxs-lookup"><span data-stu-id="89f40-136">Impacted entities</span></span>

|<span data-ttu-id="89f40-137">属性名</span><span class="sxs-lookup"><span data-stu-id="89f40-137">Property name</span></span> |<span data-ttu-id="89f40-138">描述</span><span class="sxs-lookup"><span data-stu-id="89f40-138">Description</span></span>| <span data-ttu-id="89f40-139">事件类型</span><span class="sxs-lookup"><span data-stu-id="89f40-139">Event types</span></span>|
|---------|---------|---------|
|<span data-ttu-id="89f40-140">user</span><span class="sxs-lookup"><span data-stu-id="89f40-140">user</span></span> | <span data-ttu-id="89f40-141">执行导致策略匹配的操作的用户</span><span class="sxs-lookup"><span data-stu-id="89f40-141">user who took the action that caused the policy match</span></span> | <span data-ttu-id="89f40-142">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-142">all events</span></span>|
|<span data-ttu-id="89f40-143">hostname</span><span class="sxs-lookup"><span data-stu-id="89f40-143">hostname</span></span> | <span data-ttu-id="89f40-144">发生 DLP 策略匹配的计算机的主机名</span><span class="sxs-lookup"><span data-stu-id="89f40-144">host name of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="89f40-145">设备事件</span><span class="sxs-lookup"><span data-stu-id="89f40-145">device events</span></span>|
|<span data-ttu-id="89f40-146">IP 地址</span><span class="sxs-lookup"><span data-stu-id="89f40-146">IP address</span></span> | <span data-ttu-id="89f40-147">发生 DLP 策略匹配的计算机的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="89f40-147">IP address of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="89f40-148">设备事件</span><span class="sxs-lookup"><span data-stu-id="89f40-148">device events</span></span>|
|<span data-ttu-id="89f40-149">sha1</span><span class="sxs-lookup"><span data-stu-id="89f40-149">sha1</span></span> |<span data-ttu-id="89f40-150">文件的 SHA-1 哈希</span><span class="sxs-lookup"><span data-stu-id="89f40-150">SHA-1 hash of the file</span></span> | <span data-ttu-id="89f40-151">设备事件</span><span class="sxs-lookup"><span data-stu-id="89f40-151">device events</span></span>|
|<span data-ttu-id="89f40-152">sha256</span><span class="sxs-lookup"><span data-stu-id="89f40-152">sha256</span></span> | <span data-ttu-id="89f40-153">文件的 SHA-256 哈希</span><span class="sxs-lookup"><span data-stu-id="89f40-153">SHA-256 hash of the file</span></span> | <span data-ttu-id="89f40-154">设备事件</span><span class="sxs-lookup"><span data-stu-id="89f40-154">device events</span></span>|
|<span data-ttu-id="89f40-155">MDATP 设备 ID</span><span class="sxs-lookup"><span data-stu-id="89f40-155">MDATP device ID</span></span> | <span data-ttu-id="89f40-156">终结点设备 MDATP ID</span><span class="sxs-lookup"><span data-stu-id="89f40-156">endpoint device MDATP ID</span></span>|
|<span data-ttu-id="89f40-157">文件大小</span><span class="sxs-lookup"><span data-stu-id="89f40-157">file size</span></span> | <span data-ttu-id="89f40-158">文件大小</span><span class="sxs-lookup"><span data-stu-id="89f40-158">size of the file</span></span>| <span data-ttu-id="89f40-159">SharePoint、OneDrive 和设备事件</span><span class="sxs-lookup"><span data-stu-id="89f40-159">SharePoint, OneDrive, and device events</span></span>|
|<span data-ttu-id="89f40-160">文件路径</span><span class="sxs-lookup"><span data-stu-id="89f40-160">file path</span></span> | <span data-ttu-id="89f40-161">DLP 策略匹配所涉及的项目的绝对路径</span><span class="sxs-lookup"><span data-stu-id="89f40-161">the absolute path of the item involved with the DLP policy match</span></span> | <span data-ttu-id="89f40-162">SharePoint、OneDrive 和设备事件</span><span class="sxs-lookup"><span data-stu-id="89f40-162">SharePoint, OneDrive, and devices events</span></span>|
|<span data-ttu-id="89f40-163">电子邮件收件人</span><span class="sxs-lookup"><span data-stu-id="89f40-163">email recipients</span></span> |<span data-ttu-id="89f40-164">如果电子邮件是符合 DLP 策略的敏感项目，则此字段包括该电子邮件的收件人</span><span class="sxs-lookup"><span data-stu-id="89f40-164">if an email was the sensitive item that matched the DLP policy, this field includes the recipients of that email</span></span>| <span data-ttu-id="89f40-165">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-165">Exchange events</span></span>|
|<span data-ttu-id="89f40-166">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="89f40-166">email subject</span></span> |<span data-ttu-id="89f40-167">与 DLP 策略匹配的电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="89f40-167">subject of the email that matched the DLP policy</span></span> |<span data-ttu-id="89f40-168">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-168">Exchange events</span></span>|
|<span data-ttu-id="89f40-169">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="89f40-169">email attachments</span></span> | <span data-ttu-id="89f40-170">电子邮件中匹配 DLP 策略的附件的名称</span><span class="sxs-lookup"><span data-stu-id="89f40-170">names of the attachments in the email that matched the DLP policy</span></span>| <span data-ttu-id="89f40-171">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-171">Exchange events</span></span>|
|<span data-ttu-id="89f40-172">网站所有者</span><span class="sxs-lookup"><span data-stu-id="89f40-172">site owner</span></span> |<span data-ttu-id="89f40-173">网站所有者的名称</span><span class="sxs-lookup"><span data-stu-id="89f40-173">name of the site owner</span></span>| <span data-ttu-id="89f40-174">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-174">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="89f40-175">网站 URL</span><span class="sxs-lookup"><span data-stu-id="89f40-175">site URL</span></span> |<span data-ttu-id="89f40-176">DLP 策略匹配发生时的 SharePoint 或 OneDrive 网站的完整 URL</span><span class="sxs-lookup"><span data-stu-id="89f40-176">full of the URL of the SharePoint or OneDrive site where the DLP policy match occurred</span></span> |<span data-ttu-id="89f40-177">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-177">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="89f40-178">已创建文件</span><span class="sxs-lookup"><span data-stu-id="89f40-178">file created</span></span> |<span data-ttu-id="89f40-179">创建与 DLP 策略匹配的文件的时间</span><span class="sxs-lookup"><span data-stu-id="89f40-179">time of creation of the file that matched the DLP policy</span></span> |<span data-ttu-id="89f40-180">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-180">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="89f40-181">上次修改文件</span><span class="sxs-lookup"><span data-stu-id="89f40-181">file last modified</span></span> | <span data-ttu-id="89f40-182">上次更改匹配 DLP 策略的文件的时间</span><span class="sxs-lookup"><span data-stu-id="89f40-182">the last time that the file that matched the DLP policy was changed</span></span> | <span data-ttu-id="89f40-183">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-183">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="89f40-184">文件大小</span><span class="sxs-lookup"><span data-stu-id="89f40-184">file size</span></span> | <span data-ttu-id="89f40-185">与 DLP 策略匹配的文件大小</span><span class="sxs-lookup"><span data-stu-id="89f40-185">size of the file that matched the DLP policy</span></span> |<span data-ttu-id="89f40-186">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-186">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="89f40-187">文件所有者</span><span class="sxs-lookup"><span data-stu-id="89f40-187">file owner</span></span> |<span data-ttu-id="89f40-188">与 DLP 策略匹配的文件的所有者</span><span class="sxs-lookup"><span data-stu-id="89f40-188">owner of the file that matched the DLP policy</span></span> |<span data-ttu-id="89f40-189">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="89f40-189">SharePoint and OneDrive events</span></span>|  

### <a name="policy-details"></a><span data-ttu-id="89f40-190">策略详细信息</span><span class="sxs-lookup"><span data-stu-id="89f40-190">Policy details</span></span>

|<span data-ttu-id="89f40-191">属性名</span><span class="sxs-lookup"><span data-stu-id="89f40-191">Property name</span></span> |<span data-ttu-id="89f40-192">描述</span><span class="sxs-lookup"><span data-stu-id="89f40-192">Description</span></span> |<span data-ttu-id="89f40-193">事件类型</span><span class="sxs-lookup"><span data-stu-id="89f40-193">Event types</span></span> |
|---------|---------|---------|
|<span data-ttu-id="89f40-194">匹配的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="89f40-194">DLP policy matched</span></span> |<span data-ttu-id="89f40-195">匹配的 DLP 策略的名称</span><span class="sxs-lookup"><span data-stu-id="89f40-195">name of the matched DLP policy</span></span> |<span data-ttu-id="89f40-196">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-196">all events</span></span>|
|<span data-ttu-id="89f40-197">规则匹配</span><span class="sxs-lookup"><span data-stu-id="89f40-197">rule matched</span></span> |<span data-ttu-id="89f40-198">匹配的 DLP 策略规则的名称</span><span class="sxs-lookup"><span data-stu-id="89f40-198">name of the matched DLP policy rule</span></span> |<span data-ttu-id="89f40-199">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-199">all events</span></span>|
|<span data-ttu-id="89f40-200">检测到 SIT (敏感信息) 类型</span><span class="sxs-lookup"><span data-stu-id="89f40-200">sensitive information types (SIT) detected</span></span>|<span data-ttu-id="89f40-201">检测到作为 DLP 策略匹配的一部分的 SIT</span><span class="sxs-lookup"><span data-stu-id="89f40-201">SITs that were detected as part of the DLP policy match</span></span> |<span data-ttu-id="89f40-202">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-202">all events</span></span>|
|<span data-ttu-id="89f40-203">执行的操作</span><span class="sxs-lookup"><span data-stu-id="89f40-203">actions taken</span></span> |<span data-ttu-id="89f40-204">导致 DLP 策略匹配的操作</span><span class="sxs-lookup"><span data-stu-id="89f40-204">actions that were taken that caused the DLP policy match</span></span>| <span data-ttu-id="89f40-205">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-205">all events</span></span>|
|<span data-ttu-id="89f40-206">违反操作</span><span class="sxs-lookup"><span data-stu-id="89f40-206">violating action</span></span> | <span data-ttu-id="89f40-207">引发 DLP 警报的终结点设备上的操作</span><span class="sxs-lookup"><span data-stu-id="89f40-207">action on the endpoint device that raised the DLP alert</span></span>| <span data-ttu-id="89f40-208">设备事件</span><span class="sxs-lookup"><span data-stu-id="89f40-208">device events</span></span> | 
|<span data-ttu-id="89f40-209">用户过度控制策略</span><span class="sxs-lookup"><span data-stu-id="89f40-209">user overrode policy</span></span> |<span data-ttu-id="89f40-210">用户通过策略提示覆盖策略</span><span class="sxs-lookup"><span data-stu-id="89f40-210">did the user override the policy via a policy tip</span></span> | <span data-ttu-id="89f40-211">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-211">all events</span></span>|
|<span data-ttu-id="89f40-212">使用替代理由</span><span class="sxs-lookup"><span data-stu-id="89f40-212">use override justification</span></span> |<span data-ttu-id="89f40-213">用户为替代提供的原因文本</span><span class="sxs-lookup"><span data-stu-id="89f40-213">the text of the reason provided by the user for the override</span></span> | <span data-ttu-id="89f40-214">所有事件</span><span class="sxs-lookup"><span data-stu-id="89f40-214">all events</span></span>|   

## <a name="see-also"></a><span data-ttu-id="89f40-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89f40-215">See Also</span></span>

- [<span data-ttu-id="89f40-216">数据丢失防护警报仪表板入门</span><span class="sxs-lookup"><span data-stu-id="89f40-216">Get started with the data loss prevention alert dashboard</span></span>](dlp-alerts-dashboard-get-started.md)
- [<span data-ttu-id="89f40-217">从数据丢失防护开始</span><span class="sxs-lookup"><span data-stu-id="89f40-217">Where to start with data loss prevention</span></span>](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)