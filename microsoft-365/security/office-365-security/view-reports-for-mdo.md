---
title: 查看 Defender for Office 365 报告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何查找和使用 Defender for Office 365门户中提供Microsoft 365 Defender报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8bb03202139137adf55c4c10230b1c4e99253ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454717"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="bd0ef-103">在 Office 365 门户中查看 Defender for Microsoft 365 Defender报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bd0ef-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-104">**Applies to**</span></span>
- [<span data-ttu-id="bd0ef-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="bd0ef-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bd0ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd0ef-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bd0ef-107">适用于 Office 365 组织的 Microsoft Defender (例如，Microsoft 365 E5 订阅或 Microsoft Defender for Office 365 计划 1 或 Microsoft Defender for Office 365 计划 2 加载项) 包含各种与安全相关的报告。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="bd0ef-108">如果您具有 [必要的权限](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，可以在 Microsoft 365 Defender 门户中查看这些报告，& \> **电子邮件**& \> **协作报告**。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="bd0ef-109">若要直接转到"电子邮件& **协作报告"** 页，请打开 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![电子邮件&门户中的"电子邮件Microsoft 365 Defender报告"页](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="bd0ef-111">不需要 Defender for Office 365的电子邮件安全报告在 Microsoft 365 Defender[门户中进行了介绍](view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="bd0ef-112">与邮件流相关的报告现在位于 EAC Exchange管理 () 。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="bd0ef-113">有关这些报告详细信息，请参阅新邮件管理中心Exchange[报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="bd0ef-114">保险箱附件文件类型报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="bd0ef-115">**"保险箱附件文件类型"** 报告最终将消失。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="bd0ef-116">威胁防护状态报告中提供了 [相同的信息](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="bd0ef-117">保险箱附件邮件处置报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="bd0ef-118">最终 **保险箱附件邮件** 处置报告将消失。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="bd0ef-119">威胁防护状态报告中提供了 [相同的信息](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="bd0ef-120">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-120">Mail latency report</span></span>

<span data-ttu-id="bd0ef-121">邮件 **延迟报告显示** 组织中遇到的邮件传递和触发延迟的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="bd0ef-122">服务中的邮件传递时间受多种因素的影响，绝对传递时间（以秒表示）通常不是成功或出现问题的良好指标。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="bd0ef-123">一天的较慢的送达时间可能被视为另一天的平均送达时间，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="bd0ef-124">这将尝试根据有关其他邮件的观察到送达时间的统计数据来限定邮件传递。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="bd0ef-125">不包括客户端和网络延迟。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="bd0ef-126">若要查看报告，请打开Microsoft 365 Defender [门户](https://security.microsoft.com)，**转到报告** \> **电子邮件&** \> **电子邮件&协作报告**。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="bd0ef-127">在"**电子邮件&协作报告**"页上，找到 **"邮件延迟** 报告"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="bd0ef-128">若要直接转到报告，请打开 <https://security.microsoft.com/mailLatencyReport> 。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

!["电子邮件和协作报告"页面上的邮件&小组件](../../media/mail-latency-report-widget.png)

<span data-ttu-id="bd0ef-130">在" **邮件延迟报告"** 页上，"邮件延迟报告"页上提供了 **以下** 选项卡：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="bd0ef-131">**第 50 个** 百分点值：这是邮件传递时间中间值。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="bd0ef-132">可以将此值视为平均送达时间。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="bd0ef-133">默认情况下，此选项卡为选中状态。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-133">This tab is selected by default.</span></span>
- <span data-ttu-id="bd0ef-134">**第 90** 个百分点值：这表示邮件传递的延迟很高。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="bd0ef-135">仅 10% 的邮件传递时间超过此值。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="bd0ef-136">**第 99 个** 百分点值：这表示邮件传递的延迟最高。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="bd0ef-137">无论选择哪个选项卡，图表都会显示按以下类别组织的邮件：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="bd0ef-138">**邮件传递延迟**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="bd0ef-139">**爆炸**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-139">**Detonations**</span></span>

<span data-ttu-id="bd0ef-140">将鼠标悬停在图表中的类别上时，可以看到每个类别中延迟的细分。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![邮件延迟报告的第 50 个百分点值视图](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="bd0ef-142">如果单击 **"筛选器**"，可以按以下值筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="bd0ef-143">**UTC (日期) ：\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="bd0ef-144">**消息视图**：下列值之一：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="bd0ef-145">**所有邮件**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-145">**All messages**</span></span>
  - <span data-ttu-id="bd0ef-146">**包含附件或 URL 的邮件**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="bd0ef-147">**触发的邮件**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-147">**Detonated messages**</span></span>

<span data-ttu-id="bd0ef-148">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="bd0ef-149">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="bd0ef-150">**Date (UTC)**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-150">**Date (UTC)**</span></span>
- <span data-ttu-id="bd0ef-151">**百分点值\*\*\*\*：50、90** 或 **99** </span><span class="sxs-lookup"><span data-stu-id="bd0ef-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="bd0ef-152">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-152">**Message count**</span></span>
- <span data-ttu-id="bd0ef-153">**总体延迟**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="bd0ef-154">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-154">Threat protection status report</span></span>

<span data-ttu-id="bd0ef-155">威胁防护 **状态** 报告是一个单一视图，将有关 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365 检测并阻止的恶意内容和恶意电子邮件的信息汇集在一起。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="bd0ef-156">有关详细信息，请参阅威胁 [防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="bd0ef-157">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-157">URL threat protection report</span></span>

<span data-ttu-id="bd0ef-158">URL **威胁防护报告** 提供检测到的威胁的摘要和趋势视图，以及作为链接的一部分对 URL [单击保险箱视图](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="bd0ef-159">此报告不会包含应用了"链接"策略保险箱"不跟踪用户单击"选项的用户的 **单击** 数据。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="bd0ef-160">若要查看报告，请打开Microsoft 365 Defender [门户](https://security.microsoft.com)，**转到报告** \> **电子邮件&** \> **电子邮件&协作报告**。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="bd0ef-161">在"**电子邮件&协作报告**"页上，找到 **"URL 保护"页**，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="bd0ef-162">若要直接转到报告，请打开 <https://security.microsoft.com/reports/URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

!["电子邮件和协作报告"页上& URL 保护报告小组件](../../media/url-protection-report-widget.png)

<span data-ttu-id="bd0ef-164">以下各节介绍了 **URL 威胁防护** 报告页面上的可用视图。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="bd0ef-165">这是一个 *保护趋势报告*，表示数据表示较大数据集中的趋势。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="bd0ef-166">因此，此处无法实时获得图表中的数据，但详细信息表中的数据是，因此您可能会发现这两者稍有不同。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="bd0ef-167">图表每四小时刷新一次，并包含过去 90 天的数据。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="bd0ef-168">按 URL 查看数据单击保护操作</span><span class="sxs-lookup"><span data-stu-id="bd0ef-168">View data by URL click protection action</span></span>

![URL 威胁防护报告中的 URL 单击保护操作视图](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="bd0ef-170">" **按 URL 查看数据"单击** 保护操作视图显示组织中用户单击的 URL 数以及单击结果：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="bd0ef-171">**允许**：允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="bd0ef-172">**已阻止**：阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="bd0ef-173">**阻止并单击：** 用户已选择继续导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="bd0ef-174">**在扫描过程中单击** 完成：用户已单击链接，扫描完成之前。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="bd0ef-175">单击表示用户已单击"阻止"页面访问恶意网站 (管理员可以在"链接策略" (禁用单击保险箱单击) 。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="bd0ef-176">If you click **Filters**， you can modify the report and the details table by selecting one or more of the following values in the flyout that appears：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="bd0ef-177">**UTC (日期) ：\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="bd0ef-178">**检测**：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-178">**Detection**:</span></span>
  - <span data-ttu-id="bd0ef-179">**允许**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-179">**Allowed**</span></span>
  - <span data-ttu-id="bd0ef-180">**已阻止**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-180">**Blocked**</span></span>
  - <span data-ttu-id="bd0ef-181">**阻止和单击**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="bd0ef-182">**在扫描过程中单击浏览**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="bd0ef-183">**域**：报告结果中列出的 URL 域。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="bd0ef-184">**收件人**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-184">**Recipients**</span></span>

<span data-ttu-id="bd0ef-185">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="bd0ef-186">图表下面的详细信息表提供了最近 7 天内组织中发生的所有单击的以下近实时视图：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="bd0ef-187">**单击时间**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-187">**Click time**</span></span>
- <span data-ttu-id="bd0ef-188">**用户**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-188">**User**</span></span>
- <span data-ttu-id="bd0ef-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-189">**URL**</span></span>
- <span data-ttu-id="bd0ef-190">**Action**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-190">**Action**</span></span>
- <span data-ttu-id="bd0ef-191">**应用**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="bd0ef-192">按 URL 单击应用程序查看数据</span><span class="sxs-lookup"><span data-stu-id="bd0ef-192">View data by URL click by application</span></span>

![URL 威胁防护报告中的应用程序视图单击的 URL](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="bd0ef-194">"**按 URL 单击应用程序** 查看数据"视图显示支持"链接"保险箱单击数：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="bd0ef-195">**电子邮件客户端**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-195">**Email client**</span></span>
- <span data-ttu-id="bd0ef-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-196">**PowerPoint**</span></span>
- <span data-ttu-id="bd0ef-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-197">**Word**</span></span>
- <span data-ttu-id="bd0ef-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-198">**Excel**</span></span>
- <span data-ttu-id="bd0ef-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-199">**OneNote**</span></span>
- <span data-ttu-id="bd0ef-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-200">**Visio**</span></span>
- <span data-ttu-id="bd0ef-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-201">**Teams**</span></span>
- <span data-ttu-id="bd0ef-202">**其他**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-202">**Others**</span></span>

<span data-ttu-id="bd0ef-203">If you click **Filters**， you can modify the report and the details table by selecting one or more of the following values in the flyout that appears：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="bd0ef-204">**UTC (日期) ：\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="bd0ef-205">**检测**：图表中可用的应用。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="bd0ef-206">**域**：报告结果中列出的 URL 域。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="bd0ef-207">**收件人**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-207">**Recipients**</span></span>

<span data-ttu-id="bd0ef-208">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="bd0ef-209">图表下面的详细信息表提供了最近 7 天内组织中发生的所有单击的以下近实时视图：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="bd0ef-210">**单击时间**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-210">**Click time**</span></span>
- <span data-ttu-id="bd0ef-211">**用户**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-211">**User**</span></span>
- <span data-ttu-id="bd0ef-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-212">**URL**</span></span>
- <span data-ttu-id="bd0ef-213">**Action**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-213">**Action**</span></span>
- <span data-ttu-id="bd0ef-214">**应用**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="bd0ef-215">要查看的其他报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-215">Additional reports to view</span></span>

<span data-ttu-id="bd0ef-216">除了本文中所述的报告之外，还有其他一些报告可用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="bd0ef-217">报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-217">Report</span></span>|<span data-ttu-id="bd0ef-218">主题</span><span class="sxs-lookup"><span data-stu-id="bd0ef-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="bd0ef-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1) </span><span class="sxs-lookup"><span data-stu-id="bd0ef-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="bd0ef-220">威胁资源管理器（和实时检测）</span><span class="sxs-lookup"><span data-stu-id="bd0ef-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="bd0ef-221">不需要 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="bd0ef-221">Email security reports that don't require Defender for Office 365</span></span>|[<span data-ttu-id="bd0ef-222">在电子邮件门户中查看Microsoft 365 Defender报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="bd0ef-223">EAC 管理中心Exchange中的 (流) </span><span class="sxs-lookup"><span data-stu-id="bd0ef-223">Mail flow reports in the Exchange admin center (EAC)</span></span>|[<span data-ttu-id="bd0ef-224">新管理中心中的Exchange报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|

<span data-ttu-id="bd0ef-225">PowerShell 报告 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-225">PowerShell reporting cmdlets:</span></span>

<br>

****

|<span data-ttu-id="bd0ef-226">报告</span><span class="sxs-lookup"><span data-stu-id="bd0ef-226">Report</span></span>|<span data-ttu-id="bd0ef-227">主题</span><span class="sxs-lookup"><span data-stu-id="bd0ef-227">Topic</span></span>|
|---|---|
|<span data-ttu-id="bd0ef-228">主要发件人和收件人</span><span class="sxs-lookup"><span data-stu-id="bd0ef-228">Top senders and recipients</span></span>|[<span data-ttu-id="bd0ef-229">Get-MailTrafficTopReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-229">Get-MailTrafficTopReport</span></span>](/powershell/module/exchange/get-mailtraffictopreport) <p> [<span data-ttu-id="bd0ef-230">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-230">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="bd0ef-231">热门恶意软件</span><span class="sxs-lookup"><span data-stu-id="bd0ef-231">Top malware</span></span>|[<span data-ttu-id="bd0ef-232">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-232">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="bd0ef-233">邮件通信</span><span class="sxs-lookup"><span data-stu-id="bd0ef-233">Mail traffic</span></span>|[<span data-ttu-id="bd0ef-234">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-234">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport) <p> [<span data-ttu-id="bd0ef-235">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-235">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|<span data-ttu-id="bd0ef-236">安全链接</span><span class="sxs-lookup"><span data-stu-id="bd0ef-236">Safe Links</span></span>|[<span data-ttu-id="bd0ef-237">Get-SafeLinksAggregateReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-237">Get-SafeLinksAggregateReport</span></span>](/powershell/module/exchange/get-safelinksaggregatereport) <p> [<span data-ttu-id="bd0ef-238">Get-SafeLinksDetailReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-238">Get-SafeLinksDetailReport</span></span>](/powershell/module/exchange/get-safelinksdetailreport)|
|<span data-ttu-id="bd0ef-239">遭到入侵的用户</span><span class="sxs-lookup"><span data-stu-id="bd0ef-239">Compromised users</span></span>|[<span data-ttu-id="bd0ef-240">Get-CompromisedUserAggregateReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-240">Get-CompromisedUserAggregateReport</span></span>](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [<span data-ttu-id="bd0ef-241">Get-CompromisedUserDetailReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-241">Get-CompromisedUserDetailReport</span></span>](/powershell/module/exchange/get-compromiseduserdetailreport)|
|<span data-ttu-id="bd0ef-242">邮件流状态</span><span class="sxs-lookup"><span data-stu-id="bd0ef-242">Mail flow status</span></span>|[<span data-ttu-id="bd0ef-243">Get-MailflowStatusReport</span><span class="sxs-lookup"><span data-stu-id="bd0ef-243">Get-MailflowStatusReport</span></span>](/powershell/module/exchange/get-mailflowstatusreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="bd0ef-244">查看 Defender for Office 365报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="bd0ef-244">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="bd0ef-245">若要查看和使用本文中所述的报告，你需要是本文门户中以下角色组之一Microsoft 365 Defender成员：</span><span class="sxs-lookup"><span data-stu-id="bd0ef-245">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="bd0ef-246">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-246">**Organization Management**</span></span>
- <span data-ttu-id="bd0ef-247">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-247">**Security Administrator**</span></span>
- <span data-ttu-id="bd0ef-248">**安全信息读取者**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-248">**Security Reader**</span></span>
- <span data-ttu-id="bd0ef-249">**全局读取者**</span><span class="sxs-lookup"><span data-stu-id="bd0ef-249">**Global Reader**</span></span>

<span data-ttu-id="bd0ef-250">有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-250">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="bd0ef-251">**注意**：向 Microsoft 365 管理中心 中的相应 Azure Active Directory 角色添加用户会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 </span><span class="sxs-lookup"><span data-stu-id="bd0ef-251">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bd0ef-252">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-252">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="bd0ef-253">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="bd0ef-253">What if the reports aren't showing data?</span></span>

<span data-ttu-id="bd0ef-254">如果你在 Defender for Office 365报告中看不到数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-254">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="bd0ef-255">你的组织必须保险箱[链接](set-up-safe-links-policies.md)策略保险箱[附件](set-up-safe-attachments-policies.md)策略，以便 Defender Office 365保护就位。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-255">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="bd0ef-256">另请参阅 [反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="bd0ef-256">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bd0ef-257">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd0ef-257">Related topics</span></span>

[<span data-ttu-id="bd0ef-258">智能报表和 Microsoft 365 Defender见解</span><span class="sxs-lookup"><span data-stu-id="bd0ef-258">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="bd0ef-259">角色权限 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd0ef-259">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
