---
title: 查看安全与合规中心内的电子邮件安全报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 了解如何查找和使用组织的电子邮件安全报告。 安全 & 合规性中心中提供了电子邮件安全报告。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 226f147dec7795ce6f8314a04218eab84e609218
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937010"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="33e01-104">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="33e01-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="33e01-105">[安全 & 合规性中心](https://protection.office.com)中提供了多种报告，可帮助您了解电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能如何保护您的组织）。</span><span class="sxs-lookup"><span data-stu-id="33e01-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="33e01-106">如果您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports)，则可以转到 "**报告**" \> **仪表板**，在安全 & 合规中心中查看这些报告。</span><span class="sxs-lookup"><span data-stu-id="33e01-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="33e01-107">若要直接转到 "报表" 仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-107">To go directly to the reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Security & 合规中心中的报告仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="33e01-109">已泄露用户报告</span><span class="sxs-lookup"><span data-stu-id="33e01-109">Compromised users report</span></span>

<span data-ttu-id="33e01-110">"已**泄露的用户**" 报告显示在最近7天内被标记为**可疑**或**受限制**的用户帐户数。</span><span class="sxs-lookup"><span data-stu-id="33e01-110">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="33e01-111">在上述任一状态中的帐户都有问题或甚至已损坏。</span><span class="sxs-lookup"><span data-stu-id="33e01-111">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="33e01-112">通过频繁使用，您可以使用报告发现可疑或受限帐户中的峰值、甚至是趋势。</span><span class="sxs-lookup"><span data-stu-id="33e01-112">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="33e01-113">有关受损用户的详细信息，请参阅[响应已泄露的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-113">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="33e01-114">聚合视图显示最近90天的数据，详细信息视图显示最近30天的数据。</span><span class="sxs-lookup"><span data-stu-id="33e01-114">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="33e01-115">若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "已**损坏用户**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-115">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="33e01-116">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-116">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="33e01-117">可以通过单击 "**筛选**器" 并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="33e01-117">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="33e01-118">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-118">**Start date** and **End date**</span></span>

- <span data-ttu-id="33e01-119">**可疑**：用户帐户发送了可疑电子邮件，并且存在受限制的发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="33e01-119">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="33e01-120">**受限**：由于高度可疑的模式，用户帐户受到限制，无法发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="33e01-120">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![受到威胁的用户在 Microsoft 365 中显示的报告](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

<span data-ttu-id="33e01-122">如果单击 "**查看详细信息表**"，则可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-122">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="33e01-123">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="33e01-123">**Creation time**</span></span>
- <span data-ttu-id="33e01-124">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="33e01-124">**User ID**</span></span>
- <span data-ttu-id="33e01-125">**Action**</span><span class="sxs-lookup"><span data-stu-id="33e01-125">**Action**</span></span>

<span data-ttu-id="33e01-126">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-126">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="33e01-127">加密报告</span><span class="sxs-lookup"><span data-stu-id="33e01-127">Encryption report</span></span>

<span data-ttu-id="33e01-128">**加密报告**在 EOP 中可用（使用 exchange online 中的邮箱订阅或独立 EOP，无需 Exchange online 邮箱）。</span><span class="sxs-lookup"><span data-stu-id="33e01-128">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="33e01-129">您组织的安全团队可以使用此报告中的信息来标识模式，并主动应用或调整敏感电子邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="33e01-129">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="33e01-130">例如：</span><span class="sxs-lookup"><span data-stu-id="33e01-130">For example:</span></span>

- <span data-ttu-id="33e01-131">如果您看到用户加密了大量的电子邮件，则可能需要添加加密策略以对某些用例自动进行加密。</span><span class="sxs-lookup"><span data-stu-id="33e01-131">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="33e01-132">有关详细信息，请参阅[在 Microsoft 365 中定义用于加密电子邮件的邮件流规则](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-132">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="33e01-133">如果有许多可用的加密模板，但没有用户正在使用它们，则可以考察用户是否需要功能培训。</span><span class="sxs-lookup"><span data-stu-id="33e01-133">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="33e01-134">"聚合" 视图允许筛选过去的90天，而 "详细信息" 视图允许筛选10天。</span><span class="sxs-lookup"><span data-stu-id="33e01-134">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="33e01-135">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**加密报告**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-135">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="33e01-136">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-136">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="33e01-137">若要了解有关加密的详细信息，请参阅[Microsoft 365 中的电子邮件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-137">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="33e01-138">加密报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="33e01-138">Report view for the Encryption report</span></span>

<span data-ttu-id="33e01-139">您可以在图表上使用以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="33e01-139">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="33e01-140">**数据查看依据：邮件加密报告**和**分解方式：加密方法**：以下是可用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="33e01-140">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="33e01-141">**按用户加密**</span><span class="sxs-lookup"><span data-stu-id="33e01-141">**Encryption by user**</span></span>
  - <span data-ttu-id="33e01-142">**按策略加密**</span><span class="sxs-lookup"><span data-stu-id="33e01-142">**Encryption by policy**</span></span>

  <span data-ttu-id="33e01-143">如果单击 "**筛选器**"，则可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="33e01-143">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="33e01-144">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-144">**Start date** and **End date**</span></span>
  - <span data-ttu-id="33e01-145">加密方法。</span><span class="sxs-lookup"><span data-stu-id="33e01-145">Encryption method.</span></span>
  - <span data-ttu-id="33e01-146">加密模板。</span><span class="sxs-lookup"><span data-stu-id="33e01-146">Encryption template.</span></span>

- <span data-ttu-id="33e01-147">**数据查看依据：邮件加密报告**和**分解方式：加密模板**：以下是可用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="33e01-147">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="33e01-148">**请勿转发**</span><span class="sxs-lookup"><span data-stu-id="33e01-148">**Do not forward**</span></span>
  - <span data-ttu-id="33e01-149">**仅加密**</span><span class="sxs-lookup"><span data-stu-id="33e01-149">**Encrypt only**</span></span>
  - <span data-ttu-id="33e01-150">**OME 以前**</span><span class="sxs-lookup"><span data-stu-id="33e01-150">**OME previous**</span></span>
  - <span data-ttu-id="33e01-151">**自定义**</span><span class="sxs-lookup"><span data-stu-id="33e01-151">**Custom**</span></span>

  <span data-ttu-id="33e01-152">如果单击 "**筛选器**"，则可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="33e01-152">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="33e01-153">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-153">**Start date** and **End date**</span></span>
  - <span data-ttu-id="33e01-154">加密方法</span><span class="sxs-lookup"><span data-stu-id="33e01-154">Encryption method</span></span>
  - <span data-ttu-id="33e01-155">加密模板</span><span class="sxs-lookup"><span data-stu-id="33e01-155">Encryption template</span></span>

- <span data-ttu-id="33e01-156">**按数据查看：前5个收件人域**：此视图显示包含前5个收件人域的已发送邮件计数的饼图。</span><span class="sxs-lookup"><span data-stu-id="33e01-156">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="33e01-157">如果单击 "**筛选器**"，则可以选择 "**开始日期**" 和 "**结束日期**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-157">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="33e01-158">加密报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="33e01-158">Details table view for the Encryption report</span></span>

<span data-ttu-id="33e01-159">如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="33e01-159">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="33e01-160">**分解方式：加密方法**或**分解方式：加密模板**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-160">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="33e01-161">**Date**</span><span class="sxs-lookup"><span data-stu-id="33e01-161">**Date**</span></span>
  - <span data-ttu-id="33e01-162">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="33e01-162">**Sender address**</span></span>
  - <span data-ttu-id="33e01-163">**加密模板**</span><span class="sxs-lookup"><span data-stu-id="33e01-163">**Encryption template**</span></span>
  - <span data-ttu-id="33e01-164">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="33e01-164">**Encryption method**</span></span>
  - <span data-ttu-id="33e01-165">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="33e01-165">**Recipient address**</span></span>
  - <span data-ttu-id="33e01-166">**主题**</span><span class="sxs-lookup"><span data-stu-id="33e01-166">**Subject**</span></span>

- <span data-ttu-id="33e01-167">**数据查看依据：前5个收件人域**：</span><span class="sxs-lookup"><span data-stu-id="33e01-167">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="33e01-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="33e01-168">**Date**</span></span>
  - <span data-ttu-id="33e01-169">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="33e01-169">**Recipient domain**</span></span>
  - <span data-ttu-id="33e01-170">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="33e01-170">**Message count**</span></span>
  
<span data-ttu-id="33e01-171">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="33e01-171">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="33e01-172">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="33e01-173">加密方法</span><span class="sxs-lookup"><span data-stu-id="33e01-173">Encryption method</span></span>
- <span data-ttu-id="33e01-174">加密模板</span><span class="sxs-lookup"><span data-stu-id="33e01-174">Encryption template</span></span>

<span data-ttu-id="33e01-175">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-175">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="33e01-176">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="33e01-176">Mailflow status report</span></span>

<span data-ttu-id="33e01-177">**邮件流状态报告**包含有关恶意软件、垃圾邮件、网络钓鱼和边缘阻止的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="33e01-177">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="33e01-178">有关更多详细信息，请参阅[邮件流 status report](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="33e01-178">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detection-in-email-report"></a><span data-ttu-id="33e01-179">电子邮件中的恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="33e01-179">Malware detection in email report</span></span>

<span data-ttu-id="33e01-180">"**电子邮件中的恶意软件检测**" 报告显示传入和传出电子邮件（由 Exchange Online PROTECTION 或 EOP 检测到的恶意软件）中的恶意软件检测的相关信息。</span><span class="sxs-lookup"><span data-stu-id="33e01-180">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="33e01-181">有关 EOP 中的恶意软件保护的详细信息，请参阅[EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-181">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="33e01-182">聚合视图筛选器允许90天，而详细信息表筛选器仅允许10天。</span><span class="sxs-lookup"><span data-stu-id="33e01-182">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="33e01-183">若要查看报告，请打开[安全 & 合规中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 **"在电子邮件中检测到恶意软件"**。</span><span class="sxs-lookup"><span data-stu-id="33e01-183">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="33e01-184">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-184">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

!["报告" 仪表板中电子邮件小组件中的恶意软件检测](../../media/malware-detections-widget.png)

<span data-ttu-id="33e01-186">您可以通过单击 "**筛选**器" 并选择 "筛选器" 来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="33e01-186">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="33e01-187">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-187">**Start date** and **End date**</span></span>
- <span data-ttu-id="33e01-188">**进货**</span><span class="sxs-lookup"><span data-stu-id="33e01-188">**Inbound**</span></span>
- <span data-ttu-id="33e01-189">**出站**</span><span class="sxs-lookup"><span data-stu-id="33e01-189">**Outbound**</span></span>

![电子邮件中的恶意软件检测报告中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="33e01-191">如果单击 "**查看详细信息表**"，则可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-191">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="33e01-192">**Date**</span><span class="sxs-lookup"><span data-stu-id="33e01-192">**Date**</span></span>
- <span data-ttu-id="33e01-193">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="33e01-193">**Sender address**</span></span>
- <span data-ttu-id="33e01-194">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="33e01-194">**Recipient address**</span></span>
- <span data-ttu-id="33e01-195">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="33e01-195">**Message ID**</span></span>
- <span data-ttu-id="33e01-196">**主题**</span><span class="sxs-lookup"><span data-stu-id="33e01-196">**Subject**</span></span>
- <span data-ttu-id="33e01-197">**Filename**</span><span class="sxs-lookup"><span data-stu-id="33e01-197">**Filename**</span></span>
- <span data-ttu-id="33e01-198">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="33e01-198">**Malware name**</span></span>

<span data-ttu-id="33e01-199">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-199">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="33e01-200">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="33e01-200">Sent and received email report</span></span>

<span data-ttu-id="33e01-201">**发送和接收的电子邮件**报告包含有关恶意软件、垃圾邮件、邮件流规则（也称为传输规则）的信息，以及在电子邮件进入服务后进行的高级恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="33e01-201">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="33e01-202">有关详细信息，请参阅[发送和接收的电子邮件报告](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="33e01-202">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="33e01-203">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="33e01-203">Spam detections report</span></span>

<span data-ttu-id="33e01-204">**垃圾邮件检测**报告显示由 EOP 阻止的垃圾电子邮件。</span><span class="sxs-lookup"><span data-stu-id="33e01-204">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="33e01-205">邮件单独计数，而不是每个收件人。</span><span class="sxs-lookup"><span data-stu-id="33e01-205">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="33e01-206">例如，如果将相同的垃圾邮件发送给组织中的100收件人，则会将其计为一封邮件。</span><span class="sxs-lookup"><span data-stu-id="33e01-206">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="33e01-207">聚合视图允许90天筛选，而详细信息表允许进行10天的筛选。</span><span class="sxs-lookup"><span data-stu-id="33e01-207">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="33e01-208">若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "**垃圾邮件检测**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-208">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="33e01-209">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-209">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

!["报告" 仪表板中的 "垃圾邮件检测" 小部件](../../media/spam-detections-widget.png)

<span data-ttu-id="33e01-211">有关反垃圾邮件保护的详细信息，请参阅[EOP 中的反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-211">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="33e01-212">垃圾邮件检测报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="33e01-212">Report view for the Spam detections report</span></span>

<span data-ttu-id="33e01-213">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="33e01-213">The following charts are available in the report view:</span></span>

- <span data-ttu-id="33e01-214">**分解方式：操作**：显示以下事件类型：</span><span class="sxs-lookup"><span data-stu-id="33e01-214">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="33e01-215">**筛选出的垃圾邮件内容**</span><span class="sxs-lookup"><span data-stu-id="33e01-215">**Spam content filtered**</span></span>
  - <span data-ttu-id="33e01-216">**垃圾邮件 IP 阻止**</span><span class="sxs-lookup"><span data-stu-id="33e01-216">**Spam IP block**</span></span>
  - <span data-ttu-id="33e01-217">**垃圾邮件信封块**</span><span class="sxs-lookup"><span data-stu-id="33e01-217">**Spam envelope block**</span></span>
  - <span data-ttu-id="33e01-218">**垃圾邮件 DBEB 筛选器**：基于目录的边缘阻止（DBEB）</span><span class="sxs-lookup"><span data-stu-id="33e01-218">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="33e01-219">当您将鼠标指针悬停在图表中的某一天（数据点）上时，您可以看到该日已阻止的项目数，以及这些项目的分类方式。</span><span class="sxs-lookup"><span data-stu-id="33e01-219">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾邮件检测报告的报告视图中的操作视图](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="33e01-221">**分解方式：方向**：以下说明如下所示：</span><span class="sxs-lookup"><span data-stu-id="33e01-221">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="33e01-222">**进货**</span><span class="sxs-lookup"><span data-stu-id="33e01-222">**Inbound**</span></span>
  - <span data-ttu-id="33e01-223">**出站**</span><span class="sxs-lookup"><span data-stu-id="33e01-223">**Outbound**</span></span>

<span data-ttu-id="33e01-224">如果您在报告视图中单击 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="33e01-224">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="33e01-225">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-225">**Start date** and **End date**</span></span>
- <span data-ttu-id="33e01-226">方向值</span><span class="sxs-lookup"><span data-stu-id="33e01-226">Direction values</span></span>
- <span data-ttu-id="33e01-227">事件类型值</span><span class="sxs-lookup"><span data-stu-id="33e01-227">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="33e01-228">垃圾邮件检测报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="33e01-228">Details table view for the Spam detections report</span></span>

<span data-ttu-id="33e01-229">如果您在任何报告视图中单击 "**查看详细信息表**"，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-229">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="33e01-230">**Date**</span><span class="sxs-lookup"><span data-stu-id="33e01-230">**Date**</span></span>
- <span data-ttu-id="33e01-231">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="33e01-231">**Sender address**</span></span>
- <span data-ttu-id="33e01-232">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="33e01-232">**Recipient address**</span></span>
- <span data-ttu-id="33e01-233">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="33e01-233">**Event type**</span></span>
- <span data-ttu-id="33e01-234">**Action**</span><span class="sxs-lookup"><span data-stu-id="33e01-234">**Action**</span></span>
- <span data-ttu-id="33e01-235">**主题**</span><span class="sxs-lookup"><span data-stu-id="33e01-235">**Subject**</span></span>

<span data-ttu-id="33e01-236">如果单击 "详细信息" 表中的 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="33e01-236">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="33e01-237">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="33e01-238">方向值</span><span class="sxs-lookup"><span data-stu-id="33e01-238">Direction values</span></span>
- <span data-ttu-id="33e01-239">事件类型值</span><span class="sxs-lookup"><span data-stu-id="33e01-239">Event type values</span></span>

<span data-ttu-id="33e01-240">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-240">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="33e01-241">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="33e01-241">Spoof detections report</span></span>

<span data-ttu-id="33e01-242">**欺骗检测**报告显示检测到的欺骗邮件的数量以及这些邮件被视为 "好" （欺骗邮件出于合理商业原因而完成）。</span><span class="sxs-lookup"><span data-stu-id="33e01-242">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="33e01-243">有关哄骗的详细信息，请参阅[EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-243">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="33e01-244">报告的聚合视图允许在筛选过程中90天，而详细信息视图只允许进行10天的筛选。</span><span class="sxs-lookup"><span data-stu-id="33e01-244">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="33e01-245">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**欺骗检测**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-245">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="33e01-246">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-246">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

!["报告" 仪表板中的欺骗检测小部件](../../media/spoof-detections-widget.png)

<span data-ttu-id="33e01-248">当您将鼠标指针悬停在图表中的某一天（数据点）上时，您可以看到通过的欺骗邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="33e01-248">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="33e01-249">可以通过单击 "**筛选**器" 并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="33e01-249">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="33e01-250">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-250">**Start date** and **End date**</span></span>

- <span data-ttu-id="33e01-251">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="33e01-251">**Good mail**</span></span>

- <span data-ttu-id="33e01-252">**作为垃圾邮件捕获**</span><span class="sxs-lookup"><span data-stu-id="33e01-252">**Caught as spam**</span></span>

![欺骗检测报告中的报告视图](../../media/spoof-detections-report-view.png)

<span data-ttu-id="33e01-254">如果单击 "**查看详细信息表**"，则可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-254">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="33e01-255">**Date**</span><span class="sxs-lookup"><span data-stu-id="33e01-255">**Date**</span></span>
- <span data-ttu-id="33e01-256">**欺骗发件人**</span><span class="sxs-lookup"><span data-stu-id="33e01-256">**Spoofed sender**</span></span>
- <span data-ttu-id="33e01-257">**真正发件人**</span><span class="sxs-lookup"><span data-stu-id="33e01-257">**True sender**</span></span>
- <span data-ttu-id="33e01-258">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="33e01-258">**Sender IP**</span></span>
- <span data-ttu-id="33e01-259">**Action**</span><span class="sxs-lookup"><span data-stu-id="33e01-259">**Action**</span></span>
- <span data-ttu-id="33e01-260">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="33e01-260">**Message count**</span></span>

<span data-ttu-id="33e01-261">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-261">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="33e01-262">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="33e01-262">Threat protection status report</span></span>

<span data-ttu-id="33e01-263">"**威胁防护状态**报告" 在 EOP 和 OFFICE 365 ATP 中均可用。但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="33e01-263">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="33e01-264">例如，EOP 客户可以查看有关在电子邮件中检测到的恶意软件的信息，但不是关于[SharePoint Online、OneDrive 或 Microsoft 团队中检测到的恶意文件](atp-for-spo-odb-and-teams.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="33e01-264">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="33e01-265">有关 Office 365 ATP 报告的详细信息，请参阅[查看 office 365 高级威胁防护的报告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-265">For more information about Office 365 ATP reports, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span>

<span data-ttu-id="33e01-266">这是一个显示检测到并阻止的恶意电子邮件的智能报告，它使安全管理员能够确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="33e01-266">This is a smart report that shows malicious email that was detected and blocked, and it enables security admins to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="33e01-267">若要查看报告，请打开[安全 & 合规中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**威胁保护状态**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-267">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="33e01-268">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPV2AggregateReport> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-268">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>

![威胁防护状态](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)

<span data-ttu-id="33e01-270">默认情况下，图表显示过去7天的数据。</span><span class="sxs-lookup"><span data-stu-id="33e01-270">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="33e01-271">如果单击 "**筛选器**"，则可以选择一个90天的日期范围（试用订阅可能限制为30天）。</span><span class="sxs-lookup"><span data-stu-id="33e01-271">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="33e01-272">[！说明] [！说明] 详细信息表视图允许筛选30天。</span><span class="sxs-lookup"><span data-stu-id="33e01-272">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="33e01-273">威胁防护状态报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="33e01-273">Report view for the Threat protection status report</span></span>

<span data-ttu-id="33e01-274">可以使用以下视图：</span><span class="sxs-lookup"><span data-stu-id="33e01-274">The following views are available:</span></span>

- <span data-ttu-id="33e01-275">**查看数据的依据：概述**：显示以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-275">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="33e01-276">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="33e01-276">**Email malware**</span></span>
  - <span data-ttu-id="33e01-277">**电子邮件网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="33e01-277">**Email phish**</span></span>
  - <span data-ttu-id="33e01-278">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="33e01-278">**Content malware**</span></span>

- <span data-ttu-id="33e01-279">**数据查看依据：内容 \>恶意软件**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-279">**View data by: Content \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="33e01-280">**反恶意软件引擎**</span><span class="sxs-lookup"><span data-stu-id="33e01-280">**Anti-malware engine**</span></span>
  - <span data-ttu-id="33e01-281">**文件沙箱**</span><span class="sxs-lookup"><span data-stu-id="33e01-281">**File detonation**</span></span>

- <span data-ttu-id="33e01-282">**分解方式：检测技术**和**查看数据的方式：电子邮件 \> 网络钓鱼**：将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-282">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="33e01-283">**ATP 生成的 URL 信誉**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-283">**ATP-generated URL reputation**<sup>\*</sup></span></span>
  - <span data-ttu-id="33e01-284">**高级网络钓鱼筛选器**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-284">**Advanced phish filter**<sup>\*</sup></span></span>
  - <span data-ttu-id="33e01-285">**反欺骗： DMARC 故障**</span><span class="sxs-lookup"><span data-stu-id="33e01-285">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="33e01-286">**反欺骗：组织内**</span><span class="sxs-lookup"><span data-stu-id="33e01-286">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="33e01-287">**反欺骗：外部域**</span><span class="sxs-lookup"><span data-stu-id="33e01-287">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="33e01-288">**品牌模拟**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-288">**Brand impersonation**<sup>\*</sup></span></span>
  - <span data-ttu-id="33e01-289">**域模拟**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-289">**Domain impersonation**<sup>\*</sup></span></span>
  - <span data-ttu-id="33e01-290">**EOP URL 信誉**</span><span class="sxs-lookup"><span data-stu-id="33e01-290">**EOP URL reputation**</span></span>
  - <span data-ttu-id="33e01-291">**常规网络钓鱼筛选器**</span><span class="sxs-lookup"><span data-stu-id="33e01-291">**General phish filter**</span></span>
  - <span data-ttu-id="33e01-292">**其他**</span><span class="sxs-lookup"><span data-stu-id="33e01-292">**Others**</span></span>
  - <span data-ttu-id="33e01-293">**网络钓鱼 ZAP**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-293">**Phish ZAP**<sup>\*\*</sup></span></span>
  - <span data-ttu-id="33e01-294">**URL 沙箱**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-294">**URL detonation**<sup>\*\*</sup></span></span>
  - <span data-ttu-id="33e01-295">**用户模拟**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-295">**User Impersonation**<sup>\*</sup></span></span>

- <span data-ttu-id="33e01-296">**分解方式：检测技术**和**查看数据的依据：电子邮件 \> 恶意软件**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-296">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="33e01-297">**ATP 生成的文件信誉**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-297">**ATP-generated file reputation**<sup>\*\*</sup></span></span>
  - <span data-ttu-id="33e01-298">**反恶意软件引擎**</span><span class="sxs-lookup"><span data-stu-id="33e01-298">**Anti-malware engine**</span></span>
  - <span data-ttu-id="33e01-299">**反恶意软件策略文件类型块**</span><span class="sxs-lookup"><span data-stu-id="33e01-299">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="33e01-300">**文件沙箱**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-300">**File detonation**<sup>\*\*</sup></span></span>
  - <span data-ttu-id="33e01-301">**恶意文件信誉**</span><span class="sxs-lookup"><span data-stu-id="33e01-301">**Malicious file reputation**</span></span>
  - <span data-ttu-id="33e01-302">\* \* 恶意软件 ZAP \* \* \* \*<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-302">\*\*Malware ZAP\*\*\*\*<sup>\*\*</sup></span></span>
  - <span data-ttu-id="33e01-303">**其他**</span><span class="sxs-lookup"><span data-stu-id="33e01-303">**Others**</span></span>

- <span data-ttu-id="33e01-304">**分解方式：策略类型**和**查看数据的依据：电子邮件 \> 网络钓鱼诈骗**或**查看数据：电子邮件 \> 恶意软件**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-304">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="33e01-305">**反恶意软件**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-305">**Anti-malware**<sup>\*\*</sup></span></span>
  - <span data-ttu-id="33e01-306">**安全附件**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="33e01-306">**Safe Attachment**<sup>\*\*</sup></span></span>
  - <span data-ttu-id="33e01-307">**反网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="33e01-307">**Anti-phish**</span></span>
  - <span data-ttu-id="33e01-308">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="33e01-308">**Anti-spam**</span></span>
  - <span data-ttu-id="33e01-309">**邮件流规则**（也称为传输规则）</span><span class="sxs-lookup"><span data-stu-id="33e01-309">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="33e01-310">**其他**</span><span class="sxs-lookup"><span data-stu-id="33e01-310">**Others**</span></span>

- <span data-ttu-id="33e01-311">**分解方式：传递状态**和**查看数据方式：电子邮件 \> 网络钓鱼**或**查看数据：电子邮件 \> 恶意软件**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-311">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="33e01-312">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="33e01-312">**Delivery failed**</span></span>
  - <span data-ttu-id="33e01-313">**已**</span><span class="sxs-lookup"><span data-stu-id="33e01-313">**Dropped**</span></span>
  - <span data-ttu-id="33e01-314">**哪个**</span><span class="sxs-lookup"><span data-stu-id="33e01-314">**Forwarded**</span></span>
  - <span data-ttu-id="33e01-315">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="33e01-315">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="33e01-316">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="33e01-316">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="33e01-317">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="33e01-317">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="33e01-318">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="33e01-318">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="33e01-319">**内部部署服务器：已交付**</span><span class="sxs-lookup"><span data-stu-id="33e01-319">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="33e01-320">**隔离**</span><span class="sxs-lookup"><span data-stu-id="33e01-320">**Quarantine**</span></span>

<span data-ttu-id="33e01-321"><sup>\*</sup>仅限 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="33e01-321"><sup>\*</sup> Office 365 ATP only</span></span>

<span data-ttu-id="33e01-322"><sup>\*\*</sup>零小时自动清除（ZAP）在独立 EOP 中不可用（它仅适用于 Exchange Online 邮箱）。</span><span class="sxs-lookup"><span data-stu-id="33e01-322"><sup>\*\*</sup>Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="33e01-323">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="33e01-323">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="33e01-324">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-324">**Start date** and **End date**</span></span>
- <span data-ttu-id="33e01-325">检测值</span><span class="sxs-lookup"><span data-stu-id="33e01-325">Detection value</span></span>
- <span data-ttu-id="33e01-326">**受保护者**（仅限 OFFICE 365 ATP）： **ATP**或**EOP**。</span><span class="sxs-lookup"><span data-stu-id="33e01-326">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="33e01-327">请注意，"可筛选" 属性在**View data by： Content \> 恶意软件**中不可用。</span><span class="sxs-lookup"><span data-stu-id="33e01-327">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="33e01-328">威胁防护状态报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="33e01-328">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="33e01-329">如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="33e01-329">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="33e01-330">**数据查看依据：内容 \>恶意软件**：</span><span class="sxs-lookup"><span data-stu-id="33e01-330">**View data by: Content \> Malware**:</span></span>

- <span data-ttu-id="33e01-331">**Date**</span><span class="sxs-lookup"><span data-stu-id="33e01-331">**Date**</span></span>
- <span data-ttu-id="33e01-332">**位置**</span><span class="sxs-lookup"><span data-stu-id="33e01-332">**Location**</span></span>
- <span data-ttu-id="33e01-333">**指导者**</span><span class="sxs-lookup"><span data-stu-id="33e01-333">**Directed by**</span></span>
- <span data-ttu-id="33e01-334">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="33e01-334">**Malware name**</span></span>

- <span data-ttu-id="33e01-335">**数据查看方式：概述**：没有可用的**视图详细信息表**按钮。</span><span class="sxs-lookup"><span data-stu-id="33e01-335">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="33e01-336">所有其他图表：</span><span class="sxs-lookup"><span data-stu-id="33e01-336">All other charts:</span></span>

  - <span data-ttu-id="33e01-337">**Date**</span><span class="sxs-lookup"><span data-stu-id="33e01-337">**Date**</span></span>
  - <span data-ttu-id="33e01-338">**主题**</span><span class="sxs-lookup"><span data-stu-id="33e01-338">**Subject**</span></span>
  - <span data-ttu-id="33e01-339">**发件人**</span><span class="sxs-lookup"><span data-stu-id="33e01-339">**Sender**</span></span>
  - <span data-ttu-id="33e01-340">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="33e01-340">**Recipients**</span></span>
  - <span data-ttu-id="33e01-341">**指导者**</span><span class="sxs-lookup"><span data-stu-id="33e01-341">**Directed by**</span></span>
  - <span data-ttu-id="33e01-342">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="33e01-342">**Delivery status**</span></span>
  - <span data-ttu-id="33e01-343">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="33e01-343">**Source of compromise**</span></span>

<span data-ttu-id="33e01-344">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="33e01-344">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="33e01-345">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-345">**Start date** and **End date**</span></span>
- <span data-ttu-id="33e01-346">检测值</span><span class="sxs-lookup"><span data-stu-id="33e01-346">Detection value</span></span>
- <span data-ttu-id="33e01-347">**受保护者**（仅限 OFFICE 365 ATP）： **ATP**或**EOP**。</span><span class="sxs-lookup"><span data-stu-id="33e01-347">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="33e01-348">请注意，"可筛选" 属性在**View data by： Content \> 恶意软件**中不可用。</span><span class="sxs-lookup"><span data-stu-id="33e01-348">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="33e01-349">主要恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="33e01-349">Top malware report</span></span>

<span data-ttu-id="33e01-350">**上面的恶意软件**报告显示由[EOP](eop-features.md)检测到的各种类型的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="33e01-350">The **Top Malware** report shows the various kinds of malware that was detected by [EOP](eop-features.md).</span></span>

<span data-ttu-id="33e01-351">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**主要恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-351">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="33e01-352">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopMalwaret> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-352">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalwaret>.</span></span>

![SCC-EOP 主要恶意软件](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)

<span data-ttu-id="33e01-354">当您将鼠标指针悬停在饼图中时，您可以看到某种类型的恶意软件的名称以及检测到该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="33e01-354">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="33e01-355">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="33e01-355">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

![此报告显示为你的组织检测到的主要恶意软件](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)

<span data-ttu-id="33e01-357">在图表下方，你将看到检测到的恶意软件的列表以及检测到该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="33e01-357">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span> <span data-ttu-id="33e01-358">请注意，聚合视图仅允许90天的筛选。</span><span class="sxs-lookup"><span data-stu-id="33e01-358">Note that the aggregate view only allows for 90 days filtering.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="33e01-359">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="33e01-359">URL threat protection report</span></span>

<span data-ttu-id="33e01-360">此报告的小部件在报告仪表板上命名为**URL 保护报告**，并且仅在 Office 365 高级威胁防护（ATP）中可用。</span><span class="sxs-lookup"><span data-stu-id="33e01-360">The widget for this report is named **URL protection report** on the reports dashboard, and is only available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="33e01-361">具体来说：</span><span class="sxs-lookup"><span data-stu-id="33e01-361">Specifically:</span></span>

- <span data-ttu-id="33e01-362">Microsoft 365 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="33e01-362">A Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="33e01-363">高级威胁防护外接程序（Plan 1*或*plan 2）到包括 Exchange Online PROTECTION （EOP）的任何其他订阅。</span><span class="sxs-lookup"><span data-stu-id="33e01-363">An Advanced Threat Protection add-on (Plan 1 *or* Plan 2) to any other subscription that includes Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="33e01-364">若要直接转到 " **URL 威胁防护**" 报告，请打开 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="33e01-364">To go directly to the **URL threat protection** report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

> [!NOTE]
> <span data-ttu-id="33e01-365">此报告将不会从用户处单击 "数据"，即应用了 "安全链接策略" 的用户已选中 "不**跟踪用户点击**" 选项。</span><span class="sxs-lookup"><span data-stu-id="33e01-365">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

![操作中的 URL 威胁防护报告的图形。](../../media/tp-URLThreatProRpt1.PNG)

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="33e01-367">URL 威胁防护报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="33e01-367">Report view for the URL threat protection report</span></span>

<span data-ttu-id="33e01-368">**URL 威胁防护**报告包含两个聚合视图，每四个小时刷新一次，显示最近90天的数据：</span><span class="sxs-lookup"><span data-stu-id="33e01-368">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="33e01-369">**URL 单击 "保护操作**"：显示组织中的用户单击的 url 的数量以及单击的结果：</span><span class="sxs-lookup"><span data-stu-id="33e01-369">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="33e01-370">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="33e01-370">**Blocked**</span></span>
  - <span data-ttu-id="33e01-371">**阻止并单击**</span><span class="sxs-lookup"><span data-stu-id="33e01-371">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="33e01-372">**在扫描过程中单击**</span><span class="sxs-lookup"><span data-stu-id="33e01-372">**Clicked through during scan**</span></span>

  <span data-ttu-id="33e01-373">单击指示用户已通过阻止页面单击到恶意网站（管理员可以禁用 "在安全链接策略中单击"）。</span><span class="sxs-lookup"><span data-stu-id="33e01-373">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="33e01-374">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="33e01-374">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="33e01-375">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-375">**Start date** and **End date**</span></span>
  - <span data-ttu-id="33e01-376">可用的单击保护操作，以及**允许**查看所有 URL 单击的信息的值（不只是阻止单击）。</span><span class="sxs-lookup"><span data-stu-id="33e01-376">The available click protection actions, plus  the value **Allowed** to see information for all URL clicks (not just blocked clicks).</span></span>

- <span data-ttu-id="33e01-377">**URL 单击应用程序**：显示支持 OFFICE 365 ATP 安全链接的应用程序的 url 单击次数：</span><span class="sxs-lookup"><span data-stu-id="33e01-377">**URL click by application**: Shows the number of URL clicks by applications that support Office 365 ATP Safe Links:</span></span>

  - <span data-ttu-id="33e01-378">**电子邮件客户端**</span><span class="sxs-lookup"><span data-stu-id="33e01-378">**Email client**</span></span>
  - <span data-ttu-id="33e01-379">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="33e01-379">**PowerPoint**</span></span>
  - <span data-ttu-id="33e01-380">**Word**</span><span class="sxs-lookup"><span data-stu-id="33e01-380">**Word**</span></span>
  - <span data-ttu-id="33e01-381">**Excel**</span><span class="sxs-lookup"><span data-stu-id="33e01-381">**Excel**</span></span>
  - <span data-ttu-id="33e01-382">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="33e01-382">**OneNote**</span></span>
  - <span data-ttu-id="33e01-383">**Visio**</span><span class="sxs-lookup"><span data-stu-id="33e01-383">**Visio**</span></span>
  - <span data-ttu-id="33e01-384">**Teams**</span><span class="sxs-lookup"><span data-stu-id="33e01-384">**Teams**</span></span>
  - <span data-ttu-id="33e01-385">**其他**</span><span class="sxs-lookup"><span data-stu-id="33e01-385">**Other**</span></span>

  <span data-ttu-id="33e01-386">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="33e01-386">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="33e01-387">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="33e01-387">**Start date** and **End date**</span></span>
  - <span data-ttu-id="33e01-388">可用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="33e01-388">The available applications.</span></span>

### <a name="details-table-view-for-the-threat-protection-report"></a><span data-ttu-id="33e01-389">威胁防护报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="33e01-389">Details table view for the threat protection report</span></span>

<span data-ttu-id="33e01-390">如果单击 "**查看详细信息表**"，则报告将提供最近7天内在组织内发生的所有点击的近实时视图，并提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="33e01-390">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="33e01-391">**单击 "时间"**</span><span class="sxs-lookup"><span data-stu-id="33e01-391">**Click time**</span></span>
- <span data-ttu-id="33e01-392">**用户**</span><span class="sxs-lookup"><span data-stu-id="33e01-392">**User**</span></span>
- <span data-ttu-id="33e01-393">**URL**</span><span class="sxs-lookup"><span data-stu-id="33e01-393">**URL**</span></span>
- <span data-ttu-id="33e01-394">**Action**</span><span class="sxs-lookup"><span data-stu-id="33e01-394">**Action**</span></span>
- <span data-ttu-id="33e01-395">**App**</span><span class="sxs-lookup"><span data-stu-id="33e01-395">**App**</span></span>

<span data-ttu-id="33e01-396">如果单击 "详细信息表" 视图中的 "**筛选器**"，则可以按与报表视图中相同的条件进行筛选，也可以按逗号分隔的**域**或**收件人**进行筛选。</span><span class="sxs-lookup"><span data-stu-id="33e01-396">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="33e01-397">若要返回到 "报告" 视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-397">To get back to the reports view, click **View report**.</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="33e01-398">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="33e01-398">User-reported messages report</span></span>

<span data-ttu-id="33e01-399">"**用户报告的邮件**" 报告显示用户通过使用[报告邮件外接程序](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)报告为垃圾邮件、网络钓鱼尝试或良好邮件的电子邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="33e01-399">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="33e01-400">详细信息可用于每封邮件，包括传递原因、为您的组织配置的垃圾邮件策略例外或邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="33e01-400">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="33e01-401">若要查看详细信息，请在 "用户报告" 列表中选择一个项目，然后查看 "**摘要**" 和 "**详细信息**" 选项卡上的信息。</span><span class="sxs-lookup"><span data-stu-id="33e01-401">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

!["用户报告的邮件" 报告显示用户标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试的邮件。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="33e01-403">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="33e01-403">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="33e01-404">转到 "**威胁管理** \> **仪表板** \> **用户报告的邮件**"。</span><span class="sxs-lookup"><span data-stu-id="33e01-404">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="33e01-405">转到 "**威胁管理**" \> **查看** \> **用户报告的邮件**。</span><span class="sxs-lookup"><span data-stu-id="33e01-405">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![在安全 & 合规性中心中，选择 "威胁管理" \> 查看 \> 用户报告的消息](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="33e01-407">为了使用户报告的邮件报告正常工作，必须为您的 Office 365 环境**打开审核日志记录**。</span><span class="sxs-lookup"><span data-stu-id="33e01-407">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="33e01-408">这通常由在 Exchange Online 中分配了审核日志角色的人完成。</span><span class="sxs-lookup"><span data-stu-id="33e01-408">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="33e01-409">有关详细信息，请参阅[打开或关闭 Microsoft 365 审核日志搜索](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="33e01-409">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="33e01-410">查看这些报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="33e01-410">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="33e01-411">若要查看和使用报告，您必须是安全 & 合规性中心**和**Exchange Online 中指定角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="33e01-411">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="33e01-412">在安全 & 合规性中心中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="33e01-412">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="33e01-413">-组织管理-安全管理员（也可以在[Azure Active Directory 管理中心](https://aad.portal.azure.com)中执行此操作-安全读取器</span><span class="sxs-lookup"><span data-stu-id="33e01-413">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="33e01-414">有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="33e01-414">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="33e01-415">在 Exchange Online 中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="33e01-415">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="33e01-416">-组织管理-仅查看组织管理-仅查看收件人-合规性管理</span><span class="sxs-lookup"><span data-stu-id="33e01-416">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="33e01-417">有关详细信息，请参阅[Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)中的权限和[管理 exchange online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="33e01-417">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="33e01-418">如果报告不显示数据，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="33e01-418">What if the reports aren't showing data?</span></span>

<span data-ttu-id="33e01-419">如果您未在报告中看到数据，请仔细检查您的策略设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="33e01-419">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="33e01-420">若要了解详细信息，请参阅[防止威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="33e01-420">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="33e01-421">相关主题</span><span class="sxs-lookup"><span data-stu-id="33e01-421">Related topics</span></span>

[<span data-ttu-id="33e01-422">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="33e01-422">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="33e01-423">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="33e01-423">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
