---
title: Microsoft Defender for Office 365 威胁资源管理器中的威胁搜寻
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
description: 使用威胁资源管理器或 Microsoft 365 Defender中的实时检测来有效调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ad5d73abae71cc7cc00e12665d96b2020da0c41
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105425"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="9583d-103">Microsoft Defender for Office 365 威胁资源管理器中的威胁搜寻</span><span class="sxs-lookup"><span data-stu-id="9583d-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9583d-104">本文内容：</span><span class="sxs-lookup"><span data-stu-id="9583d-104">In this article:</span></span>

- [<span data-ttu-id="9583d-105">威胁资源管理器演练</span><span class="sxs-lookup"><span data-stu-id="9583d-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="9583d-106">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="9583d-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="9583d-107">电子邮件修正</span><span class="sxs-lookup"><span data-stu-id="9583d-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="9583d-108">威胁搜寻体验改进</span><span class="sxs-lookup"><span data-stu-id="9583d-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="9583d-109">这是威胁资源管理器 (**资源管理器) 、** 电子邮件安全、资源管理器和实时检测基础知识的 **3** 篇文章系列中的一部分 **(如** 工具之间的差异以及操作它们所需的权限) 。</span><span class="sxs-lookup"><span data-stu-id="9583d-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="9583d-110">本系列中的其他两篇文章 [是使用威胁](email-security-in-microsoft-defender.md) 资源管理器和威胁资源管理器的电子邮件安全性以及实时检测 [基础知识](real-time-detections.md)。</span><span class="sxs-lookup"><span data-stu-id="9583d-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="9583d-111">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9583d-111">**Applies to**</span></span>
- [<span data-ttu-id="9583d-112">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="9583d-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9583d-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9583d-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9583d-114">如果你的组织拥有适用于 Office 365 的 [Microsoft Defender，](defender-for-office-365.md)并且你拥有 [](#required-licenses-and-permissions)权限，可以使用 **资源管理器** 或实时检测来检测和修正威胁。</span><span class="sxs-lookup"><span data-stu-id="9583d-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="9583d-115">在Microsoft 365 Defender门户 () ，转到"电子邮件&协作"，然后选择"资源管理器"或" <https://security.microsoft.com> **实时检测"。**  </span><span class="sxs-lookup"><span data-stu-id="9583d-115">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** or **Real-time detections**.</span></span> <span data-ttu-id="9583d-116">若要直接对页面执行，请使用 <https://security.microsoft.com/threatexplorer> 或 <https://security.microsoft.com/realtimereports></span><span class="sxs-lookup"><span data-stu-id="9583d-116">To do directly to the page, use <https://security.microsoft.com/threatexplorer> or <https://security.microsoft.com/realtimereports></span></span>

<span data-ttu-id="9583d-117">使用这些工具，你可以：</span><span class="sxs-lookup"><span data-stu-id="9583d-117">With these tools, you can:</span></span>

- <span data-ttu-id="9583d-118">查看由安全Microsoft 365检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="9583d-118">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="9583d-119">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="9583d-119">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="9583d-120">从资源管理器中的视图启动自动调查和响应过程</span><span class="sxs-lookup"><span data-stu-id="9583d-120">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="9583d-121">调查恶意电子邮件等</span><span class="sxs-lookup"><span data-stu-id="9583d-121">Investigate malicious email, and more</span></span>

<span data-ttu-id="9583d-122">有关详细信息，请参阅使用威胁 [资源管理器的电子邮件安全性](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="9583d-122">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="9583d-123">威胁资源管理器演练</span><span class="sxs-lookup"><span data-stu-id="9583d-123">Threat Explorer walk-through</span></span>

<span data-ttu-id="9583d-124">在 Microsoft Defender for Office 365 中，有两个订阅计划：计划 1 和计划 2。</span><span class="sxs-lookup"><span data-stu-id="9583d-124">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="9583d-125">手动操作的威胁搜寻工具存在于两个计划中，名称不同，功能不同。</span><span class="sxs-lookup"><span data-stu-id="9583d-125">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="9583d-126">Defender for Office 365 Plan 1 *使用实时* 检测，它是威胁资源管理器 *(（* 也称为计划 2 中的 *资源管理器) 搜寻* 工具）的子集。</span><span class="sxs-lookup"><span data-stu-id="9583d-126">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="9583d-127">在本系列文章中，大多数示例都是使用完整的威胁资源管理器创建的。</span><span class="sxs-lookup"><span data-stu-id="9583d-127">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="9583d-128">管理员应在实时检测中测试任何步骤，以查看其应用位置。</span><span class="sxs-lookup"><span data-stu-id="9583d-128">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="9583d-129">转到资源管理器 **后，** 默认情况下，你将到达恶意软件页面，但使用视图下拉列表来熟悉你的选项。 </span><span class="sxs-lookup"><span data-stu-id="9583d-129">After you go to **Explorer**, by default, you'll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="9583d-130">如果你搜寻网络钓鱼，或进入威胁活动，请选择这些视图。</span><span class="sxs-lookup"><span data-stu-id="9583d-130">If you're hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-131">![威胁资源管理器中的视图下拉列表](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-131">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="9583d-132">一旦安全操作 (Sec Ops) 人员选择要查看的数据，无论范围是较窄的视图（如用户提交）还是较宽的视图（如"所有电子邮件"），他们都可以使用"发件人"按钮进一步筛选。 </span><span class="sxs-lookup"><span data-stu-id="9583d-132">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="9583d-133">请记住，选择"刷新"以完成筛选操作。</span><span class="sxs-lookup"><span data-stu-id="9583d-133">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-134">![威胁资源管理器中的"发件人"按钮](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-134">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="9583d-135">可以在层中考虑在资源管理器中精简焦点或实时检测。</span><span class="sxs-lookup"><span data-stu-id="9583d-135">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="9583d-136">第 **一个视图**。</span><span class="sxs-lookup"><span data-stu-id="9583d-136">The first is **View**.</span></span> <span data-ttu-id="9583d-137">第二个可视为已 *筛选焦点*。</span><span class="sxs-lookup"><span data-stu-id="9583d-137">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="9583d-138">例如，可以通过记录类似以下的决策来重新跟踪查找威胁时所执行的步骤：为了在资源管理器中查找问题，我选择了"具有收件人筛选器焦点的 **恶意软件视图"。**</span><span class="sxs-lookup"><span data-stu-id="9583d-138">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="9583d-139">这样一来，可以更轻松地重新跟踪步骤。</span><span class="sxs-lookup"><span data-stu-id="9583d-139">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="9583d-140">如果 Sec Ops 使用 **标记** 标记他们认为高价值目标的帐户，他们可以做出选择，如具有标记筛选器焦点的网络钓鱼视图 (包括日期范围（ *如果使用*) ）。</span><span class="sxs-lookup"><span data-stu-id="9583d-140">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="9583d-141">这将显示在一个时间范围内针对其高价值用户目标的任何网络钓鱼 (例如，当某些网络钓鱼攻击针对其行业组织发生很多事件时) 。</span><span class="sxs-lookup"><span data-stu-id="9583d-141">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span>

<span data-ttu-id="9583d-142">可以使用日期范围控件对日期范围进行精简。</span><span class="sxs-lookup"><span data-stu-id="9583d-142">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="9583d-143">你可以在此处查看"恶意软件"视图中 **的** 资源管理器，具有 **检测技术** 筛选器焦点。</span><span class="sxs-lookup"><span data-stu-id="9583d-143">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="9583d-144">但高级筛选器按钮可让Sec Ops 团队深入了解。</span><span class="sxs-lookup"><span data-stu-id="9583d-144">But it's the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-145">![威胁资源管理器中的高级筛选器](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-145">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="9583d-146">单击 **"高级** "筛选器将弹出一个面板，该面板将允许 Sec Ops 执行者自己生成查询，允许他们包含或排除他们需要查看的信息。</span><span class="sxs-lookup"><span data-stu-id="9583d-146">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="9583d-147">资源管理器页面上的图表和表格都将反映其结果。</span><span class="sxs-lookup"><span data-stu-id="9583d-147">Both the chart and table on the Explorer page will reflect their results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-148">![查询结果](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-148">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="9583d-149">使用 **"列** 选项"按钮获取有关最有帮助的表的信息类型：</span><span class="sxs-lookup"><span data-stu-id="9583d-149">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-150">![突出显示的列选项按钮](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-150">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-151">![列中的可用选项](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-151">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="9583d-152">在同一方面，请确保测试你的显示选项。</span><span class="sxs-lookup"><span data-stu-id="9583d-152">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="9583d-153">不同的访问群体将很好地响应相同数据的不同演示文稿。</span><span class="sxs-lookup"><span data-stu-id="9583d-153">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="9583d-154">对于一些查看者，电子邮件来源地图可以显示威胁是普遍出现还是比它旁边的"宣传活动显示"选项更快速。</span><span class="sxs-lookup"><span data-stu-id="9583d-154">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="9583d-155">Sec 操作可充分利用这些显示，以最好地突出安全性和保护需求，或用于稍后比较，以演示其操作的有效性。</span><span class="sxs-lookup"><span data-stu-id="9583d-155">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-156">![电子邮件来源映射](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-156">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-157">![市场活动显示选项](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-157">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="9583d-158">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="9583d-158">Email investigation</span></span>

<span data-ttu-id="9583d-159">当看到可疑电子邮件时，单击该名称以展开右侧飞出。</span><span class="sxs-lookup"><span data-stu-id="9583d-159">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="9583d-160">此处提供了允许 Sec Ops 查看 [电子邮件实体页面的](mdo-email-entity-page.md) 横幅。</span><span class="sxs-lookup"><span data-stu-id="9583d-160">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="9583d-161">电子邮件实体页面将可以在详细信息、附件、设备下找到的内容汇集在一起，但包含组织性较详细的数据。 </span><span class="sxs-lookup"><span data-stu-id="9583d-161">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="9583d-162">这包括 DMARC 结果、带有复制选项的电子邮件头的纯文本显示、安全触发的附件裁定信息，以及丢弃的 (的文件可以包括联系到的 IP 地址以及页面或文件的屏幕截图) 。</span><span class="sxs-lookup"><span data-stu-id="9583d-162">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="9583d-163">还将列出 URL 及其裁定，并报告类似的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9583d-163">URLs and their verdicts are also listed with similar details reported.</span></span>

<span data-ttu-id="9583d-164">当您进入此阶段时，电子邮件实体页面将对于最后一步（修正）*至关重要*。</span><span class="sxs-lookup"><span data-stu-id="9583d-164">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-165">![电子邮件实体页面](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-165">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="9583d-166">若要了解有关"分析"选项卡)  (上显示的内容丰富的电子邮件实体页面的详细信息，包括触发的附件的结果、包含的 URL 的结果和安全的电子邮件预览，[请单击此处。](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="9583d-166">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-167">![电子邮件实体页面的"分析"选项卡](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-167">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="9583d-168">电子邮件修正</span><span class="sxs-lookup"><span data-stu-id="9583d-168">Email remediation</span></span>

<span data-ttu-id="9583d-169">Sec Ops 人员确定电子邮件是威胁后，下一个资源管理器或实时检测步骤将处理威胁并修正它。</span><span class="sxs-lookup"><span data-stu-id="9583d-169">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="9583d-170">为此，请返回到威胁资源管理器，选中问题电子邮件的复选框，然后使用"操作 **"按钮。**</span><span class="sxs-lookup"><span data-stu-id="9583d-170">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-171">![威胁资源管理器中的"操作"按钮](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-171">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="9583d-172">在此，分析员可以执行将邮件报告为垃圾邮件、网络钓鱼或恶意软件、联系收件人或进一步调查等操作，包括触发自动调查和响应 (或 AIR) 操作手册 (（如果你有计划 2) ）。</span><span class="sxs-lookup"><span data-stu-id="9583d-172">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="9583d-173">或者，也可以将邮件报告为干净。</span><span class="sxs-lookup"><span data-stu-id="9583d-173">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-174">!["操作"下拉列表](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-174">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="9583d-175">威胁搜寻体验改进</span><span class="sxs-lookup"><span data-stu-id="9583d-175">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="9583d-176">警报 ID</span><span class="sxs-lookup"><span data-stu-id="9583d-176">Alert ID</span></span>

<span data-ttu-id="9583d-177">从警报导航到威胁资源管理器时， **视图** 将按警报 **ID 进行筛选**。</span><span class="sxs-lookup"><span data-stu-id="9583d-177">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="9583d-178">这同样适用于实时检测。</span><span class="sxs-lookup"><span data-stu-id="9583d-178">This also applies in Real-time detection.</span></span> <span data-ttu-id="9583d-179">与特定警报相关的邮件，以及 (显示) 总数。</span><span class="sxs-lookup"><span data-stu-id="9583d-179">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="9583d-180">你将能够查看邮件是否属于警报，以及从该邮件导航到相关警报。</span><span class="sxs-lookup"><span data-stu-id="9583d-180">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="9583d-181">最后，警报 ID 包含在 URL 中，例如： `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="9583d-181">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-182">![筛选警报 ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-182">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-183">![详细信息中的警报 ID 飞出](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-183">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="9583d-184">扩展资源管理器 (和实时检测) 试用租户的数据保留和搜索限制</span><span class="sxs-lookup"><span data-stu-id="9583d-184">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span>

<span data-ttu-id="9583d-185">作为此更改的一部分，分析员将能够搜索和筛选 (在威胁资源管理器中为) 增加的 30 天内的电子邮件数据，以及针对 Office P1 和 P2 试用租户的 Defender 实时检测。</span><span class="sxs-lookup"><span data-stu-id="9583d-185">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="9583d-186">这不会影响 P1 和 P2 E5 客户的任何生产租户，其中保留默认值已是 30 天。</span><span class="sxs-lookup"><span data-stu-id="9583d-186">This doesn't impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="9583d-187">已更新的导出限制</span><span class="sxs-lookup"><span data-stu-id="9583d-187">Updated Export limit</span></span>

<span data-ttu-id="9583d-188">现在，可以从威胁资源管理器导出的电子邮件记录数为 200，000， (为 9990) 。</span><span class="sxs-lookup"><span data-stu-id="9583d-188">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="9583d-189">可导出的列集保持不变。</span><span class="sxs-lookup"><span data-stu-id="9583d-189">The set of columns that can be exported is unchanged.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="9583d-190">威胁资源管理器中的标记</span><span class="sxs-lookup"><span data-stu-id="9583d-190">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="9583d-191">用户标记功能在预览版中，可能并非对所有人都可用。</span><span class="sxs-lookup"><span data-stu-id="9583d-191">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="9583d-192">此外，预览可能会更改。</span><span class="sxs-lookup"><span data-stu-id="9583d-192">Also, Previews are subject to change.</span></span> <span data-ttu-id="9583d-193">有关发布计划的信息，请查看Microsoft 365路线图。</span><span class="sxs-lookup"><span data-stu-id="9583d-193">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="9583d-194">用户标记标识 Microsoft Defender for Office 365 中的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="9583d-194">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9583d-195">有关标记（包括许可和配置）的信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="9583d-195">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="9583d-196">在威胁资源管理器中，可以在以下体验中查看有关用户标记的信息。</span><span class="sxs-lookup"><span data-stu-id="9583d-196">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="9583d-197">电子邮件网格视图</span><span class="sxs-lookup"><span data-stu-id="9583d-197">Email grid view</span></span>

<span data-ttu-id="9583d-198">当分析员查看电子邮件网格的 **"** 标签"列时，他们将看到已应用于发件人或收件人邮箱的所有标记。</span><span class="sxs-lookup"><span data-stu-id="9583d-198">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="9583d-199">默认情况下，优先显示优先 *帐户等* 系统标记。</span><span class="sxs-lookup"><span data-stu-id="9583d-199">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-200">![电子邮件网格视图中的筛选器标记](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-200">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="9583d-201">筛选</span><span class="sxs-lookup"><span data-stu-id="9583d-201">Filtering</span></span>

<span data-ttu-id="9583d-202">标记可以用作筛选器。</span><span class="sxs-lookup"><span data-stu-id="9583d-202">Tags can be used as filters.</span></span> <span data-ttu-id="9583d-203">仅在优先级帐户之间搜寻，或采用这种方式使用特定用户标记方案。</span><span class="sxs-lookup"><span data-stu-id="9583d-203">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="9583d-204">还可以排除具有特定标记的结果。</span><span class="sxs-lookup"><span data-stu-id="9583d-204">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="9583d-205">将标记与其他筛选器和日期范围相结合，以缩小调查范围。</span><span class="sxs-lookup"><span data-stu-id="9583d-205">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span>

<span data-ttu-id="9583d-206">[![筛选器标记](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9583d-206">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-207">![非筛选器标记](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-207">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="9583d-208">电子邮件详细信息飞出</span><span class="sxs-lookup"><span data-stu-id="9583d-208">Email detail flyout</span></span>

<span data-ttu-id="9583d-209">若要查看发件人和收件人的单个标记，请选择一封电子邮件以打开邮件详细信息飞出。</span><span class="sxs-lookup"><span data-stu-id="9583d-209">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="9583d-210">在 **"摘要"选项卡** 上，发件人和收件人标记将单独显示。</span><span class="sxs-lookup"><span data-stu-id="9583d-210">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="9583d-211">有关发件人和收件人的单个标记的信息可以导出为 CSV 数据。</span><span class="sxs-lookup"><span data-stu-id="9583d-211">The information about individual tags for sender and recipient can be exported as CSV data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-212">![电子邮件详细信息标记](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-212">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="9583d-213">URL 单击飞出也显示标记信息。</span><span class="sxs-lookup"><span data-stu-id="9583d-213">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="9583d-214">若要查看它，请转到网络钓鱼或所有电子邮件视图> **URL** 或 **URL** 单击选项卡。选择单个 URL 飞出，以查看有关该 URL 的单击的其他详细信息，包括与该单击关联的任何标记。</span><span class="sxs-lookup"><span data-stu-id="9583d-214">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="9583d-215">更新的时间线视图</span><span class="sxs-lookup"><span data-stu-id="9583d-215">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-216">![URL 标记](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-216">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="9583d-217">观看[此视频](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="9583d-217">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="9583d-218">扩展功能</span><span class="sxs-lookup"><span data-stu-id="9583d-218">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="9583d-219">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="9583d-219">Top targeted users</span></span>

<span data-ttu-id="9583d-220">主要恶意软件系列在 **"恶意软件"部分显示** 主要目标用户。</span><span class="sxs-lookup"><span data-stu-id="9583d-220">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="9583d-221">主要目标用户也将通过钓鱼和所有电子邮件视图进行扩展。</span><span class="sxs-lookup"><span data-stu-id="9583d-221">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="9583d-222">分析员将能够查看前五个目标用户，以及每个视图中每个用户的尝试次数。</span><span class="sxs-lookup"><span data-stu-id="9583d-222">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span>

<span data-ttu-id="9583d-223">安全操作 用户可以导出目标用户列表（最多 3，000 个）以及尝试次数，以便针对每个电子邮件视图进行脱机分析。</span><span class="sxs-lookup"><span data-stu-id="9583d-223">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="9583d-224">此外，选择尝试次数 (例如，在) 下的图像中尝试 13 次将在威胁资源管理器中打开筛选视图，以便你可以查看有关该用户的电子邮件和威胁的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9583d-224">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-225">![主要目标用户](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-225">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="9583d-226">Exchange传输规则</span><span class="sxs-lookup"><span data-stu-id="9583d-226">Exchange transport rules</span></span>

<span data-ttu-id="9583d-227">安全运营团队将能够在"电子邮件"网格Exchange查看 (邮件流规则) 邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="9583d-227">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="9583d-228">选择 **网格中的**"列"选项，然后 **Exchange"添加** 传输规则"。</span><span class="sxs-lookup"><span data-stu-id="9583d-228">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="9583d-229">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span><span class="sxs-lookup"><span data-stu-id="9583d-229">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="9583d-230">将显示应用于邮件的传输规则的名称和 GUID。</span><span class="sxs-lookup"><span data-stu-id="9583d-230">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="9583d-231">分析员将能够使用传输规则的名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="9583d-231">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="9583d-232">这是 CONTAINS 搜索，这意味着您也可以执行部分搜索。</span><span class="sxs-lookup"><span data-stu-id="9583d-232">This is a CONTAINS search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9583d-233">Exchange规则搜索和名称可用性取决于分配给您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="9583d-233">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="9583d-234">您需要具有以下角色或权限之一才能查看传输规则名称和搜索。</span><span class="sxs-lookup"><span data-stu-id="9583d-234">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="9583d-235">但是，即使没有以下角色或权限，分析员也可以查看电子邮件详细信息中的传输规则标签和 GUID 信息。</span><span class="sxs-lookup"><span data-stu-id="9583d-235">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="9583d-236">电子邮件网格、电子邮件飞出、筛选器和导出中的其他记录查看体验不受影响。</span><span class="sxs-lookup"><span data-stu-id="9583d-236">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="9583d-237">Exchange Online仅 - 数据丢失防护：全部</span><span class="sxs-lookup"><span data-stu-id="9583d-237">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="9583d-238">Exchange Online仅 - O365SupportViewConfig：全部</span><span class="sxs-lookup"><span data-stu-id="9583d-238">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="9583d-239">Microsoft Azure Active Directory或Exchange Online - 安全管理员：全部</span><span class="sxs-lookup"><span data-stu-id="9583d-239">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="9583d-240">Azure Active Directory或Exchange Online - 安全读者：全部</span><span class="sxs-lookup"><span data-stu-id="9583d-240">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="9583d-241">Exchange Online仅 - 传输规则：全部</span><span class="sxs-lookup"><span data-stu-id="9583d-241">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="9583d-242">Exchange Online仅 - View-Only配置：全部</span><span class="sxs-lookup"><span data-stu-id="9583d-242">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="9583d-243">在电子邮件网格、详细信息飞出控件和导出的 CSV 中，ETR 将显示一个名称/GUID，如下所示。</span><span class="sxs-lookup"><span data-stu-id="9583d-243">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="9583d-244">![Exchange传输规则](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-244">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="9583d-245">入站连接器</span><span class="sxs-lookup"><span data-stu-id="9583d-245">Inbound connectors</span></span>

<span data-ttu-id="9583d-246">连接器是一组说明，用于自定义电子邮件在组织或组织Microsoft 365 Office 365流。</span><span class="sxs-lookup"><span data-stu-id="9583d-246">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="9583d-247">它们使您能够应用任何安全限制或控件。</span><span class="sxs-lookup"><span data-stu-id="9583d-247">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="9583d-248">在威胁资源管理器中，可以查看与电子邮件相关的连接器，然后使用连接器名称搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9583d-248">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span>

<span data-ttu-id="9583d-249">搜索连接器是 CONTAINS 查询，这意味着部分关键字搜索可以正常工作：</span><span class="sxs-lookup"><span data-stu-id="9583d-249">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9583d-250">![连接器详细信息](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="9583d-250">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="9583d-251">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="9583d-251">Required licenses and permissions</span></span>

<span data-ttu-id="9583d-252">你必须拥有[Microsoft Defender Office 365](defender-for-office-365.md)使用资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="9583d-252">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="9583d-253">资源管理器包含在计划 2 Office 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="9583d-253">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="9583d-254">实时检测报告包含在计划 1 的 Defender Office 365中。</span><span class="sxs-lookup"><span data-stu-id="9583d-254">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="9583d-255">计划为应受 Defender for Office 365 保护的所有用户分配Office 365。</span><span class="sxs-lookup"><span data-stu-id="9583d-255">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="9583d-256">资源管理器和实时检测显示许可用户的检测数据。</span><span class="sxs-lookup"><span data-stu-id="9583d-256">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="9583d-257">若要查看和使用资源管理器或实时检测，您必须具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="9583d-257">To view and use Explorer or Real-time detections, you must have the following permissions:</span></span>

- <span data-ttu-id="9583d-258">对于 Microsoft 365 Defender 门户：</span><span class="sxs-lookup"><span data-stu-id="9583d-258">For the Microsoft 365 Defender portal:</span></span>
  - <span data-ttu-id="9583d-259">组织管理</span><span class="sxs-lookup"><span data-stu-id="9583d-259">Organization Management</span></span>
  - <span data-ttu-id="9583d-260">安全 (可以在管理中心Azure Active Directory分配 <https://aad.portal.azure.com> () </span><span class="sxs-lookup"><span data-stu-id="9583d-260">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="9583d-261">安全读取者</span><span class="sxs-lookup"><span data-stu-id="9583d-261">Security Reader</span></span>
- <span data-ttu-id="9583d-262">例如Exchange Online：</span><span class="sxs-lookup"><span data-stu-id="9583d-262">For Exchange Online:</span></span>
  - <span data-ttu-id="9583d-263">组织管理</span><span class="sxs-lookup"><span data-stu-id="9583d-263">Organization Management</span></span>
  - <span data-ttu-id="9583d-264">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="9583d-264">View-Only Organization Management</span></span>
  - <span data-ttu-id="9583d-265">仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="9583d-265">View-Only Recipients</span></span>
  - <span data-ttu-id="9583d-266">合规性管理</span><span class="sxs-lookup"><span data-stu-id="9583d-266">Compliance Management</span></span>

<span data-ttu-id="9583d-267">若要详细了解角色和权限，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="9583d-267">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="9583d-268">Microsoft 365 Defender 门户中的权限</span><span class="sxs-lookup"><span data-stu-id="9583d-268">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="9583d-269">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="9583d-269">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="9583d-270">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="9583d-270">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="9583d-271">更多信息</span><span class="sxs-lookup"><span data-stu-id="9583d-271">More information</span></span>

- [<span data-ttu-id="9583d-272">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="9583d-272">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="9583d-273">查看在 SharePoint Online、OneDrive 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9583d-273">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="9583d-274">大致了解威胁资源管理器中的 (和实时检测) </span><span class="sxs-lookup"><span data-stu-id="9583d-274">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="9583d-275">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="9583d-275">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="9583d-276">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="9583d-276">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
- [<span data-ttu-id="9583d-277">使用"电子邮件实体"页调查电子邮件</span><span class="sxs-lookup"><span data-stu-id="9583d-277">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
