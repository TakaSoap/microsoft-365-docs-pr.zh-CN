---
title: 查看安全与合规中心内的电子邮件安全报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
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
ms.openlocfilehash: a87cee31b4e0251aea8eb39640d37184ccd0ee96
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104518"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="e807f-104">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="e807f-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="e807f-105">[安全 & 合规性中心](https://protection.office.com)中提供了多种报告，可帮助您了解电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能如何保护您的组织）。</span><span class="sxs-lookup"><span data-stu-id="e807f-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="e807f-106">如果您具有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，则可以转到 " **报告**" \> **仪表板**，在安全 & 合规中心中查看这些报告。</span><span class="sxs-lookup"><span data-stu-id="e807f-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e807f-107">若要直接转到 "报表" 仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Security & 合规中心中的报告仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="e807f-109">已泄露用户报告</span><span class="sxs-lookup"><span data-stu-id="e807f-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="e807f-110">此报告在具有 Exchange Online 邮箱的 Microsoft 365 组织中可用。</span><span class="sxs-lookup"><span data-stu-id="e807f-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="e807f-111">它在独立 Exchange Online Protection (EOP) 组织中不可用。</span><span class="sxs-lookup"><span data-stu-id="e807f-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="e807f-112">"已 **泄露的用户** " 报告显示在最近7天内被标记为 **可疑** 或 **受限制** 的用户帐户数。</span><span class="sxs-lookup"><span data-stu-id="e807f-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="e807f-113">在上述任一状态中的帐户都有问题或甚至已损坏。</span><span class="sxs-lookup"><span data-stu-id="e807f-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="e807f-114">通过频繁使用，您可以使用报告发现可疑或受限帐户中的峰值、甚至是趋势。</span><span class="sxs-lookup"><span data-stu-id="e807f-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="e807f-115">有关受损用户的详细信息，请参阅 [响应已泄露的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="e807f-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

!["报告" 仪表板中的 "已损坏用户" 小部件](../../media/compromised-users-report-widget.png)

<span data-ttu-id="e807f-117">聚合视图显示最近90天的数据，详细信息视图显示最近30天的数据。</span><span class="sxs-lookup"><span data-stu-id="e807f-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="e807f-118">若要查看报告，请打开 " [安全 & 合规中心](https://protection.office.com)"，转到 " **报告**" \> **仪表板** ，然后选择 "已 **损坏用户**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="e807f-119">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="e807f-120">可以通过单击 " **筛选** 器" 并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="e807f-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="e807f-121">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="e807f-122">**可疑**：用户帐户发送了可疑电子邮件，并且存在受限制的发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="e807f-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="e807f-123">**受限**：由于高度可疑的模式，用户帐户受到限制，无法发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e807f-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![已损坏的用户报告中的报告视图](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="e807f-125">如果单击 " **查看详细信息表**"，则可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e807f-126">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="e807f-126">**Creation time**</span></span>
- <span data-ttu-id="e807f-127">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="e807f-127">**User ID**</span></span>
- <span data-ttu-id="e807f-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="e807f-128">**Action**</span></span>

<span data-ttu-id="e807f-129">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="e807f-130">加密报告</span><span class="sxs-lookup"><span data-stu-id="e807f-130">Encryption report</span></span>

<span data-ttu-id="e807f-131">在 Exchange Online 或独立 EOP 中邮箱的 EOP (订阅中提供 **加密报告** ，而无需 Exchange online 邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="e807f-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="e807f-132">您组织的安全团队可以使用此报告中的信息来标识模式，并主动应用或调整敏感电子邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="e807f-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="e807f-133">例如：</span><span class="sxs-lookup"><span data-stu-id="e807f-133">For example:</span></span>

- <span data-ttu-id="e807f-134">如果您看到用户加密了大量的电子邮件，则可能需要添加加密策略以对某些用例自动进行加密。</span><span class="sxs-lookup"><span data-stu-id="e807f-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="e807f-135">有关详细信息，请参阅 [在 Microsoft 365 中定义用于加密电子邮件的邮件流规则](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="e807f-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="e807f-136">如果有许多可用的加密模板，但没有用户正在使用它们，则可以考察用户是否需要功能培训。</span><span class="sxs-lookup"><span data-stu-id="e807f-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="e807f-137">"聚合" 视图允许筛选过去的90天，而 "详细信息" 视图允许筛选10天。</span><span class="sxs-lookup"><span data-stu-id="e807f-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="e807f-138">若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **加密报告**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="e807f-139">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="e807f-140">若要了解有关加密的详细信息，请参阅 [Microsoft 365 中的电子邮件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="e807f-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="e807f-141">加密报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="e807f-141">Report view for the Encryption report</span></span>

<span data-ttu-id="e807f-142">您可以在图表上使用以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="e807f-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="e807f-143">**数据查看依据：邮件加密报告** 和 **分解方式：加密方法**：以下是可用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="e807f-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="e807f-144">**按用户加密**</span><span class="sxs-lookup"><span data-stu-id="e807f-144">**Encryption by user**</span></span>
  - <span data-ttu-id="e807f-145">**按策略加密**</span><span class="sxs-lookup"><span data-stu-id="e807f-145">**Encryption by policy**</span></span>

  <span data-ttu-id="e807f-146">如果单击 " **筛选器**"，则可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="e807f-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="e807f-147">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e807f-148">加密方法。</span><span class="sxs-lookup"><span data-stu-id="e807f-148">Encryption method.</span></span>
  - <span data-ttu-id="e807f-149">加密模板。</span><span class="sxs-lookup"><span data-stu-id="e807f-149">Encryption template.</span></span>

- <span data-ttu-id="e807f-150">**数据查看依据：邮件加密报告** 和 **分解方式：加密模板**：以下是可用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="e807f-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="e807f-151">**请勿转发**</span><span class="sxs-lookup"><span data-stu-id="e807f-151">**Do not forward**</span></span>
  - <span data-ttu-id="e807f-152">**仅加密**</span><span class="sxs-lookup"><span data-stu-id="e807f-152">**Encrypt only**</span></span>
  - <span data-ttu-id="e807f-153">**OME 以前**</span><span class="sxs-lookup"><span data-stu-id="e807f-153">**OME previous**</span></span>
  - <span data-ttu-id="e807f-154">**自定义**</span><span class="sxs-lookup"><span data-stu-id="e807f-154">**Custom**</span></span>

  <span data-ttu-id="e807f-155">如果单击 " **筛选器**"，则可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="e807f-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="e807f-156">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e807f-157">加密方法</span><span class="sxs-lookup"><span data-stu-id="e807f-157">Encryption method</span></span>
  - <span data-ttu-id="e807f-158">加密模板</span><span class="sxs-lookup"><span data-stu-id="e807f-158">Encryption template</span></span>

- <span data-ttu-id="e807f-159">**按数据查看：前5个收件人域**：此视图显示包含前5个收件人域的已发送邮件计数的饼图。</span><span class="sxs-lookup"><span data-stu-id="e807f-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="e807f-160">如果单击 " **筛选器**"，则可以选择 " **开始日期** " 和 " **结束日期**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="e807f-161">加密报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="e807f-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="e807f-162">如果您单击 " **查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="e807f-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e807f-163">**分解方式：加密方法** 或 **分解方式：加密模板**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="e807f-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="e807f-164">**Date**</span></span>
  - <span data-ttu-id="e807f-165">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="e807f-165">**Sender address**</span></span>
  - <span data-ttu-id="e807f-166">**加密模板**</span><span class="sxs-lookup"><span data-stu-id="e807f-166">**Encryption template**</span></span>
  - <span data-ttu-id="e807f-167">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="e807f-167">**Encryption method**</span></span>
  - <span data-ttu-id="e807f-168">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="e807f-168">**Recipient address**</span></span>
  - <span data-ttu-id="e807f-169">**主题**</span><span class="sxs-lookup"><span data-stu-id="e807f-169">**Subject**</span></span>

- <span data-ttu-id="e807f-170">**数据查看依据：前5个收件人域**：</span><span class="sxs-lookup"><span data-stu-id="e807f-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="e807f-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="e807f-171">**Date**</span></span>
  - <span data-ttu-id="e807f-172">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="e807f-172">**Recipient domain**</span></span>
  - <span data-ttu-id="e807f-173">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="e807f-173">**Message count**</span></span>
  
<span data-ttu-id="e807f-174">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="e807f-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e807f-175">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="e807f-176">加密方法</span><span class="sxs-lookup"><span data-stu-id="e807f-176">Encryption method</span></span>
- <span data-ttu-id="e807f-177">加密模板</span><span class="sxs-lookup"><span data-stu-id="e807f-177">Encryption template</span></span>

<span data-ttu-id="e807f-178">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e807f-179">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="e807f-179">Mailflow status report</span></span>

<span data-ttu-id="e807f-180">**邮件流状态报告**包含有关恶意软件、垃圾邮件、网络钓鱼和边缘阻止的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="e807f-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="e807f-181">有关更多详细信息，请参阅 [邮件流 status report](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="e807f-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="e807f-182">电子邮件中的恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="e807f-182">Malware detections in email report</span></span>

<span data-ttu-id="e807f-183">" **电子邮件中的恶意软件检测** " 报告显示在 Exchange Online PROTECTION 或 EOP) 检测到的传入和传出电子邮件中的恶意软件检测 (的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e807f-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="e807f-184">有关 EOP 中的恶意软件保护的详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e807f-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="e807f-185">聚合视图筛选器允许90天，而详细信息表筛选器仅允许10天。</span><span class="sxs-lookup"><span data-stu-id="e807f-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="e807f-186">若要查看报告，请打开 [安全 & 合规中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 **"在电子邮件中检测到恶意软件"**。</span><span class="sxs-lookup"><span data-stu-id="e807f-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="e807f-187">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

!["报告" 仪表板中电子邮件小组件中的恶意软件检测](../../media/malware-detections-widget.png)

<span data-ttu-id="e807f-189">您可以通过单击 " **筛选** 器" 并选择 "筛选器" 来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="e807f-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="e807f-190">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="e807f-191">**进货**</span><span class="sxs-lookup"><span data-stu-id="e807f-191">**Inbound**</span></span>
- <span data-ttu-id="e807f-192">**出站**</span><span class="sxs-lookup"><span data-stu-id="e807f-192">**Outbound**</span></span>

![电子邮件中的恶意软件检测报告中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="e807f-194">如果单击 " **查看详细信息表**"，则可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e807f-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="e807f-195">**Date**</span></span>
- <span data-ttu-id="e807f-196">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="e807f-196">**Sender address**</span></span>
- <span data-ttu-id="e807f-197">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="e807f-197">**Recipient address**</span></span>
- <span data-ttu-id="e807f-198">**邮件 id**：在邮件头的 **邮件 id** 标头字段中可用，并且应是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e807f-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="e807f-199"> (的示例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 记下尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="e807f-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="e807f-200">**主题**</span><span class="sxs-lookup"><span data-stu-id="e807f-200">**Subject**</span></span>
- <span data-ttu-id="e807f-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="e807f-201">**Filename**</span></span>
- <span data-ttu-id="e807f-202">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="e807f-202">**Malware name**</span></span>

<span data-ttu-id="e807f-203">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e807f-204">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="e807f-204">Sent and received email report</span></span>

<span data-ttu-id="e807f-205">**发送和接收的电子邮件**报告包含有关恶意软件、垃圾邮件、邮件流规则的信息 (也称为传输规则) ，以及在电子邮件进入服务后进行的高级恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="e807f-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="e807f-206">有关详细信息，请参阅 [发送和接收的电子邮件报告](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="e807f-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="e807f-207">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="e807f-207">Spam detections report</span></span>

<span data-ttu-id="e807f-208">**垃圾邮件检测**报告显示由 EOP 阻止的垃圾电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e807f-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="e807f-209">邮件单独计数，而不是每个收件人。</span><span class="sxs-lookup"><span data-stu-id="e807f-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="e807f-210">例如，如果将相同的垃圾邮件发送给组织中的100收件人，则会将其计为一封邮件。</span><span class="sxs-lookup"><span data-stu-id="e807f-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="e807f-211">聚合视图允许90天筛选，而详细信息表允许进行10天的筛选。</span><span class="sxs-lookup"><span data-stu-id="e807f-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="e807f-212">若要查看报告，请打开 " [安全 & 合规中心](https://protection.office.com)"，转到 " **报告**" \> **仪表板** ，然后选择 " **垃圾邮件检测**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="e807f-213">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

!["报告" 仪表板中的 "垃圾邮件检测" 小部件](../../media/spam-detections-report-widget.png)

<span data-ttu-id="e807f-215">有关反垃圾邮件保护的详细信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e807f-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="e807f-216">垃圾邮件检测报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="e807f-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="e807f-217">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="e807f-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e807f-218">**分解方式：操作**：显示以下事件类型：</span><span class="sxs-lookup"><span data-stu-id="e807f-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="e807f-219">**筛选出的垃圾邮件内容**</span><span class="sxs-lookup"><span data-stu-id="e807f-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="e807f-220">**垃圾邮件 IP 阻止**</span><span class="sxs-lookup"><span data-stu-id="e807f-220">**Spam IP block**</span></span>
  - <span data-ttu-id="e807f-221">**垃圾邮件信封块**</span><span class="sxs-lookup"><span data-stu-id="e807f-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="e807f-222">**垃圾邮件 DBEB 筛选器**：基于目录的边缘阻止 (DBEB) </span><span class="sxs-lookup"><span data-stu-id="e807f-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="e807f-223">当您悬停在图表中 (数据点) 的某一天时，您可以看到该日已阻止的项目数，以及这些项目的分类方式。</span><span class="sxs-lookup"><span data-stu-id="e807f-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾邮件检测报告中的操作视图](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="e807f-225">**分解方式：方向**：以下说明如下所示：</span><span class="sxs-lookup"><span data-stu-id="e807f-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="e807f-226">**进货**</span><span class="sxs-lookup"><span data-stu-id="e807f-226">**Inbound**</span></span>
  - <span data-ttu-id="e807f-227">**出站**</span><span class="sxs-lookup"><span data-stu-id="e807f-227">**Outbound**</span></span>

  ![垃圾邮件检测报告中的 "方向" 视图](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="e807f-229">如果您在报告视图中单击 " **筛选器** "，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="e807f-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e807f-230">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="e807f-231">方向值</span><span class="sxs-lookup"><span data-stu-id="e807f-231">Direction values</span></span>
- <span data-ttu-id="e807f-232">事件类型值</span><span class="sxs-lookup"><span data-stu-id="e807f-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="e807f-233">垃圾邮件检测报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="e807f-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="e807f-234">如果您在任何报告视图中单击 " **查看详细信息表** "，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="e807f-235">**Date**</span><span class="sxs-lookup"><span data-stu-id="e807f-235">**Date**</span></span>
- <span data-ttu-id="e807f-236">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="e807f-236">**Sender address**</span></span>
- <span data-ttu-id="e807f-237">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="e807f-237">**Recipient address**</span></span>
- <span data-ttu-id="e807f-238">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="e807f-238">**Event type**</span></span>
- <span data-ttu-id="e807f-239">**操作**</span><span class="sxs-lookup"><span data-stu-id="e807f-239">**Action**</span></span>
- <span data-ttu-id="e807f-240">**主题**</span><span class="sxs-lookup"><span data-stu-id="e807f-240">**Subject**</span></span>

<span data-ttu-id="e807f-241">如果单击 "详细信息" 表中的 " **筛选器** "，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="e807f-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e807f-242">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="e807f-243">方向值</span><span class="sxs-lookup"><span data-stu-id="e807f-243">Direction values</span></span>
- <span data-ttu-id="e807f-244">事件类型值</span><span class="sxs-lookup"><span data-stu-id="e807f-244">Event type values</span></span>

<span data-ttu-id="e807f-245">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="e807f-246">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="e807f-246">Spoof detections report</span></span>

<span data-ttu-id="e807f-247">**欺骗检测**报告显示检测到的欺骗邮件和这些邮件的数目，这些邮件被视为 "好" (欺骗邮件出于) 的合法商业原因而完成。</span><span class="sxs-lookup"><span data-stu-id="e807f-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="e807f-248">有关哄骗的详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e807f-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="e807f-249">报告的聚合视图允许在筛选过程中90天，而详细信息视图只允许进行10天的筛选。</span><span class="sxs-lookup"><span data-stu-id="e807f-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="e807f-250">若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **欺骗检测**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="e807f-251">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

!["报告" 仪表板中的欺骗检测小部件](../../media/spoof-detections-widget.png)

<span data-ttu-id="e807f-253">当鼠标悬停在图表中 (数据点) 时，您可以看到通过的欺骗邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="e807f-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="e807f-254">可以通过单击 " **筛选** 器" 并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="e807f-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="e807f-255">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="e807f-256">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="e807f-256">**Good mail**</span></span>

- <span data-ttu-id="e807f-257">**作为垃圾邮件捕获**</span><span class="sxs-lookup"><span data-stu-id="e807f-257">**Caught as spam**</span></span>

![欺骗检测报告中的报告视图](../../media/spoof-detections-report-view.png)

<span data-ttu-id="e807f-259">如果单击 " **查看详细信息表**"，则可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e807f-260">**Date**</span><span class="sxs-lookup"><span data-stu-id="e807f-260">**Date**</span></span>
- <span data-ttu-id="e807f-261">**欺骗发件人**</span><span class="sxs-lookup"><span data-stu-id="e807f-261">**Spoofed sender**</span></span>
- <span data-ttu-id="e807f-262">**真正发件人**</span><span class="sxs-lookup"><span data-stu-id="e807f-262">**True sender**</span></span>
- <span data-ttu-id="e807f-263">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="e807f-263">**Sender IP**</span></span>
- <span data-ttu-id="e807f-264">**操作**</span><span class="sxs-lookup"><span data-stu-id="e807f-264">**Action**</span></span>
- <span data-ttu-id="e807f-265">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="e807f-265">**Message count**</span></span>

<span data-ttu-id="e807f-266">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="e807f-267">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="e807f-267">Threat protection status report</span></span>

<span data-ttu-id="e807f-268">" **威胁防护状态** 报告" 在 EOP 和 OFFICE 365 ATP 中均可用。但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="e807f-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="e807f-269">例如，EOP 客户可以查看有关在电子邮件中检测到的恶意软件的信息，但不是关于 [SharePoint Online、OneDrive 或 Microsoft 团队中检测到的恶意文件](atp-for-spo-odb-and-teams.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="e807f-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="e807f-270">该报告提供了包含恶意内容的电子邮件（如文件或网站地址 (Url) 被反恶意软件引擎阻止、 [零小时自动清除 (ZAP) ](zero-hour-auto-purge.md)以及 atp 功能（如 [atp 安全链接](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)和 [atp 反网络钓鱼](set-up-anti-phishing-policies.md)）的邮件数。</span><span class="sxs-lookup"><span data-stu-id="e807f-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="e807f-271">您可以使用此信息来确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="e807f-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="e807f-272">请务必注意，如果将邮件发送给5个收件人，我们会将其计数为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="e807f-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="e807f-273">若要查看报告，请打开 [安全 & 合规中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **威胁保护状态**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="e807f-274">若要直接转到报告，请打开以下 Url 之一：</span><span class="sxs-lookup"><span data-stu-id="e807f-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="e807f-275">Office 365 ATP： <https://protection.office.com/reportv2?id=ATPV2AggregateReport> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="e807f-276">EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="e807f-276">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

!["报告" 仪表板中的 "威胁防护状态" 小部件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="e807f-278">默认情况下，图表显示过去7天的数据。</span><span class="sxs-lookup"><span data-stu-id="e807f-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="e807f-279">如果单击 " **筛选器**"，则可以选择一个90天的日期范围 (试用订阅可能限制为30天) 。</span><span class="sxs-lookup"><span data-stu-id="e807f-279">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="e807f-280">[！说明] [！说明] 详细信息表视图允许筛选30天。</span><span class="sxs-lookup"><span data-stu-id="e807f-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="e807f-281">威胁防护状态报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="e807f-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="e807f-282">可以使用以下视图：</span><span class="sxs-lookup"><span data-stu-id="e807f-282">The following views are available:</span></span>

- <span data-ttu-id="e807f-283">**查看数据的依据：概述**：显示以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-283">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="e807f-284">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="e807f-284">**Email malware**</span></span>
  - <span data-ttu-id="e807f-285">**电子邮件网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="e807f-285">**Email phish**</span></span>
  - <span data-ttu-id="e807f-286">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="e807f-286">**Content malware**</span></span>

  ![威胁 protection 状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="e807f-288">**数据查看依据：内容 \> 恶意软件**<sup>1</sup>：为 Office 365 ATP 组织显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="e807f-289">**反恶意软件引擎**</span><span class="sxs-lookup"><span data-stu-id="e807f-289">**Anti-malware engine**</span></span>
  - <span data-ttu-id="e807f-290">**文件沙箱**</span><span class="sxs-lookup"><span data-stu-id="e807f-290">**File detonation**</span></span>

  ![威胁 protection 状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="e807f-292">**分解方式：检测技术** 和 **查看数据的方式：电子邮件 \> 网络钓鱼**：将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-292">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="e807f-293">**ATP 生成的 URL 信誉**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-293">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="e807f-294">**高级网络钓鱼筛选器**</span><span class="sxs-lookup"><span data-stu-id="e807f-294">**Advanced phish filter**</span></span>
  - <span data-ttu-id="e807f-295">**反欺骗： DMARC 故障**</span><span class="sxs-lookup"><span data-stu-id="e807f-295">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="e807f-296">**反欺骗：组织内**</span><span class="sxs-lookup"><span data-stu-id="e807f-296">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="e807f-297">**反欺骗：外部域**</span><span class="sxs-lookup"><span data-stu-id="e807f-297">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="e807f-298">**品牌模拟**</span><span class="sxs-lookup"><span data-stu-id="e807f-298">**Brand impersonation**</span></span>
  - <span data-ttu-id="e807f-299">**域模拟**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-299">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="e807f-300">**EOP URL 信誉**</span><span class="sxs-lookup"><span data-stu-id="e807f-300">**EOP URL reputation**</span></span>
  - <span data-ttu-id="e807f-301">**常规网络钓鱼筛选器**</span><span class="sxs-lookup"><span data-stu-id="e807f-301">**General phish filter**</span></span>
  - <span data-ttu-id="e807f-302">**其他**</span><span class="sxs-lookup"><span data-stu-id="e807f-302">**Others**</span></span>
  - <span data-ttu-id="e807f-303">**网络钓鱼 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-303">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="e807f-304">**URL 沙箱**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-304">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="e807f-305">**用户模拟**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-305">**User impersonation**<sup>1</sup></span></span>

  ![威胁防护状态报告中的网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="e807f-307">**分解方式：检测技术** 和 **查看数据的依据：电子邮件 \> 恶意软件**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-307">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e807f-308">**ATP 生成的文件信誉**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-308">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="e807f-309">**反恶意软件引擎**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-309">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="e807f-310">**反恶意软件策略文件类型块**</span><span class="sxs-lookup"><span data-stu-id="e807f-310">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="e807f-311">**File 沙箱**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-311">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="e807f-312">**恶意文件信誉**</span><span class="sxs-lookup"><span data-stu-id="e807f-312">**Malicious file reputation**</span></span>
  - <span data-ttu-id="e807f-313">**恶意软件 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-313">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="e807f-314">**其他**</span><span class="sxs-lookup"><span data-stu-id="e807f-314">**Others**</span></span>

  ![威胁防护状态报告中的恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="e807f-316">**分解方式：策略类型** 和 **查看数据的依据：电子邮件 \> 网络钓鱼诈骗** 或 **查看数据：电子邮件 \> 恶意软件**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-316">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e807f-317">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="e807f-317">**Anti-malware**</span></span>
  - <span data-ttu-id="e807f-318">**安全附件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e807f-318">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="e807f-319">**反网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="e807f-319">**Anti-phish**</span></span>
  - <span data-ttu-id="e807f-320">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="e807f-320">**Anti-spam**</span></span>
  - <span data-ttu-id="e807f-321">**邮件流规则** (也称为传输规则) </span><span class="sxs-lookup"><span data-stu-id="e807f-321">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="e807f-322">**其他**</span><span class="sxs-lookup"><span data-stu-id="e807f-322">**Others**</span></span>

  ![威胁防护状态报告中的仿冒电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="e807f-324">**分解方式：传递状态** 和 **查看数据方式：电子邮件 \> 网络钓鱼** 或 **查看数据：电子邮件 \> 恶意软件**：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-324">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e807f-325">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="e807f-325">**Delivery failed**</span></span>
  - <span data-ttu-id="e807f-326">**已**</span><span class="sxs-lookup"><span data-stu-id="e807f-326">**Dropped**</span></span>
  - <span data-ttu-id="e807f-327">**哪个**</span><span class="sxs-lookup"><span data-stu-id="e807f-327">**Forwarded**</span></span>
  - <span data-ttu-id="e807f-328">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="e807f-328">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="e807f-329">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="e807f-329">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="e807f-330">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="e807f-330">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="e807f-331">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="e807f-331">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="e807f-332">**内部部署服务器：已交付**</span><span class="sxs-lookup"><span data-stu-id="e807f-332">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="e807f-333">**隔离**</span><span class="sxs-lookup"><span data-stu-id="e807f-333">**Quarantine**</span></span>

  ![威胁防护状态报告中的仿冒电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="e807f-335">仅<sup>1</sup>个 OFFICE 365 ATP</span><span class="sxs-lookup"><span data-stu-id="e807f-335"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="e807f-336"><sup>2</sup> 个零小时自动清除 (ZAP) 在独立 EOP 中不可用 (它仅适用于 Exchange Online 邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="e807f-336"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="e807f-337">如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="e807f-337">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="e807f-338">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-338">**Start date** and **End date**</span></span>
- <span data-ttu-id="e807f-339">检测值</span><span class="sxs-lookup"><span data-stu-id="e807f-339">Detection value</span></span>
- <span data-ttu-id="e807f-340">**受** (OFFICE 365 ATP) ： **atp** 或 **EOP**。</span><span class="sxs-lookup"><span data-stu-id="e807f-340">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="e807f-341">请注意，"可筛选" 属性在 **View data by： Content \> 恶意软件**中不可用。</span><span class="sxs-lookup"><span data-stu-id="e807f-341">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="e807f-342">威胁防护状态报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="e807f-342">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="e807f-343">如果您单击 " **查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="e807f-343">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e807f-344">**数据查看依据：内容 \> 恶意软件**：</span><span class="sxs-lookup"><span data-stu-id="e807f-344">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="e807f-345">**Date**</span><span class="sxs-lookup"><span data-stu-id="e807f-345">**Date**</span></span>
  - <span data-ttu-id="e807f-346">**位置**</span><span class="sxs-lookup"><span data-stu-id="e807f-346">**Location**</span></span>
  - <span data-ttu-id="e807f-347">**指导者**</span><span class="sxs-lookup"><span data-stu-id="e807f-347">**Directed by**</span></span>
  - <span data-ttu-id="e807f-348">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="e807f-348">**Malware name**</span></span>

- <span data-ttu-id="e807f-349">**数据查看方式：概述**：没有可用的 **视图详细信息表** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e807f-349">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="e807f-350">所有其他图表：</span><span class="sxs-lookup"><span data-stu-id="e807f-350">All other charts:</span></span>

  - <span data-ttu-id="e807f-351">**Date**</span><span class="sxs-lookup"><span data-stu-id="e807f-351">**Date**</span></span>
  - <span data-ttu-id="e807f-352">**主题**</span><span class="sxs-lookup"><span data-stu-id="e807f-352">**Subject**</span></span>
  - <span data-ttu-id="e807f-353">**发件人**</span><span class="sxs-lookup"><span data-stu-id="e807f-353">**Sender**</span></span>
  - <span data-ttu-id="e807f-354">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="e807f-354">**Recipients**</span></span>
  - <span data-ttu-id="e807f-355">**检测人**</span><span class="sxs-lookup"><span data-stu-id="e807f-355">**Detected by**</span></span>
  - <span data-ttu-id="e807f-356">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="e807f-356">**Delivery status**</span></span>
  - <span data-ttu-id="e807f-357">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="e807f-357">**Source of compromise**</span></span>

<span data-ttu-id="e807f-358">如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="e807f-358">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="e807f-359">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="e807f-359">**Start date** and **End date**</span></span>
- <span data-ttu-id="e807f-360">检测值</span><span class="sxs-lookup"><span data-stu-id="e807f-360">Detection value</span></span>
- <span data-ttu-id="e807f-361">**受** (OFFICE 365 ATP) ： **atp** 或 **EOP**。</span><span class="sxs-lookup"><span data-stu-id="e807f-361">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="e807f-362">请注意，"可筛选" 属性在 **View data by： Content \> 恶意软件**中不可用。</span><span class="sxs-lookup"><span data-stu-id="e807f-362">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="e807f-363">主要恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="e807f-363">Top malware report</span></span>

<span data-ttu-id="e807f-364">**最上面的恶意软件**报告显示了[EOP 中的反恶意软件保护](anti-malware-protection.md)检测到的各种类型的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e807f-364">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="e807f-365">若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **主要恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-365">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="e807f-366">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="e807f-366">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

!["报告" 仪表板中的主要恶意软件小部件](../../media/top-malware-report-widget.png)

<span data-ttu-id="e807f-368">当您将鼠标指针悬停在饼图中时，您可以看到某种类型的恶意软件的名称以及检测到该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="e807f-368">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![主要恶意软件报告视图](../../media/top-malware-report-view.png)

<span data-ttu-id="e807f-370">如果单击 " **查看详细信息表**"，则可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="e807f-370">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e807f-371">**主要恶意软件**</span><span class="sxs-lookup"><span data-stu-id="e807f-371">**Top malware**</span></span>
- <span data-ttu-id="e807f-372">**Count**</span><span class="sxs-lookup"><span data-stu-id="e807f-372">**Count**</span></span>

<span data-ttu-id="e807f-373">如果单击 "报表视图" 或 "详细信息表" 视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="e807f-373">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="e807f-374">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="e807f-374">URL threat protection report</span></span>

<span data-ttu-id="e807f-375">" **URL 威胁防护" 报告** 在 Office 365 高级威胁防护 (ATP) 中可用。</span><span class="sxs-lookup"><span data-stu-id="e807f-375">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="e807f-376">有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-atp.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="e807f-376">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="e807f-377">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="e807f-377">User-reported messages report</span></span>

<span data-ttu-id="e807f-378">" **用户报告的邮件** " 报告显示用户通过使用 [报告邮件外接程序](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)报告为垃圾邮件、网络钓鱼尝试或良好邮件的电子邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e807f-378">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="e807f-379">详细信息可用于每封邮件，包括传递原因、为您的组织配置的垃圾邮件策略例外或邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="e807f-379">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="e807f-380">若要查看详细信息，请在 "用户报告" 列表中选择一个项目，然后查看 " **摘要** " 和 " **详细信息** " 选项卡上的信息。</span><span class="sxs-lookup"><span data-stu-id="e807f-380">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

!["用户报告的邮件" 报告显示用户标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试的邮件。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="e807f-382">若要查看此报告，请在 [安全 & 合规性中心](https://protection.office.com)中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e807f-382">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="e807f-383">转到 " **威胁管理** \> **仪表板** \> **用户报告的邮件**"。</span><span class="sxs-lookup"><span data-stu-id="e807f-383">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="e807f-384">转到 " **威胁管理**" \> **查看** \> **用户报告的邮件**。</span><span class="sxs-lookup"><span data-stu-id="e807f-384">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![在安全 & 合规性中心中，选择 "威胁管理" \> 查看 \> 用户报告的消息](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="e807f-386">为了使用户报告的邮件报告正常工作，必须为您的 Office 365 环境 **打开审核日志记录** 。</span><span class="sxs-lookup"><span data-stu-id="e807f-386">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="e807f-387">这通常由在 Exchange Online 中分配了审核日志角色的人完成。</span><span class="sxs-lookup"><span data-stu-id="e807f-387">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="e807f-388">有关详细信息，请参阅 [打开或关闭 Microsoft 365 审核日志搜索](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="e807f-388">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e807f-389">查看这些报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="e807f-389">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e807f-390">若要查看和使用报告，您必须是安全 & 合规性中心 **和** Exchange Online 中指定角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="e807f-390">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="e807f-391">在安全 & 合规性中心中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="e807f-391">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="e807f-392">-组织管理-安全管理员 (你也可以在 [Azure Active Directory 管理中心](https://aad.portal.azure.com) 中执行此操作-安全读者</span><span class="sxs-lookup"><span data-stu-id="e807f-392">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="e807f-393">有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="e807f-393">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="e807f-394">在 Exchange Online 中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="e807f-394">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="e807f-395">-组织管理-仅查看组织管理-仅查看收件人-合规性管理</span><span class="sxs-lookup"><span data-stu-id="e807f-395">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="e807f-396">有关详细信息，请参阅 [Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 中的权限和 [管理 exchange online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="e807f-396">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="e807f-397">如果报告不显示数据，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="e807f-397">What if the reports aren't showing data?</span></span>

<span data-ttu-id="e807f-398">如果您未在报告中看到数据，请仔细检查您的策略设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="e807f-398">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="e807f-399">若要了解详细信息，请参阅 [防止威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="e807f-399">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e807f-400">相关主题</span><span class="sxs-lookup"><span data-stu-id="e807f-400">Related topics</span></span>

[<span data-ttu-id="e807f-401">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="e807f-401">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="e807f-402">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="e807f-402">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e807f-403">查看安全 & 合规性中心中的邮件流报告</span><span class="sxs-lookup"><span data-stu-id="e807f-403">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="e807f-404">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="e807f-404">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
