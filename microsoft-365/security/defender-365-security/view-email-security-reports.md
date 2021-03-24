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
ms.openlocfilehash: 5d9f6d12fef8a2ef6241fbbd5e0e2a980284e9cc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055141"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="1b821-104">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="1b821-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1b821-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="1b821-105">**Applies to**</span></span>
- [<span data-ttu-id="1b821-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1b821-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1b821-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="1b821-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1b821-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b821-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1b821-109">安全与合规中心提供了各种报告 [&，](https://protection.office.com) 可帮助你查看电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能）如何保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="1b821-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="1b821-110">如果您具有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在安全与合规中心内查看这些报告&"报告仪表板 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="1b821-111">若要直接转到"报表"仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="1b821-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全与合规中心&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="1b821-113">遭到入侵的用户报告</span><span class="sxs-lookup"><span data-stu-id="1b821-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="1b821-114">此报告适用于具有 Exchange Online 邮箱的 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="1b821-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="1b821-115">它不适用于独立 Exchange Online Protection (EOP) 组织。</span><span class="sxs-lookup"><span data-stu-id="1b821-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="1b821-116">"**遭到入侵的用户**"报告显示过去 7 天内标记为"可疑"或"受限"的用户帐户数量。</span><span class="sxs-lookup"><span data-stu-id="1b821-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="1b821-117">其中任一状态的帐户存在问题，甚至受到威胁。</span><span class="sxs-lookup"><span data-stu-id="1b821-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="1b821-118">通过频繁使用，可以使用报告来发现可疑或受限帐户的峰值甚至趋势。</span><span class="sxs-lookup"><span data-stu-id="1b821-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="1b821-119">有关遭到入侵的用户详细信息，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

!["报告"仪表板中的"遭到入侵的用户"小组件](../../media/compromised-users-report-widget.png)

<span data-ttu-id="1b821-121">聚合视图显示过去 90 天的数据，而详细信息视图显示最近 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="1b821-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="1b821-122">若要查看报告，请打开安全与合规 [&，转到](https://protection.office.com)**报告仪表板** \> 并选择 **泄露的用户**。</span><span class="sxs-lookup"><span data-stu-id="1b821-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="1b821-123">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="1b821-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="1b821-124">通过单击"筛选器"并选择以下一个或多个值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="1b821-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="1b821-125">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="1b821-126">**可疑**：用户帐户已发送可疑电子邮件，并且存在被限制发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="1b821-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="1b821-127">**受限**：由于高度可疑的模式，已限制用户帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b821-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

!["泄露的用户"报告中的报告视图](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="1b821-129">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1b821-130">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="1b821-130">**Creation time**</span></span>
- <span data-ttu-id="1b821-131">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="1b821-131">**User ID**</span></span>
- <span data-ttu-id="1b821-132">**操作**</span><span class="sxs-lookup"><span data-stu-id="1b821-132">**Action**</span></span>

<span data-ttu-id="1b821-133">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="1b821-134">加密报告</span><span class="sxs-lookup"><span data-stu-id="1b821-134">Encryption report</span></span>

<span data-ttu-id="1b821-135">加密 **报告** 适用于在 Exchange Online (没有 Exchange Online 邮箱的独立 EOP 中的邮箱的 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="1b821-136">组织的安全团队可以使用此报告中的信息来识别模式，并主动应用或调整敏感电子邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="1b821-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="1b821-137">例如：</span><span class="sxs-lookup"><span data-stu-id="1b821-137">For example:</span></span>

- <span data-ttu-id="1b821-138">如果您看到大量由用户加密的电子邮件，您可能需要添加加密策略以自动加密某些用例。</span><span class="sxs-lookup"><span data-stu-id="1b821-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="1b821-139">有关详细信息，请参阅在 [Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)中定义用于加密电子邮件的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="1b821-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="1b821-140">如果您具有许多可用的加密模板，但没有人使用它们，您可能会探索用户是否需要功能培训。</span><span class="sxs-lookup"><span data-stu-id="1b821-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="1b821-141">聚合视图允许筛选过去 90 天，而详细信息视图允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="1b821-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="1b821-142">若要查看报告，请打开安全与&[中心，](https://protection.office.com)**转到报告** 仪表板 \> ，然后选择加密 **报告**。</span><span class="sxs-lookup"><span data-stu-id="1b821-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="1b821-143">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="1b821-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="1b821-144">若要详细了解加密，请参阅 [Microsoft 365 中的电子邮件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="1b821-145">加密报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="1b821-145">Report view for the Encryption report</span></span>

<span data-ttu-id="1b821-146">可以在图表上使用以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="1b821-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="1b821-147">**按以下方式查看数据：邮件加密报告** 并按以下方式进行分解 **：加密** 方法：可以使用以下加密方法：</span><span class="sxs-lookup"><span data-stu-id="1b821-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="1b821-148">**按用户加密**</span><span class="sxs-lookup"><span data-stu-id="1b821-148">**Encryption by user**</span></span>
  - <span data-ttu-id="1b821-149">**按策略加密**</span><span class="sxs-lookup"><span data-stu-id="1b821-149">**Encryption by policy**</span></span>

  <span data-ttu-id="1b821-150">如果单击 **"筛选器"，** 可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="1b821-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="1b821-151">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1b821-152">加密方法。</span><span class="sxs-lookup"><span data-stu-id="1b821-152">Encryption method.</span></span>
  - <span data-ttu-id="1b821-153">加密模板。</span><span class="sxs-lookup"><span data-stu-id="1b821-153">Encryption template.</span></span>

- <span data-ttu-id="1b821-154">**按以下方式查看数据：邮件加密报告** 并按： **加密** 模板进行分解：可以使用以下加密方法：</span><span class="sxs-lookup"><span data-stu-id="1b821-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="1b821-155">**不要转发**</span><span class="sxs-lookup"><span data-stu-id="1b821-155">**Do not forward**</span></span>
  - <span data-ttu-id="1b821-156">**仅加密**</span><span class="sxs-lookup"><span data-stu-id="1b821-156">**Encrypt only**</span></span>
  - <span data-ttu-id="1b821-157">**OME 上一个**</span><span class="sxs-lookup"><span data-stu-id="1b821-157">**OME previous**</span></span>
  - <span data-ttu-id="1b821-158">**自定义**</span><span class="sxs-lookup"><span data-stu-id="1b821-158">**Custom**</span></span>

  <span data-ttu-id="1b821-159">如果单击 **"筛选器"，** 可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="1b821-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="1b821-160">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1b821-161">加密方法</span><span class="sxs-lookup"><span data-stu-id="1b821-161">Encryption method</span></span>
  - <span data-ttu-id="1b821-162">加密模板</span><span class="sxs-lookup"><span data-stu-id="1b821-162">Encryption template</span></span>

- <span data-ttu-id="1b821-163">**查看数据者：前 5 个** 收件人域：此视图显示包含前 5 个收件人域的已发送邮件计数的饼图。</span><span class="sxs-lookup"><span data-stu-id="1b821-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="1b821-164">如果单击 **"筛选器"，** 可以选择"**开始日期"和**"**结束日期"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="1b821-165">加密报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="1b821-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="1b821-166">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="1b821-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1b821-167">**分解方式：加密方法** 或按： **加密** 模板进行分解：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="1b821-168">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-168">**Date**</span></span>
  - <span data-ttu-id="1b821-169">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="1b821-169">**Sender address**</span></span>
  - <span data-ttu-id="1b821-170">**加密模板**</span><span class="sxs-lookup"><span data-stu-id="1b821-170">**Encryption template**</span></span>
  - <span data-ttu-id="1b821-171">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="1b821-171">**Encryption method**</span></span>
  - <span data-ttu-id="1b821-172">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="1b821-172">**Recipient address**</span></span>
  - <span data-ttu-id="1b821-173">**主题**</span><span class="sxs-lookup"><span data-stu-id="1b821-173">**Subject**</span></span>

- <span data-ttu-id="1b821-174">**查看数据者：前 5 个收件人域**：</span><span class="sxs-lookup"><span data-stu-id="1b821-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="1b821-175">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-175">**Date**</span></span>
  - <span data-ttu-id="1b821-176">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="1b821-176">**Recipient domain**</span></span>
  - <span data-ttu-id="1b821-177">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="1b821-177">**Message count**</span></span>

<span data-ttu-id="1b821-178">如果在详细信息 **表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="1b821-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1b821-179">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="1b821-180">加密方法</span><span class="sxs-lookup"><span data-stu-id="1b821-180">Encryption method</span></span>
- <span data-ttu-id="1b821-181">加密模板</span><span class="sxs-lookup"><span data-stu-id="1b821-181">Encryption template</span></span>

<span data-ttu-id="1b821-182">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="1b821-183">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="1b821-183">Mailflow status report</span></span>

<span data-ttu-id="1b821-184">邮件 **流状态报告** 包含有关恶意软件、垃圾邮件、网络钓鱼和边缘阻止邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="1b821-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="1b821-185">有关详细信息，请参阅邮件 [流状态报告](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="1b821-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="1b821-186">电子邮件报告中的恶意软件检测</span><span class="sxs-lookup"><span data-stu-id="1b821-186">Malware detections in email report</span></span>

<span data-ttu-id="1b821-187">电子邮件 **报告中的恶意软件** 检测显示有关传入和传出电子邮件中的恶意软件检测 (Exchange Online Protection 或 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="1b821-188">有关 EOP 中的恶意软件保护详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="1b821-189">聚合视图筛选器允许 90 天，而详细信息表筛选器仅允许 10 天。</span><span class="sxs-lookup"><span data-stu-id="1b821-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="1b821-190">若要查看报告，请打开安全与&中心，转到报告 [仪表板](https://protection.office.com) \> ，然后选择 **电子邮件中的恶意软件检测**。</span><span class="sxs-lookup"><span data-stu-id="1b821-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="1b821-191">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="1b821-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

!["报告"仪表板中电子邮件小部件中的恶意软件检测](../../media/malware-detections-widget.png)

<span data-ttu-id="1b821-193">通过单击"筛选器"并选择以下选项，可以筛选图表 **和详细信息** 表：</span><span class="sxs-lookup"><span data-stu-id="1b821-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="1b821-194">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="1b821-195">**入站**</span><span class="sxs-lookup"><span data-stu-id="1b821-195">**Inbound**</span></span>
- <span data-ttu-id="1b821-196">**出站**</span><span class="sxs-lookup"><span data-stu-id="1b821-196">**Outbound**</span></span>

![电子邮件报告中的恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="1b821-198">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1b821-199">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-199">**Date**</span></span>
- <span data-ttu-id="1b821-200">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="1b821-200">**Sender address**</span></span>
- <span data-ttu-id="1b821-201">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="1b821-201">**Recipient address**</span></span>
- <span data-ttu-id="1b821-202">**邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1b821-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="1b821-203">示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="1b821-204">**主题**</span><span class="sxs-lookup"><span data-stu-id="1b821-204">**Subject**</span></span>
- <span data-ttu-id="1b821-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="1b821-205">**Filename**</span></span>
- <span data-ttu-id="1b821-206">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="1b821-206">**Malware name**</span></span>

<span data-ttu-id="1b821-207">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="1b821-208">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="1b821-208">Mail latency report</span></span>

<span data-ttu-id="1b821-209">邮件 **延迟报告** 包含有关组织中遇到的邮件传递和触发延迟的信息。</span><span class="sxs-lookup"><span data-stu-id="1b821-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="1b821-210">有关详细信息，请参阅邮件 [延迟报告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="1b821-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="1b821-211">已发送和已接收电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="1b821-211">Sent and received email report</span></span>

<span data-ttu-id="1b821-212">" **已发送和** 已接收电子邮件"报告包含有关恶意软件、垃圾邮件、邮件流规则 (也称为传输规则) ，以及电子邮件进入服务后的高级恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="1b821-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="1b821-213">有关详细信息，请参阅已 [发送和已接收电子邮件报告](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="1b821-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="1b821-214">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="1b821-214">Spam detections report</span></span>

<span data-ttu-id="1b821-215">垃圾邮件 **检测报告显示** EOP 阻止的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="1b821-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="1b821-216">邮件单独计数，而不是按收件人计数。</span><span class="sxs-lookup"><span data-stu-id="1b821-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="1b821-217">例如，如果将同一垃圾邮件发送给您组织的 100 个收件人，则它算作一封邮件。</span><span class="sxs-lookup"><span data-stu-id="1b821-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="1b821-218">聚合视图允许筛选 90 天，而详细信息表允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="1b821-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="1b821-219">若要查看报告，请打开安全与&中心 **，转到报告**[仪表板](https://protection.office.com) \> ，然后选择垃圾邮件 **检测**。</span><span class="sxs-lookup"><span data-stu-id="1b821-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="1b821-220">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="1b821-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

!["报告"仪表板中的"垃圾邮件检测"小组件](../../media/spam-detections-report-widget.png)

<span data-ttu-id="1b821-222">有关反垃圾邮件保护的信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="1b821-223">垃圾邮件检测报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="1b821-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="1b821-224">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="1b821-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="1b821-225">**Break down by： Action**： The following event types are shown：</span><span class="sxs-lookup"><span data-stu-id="1b821-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="1b821-226">**已筛选的垃圾邮件内容**</span><span class="sxs-lookup"><span data-stu-id="1b821-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="1b821-227">**垃圾邮件 IP 阻止**</span><span class="sxs-lookup"><span data-stu-id="1b821-227">**Spam IP block**</span></span>
  - <span data-ttu-id="1b821-228">**垃圾邮件信封阻止**</span><span class="sxs-lookup"><span data-stu-id="1b821-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="1b821-229">**垃圾邮件 DBEB 筛选器**：基于目录的边缘阻止 (DBEB) </span><span class="sxs-lookup"><span data-stu-id="1b821-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="1b821-230">当您将鼠标悬停在图表中 (数据点) 时，可以看到当天阻止的项目数以及如何对这些项目进行分类。</span><span class="sxs-lookup"><span data-stu-id="1b821-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾邮件检测报告中的操作视图](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="1b821-232">**中断时间：方向**：显示以下方向：</span><span class="sxs-lookup"><span data-stu-id="1b821-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="1b821-233">**入站**</span><span class="sxs-lookup"><span data-stu-id="1b821-233">**Inbound**</span></span>
  - <span data-ttu-id="1b821-234">**出站**</span><span class="sxs-lookup"><span data-stu-id="1b821-234">**Outbound**</span></span>

  ![垃圾邮件检测报告中的方向视图](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="1b821-236">如果 **单击筛选器** 中的报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="1b821-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1b821-237">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="1b821-238">方向值</span><span class="sxs-lookup"><span data-stu-id="1b821-238">Direction values</span></span>
- <span data-ttu-id="1b821-239">事件类型值</span><span class="sxs-lookup"><span data-stu-id="1b821-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="1b821-240">垃圾邮件检测报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="1b821-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="1b821-241">如果在任 **一视图中单击** "查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="1b821-242">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-242">**Date**</span></span>
- <span data-ttu-id="1b821-243">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="1b821-243">**Sender address**</span></span>
- <span data-ttu-id="1b821-244">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="1b821-244">**Recipient address**</span></span>
- <span data-ttu-id="1b821-245">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="1b821-245">**Event type**</span></span>
- <span data-ttu-id="1b821-246">**操作**</span><span class="sxs-lookup"><span data-stu-id="1b821-246">**Action**</span></span>
- <span data-ttu-id="1b821-247">**主题**</span><span class="sxs-lookup"><span data-stu-id="1b821-247">**Subject**</span></span>

<span data-ttu-id="1b821-248">如果单击 **详细信息表中的** "筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="1b821-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1b821-249">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="1b821-250">方向值</span><span class="sxs-lookup"><span data-stu-id="1b821-250">Direction values</span></span>
- <span data-ttu-id="1b821-251">事件类型值</span><span class="sxs-lookup"><span data-stu-id="1b821-251">Event type values</span></span>

<span data-ttu-id="1b821-252">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="1b821-253">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="1b821-253">Spoof detections report</span></span>

<span data-ttu-id="1b821-254">欺骗 **检测** 报告显示检测到的欺骗邮件数，以及出于合法业务原因 (欺骗邮件被视为"良好"的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="1b821-255">有关欺骗功能详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="1b821-256">报告聚合视图允许筛选 90 天，而详细信息视图仅允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="1b821-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="1b821-257">若要查看报告，请打开安全与&中心，**转到报告**[仪表板](https://protection.office.com) \> 并选择 **欺骗检测**。</span><span class="sxs-lookup"><span data-stu-id="1b821-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="1b821-258">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="1b821-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![报告仪表板中的欺骗检测小组件](../../media/spoof-detections-widget.png)

<span data-ttu-id="1b821-260">当您将鼠标悬停在 (中) 的数据点时，可以看到经过多少封欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="1b821-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="1b821-261">通过单击"筛选器"并选择以下一个或多个值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="1b821-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="1b821-262">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="1b821-263">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="1b821-263">**Good mail**</span></span>

- <span data-ttu-id="1b821-264">**捕获为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="1b821-264">**Caught as spam**</span></span>

![欺骗检测报告中的报告视图](../../media/spoof-detections-report-view.png)

<span data-ttu-id="1b821-266">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1b821-267">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-267">**Date**</span></span>
- <span data-ttu-id="1b821-268">**欺骗发件人**</span><span class="sxs-lookup"><span data-stu-id="1b821-268">**Spoofed sender**</span></span>
- <span data-ttu-id="1b821-269">**真正的发件人**</span><span class="sxs-lookup"><span data-stu-id="1b821-269">**True sender**</span></span>
- <span data-ttu-id="1b821-270">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="1b821-270">**Sender IP**</span></span>
- <span data-ttu-id="1b821-271">**操作**</span><span class="sxs-lookup"><span data-stu-id="1b821-271">**Action**</span></span>
- <span data-ttu-id="1b821-272">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="1b821-272">**Message count**</span></span>

<span data-ttu-id="1b821-273">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="1b821-274">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="1b821-274">Threat protection status report</span></span>

<span data-ttu-id="1b821-275">威胁 **防护状态报告** 在 EOP 和 Microsoft Defender for Office 365 中均可用;但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="1b821-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="1b821-276">例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看有关 [SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件检测到的恶意文件的信息。</span><span class="sxs-lookup"><span data-stu-id="1b821-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1b821-277">该报告提供包含恶意内容的电子邮件（如反恶意软件引擎阻止的文件或网站地址 (URL) 、零时差自动清除[ (ZAP) ](zero-hour-auto-purge.md)和 Defender for Office 365 功能（如安全链接、安全附件和[防](set-up-anti-phishing-policies.md)钓鱼）的计数。 [](safe-links.md) [](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="1b821-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="1b821-278">您可以使用此信息来确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="1b821-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="1b821-279">**注意**：如果邮件发送给五个收件人，则我们将邮件计为五个不同的邮件，而不是一封邮件，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="1b821-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="1b821-280">若要查看报告，请打开安全与&中心，**转到报告**[仪表板](https://protection.office.com) \> ，然后选择 **威胁防护状态**。</span><span class="sxs-lookup"><span data-stu-id="1b821-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="1b821-281">若要直接转到报告，请打开以下 URL 之一：</span><span class="sxs-lookup"><span data-stu-id="1b821-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="1b821-282">Microsoft Defender for Office 365： <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="1b821-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="1b821-283">EOP： <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="1b821-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![报告仪表板中的威胁防护状态小组件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="1b821-285">默认情况下，图表显示过去 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="1b821-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="1b821-286">如果单击 **"筛选器**"，可以选择 90 天的日期范围 (试用版订阅可能限制为 30) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="1b821-287">详细信息表视图允许筛选 30 天。</span><span class="sxs-lookup"><span data-stu-id="1b821-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="1b821-288">威胁防护状态报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="1b821-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="1b821-289">以下视图可用：</span><span class="sxs-lookup"><span data-stu-id="1b821-289">The following views are available:</span></span>

- <span data-ttu-id="1b821-290">**查看数据者：概述**：显示以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="1b821-291">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="1b821-291">**Email malware**</span></span>
  - <span data-ttu-id="1b821-292">**电子邮件钓鱼邮件**</span><span class="sxs-lookup"><span data-stu-id="1b821-292">**Email phish**</span></span>
  - <span data-ttu-id="1b821-293">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="1b821-293">**Content malware**</span></span>

  ![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="1b821-295">**查看数据者：内容 \> 恶意软件**<sup>1：</sup>显示了适用于 Office 365 组织的 Microsoft Defender 的以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="1b821-296">**反恶意软件引擎**：Microsoft [365](virus-detection-in-spo.md)中的内置病毒检测在 Sharepoint、OneDrive 和 Microsoft Teams 中检测到的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="1b821-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="1b821-297">**文件触发**[：SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件检测到的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="1b821-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="1b821-299">**查看数据者：消息替代**：显示以下替代原因信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="1b821-300">**本地跳过**</span><span class="sxs-lookup"><span data-stu-id="1b821-300">**On-premises skip**</span></span>
  - <span data-ttu-id="1b821-301">**IP 允许**</span><span class="sxs-lookup"><span data-stu-id="1b821-301">**IP Allow**</span></span>
  - <span data-ttu-id="1b821-302">**邮件流规则**</span><span class="sxs-lookup"><span data-stu-id="1b821-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="1b821-303">**发件人允许**</span><span class="sxs-lookup"><span data-stu-id="1b821-303">**Sender allow**</span></span>
  - <span data-ttu-id="1b821-304">**域允许**</span><span class="sxs-lookup"><span data-stu-id="1b821-304">**Domain allow**</span></span>
  - <span data-ttu-id="1b821-305">**ZAP 未启用**</span><span class="sxs-lookup"><span data-stu-id="1b821-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="1b821-306">**未启用垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="1b821-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="1b821-307">**用户安全发件人**</span><span class="sxs-lookup"><span data-stu-id="1b821-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="1b821-308">**用户安全域**</span><span class="sxs-lookup"><span data-stu-id="1b821-308">**User Safe Domain**</span></span>

  ![威胁防护状态报告中的邮件替代视图](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="1b821-310">**按以下条件进行分解：检测** 技术和 **查看数据者： \> 电子邮件** 钓鱼邮件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="1b821-311">**ATP 生成的 URL 信誉**<sup>1：</sup>其他 Microsoft 365 客户的 Defender for Office 365 触发生成的恶意 URL 信誉。</span><span class="sxs-lookup"><span data-stu-id="1b821-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="1b821-312">**高级钓鱼筛选器**：基于机器学习的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="1b821-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="1b821-313">**反欺骗 - DMARC 失败**：邮件上的 DMARC 身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="1b821-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="1b821-314">**反欺骗 - 组织内部**：发件人正在尝试欺骗收件人域。</span><span class="sxs-lookup"><span data-stu-id="1b821-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="1b821-315">**反欺骗 - 外部域**：发件人正在尝试欺骗其他一些域。</span><span class="sxs-lookup"><span data-stu-id="1b821-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="1b821-316">**品牌模拟**：模拟基于发件人的已知品牌。</span><span class="sxs-lookup"><span data-stu-id="1b821-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="1b821-317">**域模拟**<sup>1：</sup>模拟客户拥有或定义的域。</span><span class="sxs-lookup"><span data-stu-id="1b821-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="1b821-318">**EOP URL 信誉**：恶意 URL 信誉。</span><span class="sxs-lookup"><span data-stu-id="1b821-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="1b821-319">**常规网络钓鱼筛选器**：基于分析员规则的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="1b821-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="1b821-320">**其他**</span><span class="sxs-lookup"><span data-stu-id="1b821-320">**Others**</span></span>
  - <span data-ttu-id="1b821-321">**网络钓鱼 ZAP**<sup>2：</sup>零时差自动清除网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="1b821-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="1b821-322">**URL 触发**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b821-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="1b821-323">**用户模拟**<sup>1：</sup>模拟管理员定义或通过邮箱智能学习的用户。</span><span class="sxs-lookup"><span data-stu-id="1b821-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![威胁防护状态报告中的网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="1b821-325">**按以下条件进行分解：检测** 技术和 **查看数据者： \> 电子邮件** 恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="1b821-326">**ATP 生成的文件信誉**<sup>1：Defender</sup>for Office 365 触发生成的所有恶意文件信誉。</span><span class="sxs-lookup"><span data-stu-id="1b821-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="1b821-327">**反恶意软件引擎**<sup>1：</sup>来自反恶意软件引擎的检测。</span><span class="sxs-lookup"><span data-stu-id="1b821-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="1b821-328">**反恶意软件策略文件类型阻止**：这些是由于邮件中标识的恶意文件类型而筛选掉的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b821-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="1b821-329">**文件触发**<sup>1：</sup>安全附件检测。</span><span class="sxs-lookup"><span data-stu-id="1b821-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="1b821-330">**恶意文件信誉**</span><span class="sxs-lookup"><span data-stu-id="1b821-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="1b821-331">**恶意软件 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1b821-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="1b821-332">**其他**</span><span class="sxs-lookup"><span data-stu-id="1b821-332">**Others**</span></span>

  ![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="1b821-334">**按以下条件进行分解：策略** 类型和 **查看数据者：电子邮件 \> 钓鱼** 或查看数据 **者： \>** 电子邮件恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="1b821-335">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="1b821-335">**Anti-malware**</span></span>
  - <span data-ttu-id="1b821-336">**安全附件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b821-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="1b821-337">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="1b821-337">**Anti-phish**</span></span>
  - <span data-ttu-id="1b821-338">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="1b821-338">**Anti-spam**</span></span>
  - <span data-ttu-id="1b821-339">**邮件流规则** (也称为传输规则) </span><span class="sxs-lookup"><span data-stu-id="1b821-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="1b821-340">**其他**</span><span class="sxs-lookup"><span data-stu-id="1b821-340">**Others**</span></span>

  ![威胁防护状态报告中的网络钓鱼电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="1b821-342">**按以下条件进行分解：传递** 状态和 **查看数据者：电子邮件 \> 钓鱼** 邮件或查看数据 **者： \>** 电子邮件恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="1b821-343">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="1b821-343">**Delivery failed**</span></span>
  - <span data-ttu-id="1b821-344">**已丢弃**</span><span class="sxs-lookup"><span data-stu-id="1b821-344">**Dropped**</span></span>
  - <span data-ttu-id="1b821-345">**转发**</span><span class="sxs-lookup"><span data-stu-id="1b821-345">**Forwarded**</span></span>
  - <span data-ttu-id="1b821-346">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="1b821-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="1b821-347">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="1b821-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="1b821-348">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="1b821-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="1b821-349">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="1b821-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="1b821-350">**本地服务器：已传递**</span><span class="sxs-lookup"><span data-stu-id="1b821-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="1b821-351">**隔离**</span><span class="sxs-lookup"><span data-stu-id="1b821-351">**Quarantine**</span></span>

  ![威胁防护状态报告中网络钓鱼电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="1b821-353"><sup>仅 1</sup> 个 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1b821-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="1b821-354"><sup>2"</sup> 零时差自动清除" (ZAP) 在独立 EOP 中 (它仅适用于 Exchange Online 邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="1b821-355">如果单击 **"筛选器**"，可用的筛选器取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="1b821-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1b821-356">For **View data by： Content \> Malware**， you can modify the report by **Start date** and End **date**， and the **Detection** value.</span><span class="sxs-lookup"><span data-stu-id="1b821-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="1b821-357">对于 **View data by： Message Override**，您可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="1b821-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1b821-358">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1b821-359">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="1b821-359">**Override Reason**</span></span>
  - <span data-ttu-id="1b821-360">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1b821-361">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1b821-362">**域**</span><span class="sxs-lookup"><span data-stu-id="1b821-362">**Domain**</span></span>

- <span data-ttu-id="1b821-363">对于所有其他视图，您可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="1b821-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1b821-364">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1b821-365">**检测**</span><span class="sxs-lookup"><span data-stu-id="1b821-365">**Detection**</span></span>
  - <span data-ttu-id="1b821-366">**受保护\*\*\*\*：ATP** 或 **EOP**</span><span class="sxs-lookup"><span data-stu-id="1b821-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="1b821-367">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1b821-368">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1b821-369">**域**</span><span class="sxs-lookup"><span data-stu-id="1b821-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="1b821-370">威胁防护状态报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="1b821-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="1b821-371">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="1b821-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1b821-372">**查看数据者：概述**：没有 **"查看详细信息表"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="1b821-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="1b821-373">**查看数据者：内容 \> 恶意软件**：</span><span class="sxs-lookup"><span data-stu-id="1b821-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="1b821-374">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-374">**Date**</span></span>
  - <span data-ttu-id="1b821-375">**位置**</span><span class="sxs-lookup"><span data-stu-id="1b821-375">**Location**</span></span>
  - <span data-ttu-id="1b821-376">**定向者**</span><span class="sxs-lookup"><span data-stu-id="1b821-376">**Directed by**</span></span>
  - <span data-ttu-id="1b821-377">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="1b821-377">**Malware name**</span></span>

  <span data-ttu-id="1b821-378">如果在此 **视图中** 单击"筛选器"，可以按"开始日期"和"结束日期"以及 **"检测"** 值修改报告。</span><span class="sxs-lookup"><span data-stu-id="1b821-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="1b821-379">**查看数据者：邮件替代**：</span><span class="sxs-lookup"><span data-stu-id="1b821-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="1b821-380">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-380">**Date**</span></span>
  - <span data-ttu-id="1b821-381">**主题**</span><span class="sxs-lookup"><span data-stu-id="1b821-381">**Subject**</span></span>
  - <span data-ttu-id="1b821-382">**发件人**</span><span class="sxs-lookup"><span data-stu-id="1b821-382">**Sender**</span></span>
  - <span data-ttu-id="1b821-383">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="1b821-383">**Recipients**</span></span>
  - <span data-ttu-id="1b821-384">**检测者**</span><span class="sxs-lookup"><span data-stu-id="1b821-384">**Detected by**</span></span>
  - <span data-ttu-id="1b821-385">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="1b821-385">**Override Reason**</span></span>
  - <span data-ttu-id="1b821-386">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="1b821-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="1b821-387">**Tags**</span><span class="sxs-lookup"><span data-stu-id="1b821-387">**Tags**</span></span>

  <span data-ttu-id="1b821-388">如果单击 **此视图中** 的"筛选器"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="1b821-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1b821-389">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1b821-390">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="1b821-390">**Override Reason**</span></span>
  - <span data-ttu-id="1b821-391">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1b821-392">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1b821-393">**域**</span><span class="sxs-lookup"><span data-stu-id="1b821-393">**Domain**</span></span>
  - <span data-ttu-id="1b821-394">**收件人 (** 请注意，此可筛选属性仅适用于详细信息表视图) </span><span class="sxs-lookup"><span data-stu-id="1b821-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="1b821-395">所有其他图表：</span><span class="sxs-lookup"><span data-stu-id="1b821-395">All other charts:</span></span>

  - <span data-ttu-id="1b821-396">"日期"</span><span class="sxs-lookup"><span data-stu-id="1b821-396">**Date**</span></span>
  - <span data-ttu-id="1b821-397">**主题**</span><span class="sxs-lookup"><span data-stu-id="1b821-397">**Subject**</span></span>
  - <span data-ttu-id="1b821-398">**发件人**</span><span class="sxs-lookup"><span data-stu-id="1b821-398">**Sender**</span></span>
  - <span data-ttu-id="1b821-399">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="1b821-399">**Recipients**</span></span>
  - <span data-ttu-id="1b821-400">**检测者**</span><span class="sxs-lookup"><span data-stu-id="1b821-400">**Detected by**</span></span>
  - <span data-ttu-id="1b821-401">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="1b821-401">**Delivery Status**</span></span>
  - <span data-ttu-id="1b821-402">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="1b821-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="1b821-403">**Tags**</span><span class="sxs-lookup"><span data-stu-id="1b821-403">**Tags**</span></span>

  <span data-ttu-id="1b821-404">如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="1b821-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1b821-405">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="1b821-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1b821-406">**检测**</span><span class="sxs-lookup"><span data-stu-id="1b821-406">**Detection**</span></span>
  - <span data-ttu-id="1b821-407">**受保护：** **Defender for Office 365** 或 **EOP**</span><span class="sxs-lookup"><span data-stu-id="1b821-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="1b821-408">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="1b821-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1b821-409">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1b821-410">**域**</span><span class="sxs-lookup"><span data-stu-id="1b821-410">**Domain**</span></span>
  - <span data-ttu-id="1b821-411">**收件人 (** 请注意，此可筛选属性仅适用于详细信息表视图) </span><span class="sxs-lookup"><span data-stu-id="1b821-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="1b821-412">热门恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="1b821-412">Top malware report</span></span>

<span data-ttu-id="1b821-413">" **热门恶意软件** "报告显示 [EOP](anti-malware-protection.md)中的反恶意软件保护检测到的各种恶意软件。</span><span class="sxs-lookup"><span data-stu-id="1b821-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="1b821-414">若要查看报告，请打开安全与&中心，**转到报告**[仪表板](https://protection.office.com) \> ，然后选择 **热门恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="1b821-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="1b821-415">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="1b821-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![报告仪表板中的热门恶意软件小组件](../../media/top-malware-report-widget.png)

<span data-ttu-id="1b821-417">当您将鼠标悬停在饼图中的一个浮点上时，可以看到某种恶意软件的名称，以及检测到具有该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="1b821-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![热门恶意软件报表视图](../../media/top-malware-report-view.png)

<span data-ttu-id="1b821-419">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="1b821-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="1b821-420">**热门恶意软件**</span><span class="sxs-lookup"><span data-stu-id="1b821-420">**Top malware**</span></span>
- <span data-ttu-id="1b821-421">**Count**</span><span class="sxs-lookup"><span data-stu-id="1b821-421">**Count**</span></span>

<span data-ttu-id="1b821-422">如果在 **视图或详细信息** 表视图中报表视图筛选器，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="1b821-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="1b821-423">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="1b821-423">URL threat protection report</span></span>

<span data-ttu-id="1b821-424">适用于 Office 365 的 Microsoft Defender 中提供了 **URL** 威胁防护报告。</span><span class="sxs-lookup"><span data-stu-id="1b821-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1b821-425">有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="1b821-425">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="1b821-426">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="1b821-426">User-reported messages report</span></span>

<span data-ttu-id="1b821-427">用户 **报告** 的邮件报告显示有关用户使用报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、网络钓鱼尝试或良好邮件 [的电子邮件的信息](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="1b821-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="1b821-428">每封邮件的详细信息可用，包括传递原因，例如为组织配置的垃圾邮件策略例外或邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="1b821-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="1b821-429">若要查看详细信息，请选择用户报告列表中的某个项目，然后查看"摘要"和"详细信息"选项卡 **上** 的信息。 </span><span class="sxs-lookup"><span data-stu-id="1b821-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![The User-Reported Messages report shows messages users labeled as junk， not junk， or phishing attempts.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="1b821-431">若要查看此报告，在安全与 [&，](https://protection.office.com)请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1b821-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="1b821-432">转到"**威胁管理** \> **""仪表板** \> **""用户报告的邮件"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="1b821-433">转到"**威胁管理** \> **""** \> **查看用户报告的邮件"。**</span><span class="sxs-lookup"><span data-stu-id="1b821-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![在安全与&中心，选择"威胁管理 \> ""查看 \> 用户报告的邮件"](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="1b821-435">为了使用户报告的邮件报告正常工作，必须为 Office 365 环境启用审核日志记录。 </span><span class="sxs-lookup"><span data-stu-id="1b821-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="1b821-436">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="1b821-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="1b821-437">有关详细信息，请参阅打开或关闭 [Microsoft 365 审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="1b821-438">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="1b821-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="1b821-439">若要查看和使用本文中所述的报告，你需要是安全与合规中心内以下角色&之一：</span><span class="sxs-lookup"><span data-stu-id="1b821-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="1b821-440">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="1b821-440">**Organization Management**</span></span>
- <span data-ttu-id="1b821-441">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="1b821-441">**Security Administrator**</span></span>
- <span data-ttu-id="1b821-442">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="1b821-442">**Security Reader**</span></span>
- <span data-ttu-id="1b821-443">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="1b821-443">**Global Reader**</span></span>

<span data-ttu-id="1b821-444">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="1b821-445">注意：将用户添加到 Microsoft 365 管理中心的相应 Azure Active Directory 角色会为用户提供安全 & 合规中心所需的权限以及Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="1b821-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1b821-446">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1b821-447">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="1b821-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1b821-448">如果报告中未显示数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="1b821-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1b821-449">若要了解更多信息，请参阅 [防范威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="1b821-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b821-450">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b821-450">Related topics</span></span>

[<span data-ttu-id="1b821-451">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="1b821-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="1b821-452">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="1b821-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="1b821-453">在安全与合规中心内查看&流报告</span><span class="sxs-lookup"><span data-stu-id="1b821-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="1b821-454">查看适用于 Office 365 的 Defender 报告</span><span class="sxs-lookup"><span data-stu-id="1b821-454">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
