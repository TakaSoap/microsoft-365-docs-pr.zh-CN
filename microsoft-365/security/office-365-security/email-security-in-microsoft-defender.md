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
ms.openlocfilehash: 917ad3caf96a982df8b88058ff1c394b3d21dd75
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028534"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="17de2-103">使用 Microsoft Defender for Office 365 中的威胁资源管理器进行电子邮件Office 365</span><span class="sxs-lookup"><span data-stu-id="17de2-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="17de2-104">本文内容：</span><span class="sxs-lookup"><span data-stu-id="17de2-104">In this article:</span></span>

- [<span data-ttu-id="17de2-105">查看电子邮件中检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="17de2-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="17de2-106">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="17de2-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="17de2-107">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="17de2-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="17de2-108">这是威胁资源管理器 (**资源管理器) 、** 电子邮件安全、资源管理器和实时检测基础知识的 **3** 篇文章系列中的一部分 **(如** 工具之间的差异以及操作它们所需的权限) 。</span><span class="sxs-lookup"><span data-stu-id="17de2-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="17de2-109">本系列中的其他两篇文章是威胁资源管理器和威胁[](threat-hunting-in-threat-explorer.md)资源管理器中的威胁搜寻和[实时检测基础知识](real-time-detections.md)。</span><span class="sxs-lookup"><span data-stu-id="17de2-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="17de2-110">本文介绍如何查看和调查电子邮件中检测到的恶意软件和网络钓鱼Microsoft 365安全功能。</span><span class="sxs-lookup"><span data-stu-id="17de2-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="17de2-111">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="17de2-111">**Applies to**</span></span>

- [<span data-ttu-id="17de2-112">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="17de2-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="17de2-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17de2-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="17de2-114">查看电子邮件中检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="17de2-114">View malware detected in email</span></span>

<span data-ttu-id="17de2-115">若要查看在电子邮件中检测到的恶意软件Microsoft 365技术排序，请使用 Explorer >[](threat-explorer-views.md#email--malware)的"电子邮件 (恶意软件"视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="17de2-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="17de2-116">恶意软件是默认视图，因此一旦打开资源管理器，可能会选择它。</span><span class="sxs-lookup"><span data-stu-id="17de2-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="17de2-117">在Microsoft 365 Defender门户 () ，选择"电子邮件&协作资源管理器 (或实时检测 <https://security.microsoft.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="17de2-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="17de2-118"> (此示例使用 Explorer.) 如果你位于聚合门户中，Microsoft 365 Defender滚动 ("电子邮件& https://security.microsoft.com/) **协作**  >  **资源管理器"。**</span><span class="sxs-lookup"><span data-stu-id="17de2-118">(This example uses Explorer.) If you're in the converged Microsoft 365 Defender portal (https://security.microsoft.com/) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="17de2-119">从此处，从"视图"开始，选择一个特定的时间范围来调查 (如果需要) ，并按资源管理器演练来聚焦 [筛选器](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)。</span><span class="sxs-lookup"><span data-stu-id="17de2-119">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="17de2-120">在"**视图"** 菜单中，选择"**电子邮件"** 下的"**恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="17de2-120">In the **View** menu, choose **Malware** under **Email**.</span></span>

3. <span data-ttu-id="17de2-121">单击 **"发件人**"，然后选择"**基本** \> **检测技术"。**</span><span class="sxs-lookup"><span data-stu-id="17de2-121">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   
   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="恶意软件检测技术":::

   <span data-ttu-id="17de2-123">你的检测技术现在用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="17de2-123">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="17de2-124">选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="17de2-124">Choose an option.</span></span> <span data-ttu-id="17de2-125">然后选择" **刷新"** 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="17de2-125">Then select the **Refresh** button to apply that filter.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="选定的检测技术"::: 

   <span data-ttu-id="17de2-127">报告将刷新，以使用所选的技术选项显示电子邮件中检测到的恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="17de2-127">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="17de2-128">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="17de2-128">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="17de2-129">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="17de2-129">View phishing URL and click verdict data</span></span>

<span data-ttu-id="17de2-130">您可以通过电子邮件中的 URL 查看网络钓鱼尝试，包括允许、阻止和覆盖的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="17de2-130">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="17de2-131">若要标识单击的[URL，保险箱链接](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="17de2-131">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="17de2-132">请确保为单击保险箱和单击[](set-up-safe-links-policies.md)裁定的日志记录设置"链接"策略保险箱链接" 。</span><span class="sxs-lookup"><span data-stu-id="17de2-132">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="17de2-133">若要查看邮件中的网络钓鱼 URL 并单击网络钓鱼邮件中的 URL，请使用资源管理器的电子邮件[  >  ](threat-explorer-views.md#email--phish)网络钓鱼视图或实时检测。</span><span class="sxs-lookup"><span data-stu-id="17de2-133">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="17de2-134">在Microsoft 365 Defender门户 () ，选择"电子邮件&协作资源管理器 (或实时检测 <https://security.microsoft.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="17de2-134">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="17de2-135"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="17de2-135">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="17de2-136">在"**视图"** 菜单中，选择"**电子邮件钓鱼** \> **邮件"。**</span><span class="sxs-lookup"><span data-stu-id="17de2-136">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17de2-137">![网络钓鱼上下文中资源管理器的"查看"菜单](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="17de2-137">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="17de2-138">单击 **"发件人**"，然后选择 **"URL""** \> **单击裁定"。**</span><span class="sxs-lookup"><span data-stu-id="17de2-138">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="17de2-139">选择一个或多个选项，如"阻止"和"阻止 **覆盖**"，然后选择与应用该筛选器的选项位于同一行上的"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="17de2-139">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="17de2-140"> (请勿刷新浏览器窗口。) </span><span class="sxs-lookup"><span data-stu-id="17de2-140">(Don't refresh your browser window.)</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL 和单击裁定":::

   <span data-ttu-id="17de2-142">报告将刷新，以在报告下的"URL"选项卡上显示两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="17de2-142">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="17de2-143">**顶部 URL** 是筛选到的邮件中的 URL，每个 URL 的电子邮件传递操作计数。</span><span class="sxs-lookup"><span data-stu-id="17de2-143">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="17de2-144">在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-144">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="17de2-145">攻击者在邮件中混合了好 URL 和坏 URL，以尝试传递这些 URL，但它们会使恶意链接看起来更有趣。</span><span class="sxs-lookup"><span data-stu-id="17de2-145">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="17de2-146">URL 表按总电子邮件计数排序，但隐藏此列以简化视图。</span><span class="sxs-lookup"><span data-stu-id="17de2-146">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="17de2-147">**点击量** 最高是保险箱链接包装的 URL，按总点击数排序。</span><span class="sxs-lookup"><span data-stu-id="17de2-147">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="17de2-148">此列也不显示，以简化视图。</span><span class="sxs-lookup"><span data-stu-id="17de2-148">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="17de2-149">按列的总计数指示每个保险箱 URL 的链接单击裁定计数。</span><span class="sxs-lookup"><span data-stu-id="17de2-149">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="17de2-150">在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-150">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="17de2-151">但是，该视图可能包含不是威胁但包含钓鱼邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-151">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="17de2-152">此处不会显示对未包链接的 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="17de2-152">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="17de2-153">这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-153">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="17de2-154">这些表显示了在出现警告时被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接以及用户点击了哪些链接。</span><span class="sxs-lookup"><span data-stu-id="17de2-154">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="17de2-155">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="17de2-155">From here, you can conduct further analysis.</span></span> <span data-ttu-id="17de2-156">例如，在图表下方，可以看到在组织环境中被阻止的电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-156">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17de2-157">![阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="17de2-157">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="17de2-158">选择 URL 以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="17de2-158">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="17de2-159">在"URL"弹出对话框中，将删除对电子邮件的筛选，以显示环境中 URL 曝光的完整视图。</span><span class="sxs-lookup"><span data-stu-id="17de2-159">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="17de2-160">这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过"URL 详细信息"对话框) 扩展你了解环境中 (中的 URL 曝光，而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="17de2-160">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="17de2-161">单击裁定的解释</span><span class="sxs-lookup"><span data-stu-id="17de2-161">Interpretation of click verdicts</span></span>

<span data-ttu-id="17de2-162">在"电子邮件或 URL"飞出、点击次数和筛选体验中，你将看到不同的单击裁定值：</span><span class="sxs-lookup"><span data-stu-id="17de2-162">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="17de2-163">**无：** 无法捕获 URL 裁定。</span><span class="sxs-lookup"><span data-stu-id="17de2-163">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="17de2-164">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="17de2-164">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="17de2-165">**允许：** 允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-165">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="17de2-166">**已阻止：** 阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-166">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="17de2-167">**待定裁定：** 向用户显示等待触发的页面。</span><span class="sxs-lookup"><span data-stu-id="17de2-167">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="17de2-168">**被阻止覆盖：** 阻止用户直接导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-168">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="17de2-169">但用户过度控制块以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="17de2-169">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="17de2-170">**已绕过待定裁定：** 向用户显示触发页面。</span><span class="sxs-lookup"><span data-stu-id="17de2-170">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="17de2-171">但是，用户为了访问 URL 而过度使用邮件。</span><span class="sxs-lookup"><span data-stu-id="17de2-171">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="17de2-172">**错误：** 向用户显示错误页面，或捕获裁定时出错。</span><span class="sxs-lookup"><span data-stu-id="17de2-172">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="17de2-173">**失败：** 捕获裁定时发生未知异常。</span><span class="sxs-lookup"><span data-stu-id="17de2-173">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="17de2-174">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="17de2-174">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="17de2-175">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="17de2-175">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="17de2-176">Microsoft Defender for *Office 365 计划 2* 和 Office 365 E5 *中提供了自动调查和响应Office 365 E5。*</span><span class="sxs-lookup"><span data-stu-id="17de2-176">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="17de2-177">[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队在调查和缓解网络攻击上花费的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="17de2-177">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="17de2-178">除了配置可触发安全手册的警报之外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="17de2-178">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="17de2-179">有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="17de2-179">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="17de2-180">其他文章</span><span class="sxs-lookup"><span data-stu-id="17de2-180">Other articles</span></span>

[<span data-ttu-id="17de2-181">使用"电子邮件实体"页调查电子邮件</span><span class="sxs-lookup"><span data-stu-id="17de2-181">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
