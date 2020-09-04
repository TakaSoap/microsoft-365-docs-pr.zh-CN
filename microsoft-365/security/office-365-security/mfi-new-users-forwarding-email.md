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
description: 管理员可以了解如何使用安全 & 合规中心中的新用户转发电子邮件，以调查组织中的用户何时将邮件转发到新域。
ms.openlocfilehash: 4d8c88cef182ab1c521d23970797e4746e188916
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357362"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="8d768-103">新用户在安全 & 合规中心转发电子邮件洞察力</span><span class="sxs-lookup"><span data-stu-id="8d768-103">New users forwarding email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="8d768-104">当组织中的新用户帐户突然开始将电子邮件转发到外部域时，这是可疑的。</span><span class="sxs-lookup"><span data-stu-id="8d768-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="8d768-105">当组织中新创建的用户将邮件转发到外部域时，将在[安全 & 合规中心](https://protection.office.com)中**转发的新域**将向您发出通知。</span><span class="sxs-lookup"><span data-stu-id="8d768-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="8d768-106">这种情况可能表示使用了已损坏的管理员帐户来创建新用户。</span><span class="sxs-lookup"><span data-stu-id="8d768-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="8d768-107">如果您怀疑帐户已损坏，请参阅 [响应已泄露的电子邮件帐户](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)。</span><span class="sxs-lookup"><span data-stu-id="8d768-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="8d768-108">此洞察力仅在检测到问题时显示，并显示在 " [转发报告](view-mail-flow-reports.md#forwarding-report) " 页上。</span><span class="sxs-lookup"><span data-stu-id="8d768-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新用户转发电子邮件见解](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="8d768-110">当您单击小组件时，将显示一个弹出对话框，可在其中找到有关转发邮件的更多详细信息，包括指向本主题后面所述的 [转发修改报告](#forwarding-modifications-report) 的链接。</span><span class="sxs-lookup"><span data-stu-id="8d768-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![单击新用户转发电子邮件洞察力后显示的详细信息浮出控件](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="8d768-112">当您在 (**报告**仪表板 "或") 上的 "**热门见解 & 建议**" 区域中单击 "**查看全部**" 后，您还可以转到此详细信息页面 \> **Dashboard** <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="8d768-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="8d768-113">您可以单击 " **查看与洞察力相关的报告** " 链接以转到 " **转发修改" 报告** ，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="8d768-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="8d768-114">转发修改报告</span><span class="sxs-lookup"><span data-stu-id="8d768-114">Forwarding modifications report</span></span>

<span data-ttu-id="8d768-115">" **转发修改" 报告** 显示有关自动从组织中的发件人转发的邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="8d768-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="8d768-116">将邮件转发到外部域的新创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="8d768-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="8d768-117">将邮件转发到组织中的其他发件人从未转发给外部域的帐户。</span><span class="sxs-lookup"><span data-stu-id="8d768-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="8d768-118">这些转发邮件类型可能会带来安全或合规性风险，并可能指示已泄露的帐户。</span><span class="sxs-lookup"><span data-stu-id="8d768-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="8d768-119">此报告包含最长为90天的数据。</span><span class="sxs-lookup"><span data-stu-id="8d768-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="8d768-120">默认情况下，此报告显示过去7天的数据。</span><span class="sxs-lookup"><span data-stu-id="8d768-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="8d768-121">此报告不能直接在 [邮件流仪表板](mail-flow-insights-v2.md) 或 [报表仪表板](view-mail-flow-reports.md)中使用。</span><span class="sxs-lookup"><span data-stu-id="8d768-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="8d768-122">除了单击**新用户发送电子邮件**见解中的 "**查看与洞察力相关的查看报告**" 链接之外，您还可以通过以下方式获取报告：</span><span class="sxs-lookup"><span data-stu-id="8d768-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="8d768-123">在要转发的新域的详细信息中单击 " **转发通知报告** " 链接， [了解如何理解电子邮件](mfi-new-domains-being-forwarded-email.md)。</span><span class="sxs-lookup"><span data-stu-id="8d768-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="8d768-124">打开 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="8d768-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8d768-125">"转发修改" 报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="8d768-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="8d768-126">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="8d768-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8d768-127">**显示以下项的数据：新的转发用户**：</span><span class="sxs-lookup"><span data-stu-id="8d768-127">**Show data for: New forwarding users**:</span></span>

  ![转发修改报告中的新转发用户视图](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="8d768-129">**显示以下项的数据：新的转发域**：</span><span class="sxs-lookup"><span data-stu-id="8d768-129">**Show data for: New forwarding domains**:</span></span>

  ![转发修改报告中的新的转发域视图](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="8d768-131">如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="8d768-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8d768-132">转发修改报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="8d768-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="8d768-133">如果您单击 " **查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="8d768-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="8d768-134">**显示以下项的数据：新的转发用户**：</span><span class="sxs-lookup"><span data-stu-id="8d768-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="8d768-135">**名称**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8d768-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="8d768-136">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="8d768-136">**Forwarding type**</span></span>
  - <span data-ttu-id="8d768-137">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="8d768-137">**Recipient address**</span></span>
  - <span data-ttu-id="8d768-138">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8d768-138">**Details**</span></span>
  - <span data-ttu-id="8d768-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="8d768-139">**Count**</span></span>
  - <span data-ttu-id="8d768-140">**第一次转发日期**</span><span class="sxs-lookup"><span data-stu-id="8d768-140">**First forward date**</span></span>

- <span data-ttu-id="8d768-141">**显示以下项的数据：新的转发域**：</span><span class="sxs-lookup"><span data-stu-id="8d768-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="8d768-142">**名称**：发件人的电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="8d768-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="8d768-143">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="8d768-143">**Forwarding type**</span></span>
  - <span data-ttu-id="8d768-144">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="8d768-144">**Recipient address**</span></span>
  - <span data-ttu-id="8d768-145">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8d768-145">**Details**</span></span>
  - <span data-ttu-id="8d768-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="8d768-146">**Count**</span></span>
  - <span data-ttu-id="8d768-147">**第一次转发日期**</span><span class="sxs-lookup"><span data-stu-id="8d768-147">**First forward date**</span></span>

<span data-ttu-id="8d768-148">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="8d768-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8d768-149">如果从表中选择行，则会显示 **详细** 信息弹出项，其中包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="8d768-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="8d768-150">**名称**：这是发件人的电子邮件地址 (来自 **显示以下项的数据：新的转发用户** 查看) 或发件人的电子邮件域 (来自 **显示以下项的数据：新的转发域** 视图) 。</span><span class="sxs-lookup"><span data-stu-id="8d768-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="8d768-151">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="8d768-151">**Forwarding type**</span></span>
- <span data-ttu-id="8d768-152">**收件人**</span><span class="sxs-lookup"><span data-stu-id="8d768-152">**Recipient**</span></span>
- <span data-ttu-id="8d768-153">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8d768-153">**Details**</span></span>
- <span data-ttu-id="8d768-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="8d768-154">**Count**</span></span>
- <span data-ttu-id="8d768-155">**开始日期**</span><span class="sxs-lookup"><span data-stu-id="8d768-155">**Start date**</span></span>
- <span data-ttu-id="8d768-156">**建议**：在此，可以单击 "Microsoft 365 管理中心" 中的 "管理用户" 的链接。</span><span class="sxs-lookup"><span data-stu-id="8d768-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

!["转发修改报告" 中 "新转发用户" 视图的 "详细信息" 表格中的详细信息表格](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="8d768-158">若要返回到 "报告" 视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="8d768-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d768-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d768-159">Related topics</span></span>

<span data-ttu-id="8d768-160">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="8d768-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
