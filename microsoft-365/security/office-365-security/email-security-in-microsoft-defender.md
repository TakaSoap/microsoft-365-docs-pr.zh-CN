---
title: 使用 Microsoft Defender for Office 365 中的威胁资源管理器进行电子邮件Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 查看和调查恶意软件钓鱼尝试。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb62961bb26b079c508cbd5bc559a95d172cff86
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029881"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="30551-103">使用 Microsoft Defender for Office 365 中的威胁资源管理器进行电子邮件Office 365</span><span class="sxs-lookup"><span data-stu-id="30551-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="30551-104">本文内容：</span><span class="sxs-lookup"><span data-stu-id="30551-104">In this article:</span></span>

- [<span data-ttu-id="30551-105">查看电子邮件中检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="30551-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="30551-106">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="30551-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="30551-107">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="30551-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="30551-108">这是威胁资源管理器 (**资源管理器) 、** 电子邮件安全、资源管理器和实时检测基础知识的 **3** 篇文章系列中的一部分 **(如** 工具之间的差异以及操作它们所需的权限) 。</span><span class="sxs-lookup"><span data-stu-id="30551-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="30551-109">本系列中的其他两篇文章是威胁资源管理器和威胁[](threat-hunting-in-threat-explorer.md)资源管理器中的威胁搜寻和[实时检测基础知识](real-time-detections.md)。</span><span class="sxs-lookup"><span data-stu-id="30551-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>

<span data-ttu-id="30551-110">本文介绍如何查看和调查电子邮件中检测到的恶意软件和网络钓鱼Microsoft 365安全功能。</span><span class="sxs-lookup"><span data-stu-id="30551-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span>

<span data-ttu-id="30551-111">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="30551-111">**Applies to:**</span></span>

- [<span data-ttu-id="30551-112">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="30551-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="30551-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30551-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="30551-114">查看电子邮件中检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="30551-114">View malware detected in email</span></span>

<span data-ttu-id="30551-115">若要查看在电子邮件中检测到的恶意软件Microsoft 365技术排序，请使用 Explorer >[](threat-explorer-views.md#email--malware)的"电子邮件 (恶意软件"视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="30551-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="30551-116">恶意软件是默认视图，因此一旦打开资源管理器，可能会选中它。</span><span class="sxs-lookup"><span data-stu-id="30551-116">Malware is the default view, so it might be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="30551-117">在Microsoft 365 Defender门户 <https://security.microsoft.com> () ，选择"电子邮件&**协作** 资源管理器 (\> 或 **实时检测";** 此示例使用 Explorer) 。</span><span class="sxs-lookup"><span data-stu-id="30551-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

   <span data-ttu-id="30551-118">从此处，从"视图"开始，选择一个特定的时间范围来调查 (如果需要) ，并按资源管理器演练来聚焦 [筛选器](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)。</span><span class="sxs-lookup"><span data-stu-id="30551-118">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="30551-119">在 **"查看** "下拉列表中，验证 **是否选择了** \> **"电子邮件恶意软件** "。</span><span class="sxs-lookup"><span data-stu-id="30551-119">In the **View** drop down list, verify that **Email** \> **Malware** is selected.</span></span>

3. <span data-ttu-id="30551-120">单击 **"发件人**"，然后在 **下拉列表** 中选择 \> "基本检测技术"。</span><span class="sxs-lookup"><span data-stu-id="30551-120">Click **Sender**, and then choose **Basic** \> **Detection technology** in the drop down list.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="恶意软件检测技术":::

   <span data-ttu-id="30551-122">你的检测技术现在用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="30551-122">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="30551-123">选择一个选项，然后单击 **"刷新"** 以应用 (不刷新浏览器窗口) 。</span><span class="sxs-lookup"><span data-stu-id="30551-123">Choose an option, and then click **Refresh** to apply that filter (don't refresh your browser window).</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="选定的检测技术":::

   <span data-ttu-id="30551-125">报告将刷新，以使用所选的技术选项显示电子邮件中检测到的恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="30551-125">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="30551-126">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="30551-126">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="30551-127">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="30551-127">View phishing URL and click verdict data</span></span>

<span data-ttu-id="30551-128">您可以通过电子邮件中的 URL 查看网络钓鱼尝试，包括允许、阻止和覆盖的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="30551-128">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="30551-129">若要标识单击的[URL，保险箱链接](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="30551-129">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="30551-130">请确保为单击保险箱和单击[](set-up-safe-links-policies.md)裁定的日志记录设置"链接"策略保险箱链接" 。</span><span class="sxs-lookup"><span data-stu-id="30551-130">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

1. <span data-ttu-id="30551-131">在Microsoft 365 Defender门户 <https://security.microsoft.com> () ，选择"电子邮件&**协作** 资源管理器 (\> 或 **实时检测";** 此示例使用 Explorer) 。</span><span class="sxs-lookup"><span data-stu-id="30551-131">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

2. <span data-ttu-id="30551-132">在"**查看"** 下拉列表中，选择"**电子邮件钓鱼** \> **邮件"。**</span><span class="sxs-lookup"><span data-stu-id="30551-132">In the **View** drop down list, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30551-133">![网络钓鱼上下文中资源管理器的"查看"菜单](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="30551-133">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="30551-134">单击 **"发件人**"，然后在下拉列表中选择 **"URL""** \> 单击裁定"。</span><span class="sxs-lookup"><span data-stu-id="30551-134">Click **Sender**, and then choose **URLs** \> **Click verdict** in the drop down list.</span></span>

4. <span data-ttu-id="30551-135">在出现的选项中，选择一个或多个选项（如"阻止"和"阻止覆盖"，然后单击"刷新 (不刷新浏览器窗口) 。 </span><span class="sxs-lookup"><span data-stu-id="30551-135">In options that appear, select one or more options, such as **Blocked** and **Block overridden**, and then click **Refresh** (don't refresh your browser window).</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL 和单击裁定":::

   <span data-ttu-id="30551-137">报告将刷新以显示报告下的"URL" **选项卡上的** 两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="30551-137">The report refreshes to show two different URL tables on the **URLs** tab under the report:</span></span>

   - <span data-ttu-id="30551-138">**顶部 URL** 是筛选到的邮件中的 URL，每个 URL 的电子邮件传递操作计数。</span><span class="sxs-lookup"><span data-stu-id="30551-138">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="30551-139">在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-139">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="30551-140">攻击者在邮件中混合了好 URL 和坏 URL，以尝试传递这些 URL，但它们会使恶意链接看起来更有趣。</span><span class="sxs-lookup"><span data-stu-id="30551-140">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="30551-141">URL 表按总电子邮件计数排序，但隐藏此列以简化视图。</span><span class="sxs-lookup"><span data-stu-id="30551-141">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="30551-142">**点击量** 最高是保险箱链接包装的 URL，按总点击数排序。</span><span class="sxs-lookup"><span data-stu-id="30551-142">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="30551-143">此列也不显示，以简化视图。</span><span class="sxs-lookup"><span data-stu-id="30551-143">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="30551-144">按列的总计数指示每个保险箱 URL 的链接单击裁定计数。</span><span class="sxs-lookup"><span data-stu-id="30551-144">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="30551-145">在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-145">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="30551-146">但是，该视图可能包含不是威胁但包含钓鱼邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-146">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="30551-147">此处不会显示对未包链接的 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="30551-147">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="30551-148">这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-148">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="30551-149">这些表显示了在出现警告时被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接以及用户点击了哪些链接。</span><span class="sxs-lookup"><span data-stu-id="30551-149">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="30551-150">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="30551-150">From here, you can conduct further analysis.</span></span> <span data-ttu-id="30551-151">例如，在图表下方，可以看到在组织环境中被阻止的电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-151">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30551-152">![阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="30551-152">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="30551-153">选择 URL 以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="30551-153">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="30551-154">在"URL"弹出对话框中，将删除对电子邮件的筛选，以显示环境中 URL 曝光的完整视图。</span><span class="sxs-lookup"><span data-stu-id="30551-154">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="30551-155">这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过"URL 详细信息"对话框) 扩展你了解环境中 (中的 URL 曝光，而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="30551-155">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="30551-156">单击裁定的解释</span><span class="sxs-lookup"><span data-stu-id="30551-156">Interpretation of click verdicts</span></span>

<span data-ttu-id="30551-157">在"电子邮件或 URL"飞出、点击次数和筛选体验中，你将看到不同的单击裁定值：</span><span class="sxs-lookup"><span data-stu-id="30551-157">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="30551-158">**无：** 无法捕获 URL 裁定。</span><span class="sxs-lookup"><span data-stu-id="30551-158">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="30551-159">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="30551-159">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="30551-160">**允许：** 允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-160">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="30551-161">**已阻止：** 阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-161">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="30551-162">**待定裁定：** 向用户显示等待触发的页面。</span><span class="sxs-lookup"><span data-stu-id="30551-162">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="30551-163">**被阻止覆盖：** 阻止用户直接导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-163">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="30551-164">但用户过度控制块以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="30551-164">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="30551-165">**已绕过待定裁定：** 向用户显示触发页面。</span><span class="sxs-lookup"><span data-stu-id="30551-165">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="30551-166">但是，用户为了访问 URL 而过度使用邮件。</span><span class="sxs-lookup"><span data-stu-id="30551-166">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="30551-167">**错误：** 向用户显示错误页面，或捕获裁定时出错。</span><span class="sxs-lookup"><span data-stu-id="30551-167">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="30551-168">**失败：** 捕获裁定时发生未知异常。</span><span class="sxs-lookup"><span data-stu-id="30551-168">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="30551-169">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="30551-169">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="30551-170">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="30551-170">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="30551-171">Microsoft Defender for *Office 365 计划 2* 和 Office 365 E5 *中提供了自动调查和响应Office 365 E5。*</span><span class="sxs-lookup"><span data-stu-id="30551-171">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="30551-172">[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队在调查和缓解网络攻击上花费的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="30551-172">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="30551-173">除了配置可触发安全手册的警报之外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="30551-173">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="30551-174">有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="30551-174">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="30551-175">其他文章</span><span class="sxs-lookup"><span data-stu-id="30551-175">Other articles</span></span>

[<span data-ttu-id="30551-176">使用"电子邮件实体"页调查电子邮件</span><span class="sxs-lookup"><span data-stu-id="30551-176">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
