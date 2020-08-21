---
title: 新用户转发电子邮件见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解如何使用安全 & 合规中心的新用户转发电子邮件见解来调查其组织的用户何时将邮件转发到新域。
ms.openlocfilehash: cb2e16d321e181916219e3425c26e59ebe31b866
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826963"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="52039-103">新用户在安全与合规中心转发&见解</span><span class="sxs-lookup"><span data-stu-id="52039-103">New users forwarding email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="52039-104">当贵组织的新用户帐户突然开始将电子邮件转发到外部域时，它是可疑的。</span><span class="sxs-lookup"><span data-stu-id="52039-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="52039-105">当 **组织中新创建的新用户** 要转发到外部域时，将向您发送转发电子邮件见解的新域会通知您。</span><span class="sxs-lookup"><span data-stu-id="52039-105">The **New domains being forwarded email** insight notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="52039-106">这种情况可能指示已使用被阻止的管理员帐户创建新用户。</span><span class="sxs-lookup"><span data-stu-id="52039-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="52039-107">如果您所在帐户已被入入入攻击，请参阅"[响应被到解的电子邮件帐户"。](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)</span><span class="sxs-lookup"><span data-stu-id="52039-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="52039-108">仅当检测到问题时，该见解是出现的，并且显示在"转 [发报告"页面上](view-mail-flow-reports.md#forwarding-report) 。</span><span class="sxs-lookup"><span data-stu-id="52039-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新用户转发电子邮件见解](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="52039-110">单击小部件时，会出现一个浮出控件，您会在其中找到有关转发邮件的更多详细信息，其中包括指向 [本主题](#forwarding-modifications-report) 后面所述的转发修改报告的链接。</span><span class="sxs-lookup"><span data-stu-id="52039-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![单击"新用户转发电子邮件见解"后显示的浮出控件](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="52039-112">在单击"查看 (报表仪表板"或"报表仪表板"的"查看上级**见解&"区域中选择**所有的见解后，还可以转到**此**详细信息**View all** \> **Dashboard** <https://protection.office.com/insightdashboard>) 。</span><span class="sxs-lookup"><span data-stu-id="52039-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="52039-113">您可以单击 **与"见解"链接关联的"查看** "报告，以转到 **下** 一节中所述的"转发修改"报告。</span><span class="sxs-lookup"><span data-stu-id="52039-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="52039-114">转发修改报告</span><span class="sxs-lookup"><span data-stu-id="52039-114">Forwarding modifications report</span></span>

<span data-ttu-id="52039-115">**"转发修改"报告**显示有关从您组织的发件人自动转发的邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="52039-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="52039-116">新创建的帐户，可将邮件转发到外部域。</span><span class="sxs-lookup"><span data-stu-id="52039-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="52039-117">将邮件转发到未被组织中其他发件人转发到的外部域的帐户。</span><span class="sxs-lookup"><span data-stu-id="52039-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="52039-118">这些类型的转发邮件可能带来安全或合规性风险，并且可能指示帐户被了安全。</span><span class="sxs-lookup"><span data-stu-id="52039-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="52039-119">此报告包含多达 90 天的数据。</span><span class="sxs-lookup"><span data-stu-id="52039-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="52039-120">默认情况下，报告显示最近 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="52039-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="52039-121">此报告不能在邮件流仪表板或 [报表仪表板](mail-flow-insights-v2.md) 中 [直接提供](view-mail-flow-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="52039-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="52039-122">除了单击新**用户转发**电子邮件见解中与见解链接关联的"查看"报告**New users forwarding email**，你还可以通过以下方式访问报告：</span><span class="sxs-lookup"><span data-stu-id="52039-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="52039-123">Clicking the **Forwarding notifications report link** in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="52039-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="52039-124">打开 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="52039-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="52039-125">转发修改报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="52039-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="52039-126">下面的图表提供了报表视图：</span><span class="sxs-lookup"><span data-stu-id="52039-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="52039-127">**显示数据：新转发用户**：</span><span class="sxs-lookup"><span data-stu-id="52039-127">**Show data for: New forwarding users**:</span></span>

  !["转发修改"报告中的新转发用户查看](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="52039-129">**显示数据：新转发域**：</span><span class="sxs-lookup"><span data-stu-id="52039-129">**Show data for: New forwarding domains**:</span></span>

  ![转发修改报告中的新转发域视图](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="52039-131">如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="52039-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="52039-132">转发修改报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="52039-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="52039-133">如果您单击 **"查看详细信息**表"，显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="52039-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="52039-134">**显示数据：新转发用户**：</span><span class="sxs-lookup"><span data-stu-id="52039-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="52039-135">**名称**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="52039-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="52039-136">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="52039-136">**Forwarding type**</span></span>
  - <span data-ttu-id="52039-137">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="52039-137">**Recipient address**</span></span>
  - <span data-ttu-id="52039-138">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="52039-138">**Details**</span></span>
  - <span data-ttu-id="52039-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="52039-139">**Count**</span></span>
  - <span data-ttu-id="52039-140">**第一个前进日期**</span><span class="sxs-lookup"><span data-stu-id="52039-140">**First forward date**</span></span>

- <span data-ttu-id="52039-141">**显示数据：新转发域**：</span><span class="sxs-lookup"><span data-stu-id="52039-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="52039-142">**名称**：发件人的电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="52039-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="52039-143">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="52039-143">**Forwarding type**</span></span>
  - <span data-ttu-id="52039-144">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="52039-144">**Recipient address**</span></span>
  - <span data-ttu-id="52039-145">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="52039-145">**Details**</span></span>
  - <span data-ttu-id="52039-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="52039-146">**Count**</span></span>
  - <span data-ttu-id="52039-147">**第一个前进日期**</span><span class="sxs-lookup"><span data-stu-id="52039-147">**First forward date**</span></span>

<span data-ttu-id="52039-148">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="52039-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="52039-149">如果从表中选择行，" **详细信息"** 浮出控件将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="52039-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="52039-150">**名称**：这是发件人的电子邮件地址 (**显示数据的：新转发用户** 查看) 或发件人在显示数据的 **中的电子邮件域 (： 新转发域** 视图) 集合。</span><span class="sxs-lookup"><span data-stu-id="52039-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="52039-151">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="52039-151">**Forwarding type**</span></span>
- <span data-ttu-id="52039-152">**收件人**</span><span class="sxs-lookup"><span data-stu-id="52039-152">**Recipient**</span></span>
- <span data-ttu-id="52039-153">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="52039-153">**Details**</span></span>
- <span data-ttu-id="52039-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="52039-154">**Count**</span></span>
- <span data-ttu-id="52039-155">**开始日期**</span><span class="sxs-lookup"><span data-stu-id="52039-155">**Start date**</span></span>
- <span data-ttu-id="52039-156">**建议**：从此处，单击此链接以在 Microsoft 365 管理中心管理用户。</span><span class="sxs-lookup"><span data-stu-id="52039-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![从"转发修改"报告中查看的"新建转发用户"视图的详细信息表格中的浮出控件](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="52039-158">若要返回报告视图，请单击"查看**报告"。**</span><span class="sxs-lookup"><span data-stu-id="52039-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="52039-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="52039-159">Related topics</span></span>

<span data-ttu-id="52039-160">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="52039-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
