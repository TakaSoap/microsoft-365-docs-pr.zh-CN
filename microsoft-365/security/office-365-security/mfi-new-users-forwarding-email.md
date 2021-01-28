---
title: 新用户转发电子邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解如何使用安全与合规中心内的新用户转发电子邮件见解&调查其组织中用户何时将邮件转发到新域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af991cb0af20a0f48bc5283d4e4fb26ea75d6ba6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029866"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="d3766-103">新用户在安全与合规中心转发&见解</span><span class="sxs-lookup"><span data-stu-id="d3766-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d3766-104">当组织的新用户帐户突然开始将电子邮件转发到外部域时，这是可疑的。</span><span class="sxs-lookup"><span data-stu-id="d3766-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="d3766-105">当 **组织中新** 创建的用户将邮件转发 [到](https://protection.office.com) 外部域时&安全与合规中心中转发的电子邮件见解的新域会通知你。</span><span class="sxs-lookup"><span data-stu-id="d3766-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="d3766-106">此条件可能指示已使用遭到入侵的管理员帐户创建新用户。</span><span class="sxs-lookup"><span data-stu-id="d3766-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="d3766-107">如果怀疑帐户已被泄露，请参阅"响应遭到入侵[的电子邮件帐户"。](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="d3766-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="d3766-108">此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。</span><span class="sxs-lookup"><span data-stu-id="d3766-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新用户转发电子邮件见解](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="d3766-110">单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括指向本文稍后介绍的转发修改[](#forwarding-modifications-report)报告的链接。</span><span class="sxs-lookup"><span data-stu-id="d3766-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![单击"新用户"转发电子邮件见解后显示的详细信息飞出](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="d3766-112">在报表仪表板或仪表板上单击"查看所有热门见解"&建议区域中的见解后，**还可以进入** (\> 页面 <https://protection.office.com/insightdashboard>) 。</span><span class="sxs-lookup"><span data-stu-id="d3766-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="d3766-113">可以单击"**查看与见解关联的** 报告"链接，转到下一节中所述的转发修改报告。</span><span class="sxs-lookup"><span data-stu-id="d3766-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="d3766-114">转发修改报告</span><span class="sxs-lookup"><span data-stu-id="d3766-114">Forwarding modifications report</span></span>

<span data-ttu-id="d3766-115">" **转发修改"报告显示** 有关自动从组织中发件人转发的邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="d3766-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="d3766-116">将邮件转发到外部域的新创建帐户。</span><span class="sxs-lookup"><span data-stu-id="d3766-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="d3766-117">将邮件转发到组织中其他发件人从未转发到的外部域的帐户。</span><span class="sxs-lookup"><span data-stu-id="d3766-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="d3766-118">这些类型的转发邮件可能会带来安全或合规性风险，并可能指示帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="d3766-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="d3766-119">该报告包含最多 90 天的数据。</span><span class="sxs-lookup"><span data-stu-id="d3766-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="d3766-120">默认情况下，报告显示最近 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="d3766-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="d3766-121">此报告不直接在邮件流仪表板或[报表](mail-flow-insights-v2.md)[仪表板中提供](view-mail-flow-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="d3766-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="d3766-122">除了单击"新用户转发电子邮件见解"中的"查看与见解"链接关联的报告外，您还可以通过以下操作访问报告：</span><span class="sxs-lookup"><span data-stu-id="d3766-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="d3766-123">单击 **正在转发电子邮件见解** 的新域 [的详细信息中的"转发通知报告"链接](mfi-new-domains-being-forwarded-email.md)。</span><span class="sxs-lookup"><span data-stu-id="d3766-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="d3766-124">打开 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="d3766-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="d3766-125">转发修改报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="d3766-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="d3766-126">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="d3766-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d3766-127">**显示其数据：新转发用户**：</span><span class="sxs-lookup"><span data-stu-id="d3766-127">**Show data for: New forwarding users**:</span></span>

  ![转发修改报告中的新转发用户视图](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="d3766-129">**显示其数据：新转发域**：</span><span class="sxs-lookup"><span data-stu-id="d3766-129">**Show data for: New forwarding domains**:</span></span>

  ![转发修改报告中新的转发域视图](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="d3766-131">如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="d3766-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="d3766-132">转发修改报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="d3766-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="d3766-133">如果单击 **"查看详细信息"表**，则显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="d3766-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d3766-134">**显示其数据：新转发用户**：</span><span class="sxs-lookup"><span data-stu-id="d3766-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="d3766-135">**名称**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d3766-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="d3766-136">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="d3766-136">**Forwarding type**</span></span>
  - <span data-ttu-id="d3766-137">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="d3766-137">**Recipient address**</span></span>
  - <span data-ttu-id="d3766-138">**Details**</span><span class="sxs-lookup"><span data-stu-id="d3766-138">**Details**</span></span>
  - <span data-ttu-id="d3766-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="d3766-139">**Count**</span></span>
  - <span data-ttu-id="d3766-140">**第一个转发日期**</span><span class="sxs-lookup"><span data-stu-id="d3766-140">**First forward date**</span></span>

- <span data-ttu-id="d3766-141">**显示其数据：新转发域**：</span><span class="sxs-lookup"><span data-stu-id="d3766-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="d3766-142">**名称**：发件人的电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="d3766-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="d3766-143">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="d3766-143">**Forwarding type**</span></span>
  - <span data-ttu-id="d3766-144">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="d3766-144">**Recipient address**</span></span>
  - <span data-ttu-id="d3766-145">**Details**</span><span class="sxs-lookup"><span data-stu-id="d3766-145">**Details**</span></span>
  - <span data-ttu-id="d3766-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="d3766-146">**Count**</span></span>
  - <span data-ttu-id="d3766-147">**第一个转发日期**</span><span class="sxs-lookup"><span data-stu-id="d3766-147">**First forward date**</span></span>

<span data-ttu-id="d3766-148">如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="d3766-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d3766-149">如果从表中选择一行，将显示"详细信息"飞出，并包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="d3766-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="d3766-150">**名称**：这是发件人的电子邮件地址 (显示其数据 **：** 新转发用户查看) 或发件人的电子邮件域 (**从"** 显示数据：新建转发域视图") 。</span><span class="sxs-lookup"><span data-stu-id="d3766-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="d3766-151">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="d3766-151">**Forwarding type**</span></span>
- <span data-ttu-id="d3766-152">**收件人**</span><span class="sxs-lookup"><span data-stu-id="d3766-152">**Recipient**</span></span>
- <span data-ttu-id="d3766-153">**Details**</span><span class="sxs-lookup"><span data-stu-id="d3766-153">**Details**</span></span>
- <span data-ttu-id="d3766-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="d3766-154">**Count**</span></span>
- <span data-ttu-id="d3766-155">**开始日期**</span><span class="sxs-lookup"><span data-stu-id="d3766-155">**Start date**</span></span>
- <span data-ttu-id="d3766-156">**建议**：你可以在此处单击链接以在 Microsoft 365 管理中心管理用户。</span><span class="sxs-lookup"><span data-stu-id="d3766-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

!["转发修改"报告中"新建转发用户"视图的详细信息表中的详细信息飞出](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="d3766-158">若要返回到报告视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="d3766-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3766-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3766-159">Related topics</span></span>

<span data-ttu-id="d3766-160">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="d3766-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
