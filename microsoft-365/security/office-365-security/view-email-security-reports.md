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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 了解如何查找和使用组织的电子邮件安全报告。 安全与合规中心提供&报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290795"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="9da91-104">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="9da91-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9da91-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9da91-105">**Applies to**</span></span>
- [<span data-ttu-id="9da91-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9da91-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9da91-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="9da91-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9da91-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9da91-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="9da91-109">安全与合规中心提供了各种报告，可帮助你查看 Microsoft 365 中的电子邮件安全功能（如反垃圾邮件、反恶意软件和加密功能）如何保护你的组织。 [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="9da91-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="9da91-110">如果您具有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以通过访问报告仪表板&安全与合规中心 **查看** \> **这些报告**。</span><span class="sxs-lookup"><span data-stu-id="9da91-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="9da91-111">若要直接转到报表仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="9da91-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全与合规中心&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="9da91-113">遭到入侵的用户报告</span><span class="sxs-lookup"><span data-stu-id="9da91-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="9da91-114">此报告适用于具有 Exchange Online 邮箱的 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="9da91-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="9da91-115">它不适用于独立 Exchange Online Protection (EOP) 组织。</span><span class="sxs-lookup"><span data-stu-id="9da91-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="9da91-116">"**遭到入侵的用户**"报告显示最近 7 天内标记为"可疑"或"受限"的用户帐户数量。</span><span class="sxs-lookup"><span data-stu-id="9da91-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="9da91-117">任一状态的帐户存在问题，甚至受到威胁。</span><span class="sxs-lookup"><span data-stu-id="9da91-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="9da91-118">通过频繁使用，您可以使用报告来发现可疑或受限帐户的峰值甚至趋势。</span><span class="sxs-lookup"><span data-stu-id="9da91-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="9da91-119">有关遭到入侵的用户详细信息，请参阅["响应遭到入侵的电子邮件帐户"。](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="9da91-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

!["报告"仪表板中的"遭到入侵的用户"小组件](../../media/compromised-users-report-widget.png)

<span data-ttu-id="9da91-121">聚合视图显示过去 90 天的数据，而详细信息视图显示过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="9da91-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="9da91-122">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，转到 **"** 报告仪表板 \> "，然后选择"泄露 **的用户"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="9da91-123">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="9da91-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="9da91-124">可以通过单击"筛选器"并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="9da91-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="9da91-125">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="9da91-126">**可疑**：用户帐户已发送可疑电子邮件，并且存在被限制发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="9da91-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="9da91-127">**受限**：由于高度可疑的模式，已限制用户帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9da91-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

!["受到威胁的用户"报告中的报告视图](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="9da91-129">如果单击 **"查看详细信息"表**，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9da91-130">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="9da91-130">**Creation time**</span></span>
- <span data-ttu-id="9da91-131">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="9da91-131">**User ID**</span></span>
- <span data-ttu-id="9da91-132">**操作**</span><span class="sxs-lookup"><span data-stu-id="9da91-132">**Action**</span></span>

<span data-ttu-id="9da91-133">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="9da91-134">加密报告</span><span class="sxs-lookup"><span data-stu-id="9da91-134">Encryption report</span></span>

<span data-ttu-id="9da91-135">加密 **报告适用于** EOP 订阅 (Exchange Online 中的邮箱或没有 Exchange Online 邮箱的独立 EOP 中的) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="9da91-136">组织的安全团队可以使用此报告中的信息识别模式，并主动应用或调整敏感电子邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="9da91-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="9da91-137">例如：</span><span class="sxs-lookup"><span data-stu-id="9da91-137">For example:</span></span>

- <span data-ttu-id="9da91-138">如果您看到大量由用户加密的电子邮件，您可能需要添加加密策略，以自动执行某些用例的加密。</span><span class="sxs-lookup"><span data-stu-id="9da91-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="9da91-139">有关详细信息，请参阅 [定义邮件流规则以加密 Microsoft 365 中的电子邮件](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="9da91-140">如果您具有许多可用的加密模板，但没有人使用它们，您可能会探索用户是否需要功能培训。</span><span class="sxs-lookup"><span data-stu-id="9da91-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="9da91-141">聚合视图允许筛选过去 90 天，而详细信息视图允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="9da91-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="9da91-142">若要查看报告，请打开安全&合规中心，转到 **"** 报告 [仪表板](https://protection.office.com) \> "并选择 **"加密"报告**。</span><span class="sxs-lookup"><span data-stu-id="9da91-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="9da91-143">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="9da91-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="9da91-144">若要了解有关加密的信息，请参阅 [Microsoft 365 中的电子邮件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="9da91-145">加密报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="9da91-145">Report view for the Encryption report</span></span>

<span data-ttu-id="9da91-146">可以在图表上使用以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="9da91-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="9da91-147">**按以下方式查看数据：邮件加密报告** 并分解 **：加密** 方法：以下加密方法可用：</span><span class="sxs-lookup"><span data-stu-id="9da91-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="9da91-148">**按用户加密**</span><span class="sxs-lookup"><span data-stu-id="9da91-148">**Encryption by user**</span></span>
  - <span data-ttu-id="9da91-149">**按策略加密**</span><span class="sxs-lookup"><span data-stu-id="9da91-149">**Encryption by policy**</span></span>

  <span data-ttu-id="9da91-150">如果单击 **"筛选器**"，可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="9da91-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="9da91-151">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9da91-152">加密方法。</span><span class="sxs-lookup"><span data-stu-id="9da91-152">Encryption method.</span></span>
  - <span data-ttu-id="9da91-153">加密模板。</span><span class="sxs-lookup"><span data-stu-id="9da91-153">Encryption template.</span></span>

- <span data-ttu-id="9da91-154">**按以下方式查看数据：邮件加密报告** 并分解 **：加密** 模板：以下加密方法可用：</span><span class="sxs-lookup"><span data-stu-id="9da91-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="9da91-155">**不要转发**</span><span class="sxs-lookup"><span data-stu-id="9da91-155">**Do not forward**</span></span>
  - <span data-ttu-id="9da91-156">**仅加密**</span><span class="sxs-lookup"><span data-stu-id="9da91-156">**Encrypt only**</span></span>
  - <span data-ttu-id="9da91-157">**OME 上一个**</span><span class="sxs-lookup"><span data-stu-id="9da91-157">**OME previous**</span></span>
  - <span data-ttu-id="9da91-158">**自定义**</span><span class="sxs-lookup"><span data-stu-id="9da91-158">**Custom**</span></span>

  <span data-ttu-id="9da91-159">如果单击 **"筛选器**"，可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="9da91-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="9da91-160">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9da91-161">加密方法</span><span class="sxs-lookup"><span data-stu-id="9da91-161">Encryption method</span></span>
  - <span data-ttu-id="9da91-162">加密模板</span><span class="sxs-lookup"><span data-stu-id="9da91-162">Encryption template</span></span>

- <span data-ttu-id="9da91-163">**查看数据者：前 5** 个收件人域：此视图显示包含前 5 个收件人域的已发送邮件计数的饼图。</span><span class="sxs-lookup"><span data-stu-id="9da91-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="9da91-164">如果单击 **"筛选器"，** 可以选择开始日期 **和\*\*\*\*结束日期**。</span><span class="sxs-lookup"><span data-stu-id="9da91-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="9da91-165">加密报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="9da91-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="9da91-166">如果单击 **"查看详细信息"表**，则显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="9da91-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9da91-167">**按：加密方法或** "加密" **模板** 进行分解：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="9da91-168">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-168">**Date**</span></span>
  - <span data-ttu-id="9da91-169">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="9da91-169">**Sender address**</span></span>
  - <span data-ttu-id="9da91-170">**加密模板**</span><span class="sxs-lookup"><span data-stu-id="9da91-170">**Encryption template**</span></span>
  - <span data-ttu-id="9da91-171">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="9da91-171">**Encryption method**</span></span>
  - <span data-ttu-id="9da91-172">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="9da91-172">**Recipient address**</span></span>
  - <span data-ttu-id="9da91-173">**主题**</span><span class="sxs-lookup"><span data-stu-id="9da91-173">**Subject**</span></span>

- <span data-ttu-id="9da91-174">**查看数据者：前 5 个收件人域**：</span><span class="sxs-lookup"><span data-stu-id="9da91-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="9da91-175">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-175">**Date**</span></span>
  - <span data-ttu-id="9da91-176">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="9da91-176">**Recipient domain**</span></span>
  - <span data-ttu-id="9da91-177">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="9da91-177">**Message count**</span></span>

<span data-ttu-id="9da91-178">如果在 **详细信息表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="9da91-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9da91-179">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="9da91-180">加密方法</span><span class="sxs-lookup"><span data-stu-id="9da91-180">Encryption method</span></span>
- <span data-ttu-id="9da91-181">加密模板</span><span class="sxs-lookup"><span data-stu-id="9da91-181">Encryption template</span></span>

<span data-ttu-id="9da91-182">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="9da91-183">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="9da91-183">Mailflow status report</span></span>

<span data-ttu-id="9da91-184">邮件 **流状态报告包含** 有关恶意软件、垃圾邮件、网络钓鱼和边缘阻止邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="9da91-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="9da91-185">有关详细信息，请参阅 [邮件流状态报告](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="9da91-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="9da91-186">电子邮件报告中的恶意软件检测</span><span class="sxs-lookup"><span data-stu-id="9da91-186">Malware detections in email report</span></span>

<span data-ttu-id="9da91-187">电子邮件 **报告中的恶意软件** 检测显示有关传入和传出电子邮件中的恶意软件检测 (Exchange Online Protection 或 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="9da91-188">有关 EOP 中的恶意软件保护详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="9da91-189">聚合视图筛选器允许 90 天，而详细信息表筛选器只允许 10 天。</span><span class="sxs-lookup"><span data-stu-id="9da91-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="9da91-190">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，转到报告 \> **仪表板**，然后选择 **电子邮件中的恶意软件检测**。</span><span class="sxs-lookup"><span data-stu-id="9da91-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="9da91-191">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="9da91-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![报告仪表板中电子邮件小部件中的恶意软件检测](../../media/malware-detections-widget.png)

<span data-ttu-id="9da91-193">通过单击"筛选器"并选择以下选项，可以筛选图表 **和详细信息表** ：</span><span class="sxs-lookup"><span data-stu-id="9da91-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="9da91-194">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="9da91-195">**入站**</span><span class="sxs-lookup"><span data-stu-id="9da91-195">**Inbound**</span></span>
- <span data-ttu-id="9da91-196">**出站**</span><span class="sxs-lookup"><span data-stu-id="9da91-196">**Outbound**</span></span>

![电子邮件报告中恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="9da91-198">如果单击 **"查看详细信息"表**，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9da91-199">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-199">**Date**</span></span>
- <span data-ttu-id="9da91-200">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="9da91-200">**Sender address**</span></span>
- <span data-ttu-id="9da91-201">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="9da91-201">**Recipient address**</span></span>
- <span data-ttu-id="9da91-202">**邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9da91-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="9da91-203">例如， (`<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 中括号) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="9da91-204">**主题**</span><span class="sxs-lookup"><span data-stu-id="9da91-204">**Subject**</span></span>
- <span data-ttu-id="9da91-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="9da91-205">**Filename**</span></span>
- <span data-ttu-id="9da91-206">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="9da91-206">**Malware name**</span></span>

<span data-ttu-id="9da91-207">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="9da91-208">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="9da91-208">Mail latency report</span></span>

<span data-ttu-id="9da91-209">邮件 **延迟报告** 包含有关组织中遇到的邮件传递和触发延迟的信息。</span><span class="sxs-lookup"><span data-stu-id="9da91-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="9da91-210">有关详细信息，请参阅邮件 [延迟报告](view-reports-for-atp.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="9da91-210">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="9da91-211">已发送和已接收电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="9da91-211">Sent and received email report</span></span>

<span data-ttu-id="9da91-212">" **已发送和** 接收的电子邮件"报告包含有关恶意软件、垃圾邮件、邮件流规则 (也称为传输规则) ，以及电子邮件进入服务后的高级恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="9da91-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="9da91-213">有关详细信息，请参阅"[已发送和已接收电子邮件报告"。](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="9da91-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="9da91-214">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="9da91-214">Spam detections report</span></span>

<span data-ttu-id="9da91-215">垃圾邮件 **检测报告显示** EOP 阻止的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="9da91-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="9da91-216">邮件单独计数，而不是按收件人计算。</span><span class="sxs-lookup"><span data-stu-id="9da91-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="9da91-217">例如，如果相同的垃圾邮件发送给了您组织的 100 个收件人，则它算作一封邮件。</span><span class="sxs-lookup"><span data-stu-id="9da91-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="9da91-218">聚合视图允许筛选 90 天，而详细信息表允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="9da91-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="9da91-219">若要查看报告，请打开安全&合规中心，转到"报告 [仪表板](https://protection.office.com) \> "并选择 **"垃圾邮件检测"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="9da91-220">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="9da91-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

!["报告"仪表板中的"垃圾邮件检测"小部件](../../media/spam-detections-report-widget.png)

<span data-ttu-id="9da91-222">有关反垃圾邮件保护的信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="9da91-223">垃圾邮件检测报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="9da91-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="9da91-224">以下图表可在以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="9da91-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9da91-225">**按：操作进行** 分解：显示以下事件类型：</span><span class="sxs-lookup"><span data-stu-id="9da91-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="9da91-226">**已筛选的垃圾邮件内容**</span><span class="sxs-lookup"><span data-stu-id="9da91-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="9da91-227">**垃圾邮件 IP 阻止**</span><span class="sxs-lookup"><span data-stu-id="9da91-227">**Spam IP block**</span></span>
  - <span data-ttu-id="9da91-228">**垃圾邮件信封阻止**</span><span class="sxs-lookup"><span data-stu-id="9da91-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="9da91-229">**垃圾邮件 DBEB 筛选器**：基于目录的边缘阻止 (DBEB) </span><span class="sxs-lookup"><span data-stu-id="9da91-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="9da91-230">当您将鼠标悬停在图表中 (一) 时，可以看到当天被阻止的项目数，以及这些项目的分类方法。</span><span class="sxs-lookup"><span data-stu-id="9da91-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾邮件检测报告中的操作视图](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="9da91-232">**按：方向：** 显示以下方向：</span><span class="sxs-lookup"><span data-stu-id="9da91-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="9da91-233">**入站**</span><span class="sxs-lookup"><span data-stu-id="9da91-233">**Inbound**</span></span>
  - <span data-ttu-id="9da91-234">**出站**</span><span class="sxs-lookup"><span data-stu-id="9da91-234">**Outbound**</span></span>

  ![垃圾邮件检测报告中的方向视图](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="9da91-236">如果 **单击"** 筛选器"报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="9da91-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9da91-237">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="9da91-238">方向值</span><span class="sxs-lookup"><span data-stu-id="9da91-238">Direction values</span></span>
- <span data-ttu-id="9da91-239">事件类型值</span><span class="sxs-lookup"><span data-stu-id="9da91-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="9da91-240">垃圾邮件检测报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="9da91-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="9da91-241">如果在任意视图中 **单击"** 查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="9da91-242">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-242">**Date**</span></span>
- <span data-ttu-id="9da91-243">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="9da91-243">**Sender address**</span></span>
- <span data-ttu-id="9da91-244">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="9da91-244">**Recipient address**</span></span>
- <span data-ttu-id="9da91-245">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="9da91-245">**Event type**</span></span>
- <span data-ttu-id="9da91-246">**操作**</span><span class="sxs-lookup"><span data-stu-id="9da91-246">**Action**</span></span>
- <span data-ttu-id="9da91-247">**主题**</span><span class="sxs-lookup"><span data-stu-id="9da91-247">**Subject**</span></span>

<span data-ttu-id="9da91-248">如果单击详细信息 **表中的** "筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="9da91-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9da91-249">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="9da91-250">方向值</span><span class="sxs-lookup"><span data-stu-id="9da91-250">Direction values</span></span>
- <span data-ttu-id="9da91-251">事件类型值</span><span class="sxs-lookup"><span data-stu-id="9da91-251">Event type values</span></span>

<span data-ttu-id="9da91-252">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="9da91-253">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="9da91-253">Spoof detections report</span></span>

<span data-ttu-id="9da91-254">欺骗 **检测** 报告显示检测到的欺骗邮件数，以及其中哪些邮件被视为"良好" (出于合法业务原因) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="9da91-255">有关欺骗功能的信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="9da91-256">报告的聚合视图允许筛选 90 天，而详细信息视图仅允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="9da91-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="9da91-257">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，转到 **报告** \> **仪表板** 并选择 **欺骗检测**。</span><span class="sxs-lookup"><span data-stu-id="9da91-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="9da91-258">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="9da91-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![报告仪表板中的欺骗检测小组件](../../media/spoof-detections-widget.png)

<span data-ttu-id="9da91-260">当您将鼠标悬停在图表中 (一) 时，可以看到通过多少封欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="9da91-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="9da91-261">可以通过单击"筛选器"并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="9da91-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="9da91-262">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="9da91-263">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="9da91-263">**Good mail**</span></span>

- <span data-ttu-id="9da91-264">**捕获为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="9da91-264">**Caught as spam**</span></span>

![欺骗检测报告中的报告视图](../../media/spoof-detections-report-view.png)

<span data-ttu-id="9da91-266">如果单击 **"查看详细信息"表**，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9da91-267">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-267">**Date**</span></span>
- <span data-ttu-id="9da91-268">**欺骗发件人**</span><span class="sxs-lookup"><span data-stu-id="9da91-268">**Spoofed sender**</span></span>
- <span data-ttu-id="9da91-269">**真正发件人**</span><span class="sxs-lookup"><span data-stu-id="9da91-269">**True sender**</span></span>
- <span data-ttu-id="9da91-270">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="9da91-270">**Sender IP**</span></span>
- <span data-ttu-id="9da91-271">**操作**</span><span class="sxs-lookup"><span data-stu-id="9da91-271">**Action**</span></span>
- <span data-ttu-id="9da91-272">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="9da91-272">**Message count**</span></span>

<span data-ttu-id="9da91-273">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="9da91-274">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="9da91-274">Threat protection status report</span></span>

<span data-ttu-id="9da91-275">威胁 **防护状态** 报告在 EOP 和 Microsoft Defender for Office 365 中均可用;但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="9da91-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="9da91-276">例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看有关 [SharePoint、OneDrive](atp-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件检测到的恶意文件的信息。</span><span class="sxs-lookup"><span data-stu-id="9da91-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="9da91-277">该报告提供包含恶意内容的电子邮件计数，如反恶意软件引擎阻止的文件或网站地址 (URL) 、零时差自动清除[ (ZAP) ](zero-hour-auto-purge.md)和 Defender for Office 365 功能（如安全链接、安全附件和[防](set-up-anti-phishing-policies.md)钓鱼）。 [](atp-safe-links.md) [](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9da91-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="9da91-278">可以使用此信息来确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="9da91-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="9da91-279">**注意**：必须了解，如果邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="9da91-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="9da91-280">若要查看报告， [请打开安全](https://protection.office.com)与合规&，转到 **报告** \> **仪表板** 并选择 **威胁防护状态**。</span><span class="sxs-lookup"><span data-stu-id="9da91-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="9da91-281">若要直接转到报告，请打开以下 URL 之一：</span><span class="sxs-lookup"><span data-stu-id="9da91-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="9da91-282">Microsoft Defender for Office 365： <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="9da91-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="9da91-283">EOP： <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="9da91-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![报告仪表板中的威胁防护状态小组件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="9da91-285">默认情况下，图表显示过去 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="9da91-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="9da91-286">如果单击 **"筛选器**"，可以选择 90 天的日期范围 (试用版订阅可能限制为 30) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="9da91-287">详细信息表视图允许筛选 30 天。</span><span class="sxs-lookup"><span data-stu-id="9da91-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="9da91-288">威胁防护状态报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="9da91-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="9da91-289">以下视图可用：</span><span class="sxs-lookup"><span data-stu-id="9da91-289">The following views are available:</span></span>

- <span data-ttu-id="9da91-290">**查看数据者：概述**：显示以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="9da91-291">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="9da91-291">**Email malware**</span></span>
  - <span data-ttu-id="9da91-292">**电子邮件网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="9da91-292">**Email phish**</span></span>
  - <span data-ttu-id="9da91-293">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="9da91-293">**Content malware**</span></span>

  ![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="9da91-295">**按内容查看数据 \> 恶意软件**<sup>1：</sup>显示了适用于 Office 365 组织的 Microsoft Defender 的以下信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="9da91-296">**反恶意软件引擎**：Microsoft [365](virus-detection-in-spo.md)中的内置病毒检测在 Sharepoint、OneDrive 和 Microsoft Teams 中检测到的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="9da91-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="9da91-297">**文件触发** [：SharePoint、OneDrive](atp-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件检测到的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="9da91-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="9da91-299">**查看数据者：消息替代**：显示以下替代原因信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="9da91-300">**本地跳过**</span><span class="sxs-lookup"><span data-stu-id="9da91-300">**On-premises skip**</span></span>
  - <span data-ttu-id="9da91-301">**IP 允许**</span><span class="sxs-lookup"><span data-stu-id="9da91-301">**IP Allow**</span></span>
  - <span data-ttu-id="9da91-302">**邮件流规则**</span><span class="sxs-lookup"><span data-stu-id="9da91-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="9da91-303">**发件人允许**</span><span class="sxs-lookup"><span data-stu-id="9da91-303">**Sender allow**</span></span>
  - <span data-ttu-id="9da91-304">**域允许**</span><span class="sxs-lookup"><span data-stu-id="9da91-304">**Domain allow**</span></span>
  - <span data-ttu-id="9da91-305">**未启用 ZAP**</span><span class="sxs-lookup"><span data-stu-id="9da91-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="9da91-306">**未启用垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="9da91-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="9da91-307">**用户安全发件人**</span><span class="sxs-lookup"><span data-stu-id="9da91-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="9da91-308">**用户安全域**</span><span class="sxs-lookup"><span data-stu-id="9da91-308">**User Safe Domain**</span></span>

  ![威胁防护状态报告中的邮件替代视图](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="9da91-310">**按以下各项进行分解：检测** 技术和 **查看数据：电子邮件 \>** 网络钓鱼：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="9da91-311">**ATP 生成的 URL** 信誉 <sup>1：</sup>其他 Microsoft 365 客户从 Defender for Office 365 触发生成的恶意 URL 信誉。</span><span class="sxs-lookup"><span data-stu-id="9da91-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="9da91-312">**高级网络钓鱼筛选器**：基于机器学习的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="9da91-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="9da91-313">**反欺骗 - DMARC 失败**：邮件上的 DMARC 身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="9da91-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="9da91-314">**反欺骗 - 组织内部**：发件人正在尝试欺骗收件人域。</span><span class="sxs-lookup"><span data-stu-id="9da91-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="9da91-315">**反欺骗 - 外部域**：发件人正在尝试欺骗某些其他域。</span><span class="sxs-lookup"><span data-stu-id="9da91-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="9da91-316">**品牌模拟**：模拟基于发件人的已知品牌。</span><span class="sxs-lookup"><span data-stu-id="9da91-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="9da91-317">**域模拟**<sup>1：</sup>模拟客户拥有或定义的域。</span><span class="sxs-lookup"><span data-stu-id="9da91-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="9da91-318">**EOP URL 信誉**：恶意 URL 信誉。</span><span class="sxs-lookup"><span data-stu-id="9da91-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="9da91-319">**常规网络钓鱼筛选器**：基于分析员规则的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="9da91-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="9da91-320">**其他**</span><span class="sxs-lookup"><span data-stu-id="9da91-320">**Others**</span></span>
  - <span data-ttu-id="9da91-321">**网络钓鱼 ZAP**<sup>2：</sup>零时差自动清除网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="9da91-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="9da91-322">**URL 触发**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9da91-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="9da91-323">**用户模拟**<sup>1：</sup>模拟由管理员定义或通过邮箱智能学习的用户。</span><span class="sxs-lookup"><span data-stu-id="9da91-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![威胁防护状态报告中网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="9da91-325">**按以下各项进行分解：检测** 技术和 **查看数据：电子邮件 \>** 恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9da91-326">**ATP 生成的文件信誉**<sup>1：Defender</sup>为 Office 365 触发生成的所有恶意文件信誉。</span><span class="sxs-lookup"><span data-stu-id="9da91-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="9da91-327">**反恶意软件引擎**<sup>1：</sup>来自反恶意软件引擎的检测。</span><span class="sxs-lookup"><span data-stu-id="9da91-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="9da91-328">**反恶意软件策略文件类型阻止**：这些是由于邮件中标识的恶意文件类型而筛选掉的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9da91-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="9da91-329">**文件触发**<sup>1：</sup>由安全附件检测。</span><span class="sxs-lookup"><span data-stu-id="9da91-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="9da91-330">**恶意文件信誉**</span><span class="sxs-lookup"><span data-stu-id="9da91-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="9da91-331">**恶意软件 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9da91-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="9da91-332">**其他**</span><span class="sxs-lookup"><span data-stu-id="9da91-332">**Others**</span></span>

  ![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="9da91-334">**按以下各项进行分解：策略类型和\*\*\*\*查看数据：电子邮件 \>** 网络钓鱼或查看数据 **者：电子邮件 \>** 恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9da91-335">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="9da91-335">**Anti-malware**</span></span>
  - <span data-ttu-id="9da91-336">**安全附件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9da91-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="9da91-337">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="9da91-337">**Anti-phish**</span></span>
  - <span data-ttu-id="9da91-338">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="9da91-338">**Anti-spam**</span></span>
  - <span data-ttu-id="9da91-339">**邮件流规则** (也称为传输规则) </span><span class="sxs-lookup"><span data-stu-id="9da91-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="9da91-340">**其他**</span><span class="sxs-lookup"><span data-stu-id="9da91-340">**Others**</span></span>

  ![威胁防护状态报告中网络钓鱼电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="9da91-342">**按以下各项** 进行分解：传递状态和 **查看数据者 \> ：电子邮件** 钓鱼或查看数据 **： \> 电子邮件** 恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9da91-343">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="9da91-343">**Delivery failed**</span></span>
  - <span data-ttu-id="9da91-344">**已丢弃**</span><span class="sxs-lookup"><span data-stu-id="9da91-344">**Dropped**</span></span>
  - <span data-ttu-id="9da91-345">**转发**</span><span class="sxs-lookup"><span data-stu-id="9da91-345">**Forwarded**</span></span>
  - <span data-ttu-id="9da91-346">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="9da91-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="9da91-347">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="9da91-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="9da91-348">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="9da91-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="9da91-349">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="9da91-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="9da91-350">**本地服务器：已送达**</span><span class="sxs-lookup"><span data-stu-id="9da91-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="9da91-351">**隔离**</span><span class="sxs-lookup"><span data-stu-id="9da91-351">**Quarantine**</span></span>

  ![威胁防护状态报告中网络钓鱼电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="9da91-353"><sup>仅 1</sup> 个 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9da91-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="9da91-354"><sup>2 0</sup> 小时自动清除 (ZAP) 在独立 EOP 中不可用 (它仅适用于 Exchange Online 邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="9da91-355">如果单击 **"筛选器**"，可用的筛选器取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="9da91-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9da91-356">对于 **查看数据者：内容 \>** 恶意软件，可以按开始日期和结束日期以及检测值修改 **报告。**</span><span class="sxs-lookup"><span data-stu-id="9da91-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="9da91-357">对于 **"查看数据者：邮件替代**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="9da91-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9da91-358">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9da91-359">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="9da91-359">**Override Reason**</span></span>
  - <span data-ttu-id="9da91-360">**标记**：按应用了指定用户标记的用户或组筛选结果 (包括优先级) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9da91-361">有关用户标记详细信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9da91-362">**域**</span><span class="sxs-lookup"><span data-stu-id="9da91-362">**Domain**</span></span>

- <span data-ttu-id="9da91-363">对于所有其他视图，您可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="9da91-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9da91-364">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9da91-365">**检测**</span><span class="sxs-lookup"><span data-stu-id="9da91-365">**Detection**</span></span>
  - <span data-ttu-id="9da91-366">**受** **：ATP 或** **EOP 保护**</span><span class="sxs-lookup"><span data-stu-id="9da91-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="9da91-367">**标记**：按应用了指定用户标记的用户或组筛选结果 (包括优先级) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9da91-368">有关用户标记详细信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9da91-369">**域**</span><span class="sxs-lookup"><span data-stu-id="9da91-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="9da91-370">威胁防护状态报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="9da91-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="9da91-371">如果单击 **"查看详细信息"表**，则显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="9da91-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9da91-372">**查看数据者：概述**：没有 **"查看详细信息表"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="9da91-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="9da91-373">**按内容查看数据 \> 恶意软件**：</span><span class="sxs-lookup"><span data-stu-id="9da91-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="9da91-374">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-374">**Date**</span></span>
  - <span data-ttu-id="9da91-375">**位置**</span><span class="sxs-lookup"><span data-stu-id="9da91-375">**Location**</span></span>
  - <span data-ttu-id="9da91-376">**定向者**</span><span class="sxs-lookup"><span data-stu-id="9da91-376">**Directed by**</span></span>
  - <span data-ttu-id="9da91-377">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="9da91-377">**Malware name**</span></span>

  <span data-ttu-id="9da91-378">如果 **单击此** 视图中的"筛选器"，可以按开始日期和结束日期以及检测值 **修改报告。**</span><span class="sxs-lookup"><span data-stu-id="9da91-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="9da91-379">**查看数据者：邮件替代**：</span><span class="sxs-lookup"><span data-stu-id="9da91-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="9da91-380">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-380">**Date**</span></span>
  - <span data-ttu-id="9da91-381">**主题**</span><span class="sxs-lookup"><span data-stu-id="9da91-381">**Subject**</span></span>
  - <span data-ttu-id="9da91-382">**发件人**</span><span class="sxs-lookup"><span data-stu-id="9da91-382">**Sender**</span></span>
  - <span data-ttu-id="9da91-383">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="9da91-383">**Recipients**</span></span>
  - <span data-ttu-id="9da91-384">**检测者**</span><span class="sxs-lookup"><span data-stu-id="9da91-384">**Detected by**</span></span>
  - <span data-ttu-id="9da91-385">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="9da91-385">**Override Reason**</span></span>
  - <span data-ttu-id="9da91-386">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="9da91-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="9da91-387">**Tags**</span><span class="sxs-lookup"><span data-stu-id="9da91-387">**Tags**</span></span>

  <span data-ttu-id="9da91-388">如果 **单击此** 视图中的"筛选器"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="9da91-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9da91-389">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9da91-390">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="9da91-390">**Override Reason**</span></span>
  - <span data-ttu-id="9da91-391">**标记**：按应用了指定用户标记的用户或组筛选结果 (包括优先级) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9da91-392">有关用户标记详细信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9da91-393">**域**</span><span class="sxs-lookup"><span data-stu-id="9da91-393">**Domain**</span></span>
  - <span data-ttu-id="9da91-394">**收件人** (请注意，此可筛选属性仅在详细信息表视图视图中) </span><span class="sxs-lookup"><span data-stu-id="9da91-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="9da91-395">所有其他图表：</span><span class="sxs-lookup"><span data-stu-id="9da91-395">All other charts:</span></span>

  - <span data-ttu-id="9da91-396">"日期"</span><span class="sxs-lookup"><span data-stu-id="9da91-396">**Date**</span></span>
  - <span data-ttu-id="9da91-397">**主题**</span><span class="sxs-lookup"><span data-stu-id="9da91-397">**Subject**</span></span>
  - <span data-ttu-id="9da91-398">**发件人**</span><span class="sxs-lookup"><span data-stu-id="9da91-398">**Sender**</span></span>
  - <span data-ttu-id="9da91-399">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="9da91-399">**Recipients**</span></span>
  - <span data-ttu-id="9da91-400">**检测者**</span><span class="sxs-lookup"><span data-stu-id="9da91-400">**Detected by**</span></span>
  - <span data-ttu-id="9da91-401">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="9da91-401">**Delivery Status**</span></span>
  - <span data-ttu-id="9da91-402">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="9da91-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="9da91-403">**Tags**</span><span class="sxs-lookup"><span data-stu-id="9da91-403">**Tags**</span></span>

  <span data-ttu-id="9da91-404">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="9da91-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9da91-405">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="9da91-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9da91-406">**检测**</span><span class="sxs-lookup"><span data-stu-id="9da91-406">**Detection**</span></span>
  - <span data-ttu-id="9da91-407">**受 ：Defender** **for Office 365** 或 **EOP 保护**</span><span class="sxs-lookup"><span data-stu-id="9da91-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="9da91-408">**标记**：按应用了指定用户标记的用户或组筛选结果 (包括优先级) 。</span><span class="sxs-lookup"><span data-stu-id="9da91-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9da91-409">有关用户标记详细信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9da91-410">**域**</span><span class="sxs-lookup"><span data-stu-id="9da91-410">**Domain**</span></span>
  - <span data-ttu-id="9da91-411">**收件人** (请注意，此可筛选属性仅在详细信息表视图视图中) </span><span class="sxs-lookup"><span data-stu-id="9da91-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="9da91-412">热门恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="9da91-412">Top malware report</span></span>

<span data-ttu-id="9da91-413">顶级 **恶意软件** 报告显示 EOP 中的反恶意软件保护检测到 [的各种恶意软件](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="9da91-414">若要查看报告，[请打开安全](https://protection.office.com)与合规&，转到 **"** 报告仪表板 \> "，然后选择 **"热门恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="9da91-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="9da91-415">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="9da91-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

!["报告"仪表板中的"首要恶意软件"小部件](../../media/top-malware-report-widget.png)

<span data-ttu-id="9da91-417">当您将鼠标悬停在饼图中的一角上时，可以看到某种恶意软件的名称，以及检测到有多少邮件具有该恶意软件。</span><span class="sxs-lookup"><span data-stu-id="9da91-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![热门恶意软件报表视图](../../media/top-malware-report-view.png)

<span data-ttu-id="9da91-419">如果单击 **"查看详细信息"表**，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="9da91-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9da91-420">**热门恶意软件**</span><span class="sxs-lookup"><span data-stu-id="9da91-420">**Top malware**</span></span>
- <span data-ttu-id="9da91-421">**Count**</span><span class="sxs-lookup"><span data-stu-id="9da91-421">**Count**</span></span>

<span data-ttu-id="9da91-422">如果在 **视图或** 详细信息表视图中报表视图筛选器，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="9da91-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="9da91-423">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="9da91-423">URL threat protection report</span></span>

<span data-ttu-id="9da91-424">MICROSOFT Defender for Office 365 中提供了 **URL** 威胁防护报告。</span><span class="sxs-lookup"><span data-stu-id="9da91-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9da91-425">有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-atp.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="9da91-425">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="9da91-426">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="9da91-426">User-reported messages report</span></span>

<span data-ttu-id="9da91-427">用户 **报告** 的邮件报告显示有关用户使用报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、网络钓鱼尝试或良好邮件 [的电子邮件的信息](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="9da91-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="9da91-428">每个邮件的详细信息都可用，包括传递原因，例如为组织配置的垃圾邮件策略例外或邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="9da91-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="9da91-429">若要查看详细信息，请选择用户报告列表中的某个项，然后查看"摘要"和"详细信息"**选项卡\*\*\*\*上** 的信息。</span><span class="sxs-lookup"><span data-stu-id="9da91-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

!["User-Reported"报告显示用户标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试的邮件。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="9da91-431">若要查看此报告，在安全& [合规中心](https://protection.office.com)，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9da91-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="9da91-432">转到 **威胁管理** \> **仪表板** \> **用户报告的消息**。</span><span class="sxs-lookup"><span data-stu-id="9da91-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="9da91-433">转到 **"威胁管理** \> **"查看** \> **用户报告的邮件**。</span><span class="sxs-lookup"><span data-stu-id="9da91-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![在安全与&中心，选择"威胁管理 \> 审阅 \> 用户报告的邮件"](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="9da91-435">为了使用户报告的邮件报告正常工作，必须为 Office 365 环境启用审核日志记录。 </span><span class="sxs-lookup"><span data-stu-id="9da91-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="9da91-436">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="9da91-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="9da91-437">有关详细信息，请参阅打开或审核日志 [Microsoft 365 搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="9da91-438">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="9da91-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="9da91-439">若要查看和使用本文中所述的报告，您需要是安全与合规中心内以下角色组&之一：</span><span class="sxs-lookup"><span data-stu-id="9da91-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9da91-440">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="9da91-440">**Organization Management**</span></span>
- <span data-ttu-id="9da91-441">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="9da91-441">**Security Administrator**</span></span>
- <span data-ttu-id="9da91-442">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="9da91-442">**Security Reader**</span></span>
- <span data-ttu-id="9da91-443">**全局阅读器**</span><span class="sxs-lookup"><span data-stu-id="9da91-443">**Global Reader**</span></span>

<span data-ttu-id="9da91-444">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="9da91-445">注意：将用户添加到 Microsoft 36 & 5 管理中心的相应 Azure Active Directory 角色会为用户提供安全与合规中心中所需的权限以及 Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="9da91-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9da91-446">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="9da91-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="9da91-447">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="9da91-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="9da91-448">如果报告中未显示数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="9da91-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="9da91-449">若要了解更多信息，请参阅["防范威胁"。](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="9da91-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9da91-450">相关主题</span><span class="sxs-lookup"><span data-stu-id="9da91-450">Related topics</span></span>

[<span data-ttu-id="9da91-451">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="9da91-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="9da91-452">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="9da91-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="9da91-453">在安全与合规中心&邮件流报告</span><span class="sxs-lookup"><span data-stu-id="9da91-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="9da91-454">查看适用于 Office 365 的 Defender 报告</span><span class="sxs-lookup"><span data-stu-id="9da91-454">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
