---
title: Microsoft Defender AV 事件 ID 和错误代码
description: 查找事件MICROSOFT DEFENDER 防病毒和错误的原因和解决方案
keywords: 事件， 错误代码， siem， 日志记录， 疑难解答， wef， windows 事件转发
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275344"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="d5359-104">查看事件日志和错误代码，解决 Microsoft Defender 防病毒软件问题</span><span class="sxs-lookup"><span data-stu-id="d5359-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d5359-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d5359-105">**Applies to:**</span></span>

- [<span data-ttu-id="d5359-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d5359-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d5359-107">如果遇到与Microsoft Defender 防病毒的问题，可以搜索本主题中的表以查找匹配的问题和潜在的解决方案。</span><span class="sxs-lookup"><span data-stu-id="d5359-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="d5359-108">表列表：</span><span class="sxs-lookup"><span data-stu-id="d5359-108">The tables list:</span></span>

- <span data-ttu-id="d5359-109">[Microsoft Defender 防病毒事件 (](#windows-defender-av-ids)都适用于事件Windows 10 Windows Server 2016) </span><span class="sxs-lookup"><span data-stu-id="d5359-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="d5359-110">Microsoft Defender 防病毒客户端错误代码</span><span class="sxs-lookup"><span data-stu-id="d5359-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="d5359-111">Microsoft Microsoft Defender 防病毒和测试 (期间使用的内部客户端错误代码) </span><span class="sxs-lookup"><span data-stu-id="d5359-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="d5359-112">还可以访问 Microsoft Defender for Endpoint 演示[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 确认以下功能是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="d5359-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="d5359-113">云端保护</span><span class="sxs-lookup"><span data-stu-id="d5359-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="d5359-114">快速学习 (包括首次看到时阻止) </span><span class="sxs-lookup"><span data-stu-id="d5359-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="d5359-115">可能不需要的应用程序阻止</span><span class="sxs-lookup"><span data-stu-id="d5359-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="d5359-116">Microsoft Defender 防病毒事件 ID</span><span class="sxs-lookup"><span data-stu-id="d5359-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="d5359-117">Microsoft Defender 防病毒事件日志中记录事件Windows。</span><span class="sxs-lookup"><span data-stu-id="d5359-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="d5359-118">你可以直接查看事件日志，或者如果你有第三方安全信息和事件管理 (SIEM) 工具，还可以使用 Microsoft Defender 防病毒 客户端事件[ID](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids)查看终结点中的特定事件和错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="d5359-119">本节中的表列出了主要事件Microsoft Defender 防病毒，并尽可能提供建议的解决方案来修复或解决错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="d5359-120">查看事件Microsoft Defender 防病毒事件</span><span class="sxs-lookup"><span data-stu-id="d5359-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="d5359-121">打开 **事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="d5359-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="d5359-122">在控制台树中，展开"**应用程序** 和服务日志"，然后展开 **"Microsoft"，** 然后Windows"，Windows Defender"。  </span><span class="sxs-lookup"><span data-stu-id="d5359-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="d5359-123">双击操作 **。**</span><span class="sxs-lookup"><span data-stu-id="d5359-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="d5359-124">在详细信息窗格中，查看各个事件的列表以查找事件。</span><span class="sxs-lookup"><span data-stu-id="d5359-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="d5359-125">单击事件以查看有关下窗格中"常规"和"详细信息"选项卡下 **的事件\*\*\*\*的特定** 详细信息。</span><span class="sxs-lookup"><span data-stu-id="d5359-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="d5359-126">事件 ID：1000</span><span class="sxs-lookup"><span data-stu-id="d5359-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-127">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="d5359-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-129">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-129">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-130">
<b>反恶意软件扫描已启动。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="d5359-131">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d5359-132">
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-133">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-133">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-134">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-134">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-135">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-135">Antimalware</span></span></li>
</ul><span data-ttu-id="d5359-136">
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-137">完全扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-137">Full scan</span></span></li>
<li><span data-ttu-id="d5359-138">快速扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-138">Quick scan</span></span></li>
<li><span data-ttu-id="d5359-139">客户扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-139">Customer scan</span></span></li>
</ul><span data-ttu-id="d5359-140">
</dt>
<dt>扫描资源： &lt;扫描 (文件/目录/BHO) 等资源。 &gt; </dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-141">事件 ID：1001</span><span class="sxs-lookup"><span data-stu-id="d5359-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-142">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-144">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-144">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-145">
<b>反恶意软件扫描已完成。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-146">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d5359-147">
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-148">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-148">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-149">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-149">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-150">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-150">Antimalware</span></span></li>
</ul><span data-ttu-id="d5359-151">
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-152">完全扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-152">Full scan</span></span></li>
<li><span data-ttu-id="d5359-153">快速扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-153">Quick scan</span></span></li>
<li><span data-ttu-id="d5359-154">客户扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-154">Customer scan</span></span></li>
</ul><span data-ttu-id="d5359-155">
</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>扫描时间 &lt; ：扫描的持续时间。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-156">事件 ID：1002</span><span class="sxs-lookup"><span data-stu-id="d5359-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-157">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-159">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-159">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-160">
<b>反恶意软件扫描在完成之前已停止。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-161">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d5359-162">
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-163">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-163">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-164">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-164">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-165">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-165">Antimalware</span></span></li>
</ul><span data-ttu-id="d5359-166">
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-167">完全扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-167">Full scan</span></span></li>
<li><span data-ttu-id="d5359-168">快速扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-168">Quick scan</span></span></li>
<li><span data-ttu-id="d5359-169">客户扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-169">Customer scan</span></span></li>
</ul><span data-ttu-id="d5359-170">
</dt>
<dt>用户： &lt;Domain &gt; &amp; lt;用户 &gt; </dt>
<dt>扫描时间 &lt; ：扫描的持续时间。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-171">事件 ID：1003</span><span class="sxs-lookup"><span data-stu-id="d5359-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-172">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-174">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-174">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-175">
<b>反恶意软件扫描已暂停。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-176">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d5359-177">
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-178">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-178">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-179">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-179">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-180">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-180">Antimalware</span></span></li>
</ul><span data-ttu-id="d5359-181">
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-182">完全扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-182">Full scan</span></span></li>
<li><span data-ttu-id="d5359-183">快速扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-183">Quick scan</span></span></li>
<li><span data-ttu-id="d5359-184">客户扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-184">Customer scan</span></span></li>
</ul><span data-ttu-id="d5359-185">
</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-186">事件 ID：1004</span><span class="sxs-lookup"><span data-stu-id="d5359-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-187">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-189">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-189">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-190">
<b>反恶意软件扫描已恢复。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-191">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d5359-192">
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-193">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-193">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-194">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-194">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-195">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-195">Antimalware</span></span></li>
</ul><span data-ttu-id="d5359-196">
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-197">完全扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-197">Full scan</span></span></li>
<li><span data-ttu-id="d5359-198">快速扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-198">Quick scan</span></span></li>
<li><span data-ttu-id="d5359-199">客户扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-199">Customer scan</span></span></li>
</ul><span data-ttu-id="d5359-200">
</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-201">事件 ID：1005</span><span class="sxs-lookup"><span data-stu-id="d5359-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-202">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-204">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-204">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-205">
<b>反恶意软件扫描失败。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-206">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d5359-207">
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-208">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-208">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-209">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-209">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-210">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-210">Antimalware</span></span></li>
</ul><span data-ttu-id="d5359-211">
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-212">完全扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-212">Full scan</span></span></li>
<li><span data-ttu-id="d5359-213">快速扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-213">Quick scan</span></span></li>
<li><span data-ttu-id="d5359-214">客户扫描</span><span class="sxs-lookup"><span data-stu-id="d5359-214">Customer scan</span></span></li>
</ul><span data-ttu-id="d5359-215">
</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-216">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-217">防病毒客户端遇到错误，并且当前扫描已停止。</span><span class="sxs-lookup"><span data-stu-id="d5359-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="d5359-218">扫描可能由于客户端问题而失败。</span><span class="sxs-lookup"><span data-stu-id="d5359-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="d5359-219">此事件记录包括扫描 ID、扫描类型 (Microsoft Defender 防病毒、反间谍软件、反恶意软件) 、扫描参数、启动扫描的用户、错误代码和错误描述。</span><span class="sxs-lookup"><span data-stu-id="d5359-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="d5359-220">若要对此事件进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="d5359-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d5359-221">再次运行扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="d5359-222">如果以相同方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持</a>站点，在"搜索"框中输入错误编号<b></b>以查找错误代码。</span><span class="sxs-lookup"><span data-stu-id="d5359-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="d5359-223">与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系</span><span class="sxs-lookup"><span data-stu-id="d5359-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-224">事件 ID：1006</span><span class="sxs-lookup"><span data-stu-id="d5359-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-225">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-227">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-227">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-228">
<b>反恶意软件引擎发现恶意软件或其他可能不需要的软件。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-229">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-230">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-231">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-232">低</span><span class="sxs-lookup"><span data-stu-id="d5359-232">Low</span></span></li>
<li><span data-ttu-id="d5359-233">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-233">Moderate</span></span></li>
<li><span data-ttu-id="d5359-234">高</span><span class="sxs-lookup"><span data-stu-id="d5359-234">High</span></span></li>
<li><span data-ttu-id="d5359-235">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-235">Severe</span></span></li>
</ul><span data-ttu-id="d5359-236">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-237">未知</span><span class="sxs-lookup"><span data-stu-id="d5359-237">Unknown</span></span></li>
<li><span data-ttu-id="d5359-238">本地计算机</span><span class="sxs-lookup"><span data-stu-id="d5359-238">Local computer</span></span></li>
<li><span data-ttu-id="d5359-239">网络共享</span><span class="sxs-lookup"><span data-stu-id="d5359-239">Network share</span></span></li>
<li><span data-ttu-id="d5359-240">Internet</span><span class="sxs-lookup"><span data-stu-id="d5359-240">Internet</span></span></li>
<li><span data-ttu-id="d5359-241">传入流量</span><span class="sxs-lookup"><span data-stu-id="d5359-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="d5359-242">传出流量</span><span class="sxs-lookup"><span data-stu-id="d5359-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d5359-243">
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-244">启发式</span><span class="sxs-lookup"><span data-stu-id="d5359-244">Heuristics</span></span></li>
<li><span data-ttu-id="d5359-245">Generic</span><span class="sxs-lookup"><span data-stu-id="d5359-245">Generic</span></span></li>
<li><span data-ttu-id="d5359-246">具体</span><span class="sxs-lookup"><span data-stu-id="d5359-246">Concrete</span></span></li>
<li><span data-ttu-id="d5359-247">动态签名</span><span class="sxs-lookup"><span data-stu-id="d5359-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d5359-248">
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d5359-249">用户：用户启动</span><span class="sxs-lookup"><span data-stu-id="d5359-249">User: user initiated</span></span></li>
<li><span data-ttu-id="d5359-250">系统：系统已启动</span><span class="sxs-lookup"><span data-stu-id="d5359-250">System: system initiated</span></span></li>
<li><span data-ttu-id="d5359-251">实时：启动实时组件</span><span class="sxs-lookup"><span data-stu-id="d5359-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d5359-252">IOAV：IE 下载Outlook快速附件启动</span><span class="sxs-lookup"><span data-stu-id="d5359-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d5359-253">NIS：网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d5359-254">IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</span><span class="sxs-lookup"><span data-stu-id="d5359-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d5359-255">提前启动反恶意软件 (ELAM) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d5359-256">这包括启动序列检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d5359-257">远程证明</span><span class="sxs-lookup"><span data-stu-id="d5359-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="d5359-258">反恶意软件扫描接口 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d5359-259">主要用于保护 PS (VBS) 脚本，尽管也可由第三方调用。</span><span class="sxs-lookup"><span data-stu-id="d5359-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d5359-260">UAC </dt> 
<dt>状态 &lt; ： &gt; 状态</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt>签名版本中的进程
<dt>： &lt; 定义版本 &gt; </dt>引擎
<dt>版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-261">事件 ID：1007</span><span class="sxs-lookup"><span data-stu-id="d5359-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-262">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-264">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-264">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-265">
<b>反恶意软件平台执行了一个操作来保护系统免受恶意软件或其他可能不需要的软件的攻击。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-266">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-267">Microsoft Defender 防病毒已采取措施保护此计算机免受恶意软件或其他可能不需要的软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="d5359-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="d5359-268">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-269">
<dt>用户： &lt;Domain &gt; \& lt;用户名 &gt; </dt>
<dt>： &lt; 威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ： &gt; 严重性，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-270">低</span><span class="sxs-lookup"><span data-stu-id="d5359-270">Low</span></span></li>
<li><span data-ttu-id="d5359-271">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-271">Moderate</span></span></li>
<li><span data-ttu-id="d5359-272">高</span><span class="sxs-lookup"><span data-stu-id="d5359-272">High</span></span></li>
<li><span data-ttu-id="d5359-273">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-273">Severe</span></span></li>
</ul><span data-ttu-id="d5359-274">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt> 
<dt>操作： &lt; 操作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-275">清理：资源已清理</span><span class="sxs-lookup"><span data-stu-id="d5359-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d5359-276">隔离：已隔离资源</span><span class="sxs-lookup"><span data-stu-id="d5359-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d5359-277">删除：已删除资源</span><span class="sxs-lookup"><span data-stu-id="d5359-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d5359-278">允许：允许执行/存在资源</span><span class="sxs-lookup"><span data-stu-id="d5359-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d5359-279">用户定义：用户定义的操作，通常来自用户指定的操作列表</span><span class="sxs-lookup"><span data-stu-id="d5359-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d5359-280">无操作：无操作</span><span class="sxs-lookup"><span data-stu-id="d5359-280">No action: No action</span></span></li>
<li><span data-ttu-id="d5359-281">阻止：资源被阻止执行</span><span class="sxs-lookup"><span data-stu-id="d5359-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d5359-282">
</dt>
<dt>状态： &lt;状态 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-283">事件 ID：1008</span><span class="sxs-lookup"><span data-stu-id="d5359-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-284">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-286">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-286">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-287">
<b>反恶意软件平台尝试执行保护系统免受恶意软件或其他可能不需要的软件的攻击，但操作失败。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-288">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-289">Microsoft Defender 防病毒恶意软件或其他可能不需要的软件时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="d5359-290">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-291">
<dt>用户： &lt;Domain &gt; \& lt;用户名 &gt; </dt>
<dt>： &lt; 威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ： &gt; 严重性，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-292">低</span><span class="sxs-lookup"><span data-stu-id="d5359-292">Low</span></span></li>
<li><span data-ttu-id="d5359-293">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-293">Moderate</span></span></li>
<li><span data-ttu-id="d5359-294">高</span><span class="sxs-lookup"><span data-stu-id="d5359-294">High</span></span></li>
<li><span data-ttu-id="d5359-295">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-295">Severe</span></span></li>
</ul><span data-ttu-id="d5359-296">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 操作 &lt; ：操作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-297">清理：资源已清理</span><span class="sxs-lookup"><span data-stu-id="d5359-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d5359-298">隔离：已隔离资源</span><span class="sxs-lookup"><span data-stu-id="d5359-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d5359-299">删除：已删除资源</span><span class="sxs-lookup"><span data-stu-id="d5359-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d5359-300">允许：允许执行/存在资源</span><span class="sxs-lookup"><span data-stu-id="d5359-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d5359-301">用户定义：用户定义的操作，通常来自用户指定的操作列表</span><span class="sxs-lookup"><span data-stu-id="d5359-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d5359-302">无操作：无操作</span><span class="sxs-lookup"><span data-stu-id="d5359-302">No action: No action</span></span></li>
<li><span data-ttu-id="d5359-303">阻止：资源被阻止执行</span><span class="sxs-lookup"><span data-stu-id="d5359-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d5359-304">
</dt>
<dt>错误代码： &lt;错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
<dt>状态： &lt;状态 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-305">事件 ID：1009</span><span class="sxs-lookup"><span data-stu-id="d5359-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-306">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-308">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-308">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-309">
<b>反恶意软件平台从隔离区还原了一个项目。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-310">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-311">Microsoft Defender 防病毒已还原隔离项目。</span><span class="sxs-lookup"><span data-stu-id="d5359-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="d5359-312">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-313">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-314">低</span><span class="sxs-lookup"><span data-stu-id="d5359-314">Low</span></span></li>
<li><span data-ttu-id="d5359-315">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-315">Moderate</span></span></li>
<li><span data-ttu-id="d5359-316">高</span><span class="sxs-lookup"><span data-stu-id="d5359-316">High</span></span></li>
<li><span data-ttu-id="d5359-317">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-317">Severe</span></span></li>
</ul><span data-ttu-id="d5359-318">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-319">事件 ID：1010</span><span class="sxs-lookup"><span data-stu-id="d5359-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-320">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-322">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-322">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-323">
<b>反恶意软件平台无法从隔离中还原项目。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-324">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-325">Microsoft Defender 防病毒尝试从隔离区还原项目时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="d5359-326">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-327">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-328">低</span><span class="sxs-lookup"><span data-stu-id="d5359-328">Low</span></span></li>
<li><span data-ttu-id="d5359-329">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-329">Moderate</span></span></li>
<li><span data-ttu-id="d5359-330">高</span><span class="sxs-lookup"><span data-stu-id="d5359-330">High</span></span></li>
<li><span data-ttu-id="d5359-331">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-331">Severe</span></span></li>
</ul><span data-ttu-id="d5359-332">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-333">事件 ID：1011</span><span class="sxs-lookup"><span data-stu-id="d5359-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-334">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-336">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-336">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-337">
<b>反恶意软件平台从隔离区中删除了一个项目。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-338">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-339">Microsoft Defender 防病毒已删除隔离项目。</span><span class="sxs-lookup"><span data-stu-id="d5359-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="d5359-340">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-341">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-342">低</span><span class="sxs-lookup"><span data-stu-id="d5359-342">Low</span></span></li>
<li><span data-ttu-id="d5359-343">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-343">Moderate</span></span></li>
<li><span data-ttu-id="d5359-344">高</span><span class="sxs-lookup"><span data-stu-id="d5359-344">High</span></span></li>
<li><span data-ttu-id="d5359-345">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-345">Severe</span></span></li>
</ul><span data-ttu-id="d5359-346">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-347">事件 ID：1012</span><span class="sxs-lookup"><span data-stu-id="d5359-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-348">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-350">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-350">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-351">
<b>反恶意软件平台无法从隔离区中删除项目。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-352">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-353">Microsoft Defender 防病毒尝试从隔离区删除项目时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="d5359-354">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-355">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-356">低</span><span class="sxs-lookup"><span data-stu-id="d5359-356">Low</span></span></li>
<li><span data-ttu-id="d5359-357">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-357">Moderate</span></span></li>
<li><span data-ttu-id="d5359-358">高</span><span class="sxs-lookup"><span data-stu-id="d5359-358">High</span></span></li>
<li><span data-ttu-id="d5359-359">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-359">Severe</span></span></li>
</ul><span data-ttu-id="d5359-360">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-361">事件 ID：1013</span><span class="sxs-lookup"><span data-stu-id="d5359-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-362">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-364">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-364">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-365">
<b>反恶意软件平台已删除恶意软件和其他可能不需要的软件的历史记录。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-366">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-367">Microsoft Defender 防病毒已删除恶意软件和其他可能不需要的软件的历史记录。</span><span class="sxs-lookup"><span data-stu-id="d5359-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="d5359-368">
<dt>Time：事件发生的时间，例如清除历史记录的时间。此参数不用于威胁事件，因此不会混淆它是修正时间还是感染时间。对于这些时间，我们专门将它们称为"操作时间"或"检测时间"。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-369">事件 ID：1014</span><span class="sxs-lookup"><span data-stu-id="d5359-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-370">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-372">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="d5359-373">反恶意软件平台无法删除恶意软件和其他可能不需要的软件的历史记录。</span><span class="sxs-lookup"><span data-stu-id="d5359-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-374">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-375">Microsoft Defender 防病毒尝试删除恶意软件和其他可能不需要的软件的历史记录时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="d5359-376">
<dt>Time：事件发生的时间，例如清除历史记录的时间。此参数不用于威胁事件，因此不会混淆它是修正时间还是感染时间。对于这些时间，我们专门将它们称为"操作时间"或"检测时间"。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-377">事件 ID：1015</span><span class="sxs-lookup"><span data-stu-id="d5359-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-378">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-380">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-380">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-381">
<b>反恶意软件平台检测到可疑行为。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-382">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-383">Microsoft Defender 防病毒检测到可疑行为。</span><span class="sxs-lookup"><span data-stu-id="d5359-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="d5359-384">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-385">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-386">低</span><span class="sxs-lookup"><span data-stu-id="d5359-386">Low</span></span></li>
<li><span data-ttu-id="d5359-387">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-387">Moderate</span></span></li>
<li><span data-ttu-id="d5359-388">高</span><span class="sxs-lookup"><span data-stu-id="d5359-388">High</span></span></li>
<li><span data-ttu-id="d5359-389">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-389">Severe</span></span></li>
</ul><span data-ttu-id="d5359-390">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-391">未知</span><span class="sxs-lookup"><span data-stu-id="d5359-391">Unknown</span></span></li>
<li><span data-ttu-id="d5359-392">本地计算机</span><span class="sxs-lookup"><span data-stu-id="d5359-392">Local computer</span></span></li>
<li><span data-ttu-id="d5359-393">网络共享</span><span class="sxs-lookup"><span data-stu-id="d5359-393">Network share</span></span></li>
<li><span data-ttu-id="d5359-394">Internet</span><span class="sxs-lookup"><span data-stu-id="d5359-394">Internet</span></span></li>
<li><span data-ttu-id="d5359-395">传入流量</span><span class="sxs-lookup"><span data-stu-id="d5359-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="d5359-396">传出流量</span><span class="sxs-lookup"><span data-stu-id="d5359-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d5359-397">
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-398">启发式</span><span class="sxs-lookup"><span data-stu-id="d5359-398">Heuristics</span></span></li>
<li><span data-ttu-id="d5359-399">Generic</span><span class="sxs-lookup"><span data-stu-id="d5359-399">Generic</span></span></li>
<li><span data-ttu-id="d5359-400">具体</span><span class="sxs-lookup"><span data-stu-id="d5359-400">Concrete</span></span></li>
<li><span data-ttu-id="d5359-401">动态签名</span><span class="sxs-lookup"><span data-stu-id="d5359-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d5359-402">
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d5359-403">用户：用户启动</span><span class="sxs-lookup"><span data-stu-id="d5359-403">User: user initiated</span></span></li>
<li><span data-ttu-id="d5359-404">系统：系统已启动</span><span class="sxs-lookup"><span data-stu-id="d5359-404">System: system initiated</span></span></li>
<li><span data-ttu-id="d5359-405">实时：启动实时组件</span><span class="sxs-lookup"><span data-stu-id="d5359-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d5359-406">IOAV：IE 下载Outlook快速附件启动</span><span class="sxs-lookup"><span data-stu-id="d5359-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d5359-407">NIS：网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d5359-408">IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</span><span class="sxs-lookup"><span data-stu-id="d5359-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d5359-409">提前启动反恶意软件 (ELAM) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d5359-410">这包括启动序列检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d5359-411">远程证明</span><span class="sxs-lookup"><span data-stu-id="d5359-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="d5359-412">反恶意软件扫描接口 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d5359-413">主要用于保护 PS (VBS) 脚本，尽管也可由第三方调用。</span><span class="sxs-lookup"><span data-stu-id="d5359-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d5359-414">UAC </dt> 
<dt>状态 &lt; ： &gt; 状态</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; ：PID &gt; 签名</dt>ID
<dt>中的进程：枚举匹配严重性。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎 &gt; </dt>保真
<dt>度标签：</dt>
<dt>目标文件名： &lt; &gt; 文件名文件的名称。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-415">事件 ID：1116</span><span class="sxs-lookup"><span data-stu-id="d5359-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-416">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-418">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-418">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-419">
<b>反恶意软件平台检测到恶意软件或其他可能不需要的软件。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-420">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-421">Microsoft Defender 防病毒检测到恶意软件或其他可能不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="d5359-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d5359-422">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-423">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-424">低</span><span class="sxs-lookup"><span data-stu-id="d5359-424">Low</span></span></li>
<li><span data-ttu-id="d5359-425">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-425">Moderate</span></span></li>
<li><span data-ttu-id="d5359-426">高</span><span class="sxs-lookup"><span data-stu-id="d5359-426">High</span></span></li>
<li><span data-ttu-id="d5359-427">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-427">Severe</span></span></li>
</ul><span data-ttu-id="d5359-428">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-429">未知</span><span class="sxs-lookup"><span data-stu-id="d5359-429">Unknown</span></span></li>
<li><span data-ttu-id="d5359-430">本地计算机</span><span class="sxs-lookup"><span data-stu-id="d5359-430">Local computer</span></span></li>
<li><span data-ttu-id="d5359-431">网络共享</span><span class="sxs-lookup"><span data-stu-id="d5359-431">Network share</span></span></li>
<li><span data-ttu-id="d5359-432">Internet</span><span class="sxs-lookup"><span data-stu-id="d5359-432">Internet</span></span></li>
<li><span data-ttu-id="d5359-433">传入流量</span><span class="sxs-lookup"><span data-stu-id="d5359-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="d5359-434">传出流量</span><span class="sxs-lookup"><span data-stu-id="d5359-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d5359-435">
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-436">启发式</span><span class="sxs-lookup"><span data-stu-id="d5359-436">Heuristics</span></span></li>
<li><span data-ttu-id="d5359-437">Generic</span><span class="sxs-lookup"><span data-stu-id="d5359-437">Generic</span></span></li>
<li><span data-ttu-id="d5359-438">具体</span><span class="sxs-lookup"><span data-stu-id="d5359-438">Concrete</span></span></li>
<li><span data-ttu-id="d5359-439">动态签名</span><span class="sxs-lookup"><span data-stu-id="d5359-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d5359-440">
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d5359-441">用户：用户启动</span><span class="sxs-lookup"><span data-stu-id="d5359-441">User: user initiated</span></span></li>
<li><span data-ttu-id="d5359-442">系统：系统已启动</span><span class="sxs-lookup"><span data-stu-id="d5359-442">System: system initiated</span></span></li>
<li><span data-ttu-id="d5359-443">实时：启动实时组件</span><span class="sxs-lookup"><span data-stu-id="d5359-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d5359-444">IOAV：IE 下载Outlook快速附件启动</span><span class="sxs-lookup"><span data-stu-id="d5359-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d5359-445">NIS：网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d5359-446">IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</span><span class="sxs-lookup"><span data-stu-id="d5359-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d5359-447">提前启动反恶意软件 (ELAM) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d5359-448">这包括启动序列检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d5359-449">远程证明</span><span class="sxs-lookup"><span data-stu-id="d5359-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="d5359-450">反恶意软件扫描接口 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d5359-451">主要用于保护 PS (VBS) 脚本，尽管也可由第三方调用。</span><span class="sxs-lookup"><span data-stu-id="d5359-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d5359-452">UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt>签名版本中的进程
<dt>： &lt; 定义版本 &gt; </dt>引擎
<dt>版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-453">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-454">不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-454">No action is required.</span></span> <span data-ttu-id="d5359-455">Microsoft Defender 防病毒可以暂停此威胁并对此威胁采取常规操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="d5359-456">如果要手动删除威胁，请在 Microsoft Defender 防病毒 界面中，单击"清理计算机<b>"。</b></span><span class="sxs-lookup"><span data-stu-id="d5359-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-457">事件 ID：1117</span><span class="sxs-lookup"><span data-stu-id="d5359-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-458">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-460">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-460">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-461">
<b>反恶意软件平台执行了一个操作来保护系统免受恶意软件或其他可能不需要的软件的攻击。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-462">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-463">Microsoft Defender 防病毒已采取措施保护此计算机免受恶意软件或其他可能不需要的软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="d5359-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d5359-464">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-465">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-466">低</span><span class="sxs-lookup"><span data-stu-id="d5359-466">Low</span></span></li>
<li><span data-ttu-id="d5359-467">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-467">Moderate</span></span></li>
<li><span data-ttu-id="d5359-468">高</span><span class="sxs-lookup"><span data-stu-id="d5359-468">High</span></span></li>
<li><span data-ttu-id="d5359-469">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-469">Severe</span></span></li>
</ul><span data-ttu-id="d5359-470">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-471">未知</span><span class="sxs-lookup"><span data-stu-id="d5359-471">Unknown</span></span></li>
<li><span data-ttu-id="d5359-472">本地计算机</span><span class="sxs-lookup"><span data-stu-id="d5359-472">Local computer</span></span></li>
<li><span data-ttu-id="d5359-473">网络共享</span><span class="sxs-lookup"><span data-stu-id="d5359-473">Network share</span></span></li>
<li><span data-ttu-id="d5359-474">Internet</span><span class="sxs-lookup"><span data-stu-id="d5359-474">Internet</span></span></li>
<li><span data-ttu-id="d5359-475">传入流量</span><span class="sxs-lookup"><span data-stu-id="d5359-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="d5359-476">传出流量</span><span class="sxs-lookup"><span data-stu-id="d5359-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d5359-477">
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-478">启发式</span><span class="sxs-lookup"><span data-stu-id="d5359-478">Heuristics</span></span></li>
<li><span data-ttu-id="d5359-479">Generic</span><span class="sxs-lookup"><span data-stu-id="d5359-479">Generic</span></span></li>
<li><span data-ttu-id="d5359-480">具体</span><span class="sxs-lookup"><span data-stu-id="d5359-480">Concrete</span></span></li>
<li><span data-ttu-id="d5359-481">动态签名</span><span class="sxs-lookup"><span data-stu-id="d5359-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d5359-482">
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d5359-483">用户：用户启动</span><span class="sxs-lookup"><span data-stu-id="d5359-483">User: user initiated</span></span></li>
<li><span data-ttu-id="d5359-484">系统：系统已启动</span><span class="sxs-lookup"><span data-stu-id="d5359-484">System: system initiated</span></span></li>
<li><span data-ttu-id="d5359-485">实时：启动实时组件</span><span class="sxs-lookup"><span data-stu-id="d5359-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d5359-486">IOAV：IE 下载Outlook快速附件启动</span><span class="sxs-lookup"><span data-stu-id="d5359-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d5359-487">NIS：网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d5359-488">IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</span><span class="sxs-lookup"><span data-stu-id="d5359-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d5359-489">提前启动反恶意软件 (ELAM) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d5359-490">这包括启动序列检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d5359-491">远程证明</span><span class="sxs-lookup"><span data-stu-id="d5359-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="d5359-492">反恶意软件扫描接口 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d5359-493">主要用于保护 PS (VBS) 脚本，尽管也可由第三方调用。</span><span class="sxs-lookup"><span data-stu-id="d5359-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d5359-494">UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt> 
<dt> 操作中的进程： &lt; 操作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-495">清理：资源已清理</span><span class="sxs-lookup"><span data-stu-id="d5359-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d5359-496">隔离：已隔离资源</span><span class="sxs-lookup"><span data-stu-id="d5359-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d5359-497">删除：已删除资源</span><span class="sxs-lookup"><span data-stu-id="d5359-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d5359-498">允许：允许执行/存在资源</span><span class="sxs-lookup"><span data-stu-id="d5359-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d5359-499">用户定义：用户定义的操作，通常来自用户指定的操作列表</span><span class="sxs-lookup"><span data-stu-id="d5359-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d5359-500">无操作：无操作</span><span class="sxs-lookup"><span data-stu-id="d5359-500">No action: No action</span></span></li>
<li><span data-ttu-id="d5359-501">阻止：资源被阻止执行</span><span class="sxs-lookup"><span data-stu-id="d5359-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d5359-502">
</dt>
<dt>操作状态： &lt;其他操作的说明 &gt; 错误</dt>
<dt>代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>引擎版本
<dt> &lt; ：反恶意软件引擎 &gt; </dt>版本 注意：每当 Microsoft Defender 防病毒、Microsoft Security Essentials、恶意软件删除工具或 System Center Endpoint Protection 检测到恶意软件时，它将还原恶意软件可能已更改的以下系统设置和服务：</span><span class="sxs-lookup"><span data-stu-id="d5359-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="d5359-503">默认Internet Explorer或Microsoft Edge设置</span><span class="sxs-lookup"><span data-stu-id="d5359-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="d5359-504">用户访问控制设置</span><span class="sxs-lookup"><span data-stu-id="d5359-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="d5359-505">部件版式设置</span><span class="sxs-lookup"><span data-stu-id="d5359-505">Chrome settings</span></span></li>
<li><span data-ttu-id="d5359-506">启动控件数据</span><span class="sxs-lookup"><span data-stu-id="d5359-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="d5359-507">Regedit 和任务管理器注册表设置</span><span class="sxs-lookup"><span data-stu-id="d5359-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="d5359-508">Windows更新、后台智能传输服务和远程过程调用服务</span><span class="sxs-lookup"><span data-stu-id="d5359-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="d5359-509">Windows操作系统文件</span><span class="sxs-lookup"><span data-stu-id="d5359-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="d5359-510">上述上下文适用于以下客户端和服务器版本：</span><span class="sxs-lookup"><span data-stu-id="d5359-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="d5359-511">操作系统</span><span class="sxs-lookup"><span data-stu-id="d5359-511">Operating system</span></span></th>
<th><span data-ttu-id="d5359-512">操作系统版本</span><span class="sxs-lookup"><span data-stu-id="d5359-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-513">客户端操作系统</span><span class="sxs-lookup"><span data-stu-id="d5359-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="d5359-514">WindowsVista (Service Pack 1 或 Service Pack 2) 7 Windows更高版本</span><span class="sxs-lookup"><span data-stu-id="d5359-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-515">服务器操作系统</span><span class="sxs-lookup"><span data-stu-id="d5359-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="d5359-516">WindowsServer 2008、Windows Server 2008 R2、Windows Server 2012 和 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d5359-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-517">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-518">无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-518">No action is necessary.</span></span> <span data-ttu-id="d5359-519">Microsoft Defender 防病毒或隔离威胁。</span><span class="sxs-lookup"><span data-stu-id="d5359-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-520">事件 ID：1118</span><span class="sxs-lookup"><span data-stu-id="d5359-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-521">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-523">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-523">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-524">
<b>反恶意软件平台尝试执行保护系统免受恶意软件或其他可能不需要的软件的攻击，但操作失败。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-525">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-526">Microsoft Defender 防病毒恶意软件或其他可能不需要的软件时遇到非严重错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d5359-527">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-528">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-529">低</span><span class="sxs-lookup"><span data-stu-id="d5359-529">Low</span></span></li>
<li><span data-ttu-id="d5359-530">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-530">Moderate</span></span></li>
<li><span data-ttu-id="d5359-531">高</span><span class="sxs-lookup"><span data-stu-id="d5359-531">High</span></span></li>
<li><span data-ttu-id="d5359-532">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-532">Severe</span></span></li>
</ul><span data-ttu-id="d5359-533">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-534">未知</span><span class="sxs-lookup"><span data-stu-id="d5359-534">Unknown</span></span></li>
<li><span data-ttu-id="d5359-535">本地计算机</span><span class="sxs-lookup"><span data-stu-id="d5359-535">Local computer</span></span></li>
<li><span data-ttu-id="d5359-536">网络共享</span><span class="sxs-lookup"><span data-stu-id="d5359-536">Network share</span></span></li>
<li><span data-ttu-id="d5359-537">Internet</span><span class="sxs-lookup"><span data-stu-id="d5359-537">Internet</span></span></li>
<li><span data-ttu-id="d5359-538">传入流量</span><span class="sxs-lookup"><span data-stu-id="d5359-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="d5359-539">传出流量</span><span class="sxs-lookup"><span data-stu-id="d5359-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d5359-540">
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-541">启发式</span><span class="sxs-lookup"><span data-stu-id="d5359-541">Heuristics</span></span></li>
<li><span data-ttu-id="d5359-542">Generic</span><span class="sxs-lookup"><span data-stu-id="d5359-542">Generic</span></span></li>
<li><span data-ttu-id="d5359-543">具体</span><span class="sxs-lookup"><span data-stu-id="d5359-543">Concrete</span></span></li>
<li><span data-ttu-id="d5359-544">动态签名</span><span class="sxs-lookup"><span data-stu-id="d5359-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d5359-545">
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d5359-546">用户：用户启动</span><span class="sxs-lookup"><span data-stu-id="d5359-546">User: user initiated</span></span></li>
<li><span data-ttu-id="d5359-547">系统：系统已启动</span><span class="sxs-lookup"><span data-stu-id="d5359-547">System: system initiated</span></span></li>
<li><span data-ttu-id="d5359-548">实时：启动实时组件</span><span class="sxs-lookup"><span data-stu-id="d5359-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d5359-549">IOAV：IE 下载Outlook快速附件启动</span><span class="sxs-lookup"><span data-stu-id="d5359-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d5359-550">NIS：网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d5359-551">IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</span><span class="sxs-lookup"><span data-stu-id="d5359-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d5359-552">提前启动反恶意软件 (ELAM) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d5359-553">这包括启动序列检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d5359-554">远程证明</span><span class="sxs-lookup"><span data-stu-id="d5359-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="d5359-555">反恶意软件扫描接口 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d5359-556">主要用于保护 PS (VBS) 脚本，尽管也可由第三方调用。</span><span class="sxs-lookup"><span data-stu-id="d5359-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d5359-557">UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt> 
<dt> 操作中的进程： &lt; 操作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-558">清理：资源已清理</span><span class="sxs-lookup"><span data-stu-id="d5359-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d5359-559">隔离：已隔离资源</span><span class="sxs-lookup"><span data-stu-id="d5359-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d5359-560">删除：已删除资源</span><span class="sxs-lookup"><span data-stu-id="d5359-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d5359-561">允许：允许执行/存在资源</span><span class="sxs-lookup"><span data-stu-id="d5359-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d5359-562">用户定义：用户定义的操作，通常来自用户指定的操作列表</span><span class="sxs-lookup"><span data-stu-id="d5359-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d5359-563">无操作：无操作</span><span class="sxs-lookup"><span data-stu-id="d5359-563">No action: No action</span></span></li>
<li><span data-ttu-id="d5359-564">阻止：资源被阻止执行</span><span class="sxs-lookup"><span data-stu-id="d5359-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d5359-565">
</dt>
<dt>操作状态： &lt;其他操作的说明 &gt; 错误</dt>
<dt>代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-566">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-567">无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-567">No action is necessary.</span></span> <span data-ttu-id="d5359-568">Microsoft Defender 防病毒未能完成与恶意软件修正相关的任务。</span><span class="sxs-lookup"><span data-stu-id="d5359-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="d5359-569">这不是一个关键故障。</span><span class="sxs-lookup"><span data-stu-id="d5359-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-570">事件 ID：1119</span><span class="sxs-lookup"><span data-stu-id="d5359-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-571">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-573">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-573">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-574">
<b>反恶意软件平台在尝试对恶意软件或其他可能不需要的软件采取操作时遇到严重错误。事件消息中会提供更多详细信息。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-575">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-576">Microsoft Defender 防病毒恶意软件或其他可能不需要的软件时遇到严重错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d5359-577">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d5359-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="d5359-578">
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-579">低</span><span class="sxs-lookup"><span data-stu-id="d5359-579">Low</span></span></li>
<li><span data-ttu-id="d5359-580">适度</span><span class="sxs-lookup"><span data-stu-id="d5359-580">Moderate</span></span></li>
<li><span data-ttu-id="d5359-581">高</span><span class="sxs-lookup"><span data-stu-id="d5359-581">High</span></span></li>
<li><span data-ttu-id="d5359-582">严重</span><span class="sxs-lookup"><span data-stu-id="d5359-582">Severe</span></span></li>
</ul><span data-ttu-id="d5359-583">
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-584">未知</span><span class="sxs-lookup"><span data-stu-id="d5359-584">Unknown</span></span></li>
<li><span data-ttu-id="d5359-585">本地计算机</span><span class="sxs-lookup"><span data-stu-id="d5359-585">Local computer</span></span></li>
<li><span data-ttu-id="d5359-586">网络共享</span><span class="sxs-lookup"><span data-stu-id="d5359-586">Network share</span></span></li>
<li><span data-ttu-id="d5359-587">Internet</span><span class="sxs-lookup"><span data-stu-id="d5359-587">Internet</span></span></li>
<li><span data-ttu-id="d5359-588">传入流量</span><span class="sxs-lookup"><span data-stu-id="d5359-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="d5359-589">传出流量</span><span class="sxs-lookup"><span data-stu-id="d5359-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d5359-590">
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-591">启发式</span><span class="sxs-lookup"><span data-stu-id="d5359-591">Heuristics</span></span></li>
<li><span data-ttu-id="d5359-592">Generic</span><span class="sxs-lookup"><span data-stu-id="d5359-592">Generic</span></span></li>
<li><span data-ttu-id="d5359-593">具体</span><span class="sxs-lookup"><span data-stu-id="d5359-593">Concrete</span></span></li>
<li><span data-ttu-id="d5359-594">动态签名</span><span class="sxs-lookup"><span data-stu-id="d5359-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d5359-595">
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d5359-596">用户：用户启动</span><span class="sxs-lookup"><span data-stu-id="d5359-596">User: user initiated</span></span></li>
<li><span data-ttu-id="d5359-597">系统：系统已启动</span><span class="sxs-lookup"><span data-stu-id="d5359-597">System: system initiated</span></span></li>
<li><span data-ttu-id="d5359-598">实时：启动实时组件</span><span class="sxs-lookup"><span data-stu-id="d5359-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d5359-599">IOAV：IE 下载Outlook快速附件启动</span><span class="sxs-lookup"><span data-stu-id="d5359-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d5359-600">NIS：网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d5359-601">IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</span><span class="sxs-lookup"><span data-stu-id="d5359-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d5359-602">提前启动反恶意软件 (ELAM) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d5359-603">这包括启动序列检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d5359-604">远程证明</span><span class="sxs-lookup"><span data-stu-id="d5359-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="d5359-605">反恶意软件扫描接口 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="d5359-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d5359-606">主要用于保护 PS (VBS) 脚本，尽管也可由第三方调用。</span><span class="sxs-lookup"><span data-stu-id="d5359-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d5359-607">UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt> 
<dt> 操作中的进程： &lt; 操作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d5359-608">清理：资源已清理</span><span class="sxs-lookup"><span data-stu-id="d5359-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d5359-609">隔离：已隔离资源</span><span class="sxs-lookup"><span data-stu-id="d5359-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d5359-610">删除：已删除资源</span><span class="sxs-lookup"><span data-stu-id="d5359-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d5359-611">允许：允许执行/存在资源</span><span class="sxs-lookup"><span data-stu-id="d5359-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d5359-612">用户定义：用户定义的操作，通常来自用户指定的操作列表</span><span class="sxs-lookup"><span data-stu-id="d5359-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d5359-613">无操作：无操作</span><span class="sxs-lookup"><span data-stu-id="d5359-613">No action: No action</span></span></li>
<li><span data-ttu-id="d5359-614">阻止：资源被阻止执行</span><span class="sxs-lookup"><span data-stu-id="d5359-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d5359-615">
</dt>
<dt>操作状态： &lt;其他操作的说明 &gt; 错误</dt>
<dt>代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-616">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-617">由于Microsoft Defender 防病毒，客户端遇到了此错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="d5359-618">终结点可能不受保护。</span><span class="sxs-lookup"><span data-stu-id="d5359-618">The endpoint might not be protected.</span></span> <span data-ttu-id="d5359-619">查看错误描述，然后按照下面的相关 <b>用户操作</b> 步骤操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="d5359-620">Action</span><span class="sxs-lookup"><span data-stu-id="d5359-620">Action</span></span></th>
<th><span data-ttu-id="d5359-621">用户操作</span><span class="sxs-lookup"><span data-stu-id="d5359-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="d5359-622">
<b>删除</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="d5359-623">更新定义，然后验证删除是否成功。</span><span class="sxs-lookup"><span data-stu-id="d5359-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="d5359-624">
<b>Clean</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="d5359-625">更新定义，然后验证修正是否成功。</span><span class="sxs-lookup"><span data-stu-id="d5359-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="d5359-626">
<b>隔离</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="d5359-627">更新定义并验证用户是否有权访问必要的资源。</span><span class="sxs-lookup"><span data-stu-id="d5359-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="d5359-628">
<b>允许</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="d5359-629">验证用户是否有权访问必要的资源。</span><span class="sxs-lookup"><span data-stu-id="d5359-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="d5359-630">如果此事件仍然存在：</span><span class="sxs-lookup"><span data-stu-id="d5359-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="d5359-631">再次运行扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="d5359-632">如果以相同方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持</a>站点，在"搜索"框中输入错误编号<b></b>以查找错误代码。</span><span class="sxs-lookup"><span data-stu-id="d5359-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="d5359-633">与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系</span><span class="sxs-lookup"><span data-stu-id="d5359-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-634">事件 ID：1120</span><span class="sxs-lookup"><span data-stu-id="d5359-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-635">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-637">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-637">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-638">
<b>Microsoft Defender 防病毒威胁资源推断哈希值。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-639">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-640">Microsoft Defender 防病毒客户端正常运行。</span><span class="sxs-lookup"><span data-stu-id="d5359-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="d5359-641">
<dt>当前平台版本： &lt;当前平台版本 &gt; </dt>
<dt>威胁资源路径 &lt; ：路径 &gt; </dt>
<dt>哈希： &lt; 哈希 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="d5359-642"><b>注意：只有在设置了以下策略时，才能记录 <b>此事件：ThreatFileHashLogging 未签名</b>。</span><span class="sxs-lookup"><span data-stu-id="d5359-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-643">事件 ID：1150</span><span class="sxs-lookup"><span data-stu-id="d5359-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-644">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-646">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-646">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-647">
<b>如果反恶意软件平台向监控平台报告状态，则此事件指示反恶意软件平台正在运行且状态正常。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-648">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-649">Microsoft Defender 防病毒客户端正常运行。</span><span class="sxs-lookup"><span data-stu-id="d5359-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="d5359-650">
<dt>平台版本： &lt;当前平台版本 &gt; </dt>
<dt>签名版本 &lt; ：定义版本 &gt; </dt>引擎
<dt>版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-651">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-652">无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-652">No action is necessary.</span></span> <span data-ttu-id="d5359-653">客户端Microsoft Defender 防病毒状态正常。</span><span class="sxs-lookup"><span data-stu-id="d5359-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d5359-654">此事件每小时报告一次。</span><span class="sxs-lookup"><span data-stu-id="d5359-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="d5359-655">事件 ID：1151</span><span class="sxs-lookup"><span data-stu-id="d5359-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-656">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-658">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-658">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-659">
<b>Endpoint Protection客户端运行状况报告 (UTC 时间) </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-660">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-661">防病毒客户端运行状况报告。</span><span class="sxs-lookup"><span data-stu-id="d5359-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="d5359-662">
<dt>平台版本： &lt;当前 &gt; 平台</dt>版本 引擎
<dt>版本 &lt; ：反恶意软件引擎 版本 &gt; </dt>网络实时检查引擎版本：
<dt> &lt; 网络实时 &gt; </dt>检查引擎版本 防病毒
<dt>签名版本： &lt; 防病毒 &gt; </dt>签名版本 反
<dt>间谍软件签名版本： &lt; 反间谍软件签名版本 &gt; </dt>网络实时检查
<dt>签名版本： &lt; 网络实时检查签名 版本 &gt; </dt>RTP 状态：实时保护状态 (
<dt> &lt; &gt; 已启用或</dt>已禁用) 
<dt>OA 状态：访问状态 (启用或禁用 &lt; &gt;) </dt> 
<dt>IOAV 状态 &lt; ：IE 下载和 Outlook 快速附件状态 (启用或禁用 &gt;) </dt>BM 状态：行为监视状态 (
<dt> &lt; &gt; 已启用或</dt>已禁用) 防病毒签名年龄：防病毒签名年龄 (天
<dt> &lt; &gt;) </dt>反间谍软件签名时间
<dt>： &lt; 反spyware signature age (days &gt;) </dt>Last quick scan 
<dt>age： Last quick scan age (in days &lt; &gt;) </dt>Last full scan 
<dt>age： Last full scan age (in days &lt; &gt;) </dt> 
<dt>Antivirus signature creation time: ?&lt;防病毒签名创建时间 &gt; </dt>
<dt>反间谍软件签名创建时间：？ &lt;反间谍软件签名创建时间 上次 &gt; </dt>
<dt>快速扫描开始时间：？ &lt;上次快速扫描开始时间 &gt; 上次</dt>
<dt>快速扫描结束时间：？ &lt;上次快速 &gt; </dt>扫描结束时间 上次快速扫描源：上次快速扫描源 (0 = 扫描未
<dt> &lt; &gt;&#39;，1 = 用户启动，2 =</dt>系统启动) 上次完全扫描
<dt>开始时间：？ &lt;上次完全扫描开始时间 &gt; 上次</dt>
<dt>完全扫描结束时间：？ &lt;上次完全 &gt; </dt>扫描结束时间 上次完全扫描源：上次完全扫描源 (0 = 扫描未运行
<dt> &lt; &gt;&#39;，1 = 用户启动，2 =</dt>系统启动) 
<dt> 产品状态：针对内部疑难解答</span><span class="sxs-lookup"><span data-stu-id="d5359-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="d5359-663">
<th colspan="2">事件 ID：2000</span><span class="sxs-lookup"><span data-stu-id="d5359-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-664">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-666">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-666">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-667">
<b>反恶意软件定义已成功更新。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-668">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-669">防病毒签名版本已更新。</span><span class="sxs-lookup"><span data-stu-id="d5359-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="d5359-670">
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt>
<dt>上一个签名版本 &lt; ： &gt; 上一个签名版本</dt>签名 
<dt> 类型 &lt; ：签名 &gt; 类型，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d5359-671">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-671">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-672">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-672">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-673">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-673">Antimalware</span></span></li>
<li><span data-ttu-id="d5359-674">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-675">
</dt>
<dt>更新类型： &lt;更新类型 &gt; ，Full 或 Delta。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎版本 &gt; </dt>
<dt>上一个引擎 &lt; 版本： &gt; 上一个引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-676">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-677">无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-677">No action is necessary.</span></span> <span data-ttu-id="d5359-678">客户端Microsoft Defender 防病毒状态正常。</span><span class="sxs-lookup"><span data-stu-id="d5359-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d5359-679">当签名成功更新时，将报告此事件。</span><span class="sxs-lookup"><span data-stu-id="d5359-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-680">事件 ID：2001</span><span class="sxs-lookup"><span data-stu-id="d5359-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-681">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-683">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-683">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-684">
<b>安全智能更新失败。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-685">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-686">Microsoft Defender 防病毒尝试更新签名时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="d5359-687">
<dt>新的安全智能版本： &lt;新版本编号 &gt; </dt>
<dt>以前的安全智能版本： &lt; 上一 &gt; 版本</dt> 
<dt> 更新源 &lt; ：更新 &gt; 源，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-688">安全智能更新文件夹</span><span class="sxs-lookup"><span data-stu-id="d5359-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="d5359-689">内部安全智能更新服务器</span><span class="sxs-lookup"><span data-stu-id="d5359-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="d5359-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="d5359-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="d5359-691">文件共享</span><span class="sxs-lookup"><span data-stu-id="d5359-691">File share</span></span></li>
<li><span data-ttu-id="d5359-692">Microsoft 恶意软件防护中心 (MMPC) </span><span class="sxs-lookup"><span data-stu-id="d5359-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="d5359-693">
</dt>
<dt>更新阶段 &lt; ：更新阶段 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-694">搜索</span><span class="sxs-lookup"><span data-stu-id="d5359-694">Search</span></span></li>
<li><span data-ttu-id="d5359-695">下载</span><span class="sxs-lookup"><span data-stu-id="d5359-695">Download</span></span></li>
<li><span data-ttu-id="d5359-696">安装</span><span class="sxs-lookup"><span data-stu-id="d5359-696">Install</span></span></li>
</ul><span data-ttu-id="d5359-697">
</dt>
<dt>源路径：通用命名约定的文件共享名称 (UNC) 、Windows Server Update Services (WSUS) /Microsoft Update/ADL 的服务器名称。</dt> 
<dt>签名类型 &lt; ：签名类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d5359-698">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-698">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-699">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-699">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-700">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-700">Antimalware</span></span></li>
<li><span data-ttu-id="d5359-701">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-702">
</dt>
<dt>更新类型： &lt;更新类型 &gt; ，Full 或 Delta。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎版本 &gt; </dt>上一个引擎版本
<dt>： &lt; 上 &gt; </dt>一个引擎版本
<dt>错误代码： &lt; 错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-703">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-704">当更新定义时出现问题时，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="d5359-705">若要对此事件进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="d5359-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d5359-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定义</a> 并强制直接在终结点上重新扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="d5359-707">有关此错误的详细信息，请查看 %Windir%\WindowsUpdate.日志文件中的条目。</span><span class="sxs-lookup"><span data-stu-id="d5359-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="d5359-708">与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系</span><span class="sxs-lookup"><span data-stu-id="d5359-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-709">事件 ID：2002</span><span class="sxs-lookup"><span data-stu-id="d5359-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-710">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-712">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-712">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-713">
<b>反恶意软件引擎已成功更新。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-714">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-715">Microsoft Defender 防病毒引擎版本已更新。</span><span class="sxs-lookup"><span data-stu-id="d5359-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="d5359-716">
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt>上一个引擎版本：
<dt> &lt; &gt; 以前的</dt>引擎版本 引擎
<dt>类型：引擎类型 ，反 &lt; &gt; 恶意软件引擎或网络检查系统引擎。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-717">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-718">无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-718">No action is necessary.</span></span> <span data-ttu-id="d5359-719">客户端Microsoft Defender 防病毒状态正常。</span><span class="sxs-lookup"><span data-stu-id="d5359-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d5359-720">当反恶意软件引擎成功更新时，将报告此事件。</span><span class="sxs-lookup"><span data-stu-id="d5359-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-721">事件 ID：2003</span><span class="sxs-lookup"><span data-stu-id="d5359-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-722">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-724">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-724">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-725">
<b>反恶意软件引擎更新失败。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-726">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-727">Microsoft Defender 防病毒尝试更新引擎时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="d5359-728">
<dt>新引擎版本：</dt>
<dt>以前的引擎版本： &lt; &gt; 以前的</dt>引擎版本 引擎类型：引擎类型 ，反
<dt> &lt; &gt; 恶意软件引擎或网络检查系统引擎。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-729">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-730">客户端Microsoft Defender 防病毒失败。</span><span class="sxs-lookup"><span data-stu-id="d5359-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="d5359-731">当客户端无法更新自身时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="d5359-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="d5359-732">此事件通常是由于更新期间网络连接中断引起的。</span><span class="sxs-lookup"><span data-stu-id="d5359-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="d5359-733">若要对此事件进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="d5359-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d5359-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定义</a> 并强制直接在终结点上重新扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="d5359-735">与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系</span><span class="sxs-lookup"><span data-stu-id="d5359-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-736">事件 ID：2004</span><span class="sxs-lookup"><span data-stu-id="d5359-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-737">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-739">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-739">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-740">
<b>加载反恶意软件定义时出现问题。反恶意软件引擎将尝试加载上一个已知良好的定义集。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-741">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-742">Microsoft Defender 防病毒尝试加载签名时遇到错误，并且将尝试还原回已知良好的签名集。</span><span class="sxs-lookup"><span data-stu-id="d5359-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="d5359-743">
<dt>尝试签名：</dt>
<dt>错误代码 &lt; ：错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-744">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-745">客户端Microsoft Defender 防病毒下载并安装最新的定义文件，但失败。</span><span class="sxs-lookup"><span data-stu-id="d5359-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="d5359-746">当客户端在尝试加载定义时遇到错误，或者文件已损坏时，可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="d5359-747">Microsoft Defender 防病毒将尝试还原到已知良好的定义集。</span><span class="sxs-lookup"><span data-stu-id="d5359-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="d5359-748">若要对此事件进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="d5359-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d5359-749">重新启动计算机并重试。</span><span class="sxs-lookup"><span data-stu-id="d5359-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="d5359-750">从网站 下载Microsoft 安全智能<a href="https://aka.ms/wdsi">定义</a>。</span><span class="sxs-lookup"><span data-stu-id="d5359-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="d5359-751">注意：从网站下载的定义文件的大小可能超过 60 MB，不应用作更新定义的长期解决方案。</span><span class="sxs-lookup"><span data-stu-id="d5359-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="d5359-752">与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系</span><span class="sxs-lookup"><span data-stu-id="d5359-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-753">事件 ID：2005</span><span class="sxs-lookup"><span data-stu-id="d5359-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-754">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-756">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-756">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-757">
<b>反恶意软件引擎加载失败，因为反恶意软件平台已过期。反恶意软件平台将加载已知良好的反恶意软件引擎并尝试更新。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-758">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-759">Microsoft Defender 防病毒无法加载反恶意软件引擎，因为当前平台版本不受支持。</span><span class="sxs-lookup"><span data-stu-id="d5359-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="d5359-760">Microsoft Defender 防病毒将还原到上一个已知良好的引擎，并尝试进行平台更新。</span><span class="sxs-lookup"><span data-stu-id="d5359-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="d5359-761">
<dt>当前平台版本： &lt; 当前平台版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-762">事件 ID：2006</span><span class="sxs-lookup"><span data-stu-id="d5359-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-763">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-765">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-765">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-766">
<b>平台更新失败。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-767">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-768">Microsoft Defender 防病毒尝试更新平台时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="d5359-769">
<dt>当前平台版本： &lt;当前平台版本 &gt; </dt>
<dt>错误代码 &lt; ：错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-770">事件 ID：2007</span><span class="sxs-lookup"><span data-stu-id="d5359-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-771">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-773">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-773">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-774">
<b>该平台即将过期。下载最新的平台以保持最新的保护。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-775">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-776">Microsoft Defender 防病毒需要更新的平台版本来支持反恶意软件引擎的未来版本。</span><span class="sxs-lookup"><span data-stu-id="d5359-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="d5359-777">下载最新的 Microsoft Defender 防病毒 平台以保持可用的最佳保护级别。</span><span class="sxs-lookup"><span data-stu-id="d5359-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="d5359-778">
<dt>当前平台版本： &lt; 当前平台版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-779">事件 ID：2010</span><span class="sxs-lookup"><span data-stu-id="d5359-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-780">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-782">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-782">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-783">
<b>反恶意软件引擎使用动态签名服务获取其他定义。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-784">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-785">Microsoft Defender 防病毒动态<i>签名服务</i>检索其他签名以帮助保护你的计算机。</span><span class="sxs-lookup"><span data-stu-id="d5359-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="d5359-786">
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt> 
<dt> 签名类型： &lt; 签名 &gt; 类型 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d5359-787">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-787">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-788">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-788">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-789">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-789">Antimalware</span></span></li>
<li><span data-ttu-id="d5359-790">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-791">
</dt>
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt> 
<dt> 动态签名类型 &lt; ：动态签名 &gt; 类型 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-792">版本</span><span class="sxs-lookup"><span data-stu-id="d5359-792">Version</span></span></li>
<li><span data-ttu-id="d5359-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d5359-793">Timestamp</span></span></li>
<li><span data-ttu-id="d5359-794">无限制</span><span class="sxs-lookup"><span data-stu-id="d5359-794">No limit</span></span></li>
<li><span data-ttu-id="d5359-795">期限</span><span class="sxs-lookup"><span data-stu-id="d5359-795">Duration</span></span></li>
</ul><span data-ttu-id="d5359-796">
</dt>
<dt>持久性路径： &lt;路径 &gt; </dt>
<dt>动态签名版本 &lt; ： &gt; 版本号</dt>动态签名编译时间戳：
<dt> &lt; 时间戳 &gt; </dt> 
<dt> 持久性限制类型： &lt; 持久性限制 &gt; 类型，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-797">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="d5359-797">VDM version</span></span></li>
<li><span data-ttu-id="d5359-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d5359-798">Timestamp</span></span></li>
<li><span data-ttu-id="d5359-799">无限制</span><span class="sxs-lookup"><span data-stu-id="d5359-799">No limit</span></span></li>
</ul><span data-ttu-id="d5359-800">
</dt>
<dt>持久性限制：fastpath 签名的持久性限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-801">事件 ID：2011</span><span class="sxs-lookup"><span data-stu-id="d5359-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-802">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-804">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-804">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-805">
<b>动态签名服务删除了过期的动态定义。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-806">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-807">Microsoft Defender 防病毒动态<i>签名服务丢弃</i>过时的签名。</span><span class="sxs-lookup"><span data-stu-id="d5359-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="d5359-808">
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt> 
<dt> 签名类型： &lt; 签名 &gt; 类型 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d5359-809">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-809">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-810">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-810">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-811">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-811">Antimalware</span></span></li>
<li><span data-ttu-id="d5359-812">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-813">
</dt>
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt> 
<dt> 动态签名类型 &lt; ：动态签名 &gt; 类型 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-814">版本</span><span class="sxs-lookup"><span data-stu-id="d5359-814">Version</span></span></li>
<li><span data-ttu-id="d5359-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d5359-815">Timestamp</span></span></li>
<li><span data-ttu-id="d5359-816">无限制</span><span class="sxs-lookup"><span data-stu-id="d5359-816">No limit</span></span></li>
<li><span data-ttu-id="d5359-817">期限</span><span class="sxs-lookup"><span data-stu-id="d5359-817">Duration</span></span></li>
</ul><span data-ttu-id="d5359-818">
</dt>
<dt>持久性路径： &lt;路径 &gt; </dt>
<dt>动态签名版本： &lt; 版本号 &gt; </dt>动态签名
<dt>编译 &lt; &gt; </dt>时间戳：时间戳删除
<dt>原因：</dt> 
<dt> 持久性限制类型： &lt; 持久性限制 &gt; 类型，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-819">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="d5359-819">VDM version</span></span></li>
<li><span data-ttu-id="d5359-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d5359-820">Timestamp</span></span></li>
<li><span data-ttu-id="d5359-821">无限制</span><span class="sxs-lookup"><span data-stu-id="d5359-821">No limit</span></span></li>
</ul><span data-ttu-id="d5359-822">
</dt>
<dt>持久性限制：fastpath 签名的持久性限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-823">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-824">无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="d5359-824">No action is necessary.</span></span> <span data-ttu-id="d5359-825">客户端Microsoft Defender 防病毒状态正常。</span><span class="sxs-lookup"><span data-stu-id="d5359-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d5359-826">当动态签名服务成功删除过期的动态定义时，将报告此事件。</span><span class="sxs-lookup"><span data-stu-id="d5359-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-827">事件 ID：2012</span><span class="sxs-lookup"><span data-stu-id="d5359-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-828">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-830">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-830">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-831">
<b>反恶意软件引擎在尝试使用动态签名服务时遇到错误。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-832">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-833">Microsoft Defender 防病毒尝试使用动态签名服务<i>时遇到错误</i>。</span><span class="sxs-lookup"><span data-stu-id="d5359-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="d5359-834">
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt> 
<dt> 签名类型： &lt; 签名 &gt; 类型 ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d5359-835">防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-835">Antivirus</span></span></li>
<li><span data-ttu-id="d5359-836">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="d5359-836">Antispyware</span></span></li>
<li><span data-ttu-id="d5359-837">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="d5359-837">Antimalware</span></span></li>
<li><span data-ttu-id="d5359-838">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-839">
</dt>
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt>
<dt>错误代码 &lt; ：错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt> 
<dt>动态签名类型： &lt; 动态签名类型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-840">版本</span><span class="sxs-lookup"><span data-stu-id="d5359-840">Version</span></span></li>
<li><span data-ttu-id="d5359-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d5359-841">Timestamp</span></span></li>
<li><span data-ttu-id="d5359-842">无限制</span><span class="sxs-lookup"><span data-stu-id="d5359-842">No limit</span></span></li>
<li><span data-ttu-id="d5359-843">期限</span><span class="sxs-lookup"><span data-stu-id="d5359-843">Duration</span></span></li>
</ul><span data-ttu-id="d5359-844">
</dt>
<dt>持久性路径： &lt;路径 &gt; </dt>
<dt>动态签名版本 &lt; ： &gt; 版本号</dt>动态签名编译时间戳：
<dt> &lt; 时间戳 &gt; </dt> 
<dt> 持久性限制类型： &lt; 持久性限制 &gt; 类型，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-845">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="d5359-845">VDM version</span></span></li>
<li><span data-ttu-id="d5359-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d5359-846">Timestamp</span></span></li>
<li><span data-ttu-id="d5359-847">无限制</span><span class="sxs-lookup"><span data-stu-id="d5359-847">No limit</span></span></li>
</ul><span data-ttu-id="d5359-848">
</dt>
<dt>持久性限制：fastpath 签名的持久性限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-849">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-850">检查 Internet 连接设置。</span><span class="sxs-lookup"><span data-stu-id="d5359-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-851">事件 ID：2013</span><span class="sxs-lookup"><span data-stu-id="d5359-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-852">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-854">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-854">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-855">
<b>动态签名服务删除了所有动态定义。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-856">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-857">Microsoft Defender 防病毒丢弃所有<i>动态签名服务</i>签名。</span><span class="sxs-lookup"><span data-stu-id="d5359-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="d5359-858">
<dt>当前签名版本： &lt; 当前签名版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-859">事件 ID：2020</span><span class="sxs-lookup"><span data-stu-id="d5359-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-860">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-862">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-862">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-863">
<b>反恶意软件引擎下载了一个干净文件。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-864">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-865">Microsoft Defender 防病毒下载了一个干净文件。</span><span class="sxs-lookup"><span data-stu-id="d5359-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="d5359-866">
<dt>文件名： &lt;文件名 &gt; 文件的名称。</dt>
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-867">事件 ID：2021</span><span class="sxs-lookup"><span data-stu-id="d5359-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-868">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-870">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-870">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-871">
<b>反恶意软件引擎无法下载干净文件。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-872">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-873">Microsoft Defender 防病毒尝试下载干净文件时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="d5359-874">
<dt>文件名： &lt;文件名 &gt; 文件的名称。</dt>
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎 &gt; 版本</dt>
<dt>错误代码： &lt; 错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-875">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-876">检查 Internet 连接设置。</span><span class="sxs-lookup"><span data-stu-id="d5359-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="d5359-877">使用Microsoft Defender 防病毒签名服务将最新定义下载到特定威胁时，客户端遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="d5359-878">此错误可能是由网络连接问题导致的。</span><span class="sxs-lookup"><span data-stu-id="d5359-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-879">事件 ID：2030</span><span class="sxs-lookup"><span data-stu-id="d5359-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-880">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-882">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-882">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-883">
<b>反恶意软件引擎已下载，并配置为在下次系统重启时脱机运行。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-884">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-885">Microsoft Defender 防病毒下载并配置脱机防病毒，以在下次重新启动时运行。</span><span class="sxs-lookup"><span data-stu-id="d5359-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-886">事件 ID：2031</span><span class="sxs-lookup"><span data-stu-id="d5359-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-887">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-889">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-889">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-890">
<b>反恶意软件引擎无法下载和配置脱机扫描。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-891">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-892">Microsoft Defender 防病毒尝试下载和配置脱机防病毒时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="d5359-893">
<dt>错误代码： &lt;错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-894">事件 ID：2040</span><span class="sxs-lookup"><span data-stu-id="d5359-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-895">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-897">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-897">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-898">
<b>此操作系统版本的反恶意软件支持即将结束。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-899">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-900">对操作系统的支持即将过期。</span><span class="sxs-lookup"><span data-stu-id="d5359-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="d5359-901">在Microsoft Defender 防病毒操作系统上运行非支持操作系统不是防止威胁的足够解决方案。</span><span class="sxs-lookup"><span data-stu-id="d5359-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-902">事件 ID：2041</span><span class="sxs-lookup"><span data-stu-id="d5359-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-903">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-905">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-905">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-906">
<b>此操作系统的反恶意软件支持已终止。必须升级操作系统，获得持续支持。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-907">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-908">对操作系统的支持已过期。</span><span class="sxs-lookup"><span data-stu-id="d5359-908">The support for your operating system has expired.</span></span> <span data-ttu-id="d5359-909">在Microsoft Defender 防病毒操作系统上运行非支持操作系统不是防止威胁的足够解决方案。</span><span class="sxs-lookup"><span data-stu-id="d5359-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-910">事件 ID：2042</span><span class="sxs-lookup"><span data-stu-id="d5359-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-911">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-913">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-913">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-914">
<b>反恶意软件引擎不再支持此操作系统，并且不再保护系统免受恶意软件的攻击。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-915">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-916">对操作系统的支持已过期。</span><span class="sxs-lookup"><span data-stu-id="d5359-916">The support for your operating system has expired.</span></span> <span data-ttu-id="d5359-917">Microsoft Defender 防病毒操作系统上不再支持，已停止运行，并且无法抵御恶意软件威胁。</span><span class="sxs-lookup"><span data-stu-id="d5359-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-918">事件 ID：3002</span><span class="sxs-lookup"><span data-stu-id="d5359-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-919">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-921">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-921">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-922">
<b>实时保护遇到错误并失败。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-923">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-924">Microsoft Defender 防病毒 Real-Time保护功能遇到错误并失败。</span><span class="sxs-lookup"><span data-stu-id="d5359-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="d5359-925">
<dt>功能 &lt; ：功能 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-926">On Access</span><span class="sxs-lookup"><span data-stu-id="d5359-926">On Access</span></span></li>
<li><span data-ttu-id="d5359-927">Internet Explorer下载和 Microsoft Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="d5359-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="d5359-928">行为监视</span><span class="sxs-lookup"><span data-stu-id="d5359-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="d5359-929">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-930">
</dt>
<dt>错误代码： &lt;错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>原因：Microsoft Defender 防病毒保护已重启功能的原因。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-931">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-932">应重新启动系统，然后运行完全扫描，&#39;系统可能一段时间未受保护。</span><span class="sxs-lookup"><span data-stu-id="d5359-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="d5359-933">Microsoft Defender 防病毒客户端&#39;实时保护功能遇到错误，因为其中一个服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="d5359-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="d5359-934">如果后跟 3007 事件 ID，则失败是临时性的，并且反恶意软件客户端从故障中恢复。</span><span class="sxs-lookup"><span data-stu-id="d5359-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-935">事件 ID：3007</span><span class="sxs-lookup"><span data-stu-id="d5359-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-936">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-938">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-938">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-939">
<b>从故障中恢复实时保护。当看到此错误时，我们建议运行完整系统扫描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-940">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-941">Microsoft Defender 防病毒实时保护已重新启动功能。</span><span class="sxs-lookup"><span data-stu-id="d5359-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="d5359-942">建议运行完整系统扫描，以检测此代理关闭时可能错过的任何项目。</span><span class="sxs-lookup"><span data-stu-id="d5359-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="d5359-943">
<dt>功能 &lt; ：功能 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-944">On Access</span><span class="sxs-lookup"><span data-stu-id="d5359-944">On Access</span></span></li>
<li><span data-ttu-id="d5359-945">IE 下载和Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="d5359-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="d5359-946">行为监视</span><span class="sxs-lookup"><span data-stu-id="d5359-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="d5359-947">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-948">
</dt>
<dt>原因：Microsoft Defender 防病毒保护已重启功能的原因。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-949">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-950">实时保护功能已重新启动。</span><span class="sxs-lookup"><span data-stu-id="d5359-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="d5359-951">如果再次发生此事件，请联系 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持</a>。</span><span class="sxs-lookup"><span data-stu-id="d5359-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-952">事件 ID：5000</span><span class="sxs-lookup"><span data-stu-id="d5359-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-953">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-955">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-955">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-956">
<b>实时保护已启用。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-957">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-958">Microsoft Defender 防病毒恶意软件和其他可能不需要的软件进行实时保护扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-959">事件 ID：5001</span><span class="sxs-lookup"><span data-stu-id="d5359-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-960">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-962">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-962">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-963">
<b>实时保护处于禁用状态。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-964">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-965">Microsoft Defender 防病毒恶意软件和其他可能不需要的软件进行实时保护扫描已禁用。</span><span class="sxs-lookup"><span data-stu-id="d5359-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-966">事件 ID：5004</span><span class="sxs-lookup"><span data-stu-id="d5359-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-967">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-969">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-969">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-970">
<b>实时保护配置已更改。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-971">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-972">Microsoft Defender 防病毒实时保护功能配置已更改。</span><span class="sxs-lookup"><span data-stu-id="d5359-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="d5359-973">
<dt>功能 &lt; ：功能 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="d5359-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d5359-974">On Access</span><span class="sxs-lookup"><span data-stu-id="d5359-974">On Access</span></span></li>
<li><span data-ttu-id="d5359-975">IE 下载和Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="d5359-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="d5359-976">行为监视</span><span class="sxs-lookup"><span data-stu-id="d5359-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="d5359-977">网络检查系统</span><span class="sxs-lookup"><span data-stu-id="d5359-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d5359-978">
</dt>
<dt>配置： </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-979">事件 ID：5007</span><span class="sxs-lookup"><span data-stu-id="d5359-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-980">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-982">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-982">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-983">
<b>反恶意软件平台配置已更改。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-984">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-985">Microsoft Defender 防病毒已更改。</span><span class="sxs-lookup"><span data-stu-id="d5359-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="d5359-986">如果这是意外事件，应查看设置，因为这可能是恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="d5359-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="d5359-987">
<dt>旧值： &lt;旧值编号 &gt; 旧的防病毒配置值。</dt>
<dt>新值： &lt;新值编号 &gt; 新的防病毒配置值。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-988">事件 ID：5008</span><span class="sxs-lookup"><span data-stu-id="d5359-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-989">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-991">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-991">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-992">
<b>反恶意软件引擎遇到错误并失败。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-993">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-994">Microsoft Defender 防病毒引擎由于意外错误而终止。</span><span class="sxs-lookup"><span data-stu-id="d5359-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="d5359-995">
<dt>失败类型： &lt;失败类型 &gt; ，例如：崩溃或挂起</dt>
<dt>异常代码 &lt; ：错误代码 &gt; </dt>
<dt>资源： &lt; 资源 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-996">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-997">若要对此事件进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="d5359-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="d5359-998">尝试重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="d5359-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="d5359-999">对于反恶意软件、防病毒和间谍软件，在提升的命令提示符下，键入 <b>net stop msmpsvc</b>，然后键入 <b>net start msmpsvc</b> 以重新启动反恶意软件引擎。</span><span class="sxs-lookup"><span data-stu-id="d5359-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="d5359-1000">对于<i>网络检查系统</i>，在提升的命令提示符下，键入<b>net start nissrv</b>，然后键入<b>net start nissrv</b>以使用 NiSSRV.exe 文件重新启动网络检查系统引擎。 <i></i></span><span class="sxs-lookup"><span data-stu-id="d5359-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="d5359-1001">如果以相同方式失败，请通过访问<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>支持站点，在"搜索"框中输入错误号来查找错误代码<b></b>，然后联系<a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持</a>。</span><span class="sxs-lookup"><span data-stu-id="d5359-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1002">用户操作：</span><span class="sxs-lookup"><span data-stu-id="d5359-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="d5359-1003">由于Microsoft Defender 防病毒错误，客户端引擎停止运行。</span><span class="sxs-lookup"><span data-stu-id="d5359-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="d5359-1004">若要对此事件进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="d5359-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d5359-1005">再次运行扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="d5359-1006">如果以相同方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持</a>站点，在"搜索"框中输入错误编号<b></b>以查找错误代码。</span><span class="sxs-lookup"><span data-stu-id="d5359-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="d5359-1007">与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系</span><span class="sxs-lookup"><span data-stu-id="d5359-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1008">事件 ID：5009</span><span class="sxs-lookup"><span data-stu-id="d5359-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-1009">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1011">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-1012">
<b>扫描恶意软件和其他可能不需要的软件已启用。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1013">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-1014">Microsoft Defender 防病毒恶意软件和其他可能不需要的软件扫描已启用。</span><span class="sxs-lookup"><span data-stu-id="d5359-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1015">事件 ID：5010</span><span class="sxs-lookup"><span data-stu-id="d5359-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-1016">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1018">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-1019">
<b>扫描恶意软件和其他可能不需要的软件处于禁用状态。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1020">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-1021">Microsoft Defender 防病毒恶意软件和其他可能不需要的软件扫描已禁用。</span><span class="sxs-lookup"><span data-stu-id="d5359-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1022">事件 ID：5011</span><span class="sxs-lookup"><span data-stu-id="d5359-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-1023">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1025">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-1026">
<b>扫描病毒已启用。</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1027">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-1028">Microsoft Defender 防病毒病毒扫描已启用。</span><span class="sxs-lookup"><span data-stu-id="d5359-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1029">事件 ID：5012</span><span class="sxs-lookup"><span data-stu-id="d5359-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-1030">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1032">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-1033">
<b>扫描病毒已禁用。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1034">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-1035">Microsoft Defender 防病毒病毒扫描处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d5359-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1036">事件 ID：5100</span><span class="sxs-lookup"><span data-stu-id="d5359-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-1037">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1039">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-1040">
<b>反恶意软件平台即将过期。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1041">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-1042">Microsoft Defender 防病毒已进入宽限期并且即将到期。</span><span class="sxs-lookup"><span data-stu-id="d5359-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="d5359-1043">过期后，此计划将禁用对病毒、间谍软件和其他可能不需要的软件的保护。</span><span class="sxs-lookup"><span data-stu-id="d5359-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="d5359-1044">
<dt>过期原因：Microsoft Defender 防病毒过期的原因。</dt>
<dt>到期日期：Microsoft Defender 防病毒到期日期。</dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1045">事件 ID：5101</span><span class="sxs-lookup"><span data-stu-id="d5359-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d5359-1046">符号名称：</span><span class="sxs-lookup"><span data-stu-id="d5359-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d5359-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1048">消息：</span><span class="sxs-lookup"><span data-stu-id="d5359-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="d5359-1049">
<b>反恶意软件平台已过期。 </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1050">说明:</span><span class="sxs-lookup"><span data-stu-id="d5359-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="d5359-1051">Microsoft Defender 防病毒宽限期已过期。</span><span class="sxs-lookup"><span data-stu-id="d5359-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="d5359-1052">对病毒、间谍软件和其他可能不需要的软件的保护处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d5359-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="d5359-1053">
<dt>过期原因：</dt>
<dt>到期日期： </dt>
<dt>错误代码： &lt; 错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="d5359-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender 防病毒客户端错误代码 如果Microsoft Defender 防病毒遇到任何问题，它通常会提供一个错误代码来帮助你解决问题。</span><span class="sxs-lookup"><span data-stu-id="d5359-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="d5359-1055">最常见的错误意味着安装更新时出现问题。</span><span class="sxs-lookup"><span data-stu-id="d5359-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="d5359-1056">本节提供有关客户端错误的Microsoft Defender 防病毒信息。</span><span class="sxs-lookup"><span data-stu-id="d5359-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="d5359-1057">-   错误代码 -   有关现在要执行哪些操作的建议 -   错误的可能原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="d5359-1058">使用这些表中的信息帮助排查错误Microsoft Defender 防病毒错误代码。</span><span class="sxs-lookup"><span data-stu-id="d5359-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="d5359-1059">错误代码：0x80508007</span><span class="sxs-lookup"><span data-stu-id="d5359-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="d5359-1060">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1060">Message</span></span></td>
<td><span data-ttu-id="d5359-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1062">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="d5359-1063">此错误指示您可能内存不足。</span><span class="sxs-lookup"><span data-stu-id="d5359-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="d5359-1064">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="d5359-1065">检查设备上可用的内存。</span><span class="sxs-lookup"><span data-stu-id="d5359-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="d5359-1066">关闭运行以释放设备上内存的任何未使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5359-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="d5359-1067">重新启动设备并再次运行扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1068">错误代码：0x8050800C</span><span class="sxs-lookup"><span data-stu-id="d5359-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="d5359-1069">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1069">Message</span></span></td>
<td><span data-ttu-id="d5359-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1071">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1072">此错误指示安全产品可能有问题。</span><span class="sxs-lookup"><span data-stu-id="d5359-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="d5359-1073">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="d5359-1074">更新定义。</span><span class="sxs-lookup"><span data-stu-id="d5359-1074">Update the definitions.</span></span> <span data-ttu-id="d5359-1075">任一：</span><span class="sxs-lookup"><span data-stu-id="d5359-1075">Either:</span></span><ol>
<li><span data-ttu-id="d5359-1076">单击"<b>更新"</b>选项卡上的"更新<b></b>定义"Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="d5359-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="d5359-1077">或者，</span><span class="sxs-lookup"><span data-stu-id="d5359-1077">Or,</span></span>
</li>
<li><span data-ttu-id="d5359-1078">从网站 下载Microsoft 安全智能<a href="https://aka.ms/wdsi">定义</a>。</span><span class="sxs-lookup"><span data-stu-id="d5359-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="d5359-1079">注意：从网站下载的定义文件的大小可能超过 60 MB，不应用作更新定义的长期解决方案。</span><span class="sxs-lookup"><span data-stu-id="d5359-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="d5359-1080">运行完整扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="d5359-1081">重新启动设备并重试。</span><span class="sxs-lookup"><span data-stu-id="d5359-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1082">错误代码：0x80508020</span><span class="sxs-lookup"><span data-stu-id="d5359-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="d5359-1083">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1083">Message</span></span></td>
<td><span data-ttu-id="d5359-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1085">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1086">此错误指示可能有引擎配置错误;通常，这与不允许引擎正常运行的输入数据相关。</span><span class="sxs-lookup"><span data-stu-id="d5359-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1087">错误代码：0x805080211</span><span class="sxs-lookup"><span data-stu-id="d5359-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1088">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1088">Message</span></span></td>
<td><span data-ttu-id="d5359-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1090">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1091">此错误指示无法Microsoft Defender 防病毒威胁。</span><span class="sxs-lookup"><span data-stu-id="d5359-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1092">错误代码：0x80508022</span><span class="sxs-lookup"><span data-stu-id="d5359-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1093">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1093">Message</span></span></td>
<td><span data-ttu-id="d5359-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1095">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1096">此错误指示需要重新启动才能完成威胁删除。</span><span class="sxs-lookup"><span data-stu-id="d5359-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="d5359-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="d5359-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1098">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1098">Message</span></span></td>
<td><span data-ttu-id="d5359-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1100">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1101">此错误指示威胁可能不再存在于媒体上，或者恶意软件可能会阻止你扫描设备。</span><span class="sxs-lookup"><span data-stu-id="d5359-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="d5359-1102">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="d5359-1103">运行<a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft 安全扫描程序，</a>然后更新你的安全软件，然后重试。</span><span class="sxs-lookup"><span data-stu-id="d5359-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1104">错误代码：0x80508024</span><span class="sxs-lookup"><span data-stu-id="d5359-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="d5359-1105">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1105">Message</span></span></td>
<td><span data-ttu-id="d5359-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1107">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1108">此错误指示可能需要进行完整系统扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="d5359-1109">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1109">Resolution</span></span></td><td>
<span data-ttu-id="d5359-1110">运行完整系统扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1111">错误代码：0x80508025</span><span class="sxs-lookup"><span data-stu-id="d5359-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1112">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1112">Message</span></span></td>
<td><span data-ttu-id="d5359-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1114">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1115">此错误指示需要手动步骤才能完成威胁删除。</span><span class="sxs-lookup"><span data-stu-id="d5359-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="d5359-1116">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1116">Resolution</span></span></td><td>
<span data-ttu-id="d5359-1117">按照 Microsoft Malware Protection Malware 中概述的 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">手动修正步骤操作</a>。</span><span class="sxs-lookup"><span data-stu-id="d5359-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="d5359-1118">可以在事件历史记录中查找特定于威胁的链接。</span><span class="sxs-lookup"><span data-stu-id="d5359-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1119">错误代码：0x80508026</span><span class="sxs-lookup"><span data-stu-id="d5359-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1120">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1120">Message</span></span></td>
<td><span data-ttu-id="d5359-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1122">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1123">此错误指示可能不支持在容器类型内删除。</span><span class="sxs-lookup"><span data-stu-id="d5359-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="d5359-1124">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1124">Resolution</span></span></td><td>
<span data-ttu-id="d5359-1125">Microsoft Defender 防病毒无法修正在存档内检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="d5359-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="d5359-1126">请考虑手动删除检测到的资源。</span><span class="sxs-lookup"><span data-stu-id="d5359-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1127">错误代码：0x80508027</span><span class="sxs-lookup"><span data-stu-id="d5359-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1128">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1128">Message</span></span></td>
<td><span data-ttu-id="d5359-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1130">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1131">此错误指示可能会禁用低威胁和中等威胁的删除。</span><span class="sxs-lookup"><span data-stu-id="d5359-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="d5359-1132">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1132">Resolution</span></span></td><td>
<span data-ttu-id="d5359-1133">检查检测到的威胁并按要求解决它们。</span><span class="sxs-lookup"><span data-stu-id="d5359-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1134">错误代码：0x80508029</span><span class="sxs-lookup"><span data-stu-id="d5359-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1135">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1135">Message</span></span></td>
<td><span data-ttu-id="d5359-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1137">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1138">此错误指示需要重新扫描威胁。</span><span class="sxs-lookup"><span data-stu-id="d5359-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="d5359-1139">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1139">Resolution</span></span></td><td>
<span data-ttu-id="d5359-1140">运行完整系统扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1141">错误代码：0x80508030</span><span class="sxs-lookup"><span data-stu-id="d5359-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1142">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1142">Message</span></span></td>
<td><span data-ttu-id="d5359-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d5359-1144">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1145">此错误指示需要脱机扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="d5359-1146">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1146">Resolution</span></span></td><td>
<span data-ttu-id="d5359-1147">脱机运行Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="d5359-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="d5359-1148">可以在脱机访问文章中Microsoft Defender 防病毒<a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">操作</a>。</span><span class="sxs-lookup"><span data-stu-id="d5359-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d5359-1149">错误代码：0x80508031</span><span class="sxs-lookup"><span data-stu-id="d5359-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="d5359-1150">邮件</span><span class="sxs-lookup"><span data-stu-id="d5359-1150">Message</span></span></td>
<td><span data-ttu-id="d5359-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="d5359-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="d5359-1152">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d5359-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="d5359-1153">此错误指示Microsoft Defender 防病毒不支持平台的当前版本，并且需要新版本的平台。</span><span class="sxs-lookup"><span data-stu-id="d5359-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="d5359-1154">解决方案</span><span class="sxs-lookup"><span data-stu-id="d5359-1154">Resolution</span></span></td><td>
<span data-ttu-id="d5359-1155">只能在 Microsoft Defender 防病毒 中Windows 10。</span><span class="sxs-lookup"><span data-stu-id="d5359-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="d5359-1156">对于 Windows 8、Windows 7 和 Windows Vista，可以使用<a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>。</span><span class="sxs-lookup"><span data-stu-id="d5359-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="d5359-1157">

<a id="internal-error-codes"></a>以下错误代码用于内部测试Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="d5359-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="d5359-1158">如果看到这些错误，可以尝试 [更新定义](manage-updates-baselines-microsoft-defender-antivirus.md) 并强制直接在终结点上重新扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="d5359-1159">内部错误代码</span><span class="sxs-lookup"><span data-stu-id="d5359-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d5359-1160"><b>错误代码</b></span><span class="sxs-lookup"><span data-stu-id="d5359-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="d5359-1161">显示的消息</span><span class="sxs-lookup"><span data-stu-id="d5359-1161">Message displayed</span></span></th>
<th><span data-ttu-id="d5359-1162">可能的错误原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="d5359-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="d5359-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="d5359-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="d5359-1165">请检查 Internet 连接，然后再次运行扫描。</span><span class="sxs-lookup"><span data-stu-id="d5359-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="d5359-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="d5359-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span><span class="sxs-lookup"><span data-stu-id="d5359-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="d5359-1168">这是内部错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-1168">This is an internal error.</span></span> <span data-ttu-id="d5359-1169">原因未明确定义。</span><span class="sxs-lookup"><span data-stu-id="d5359-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="d5359-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="d5359-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="d5359-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="d5359-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="d5359-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="d5359-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="d5359-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="d5359-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="d5359-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="d5359-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="d5359-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="d5359-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="d5359-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="d5359-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="d5359-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="d5359-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="d5359-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="d5359-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="d5359-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="d5359-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="d5359-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="d5359-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="d5359-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="d5359-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="d5359-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="d5359-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="d5359-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="d5359-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="d5359-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="d5359-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="d5359-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="d5359-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="d5359-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="d5359-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="d5359-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="d5359-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="d5359-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="d5359-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="d5359-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="d5359-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="d5359-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="d5359-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="d5359-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="d5359-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="d5359-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="d5359-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="d5359-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="d5359-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="d5359-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="d5359-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="d5359-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="d5359-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="d5359-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="d5359-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="d5359-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="d5359-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="d5359-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="d5359-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="d5359-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="d5359-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="d5359-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="d5359-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="d5359-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="d5359-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="d5359-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="d5359-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="d5359-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="d5359-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="d5359-1238">这是内部错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-1238">This is an internal error.</span></span> <span data-ttu-id="d5359-1239">在恶意软件删除未成功时可能会触发它。</span><span class="sxs-lookup"><span data-stu-id="d5359-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d5359-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="d5359-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="d5359-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d5359-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="d5359-1242">这是内部错误。</span><span class="sxs-lookup"><span data-stu-id="d5359-1242">This is an internal error.</span></span> <span data-ttu-id="d5359-1243">它可能在扫描无法完成时触发。</span><span class="sxs-lookup"><span data-stu-id="d5359-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="d5359-1244">相关主题</span><span class="sxs-lookup"><span data-stu-id="d5359-1244">Related topics</span></span>

- [<span data-ttu-id="d5359-1245">有关保护Microsoft Defender 防病毒报告</span><span class="sxs-lookup"><span data-stu-id="d5359-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d5359-1246">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d5359-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)