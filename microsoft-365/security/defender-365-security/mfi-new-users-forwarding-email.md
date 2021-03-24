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
description: 管理员可以了解如何使用安全与合规中心中的"新用户转发电子邮件见解&以调查其组织中用户何时将邮件转发到新域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055199"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="719fb-103">新用户在安全与合规中心转发&见解</span><span class="sxs-lookup"><span data-stu-id="719fb-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="719fb-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="719fb-104">**Applies to**</span></span>
- [<span data-ttu-id="719fb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="719fb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="719fb-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="719fb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="719fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="719fb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="719fb-108">当组织中新的用户帐户突然开始将电子邮件转发到外部域时，这是可疑的。</span><span class="sxs-lookup"><span data-stu-id="719fb-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="719fb-109">当 **组织中新** 创建的用户将邮件转发到外部域时，安全与合规中心 [&](https://protection.office.com) 转发的电子邮件见解会通知你。</span><span class="sxs-lookup"><span data-stu-id="719fb-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="719fb-110">此条件可能指示已使用遭到入侵的管理员帐户创建新用户。</span><span class="sxs-lookup"><span data-stu-id="719fb-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="719fb-111">如果您怀疑帐户已被泄露，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="719fb-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="719fb-112">此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。</span><span class="sxs-lookup"><span data-stu-id="719fb-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新用户转发电子邮件见解](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="719fb-114">单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括指向本文稍后所述的转发修改报告[](#forwarding-modifications-report)的链接。</span><span class="sxs-lookup"><span data-stu-id="719fb-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![单击"新用户转发电子邮件见解"后显示的详细信息飞出](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="719fb-116">单击报表仪表板或仪表板上"热门见解"&建议"区域中的"查看全部"后，选择见解后， (**进入** 此 \>  <https://protection.office.com/insightdashboard> 详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="719fb-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="719fb-117">可以单击" **查看与见解关联的** 报告"链接转到"转发修改" **报告，如下** 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="719fb-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="719fb-118">转发修改报告</span><span class="sxs-lookup"><span data-stu-id="719fb-118">Forwarding modifications report</span></span>

<span data-ttu-id="719fb-119">转发 **修改报告显示** 有关从组织中发件人自动转发的邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="719fb-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="719fb-120">将邮件转发到外部域的新创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="719fb-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="719fb-121">将邮件转发到组织中其他发件人从未转发给的外部域的帐户。</span><span class="sxs-lookup"><span data-stu-id="719fb-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="719fb-122">这些类型的转发邮件可能会带来安全或合规性风险，并可能指示帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="719fb-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="719fb-123">该报告包含最多 90 天的数据。</span><span class="sxs-lookup"><span data-stu-id="719fb-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="719fb-124">默认情况下，报告显示最近 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="719fb-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="719fb-125">此报告不能直接在邮件流仪表板或[报表仪表板](mail-flow-insights-v2.md)[中提供](view-mail-flow-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="719fb-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="719fb-126">除了单击"新用户转发电子邮件见解"中的"查看与见解关联的报告"链接，您还可以通过以下操作访问报告：</span><span class="sxs-lookup"><span data-stu-id="719fb-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="719fb-127">单击 **"正在转发的新** 域"电子邮件见解的详细信息中的 ["转发通知报告"链接](mfi-new-domains-being-forwarded-email.md)。</span><span class="sxs-lookup"><span data-stu-id="719fb-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="719fb-128">打开 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="719fb-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="719fb-129">转发修改报告的报表视图</span><span class="sxs-lookup"><span data-stu-id="719fb-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="719fb-130">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="719fb-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="719fb-131">**显示数据：新转发用户**：</span><span class="sxs-lookup"><span data-stu-id="719fb-131">**Show data for: New forwarding users**:</span></span>

  ![转发修改报告中的新转发用户视图](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="719fb-133">**显示数据：新转发域**：</span><span class="sxs-lookup"><span data-stu-id="719fb-133">**Show data for: New forwarding domains**:</span></span>

  ![转发修改报告中的新转发域视图](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="719fb-135">如果 **单击筛选器中的** 报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="719fb-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="719fb-136">转发修改报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="719fb-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="719fb-137">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="719fb-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="719fb-138">**显示数据：新转发用户**：</span><span class="sxs-lookup"><span data-stu-id="719fb-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="719fb-139">**名称**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="719fb-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="719fb-140">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="719fb-140">**Forwarding type**</span></span>
  - <span data-ttu-id="719fb-141">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="719fb-141">**Recipient address**</span></span>
  - <span data-ttu-id="719fb-142">**Details**</span><span class="sxs-lookup"><span data-stu-id="719fb-142">**Details**</span></span>
  - <span data-ttu-id="719fb-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="719fb-143">**Count**</span></span>
  - <span data-ttu-id="719fb-144">**第一个转发日期**</span><span class="sxs-lookup"><span data-stu-id="719fb-144">**First forward date**</span></span>

- <span data-ttu-id="719fb-145">**显示数据：新转发域**：</span><span class="sxs-lookup"><span data-stu-id="719fb-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="719fb-146">**名称**：发件人的电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="719fb-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="719fb-147">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="719fb-147">**Forwarding type**</span></span>
  - <span data-ttu-id="719fb-148">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="719fb-148">**Recipient address**</span></span>
  - <span data-ttu-id="719fb-149">**Details**</span><span class="sxs-lookup"><span data-stu-id="719fb-149">**Details**</span></span>
  - <span data-ttu-id="719fb-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="719fb-150">**Count**</span></span>
  - <span data-ttu-id="719fb-151">**第一个转发日期**</span><span class="sxs-lookup"><span data-stu-id="719fb-151">**First forward date**</span></span>

<span data-ttu-id="719fb-152">如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="719fb-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="719fb-153">如果从表中选择一行，将显示"详细信息"飞出，并包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="719fb-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="719fb-154">名称：这是发件人的电子邮件地址 ("显示数据"中的"新建转发用户"视图) 或发件人的电子邮件域 (from **Show data for： New forwarding domains** view) 。</span><span class="sxs-lookup"><span data-stu-id="719fb-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="719fb-155">**转发类型**</span><span class="sxs-lookup"><span data-stu-id="719fb-155">**Forwarding type**</span></span>
- <span data-ttu-id="719fb-156">**收件人**</span><span class="sxs-lookup"><span data-stu-id="719fb-156">**Recipient**</span></span>
- <span data-ttu-id="719fb-157">**Details**</span><span class="sxs-lookup"><span data-stu-id="719fb-157">**Details**</span></span>
- <span data-ttu-id="719fb-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="719fb-158">**Count**</span></span>
- <span data-ttu-id="719fb-159">**开始日期**</span><span class="sxs-lookup"><span data-stu-id="719fb-159">**Start date**</span></span>
- <span data-ttu-id="719fb-160">**建议**：你可以从此处单击链接以在 Microsoft 365 管理中心管理用户。</span><span class="sxs-lookup"><span data-stu-id="719fb-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

!["转发修改"报告中"新建转发用户"视图的详细信息表中的"详细信息"飞出](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="719fb-162">若要返回到报告视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="719fb-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="719fb-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="719fb-163">Related topics</span></span>

<span data-ttu-id="719fb-164">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="719fb-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
