---
title: 在 defender 门户中查看Microsoft 365安全报告
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
description: 了解如何查找和使用组织的电子邮件安全报告。 电子邮件安全报告在 Microsoft 365 Defender 门户中提供。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930316"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="d0398-104">在 defender 门户中查看Microsoft 365安全报告</span><span class="sxs-lookup"><span data-stu-id="d0398-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d0398-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="d0398-105">**Applies to**</span></span>
- [<span data-ttu-id="d0398-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d0398-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d0398-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="d0398-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d0398-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0398-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d0398-109">[Microsoft 365 Defender](https://security.microsoft.com)门户中提供了各种报告，可帮助你查看电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能）如何保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="d0398-109">A variety of reports are available in the [Microsoft 365 Defender portal](https://security.microsoft.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="d0398-110">如果你拥有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在 Microsoft 365 Defender 门户中查看这些报告，&报告电子邮件& \>  \> **协作报告**。</span><span class="sxs-lookup"><span data-stu-id="d0398-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d0398-111">若要直接转到"报表"仪表板，请打开 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="d0398-111">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![报告 Defender 门户Microsoft 365仪表板](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a><span data-ttu-id="d0398-113">遭到入侵的用户报告</span><span class="sxs-lookup"><span data-stu-id="d0398-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="d0398-114">此报告适用于Microsoft 365邮箱Exchange Online报告。</span><span class="sxs-lookup"><span data-stu-id="d0398-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="d0398-115">它不适用于独立 EOP Exchange Online Protection (EOP) 组织。</span><span class="sxs-lookup"><span data-stu-id="d0398-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="d0398-116">"**遭到入侵的用户**"报告显示过去 7 天内标记为"可疑"或"受限"的用户帐户数量。</span><span class="sxs-lookup"><span data-stu-id="d0398-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="d0398-117">其中任一状态的帐户存在问题，甚至受到威胁。</span><span class="sxs-lookup"><span data-stu-id="d0398-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="d0398-118">通过频繁使用，可以使用报告来发现可疑或受限帐户的峰值甚至趋势。</span><span class="sxs-lookup"><span data-stu-id="d0398-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="d0398-119">有关遭到入侵的用户详细信息，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

!["报告"仪表板中的"遭到入侵的用户"小组件](../../media/compromised-users-report-widget.png)

<span data-ttu-id="d0398-121">聚合视图显示过去 90 天的数据，而详细信息视图显示最近 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="d0398-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="d0398-122">若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件 \> **&协作** 电子邮件 \> **& 协作报告**，然后单击泄露用户下的查看 **详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0398-122">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Compromised users**.</span></span> <span data-ttu-id="d0398-123">若要直接转到报告，请打开 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="d0398-123">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="d0398-124">通过单击"筛选器"并选择以下一个或多个值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="d0398-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="d0398-125">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="d0398-126">**可疑**：用户帐户已发送可疑电子邮件，并且存在被限制发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="d0398-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="d0398-127">**受限**：由于高度可疑的模式，已限制用户帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d0398-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

!["泄露的用户"报告中的报告视图](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="d0398-129">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d0398-130">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="d0398-130">**Creation time**</span></span>
- <span data-ttu-id="d0398-131">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="d0398-131">**User ID**</span></span>
- <span data-ttu-id="d0398-132">**Action**</span><span class="sxs-lookup"><span data-stu-id="d0398-132">**Action**</span></span>

<span data-ttu-id="d0398-133">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="d0398-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="d0398-134">加密报告</span><span class="sxs-lookup"><span data-stu-id="d0398-134">Encryption report</span></span>

<span data-ttu-id="d0398-135">加密 **报告** 在 EOP (订阅中提供，Exchange Online或独立 EOP 中，Exchange Online邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="d0398-136">组织的安全团队可以使用此报告中的信息来识别模式，并主动应用或调整敏感电子邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="d0398-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="d0398-137">例如：</span><span class="sxs-lookup"><span data-stu-id="d0398-137">For example:</span></span>

- <span data-ttu-id="d0398-138">如果您看到大量由用户加密的电子邮件，您可能需要添加加密策略以自动加密某些用例。</span><span class="sxs-lookup"><span data-stu-id="d0398-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="d0398-139">有关详细信息，请参阅 Define [mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="d0398-140">如果您具有许多可用的加密模板，但没有人使用它们，您可能会探索用户是否需要功能培训。</span><span class="sxs-lookup"><span data-stu-id="d0398-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="d0398-141">聚合视图允许筛选过去 90 天，而详细信息视图允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="d0398-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="d0398-142">若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件 \> **&协作** 电子邮件 \> **&协作** 报告，然后单击加密报告 下的查看 **详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0398-142">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Encryption report**.</span></span> <span data-ttu-id="d0398-143">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="d0398-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="d0398-144">若要了解有关加密的信息，请参阅电子邮件[加密Microsoft 365。](../../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="d0398-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="d0398-145">加密报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="d0398-145">Report view for the Encryption report</span></span>

<span data-ttu-id="d0398-146">可以在图表上使用以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="d0398-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="d0398-147">**按以下方式查看数据：邮件加密报告** 并按以下方式进行分解 **：加密** 方法：可以使用以下加密方法：</span><span class="sxs-lookup"><span data-stu-id="d0398-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="d0398-148">**按用户加密**</span><span class="sxs-lookup"><span data-stu-id="d0398-148">**Encryption by user**</span></span>
  - <span data-ttu-id="d0398-149">**按策略加密**</span><span class="sxs-lookup"><span data-stu-id="d0398-149">**Encryption by policy**</span></span>

  <span data-ttu-id="d0398-150">如果单击 **"筛选器"，** 可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="d0398-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="d0398-151">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d0398-152">加密方法。</span><span class="sxs-lookup"><span data-stu-id="d0398-152">Encryption method.</span></span>
  - <span data-ttu-id="d0398-153">加密模板。</span><span class="sxs-lookup"><span data-stu-id="d0398-153">Encryption template.</span></span>

- <span data-ttu-id="d0398-154">**按以下方式查看数据：邮件加密报告** 并按： **加密** 模板进行分解：可以使用以下加密方法：</span><span class="sxs-lookup"><span data-stu-id="d0398-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="d0398-155">**不要转发**</span><span class="sxs-lookup"><span data-stu-id="d0398-155">**Do not forward**</span></span>
  - <span data-ttu-id="d0398-156">**仅加密**</span><span class="sxs-lookup"><span data-stu-id="d0398-156">**Encrypt only**</span></span>
  - <span data-ttu-id="d0398-157">**OME 上一个**</span><span class="sxs-lookup"><span data-stu-id="d0398-157">**OME previous**</span></span>
  - <span data-ttu-id="d0398-158">**自定义**</span><span class="sxs-lookup"><span data-stu-id="d0398-158">**Custom**</span></span>

  <span data-ttu-id="d0398-159">如果单击 **"筛选器"，** 可以使用以下筛选器修改图表：</span><span class="sxs-lookup"><span data-stu-id="d0398-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="d0398-160">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d0398-161">加密方法</span><span class="sxs-lookup"><span data-stu-id="d0398-161">Encryption method</span></span>
  - <span data-ttu-id="d0398-162">加密模板</span><span class="sxs-lookup"><span data-stu-id="d0398-162">Encryption template</span></span>

- <span data-ttu-id="d0398-163">**查看数据者：前 5 个** 收件人域：此视图显示包含前 5 个收件人域的已发送邮件计数的饼图。</span><span class="sxs-lookup"><span data-stu-id="d0398-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="d0398-164">如果单击 **"筛选器"，** 可以选择"**开始日期"和**"**结束日期"。**</span><span class="sxs-lookup"><span data-stu-id="d0398-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="d0398-165">加密报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="d0398-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="d0398-166">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="d0398-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d0398-167">**分解方式：加密方法** 或按： **加密** 模板进行分解：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="d0398-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-168">**Date**</span></span>
  - <span data-ttu-id="d0398-169">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="d0398-169">**Sender address**</span></span>
  - <span data-ttu-id="d0398-170">**加密模板**</span><span class="sxs-lookup"><span data-stu-id="d0398-170">**Encryption template**</span></span>
  - <span data-ttu-id="d0398-171">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="d0398-171">**Encryption method**</span></span>
  - <span data-ttu-id="d0398-172">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="d0398-172">**Recipient address**</span></span>
  - <span data-ttu-id="d0398-173">**主题**</span><span class="sxs-lookup"><span data-stu-id="d0398-173">**Subject**</span></span>

- <span data-ttu-id="d0398-174">**查看数据者：前 5 个收件人域**：</span><span class="sxs-lookup"><span data-stu-id="d0398-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="d0398-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-175">**Date**</span></span>
  - <span data-ttu-id="d0398-176">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="d0398-176">**Recipient domain**</span></span>
  - <span data-ttu-id="d0398-177">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="d0398-177">**Message count**</span></span>

<span data-ttu-id="d0398-178">如果在详细信息 **表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="d0398-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d0398-179">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="d0398-180">加密方法</span><span class="sxs-lookup"><span data-stu-id="d0398-180">Encryption method</span></span>
- <span data-ttu-id="d0398-181">加密模板</span><span class="sxs-lookup"><span data-stu-id="d0398-181">Encryption template</span></span>

<span data-ttu-id="d0398-182">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="d0398-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="d0398-183">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="d0398-183">Mailflow status report</span></span>

<span data-ttu-id="d0398-184">邮件 **流状态报告** 包含有关恶意软件、垃圾邮件、网络钓鱼和边缘阻止邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="d0398-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="d0398-185">有关详细信息，请参阅邮件 [流状态报告](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="d0398-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="d0398-186">电子邮件报告中的恶意软件检测</span><span class="sxs-lookup"><span data-stu-id="d0398-186">Malware detections in email report</span></span>

<span data-ttu-id="d0398-187">电子邮件 **报告中的** 恶意软件检测显示有关传入和传出电子邮件中的恶意软件检测信息 (EOP Exchange Online Protection或 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="d0398-188">有关 EOP 中的恶意软件保护详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="d0398-189">聚合视图筛选器允许 90 天，而详细信息表筛选器仅允许 10 天。</span><span class="sxs-lookup"><span data-stu-id="d0398-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="d0398-190">若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告 \> **电子邮件&协作** 电子邮件 & \> **协作报告**，然后单击查看电子邮件中检测到的恶意软件 **下的详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0398-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Malware detected in email**.</span></span> <span data-ttu-id="d0398-191">若要直接转到报告，请打开 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="d0398-191">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

!["报告"仪表板中电子邮件小部件中的恶意软件检测](../../media/malware-detections-widget.png)

<span data-ttu-id="d0398-193">通过单击"筛选器"并选择以下选项，可以筛选图表 **和详细信息** 表：</span><span class="sxs-lookup"><span data-stu-id="d0398-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="d0398-194">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="d0398-195">**入站**</span><span class="sxs-lookup"><span data-stu-id="d0398-195">**Inbound**</span></span>
- <span data-ttu-id="d0398-196">**出站**</span><span class="sxs-lookup"><span data-stu-id="d0398-196">**Outbound**</span></span>

![电子邮件报告中的恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="d0398-198">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d0398-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-199">**Date**</span></span>
- <span data-ttu-id="d0398-200">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="d0398-200">**Sender address**</span></span>
- <span data-ttu-id="d0398-201">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="d0398-201">**Recipient address**</span></span>
- <span data-ttu-id="d0398-202">**邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d0398-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="d0398-203">示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="d0398-204">**主题**</span><span class="sxs-lookup"><span data-stu-id="d0398-204">**Subject**</span></span>
- <span data-ttu-id="d0398-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="d0398-205">**Filename**</span></span>
- <span data-ttu-id="d0398-206">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="d0398-206">**Malware name**</span></span>

<span data-ttu-id="d0398-207">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="d0398-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="d0398-208">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="d0398-208">Mail latency report</span></span>

<span data-ttu-id="d0398-209">邮件 **延迟报告** 包含有关组织中遇到的邮件传递和触发延迟的信息。</span><span class="sxs-lookup"><span data-stu-id="d0398-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="d0398-210">有关详细信息，请参阅邮件 [延迟报告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="d0398-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="d0398-211">已发送和已接收电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="d0398-211">Sent and received email report</span></span>

<span data-ttu-id="d0398-212">" **已发送和** 已接收电子邮件"报告包含有关恶意软件、垃圾邮件、邮件流规则 (也称为传输规则) ，以及电子邮件进入服务后的高级恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="d0398-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="d0398-213">有关详细信息，请参阅已 [发送和已接收电子邮件报告](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="d0398-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="d0398-214">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="d0398-214">Spam detections report</span></span>

<span data-ttu-id="d0398-215">垃圾邮件 **检测报告显示** EOP 阻止的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d0398-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="d0398-216">邮件单独计数，而不是按收件人计数。</span><span class="sxs-lookup"><span data-stu-id="d0398-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="d0398-217">例如，如果将同一垃圾邮件发送给您组织的 100 个收件人，则它算作一封邮件。</span><span class="sxs-lookup"><span data-stu-id="d0398-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="d0398-218">聚合视图允许筛选 90 天，而详细信息表允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="d0398-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="d0398-219">若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件 \> **&协作** 电子邮件 \> **& 协作报告**，然后单击垃圾邮件检测下的查看 **详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0398-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click click **View details** under **Spam detections**.</span></span> <span data-ttu-id="d0398-220">若要直接转到报告，请打开 <https://security.microsoft.com/reports/SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="d0398-220">To go directly to the report, open <https://security.microsoft.com/reports/SpamDetections>.</span></span>

!["报告"仪表板中的"垃圾邮件检测"小组件](../../media/spam-detections-report-widget.png)

<span data-ttu-id="d0398-222">有关反垃圾邮件保护的信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="d0398-223">垃圾邮件检测报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="d0398-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="d0398-224">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="d0398-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d0398-225">**Break down by： Action**： The following event types are shown：</span><span class="sxs-lookup"><span data-stu-id="d0398-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="d0398-226">**已筛选的垃圾邮件内容**</span><span class="sxs-lookup"><span data-stu-id="d0398-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="d0398-227">**垃圾邮件 IP 阻止**</span><span class="sxs-lookup"><span data-stu-id="d0398-227">**Spam IP block**</span></span>
  - <span data-ttu-id="d0398-228">**垃圾邮件信封阻止**</span><span class="sxs-lookup"><span data-stu-id="d0398-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="d0398-229">**垃圾邮件 DBEB 筛选器**：基于目录的边缘阻止 (DBEB) </span><span class="sxs-lookup"><span data-stu-id="d0398-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="d0398-230">当您将鼠标悬停在图表中 (数据点) 时，可以看到当天阻止的项目数以及如何对这些项目进行分类。</span><span class="sxs-lookup"><span data-stu-id="d0398-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾邮件检测报告中的操作视图](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="d0398-232">**中断时间：方向**：显示以下方向：</span><span class="sxs-lookup"><span data-stu-id="d0398-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="d0398-233">**入站**</span><span class="sxs-lookup"><span data-stu-id="d0398-233">**Inbound**</span></span>
  - <span data-ttu-id="d0398-234">**出站**</span><span class="sxs-lookup"><span data-stu-id="d0398-234">**Outbound**</span></span>

  ![垃圾邮件检测报告中的方向视图](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="d0398-236">如果 **单击筛选器** 中的报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="d0398-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d0398-237">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="d0398-238">方向值</span><span class="sxs-lookup"><span data-stu-id="d0398-238">Direction values</span></span>
- <span data-ttu-id="d0398-239">事件类型值</span><span class="sxs-lookup"><span data-stu-id="d0398-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="d0398-240">垃圾邮件检测报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="d0398-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="d0398-241">如果在任 **一视图中单击** "查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="d0398-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-242">**Date**</span></span>
- <span data-ttu-id="d0398-243">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="d0398-243">**Sender address**</span></span>
- <span data-ttu-id="d0398-244">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="d0398-244">**Recipient address**</span></span>
- <span data-ttu-id="d0398-245">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="d0398-245">**Event type**</span></span>
- <span data-ttu-id="d0398-246">**Action**</span><span class="sxs-lookup"><span data-stu-id="d0398-246">**Action**</span></span>
- <span data-ttu-id="d0398-247">**主题**</span><span class="sxs-lookup"><span data-stu-id="d0398-247">**Subject**</span></span>

<span data-ttu-id="d0398-248">如果单击 **详细信息表中的** "筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="d0398-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d0398-249">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="d0398-250">方向值</span><span class="sxs-lookup"><span data-stu-id="d0398-250">Direction values</span></span>
- <span data-ttu-id="d0398-251">事件类型值</span><span class="sxs-lookup"><span data-stu-id="d0398-251">Event type values</span></span>

<span data-ttu-id="d0398-252">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="d0398-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="d0398-253">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="d0398-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="d0398-254">本文中所述的改进的欺骗检测报告在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="d0398-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="d0398-255">较旧版本的报告只显示"**良好邮件"和**"**捕获为垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="d0398-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="d0398-256">欺骗 **检测报告显示** 有关由于欺骗被阻止或允许的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="d0398-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="d0398-257">有关欺骗功能详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="d0398-258">报告聚合视图允许筛选 45 天，而详细信息视图仅 <sup>\*</sup> 允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="d0398-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="d0398-259"><sup>\*</sup> 最终，你将能够使用最多 90 天的筛选。</span><span class="sxs-lookup"><span data-stu-id="d0398-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="d0398-260">若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件 \> **&协作** 电子邮件 \> **& 协作报告**，然后单击欺骗检测下的查看 **详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0398-260">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Spoof detections**.</span></span> <span data-ttu-id="d0398-261">若要直接转到报告，请打开 <https://security.microsoft.com/reports/SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="d0398-261">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReport>.</span></span>

![报告仪表板中的欺骗检测小组件](../../media/spoof-detections-widget.png)

<span data-ttu-id="d0398-263">当您将鼠标悬停在 (中) 的数据点时，可以看到检测到的欺骗邮件的个个和原因。</span><span class="sxs-lookup"><span data-stu-id="d0398-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="d0398-264">通过单击"筛选器"并选择以下一个或多个值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="d0398-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="d0398-265">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="d0398-266">**结果**</span><span class="sxs-lookup"><span data-stu-id="d0398-266">**Result**</span></span>
  - <span data-ttu-id="d0398-267">**Pass**</span><span class="sxs-lookup"><span data-stu-id="d0398-267">**Pass**</span></span>
  - <span data-ttu-id="d0398-268">**失败**</span><span class="sxs-lookup"><span data-stu-id="d0398-268">**Fail**</span></span>
  - <span data-ttu-id="d0398-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="d0398-269">**SoftPass**</span></span>
  - <span data-ttu-id="d0398-270">**无**</span><span class="sxs-lookup"><span data-stu-id="d0398-270">**None**</span></span>
  - <span data-ttu-id="d0398-271">**其他**</span><span class="sxs-lookup"><span data-stu-id="d0398-271">**Other**</span></span>

- <span data-ttu-id="d0398-272">**欺骗类型**：**内部和外部**</span><span class="sxs-lookup"><span data-stu-id="d0398-272">**Spoof type**: **Internal** and **External**</span></span>

![欺骗检测报告中的报告视图](../../media/spoof-detections-report-view.png)

<span data-ttu-id="d0398-274">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d0398-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-275">**Date**</span></span>
- <span data-ttu-id="d0398-276">**欺骗用户**</span><span class="sxs-lookup"><span data-stu-id="d0398-276">**Spoofed user**</span></span>
- <span data-ttu-id="d0398-277">**发送基础结构**</span><span class="sxs-lookup"><span data-stu-id="d0398-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="d0398-278">**欺骗类型**</span><span class="sxs-lookup"><span data-stu-id="d0398-278">**Spoof type**</span></span>
- <span data-ttu-id="d0398-279">**结果**</span><span class="sxs-lookup"><span data-stu-id="d0398-279">**Result**</span></span>
- <span data-ttu-id="d0398-280">**结果代码**</span><span class="sxs-lookup"><span data-stu-id="d0398-280">**Result code**</span></span>
- <span data-ttu-id="d0398-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="d0398-281">**SPF**</span></span>
- <span data-ttu-id="d0398-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="d0398-282">**DKIM**</span></span>
- <span data-ttu-id="d0398-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="d0398-283">**DMARC**</span></span>
- <span data-ttu-id="d0398-284">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="d0398-284">**Message count**</span></span>

<span data-ttu-id="d0398-285">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="d0398-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="d0398-286">有关复合身份验证结果代码详细信息，请参阅邮件中的[反垃圾邮件Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="d0398-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="d0398-287">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="d0398-287">Threat protection status report</span></span>

<span data-ttu-id="d0398-288">威胁 **防护状态报告** 在 EOP 和 Microsoft Defender for Office 365;但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="d0398-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="d0398-289">例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看有关 SharePoint、OneDrive 和 Microsoft Teams 的 保险箱 附件检测到的恶意[文件的信息](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d0398-290">该报告提供包含恶意内容的电子邮件数量，如反恶意软件引擎阻止的文件或网站地址 (URL) 、零时差自动清除[ (ZAP) ](zero-hour-auto-purge.md)和针对 Office 365 功能（如 保险箱[链接](safe-links.md)[、保险箱](safe-attachments.md)附件和反网络钓鱼）的 Defender。 [](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d0398-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="d0398-291">您可以使用此信息来确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="d0398-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="d0398-292">**注意**：如果邮件发送给五个收件人，则我们将邮件计为五个不同的邮件，而不是一封邮件，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="d0398-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="d0398-293">若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件 \> **&协作** 电子邮件 \> **& 协作报告**，然后单击威胁防护状态下的查看 **详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0398-293">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Threat protection status**.</span></span> <span data-ttu-id="d0398-294">若要直接转到报告，请打开以下 URL 之一：</span><span class="sxs-lookup"><span data-stu-id="d0398-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="d0398-295">Microsoft Defender for Office 365：<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="d0398-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="d0398-296">EOP： <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="d0398-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![报告仪表板中的威胁防护状态小组件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="d0398-298">默认情况下，图表显示过去 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="d0398-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="d0398-299">如果单击 **"筛选器**"，可以选择 90 天的日期范围 (试用版订阅可能限制为 30) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="d0398-300">详细信息表视图允许筛选 30 天。</span><span class="sxs-lookup"><span data-stu-id="d0398-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="d0398-301">威胁防护状态报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="d0398-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="d0398-302">提供以下视图：</span><span class="sxs-lookup"><span data-stu-id="d0398-302">The following views are available:</span></span>

- <span data-ttu-id="d0398-303">**查看数据者：概述**：显示以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="d0398-304">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="d0398-304">**Email malware**</span></span>
  - <span data-ttu-id="d0398-305">**电子邮件钓鱼邮件**</span><span class="sxs-lookup"><span data-stu-id="d0398-305">**Email phish**</span></span>
  - <span data-ttu-id="d0398-306">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="d0398-306">**Content malware**</span></span>

  ![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="d0398-308">**查看数据者：内容 \>恶意软件**<sup>1：</sup>为 Microsoft Defender 组织显示Office 365信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="d0398-309">**反恶意软件引擎**：Sharepoint、OneDrive 和 Microsoft Teams 中内置的病毒检测 [检测到的恶意](virus-detection-in-spo.md)Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d0398-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="d0398-310">**文件触发**：附件检测到的恶意保险箱 [文件SharePoint、OneDrive和Microsoft Teams。](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d0398-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="d0398-312">**查看数据者：消息替代**：显示以下替代原因信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="d0398-313">**本地跳过**</span><span class="sxs-lookup"><span data-stu-id="d0398-313">**On-premises skip**</span></span>
  - <span data-ttu-id="d0398-314">**IP 允许**</span><span class="sxs-lookup"><span data-stu-id="d0398-314">**IP Allow**</span></span>
  - <span data-ttu-id="d0398-315">**邮件流规则**</span><span class="sxs-lookup"><span data-stu-id="d0398-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="d0398-316">**发件人允许**</span><span class="sxs-lookup"><span data-stu-id="d0398-316">**Sender allow**</span></span>
  - <span data-ttu-id="d0398-317">**域允许**</span><span class="sxs-lookup"><span data-stu-id="d0398-317">**Domain allow**</span></span>
  - <span data-ttu-id="d0398-318">**ZAP 未启用**</span><span class="sxs-lookup"><span data-stu-id="d0398-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="d0398-319">**未启用垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="d0398-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="d0398-320">**用户保险箱发件人**</span><span class="sxs-lookup"><span data-stu-id="d0398-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="d0398-321">**用户保险箱域**</span><span class="sxs-lookup"><span data-stu-id="d0398-321">**User Safe Domain**</span></span>

  ![威胁防护状态报告中的邮件替代视图](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="d0398-323">**按以下条件进行分解：检测** 技术和 **查看数据者： \> 电子邮件** 钓鱼邮件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="d0398-324">**ATP 生成的 URL 信誉**<sup>1：</sup>来自 Defender 的恶意 URL 信誉，Office 365客户的其他Microsoft 365触发。</span><span class="sxs-lookup"><span data-stu-id="d0398-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="d0398-325">**高级钓鱼筛选器**：基于机器学习的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="d0398-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="d0398-326">**反欺骗 - DMARC 失败**：邮件上的 DMARC 身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="d0398-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="d0398-327">**反欺骗 - 组织内部**：发件人正在尝试欺骗收件人域。</span><span class="sxs-lookup"><span data-stu-id="d0398-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="d0398-328">**反欺骗 - 外部域**：发件人正在尝试欺骗其他一些域。</span><span class="sxs-lookup"><span data-stu-id="d0398-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="d0398-329">**品牌模拟**：模拟基于发件人的已知品牌。</span><span class="sxs-lookup"><span data-stu-id="d0398-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="d0398-330">**域模拟**<sup>1：</sup>模拟客户拥有或定义的域。</span><span class="sxs-lookup"><span data-stu-id="d0398-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="d0398-331">**EOP URL 信誉**：恶意 URL 信誉。</span><span class="sxs-lookup"><span data-stu-id="d0398-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="d0398-332">**常规网络钓鱼筛选器**：基于分析员规则的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="d0398-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="d0398-333">**其他**</span><span class="sxs-lookup"><span data-stu-id="d0398-333">**Others**</span></span>
  - <span data-ttu-id="d0398-334">**网络钓鱼 ZAP**<sup>2：</sup>零时差自动清除网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="d0398-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="d0398-335">**URL 触发**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d0398-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="d0398-336">**用户模拟**<sup>1：</sup>模拟管理员定义或通过邮箱智能学习的用户。</span><span class="sxs-lookup"><span data-stu-id="d0398-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![威胁防护状态报告中的网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="d0398-338">**按以下条件进行分解：检测** 技术和 **查看数据者： \> 电子邮件** 恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="d0398-339">**ATP 生成的文件信誉**<sup>1：Defender</sup>为安全触发生成的所有恶意Office 365信誉。</span><span class="sxs-lookup"><span data-stu-id="d0398-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="d0398-340">**反恶意软件引擎**<sup>1：</sup>来自反恶意软件引擎的检测。</span><span class="sxs-lookup"><span data-stu-id="d0398-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="d0398-341">**反恶意软件策略文件类型阻止**：这些是由于邮件中标识的恶意文件类型而筛选掉的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d0398-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="d0398-342">**文件触发**<sup>1：</sup>按附件保险箱检测。</span><span class="sxs-lookup"><span data-stu-id="d0398-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="d0398-343">**恶意文件信誉**</span><span class="sxs-lookup"><span data-stu-id="d0398-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="d0398-344">**恶意软件 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d0398-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="d0398-345">**其他**</span><span class="sxs-lookup"><span data-stu-id="d0398-345">**Others**</span></span>

  ![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="d0398-347">**按以下条件进行分解：策略** 类型和 **查看数据者：电子邮件 \> 钓鱼** 或查看数据 **者： \>** 电子邮件恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="d0398-348">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="d0398-348">**Anti-malware**</span></span>
  - <span data-ttu-id="d0398-349">**保险箱附件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d0398-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="d0398-350">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="d0398-350">**Anti-phish**</span></span>
  - <span data-ttu-id="d0398-351">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="d0398-351">**Anti-spam**</span></span>
  - <span data-ttu-id="d0398-352">**邮件流规则** (也称为传输规则) </span><span class="sxs-lookup"><span data-stu-id="d0398-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="d0398-353">**其他**</span><span class="sxs-lookup"><span data-stu-id="d0398-353">**Others**</span></span>

  ![威胁防护状态报告中的网络钓鱼电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="d0398-355">**按以下条件进行分解：传递** 状态和 **查看数据者：电子邮件 \> 钓鱼** 邮件或查看数据 **者： \>** 电子邮件恶意软件：显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="d0398-356">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="d0398-356">**Delivery failed**</span></span>
  - <span data-ttu-id="d0398-357">**已丢弃**</span><span class="sxs-lookup"><span data-stu-id="d0398-357">**Dropped**</span></span>
  - <span data-ttu-id="d0398-358">**转发**</span><span class="sxs-lookup"><span data-stu-id="d0398-358">**Forwarded**</span></span>
  - <span data-ttu-id="d0398-359">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="d0398-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="d0398-360">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="d0398-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="d0398-361">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="d0398-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="d0398-362">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="d0398-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="d0398-363">**本地服务器：已传递**</span><span class="sxs-lookup"><span data-stu-id="d0398-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="d0398-364">**隔离**</span><span class="sxs-lookup"><span data-stu-id="d0398-364">**Quarantine**</span></span>

  ![威胁防护状态报告中网络钓鱼电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="d0398-366"><sup>1</sup> Defender for Office 365 仅</span><span class="sxs-lookup"><span data-stu-id="d0398-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="d0398-367"><sup>2</sup> ZAP (的零时差自动清除) 在独立 EOP (它仅适用于 Exchange Online 邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="d0398-368">如果单击 **"筛选器**"，可用的筛选器取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="d0398-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d0398-369">For **View data by： Content \> Malware**， you can modify the report by **Start date** and End **date**， and the **Detection** value.</span><span class="sxs-lookup"><span data-stu-id="d0398-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="d0398-370">对于 **View data by： Message Override**，您可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="d0398-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d0398-371">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d0398-372">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="d0398-372">**Override Reason**</span></span>
  - <span data-ttu-id="d0398-373">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d0398-374">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d0398-375">**域**</span><span class="sxs-lookup"><span data-stu-id="d0398-375">**Domain**</span></span>

- <span data-ttu-id="d0398-376">对于所有其他视图，您可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="d0398-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d0398-377">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d0398-378">**检测**</span><span class="sxs-lookup"><span data-stu-id="d0398-378">**Detection**</span></span>
  - <span data-ttu-id="d0398-379">**受保护\*\*\*\*：ATP** 或 **EOP**</span><span class="sxs-lookup"><span data-stu-id="d0398-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="d0398-380">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d0398-381">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d0398-382">**域**</span><span class="sxs-lookup"><span data-stu-id="d0398-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="d0398-383">威胁防护状态报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="d0398-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="d0398-384">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="d0398-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d0398-385">**查看数据者：概述**：没有 **"查看详细信息表"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="d0398-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="d0398-386">**查看数据者：内容 \> 恶意软件**：</span><span class="sxs-lookup"><span data-stu-id="d0398-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="d0398-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-387">**Date**</span></span>
  - <span data-ttu-id="d0398-388">**位置**</span><span class="sxs-lookup"><span data-stu-id="d0398-388">**Location**</span></span>
  - <span data-ttu-id="d0398-389">**定向者**</span><span class="sxs-lookup"><span data-stu-id="d0398-389">**Directed by**</span></span>
  - <span data-ttu-id="d0398-390">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="d0398-390">**Malware name**</span></span>

  <span data-ttu-id="d0398-391">如果在此 **视图中** 单击"筛选器"，可以按"开始日期"和"结束日期"以及 **"检测"** 值修改报告。</span><span class="sxs-lookup"><span data-stu-id="d0398-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="d0398-392">**查看数据者：邮件替代**：</span><span class="sxs-lookup"><span data-stu-id="d0398-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="d0398-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-393">**Date**</span></span>
  - <span data-ttu-id="d0398-394">**主题**</span><span class="sxs-lookup"><span data-stu-id="d0398-394">**Subject**</span></span>
  - <span data-ttu-id="d0398-395">**发件人**</span><span class="sxs-lookup"><span data-stu-id="d0398-395">**Sender**</span></span>
  - <span data-ttu-id="d0398-396">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="d0398-396">**Recipients**</span></span>
  - <span data-ttu-id="d0398-397">**检测者**</span><span class="sxs-lookup"><span data-stu-id="d0398-397">**Detected by**</span></span>
  - <span data-ttu-id="d0398-398">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="d0398-398">**Override Reason**</span></span>
  - <span data-ttu-id="d0398-399">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="d0398-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="d0398-400">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d0398-400">**Tags**</span></span>

  <span data-ttu-id="d0398-401">如果单击 **此视图中** 的"筛选器"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="d0398-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d0398-402">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d0398-403">**替代原因**</span><span class="sxs-lookup"><span data-stu-id="d0398-403">**Override Reason**</span></span>
  - <span data-ttu-id="d0398-404">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d0398-405">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d0398-406">**域**</span><span class="sxs-lookup"><span data-stu-id="d0398-406">**Domain**</span></span>
  - <span data-ttu-id="d0398-407">**收件人 (** 请注意，此可筛选属性仅适用于详细信息表视图) </span><span class="sxs-lookup"><span data-stu-id="d0398-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="d0398-408">所有其他图表：</span><span class="sxs-lookup"><span data-stu-id="d0398-408">All other charts:</span></span>

  - <span data-ttu-id="d0398-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="d0398-409">**Date**</span></span>
  - <span data-ttu-id="d0398-410">**主题**</span><span class="sxs-lookup"><span data-stu-id="d0398-410">**Subject**</span></span>
  - <span data-ttu-id="d0398-411">**发件人**</span><span class="sxs-lookup"><span data-stu-id="d0398-411">**Sender**</span></span>
  - <span data-ttu-id="d0398-412">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="d0398-412">**Recipients**</span></span>
  - <span data-ttu-id="d0398-413">**检测者**</span><span class="sxs-lookup"><span data-stu-id="d0398-413">**Detected by**</span></span>
  - <span data-ttu-id="d0398-414">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="d0398-414">**Delivery Status**</span></span>
  - <span data-ttu-id="d0398-415">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="d0398-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="d0398-416">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d0398-416">**Tags**</span></span>

  <span data-ttu-id="d0398-417">如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="d0398-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d0398-418">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="d0398-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d0398-419">**检测**</span><span class="sxs-lookup"><span data-stu-id="d0398-419">**Detection**</span></span>
  - <span data-ttu-id="d0398-420">**受：Defender** **for Office 365** **或 EOP 保护**</span><span class="sxs-lookup"><span data-stu-id="d0398-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="d0398-421">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="d0398-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d0398-422">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d0398-423">**域**</span><span class="sxs-lookup"><span data-stu-id="d0398-423">**Domain**</span></span>
  - <span data-ttu-id="d0398-424">**收件人 (** 请注意，此可筛选属性仅适用于详细信息表视图) </span><span class="sxs-lookup"><span data-stu-id="d0398-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="d0398-425">热门恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="d0398-425">Top malware report</span></span>

<span data-ttu-id="d0398-426">" **热门恶意软件** "报告显示 [EOP](anti-malware-protection.md)中的反恶意软件保护检测到的各种恶意软件。</span><span class="sxs-lookup"><span data-stu-id="d0398-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="d0398-427">若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件 \> **&协作** 电子邮件 \> **&协作报告**，然后单击顶部恶意软件下的查看 **详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0398-427">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Top malware**.</span></span> <span data-ttu-id="d0398-428">若要直接转到报告，请打开 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="d0398-428">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![报告仪表板中的热门恶意软件小组件](../../media/top-malware-report-widget.png)

<span data-ttu-id="d0398-430">当您将鼠标悬停在饼图中的一个浮点上时，可以看到某种恶意软件的名称，以及检测到具有该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="d0398-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![热门恶意软件报表视图](../../media/top-malware-report-view.png)

<span data-ttu-id="d0398-432">如果单击 **"查看详细信息表"，** 可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="d0398-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d0398-433">**热门恶意软件**</span><span class="sxs-lookup"><span data-stu-id="d0398-433">**Top malware**</span></span>
- <span data-ttu-id="d0398-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="d0398-434">**Count**</span></span>

<span data-ttu-id="d0398-435">如果在 **视图或详细信息** 表视图中报表视图筛选器，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="d0398-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="d0398-436">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="d0398-436">URL threat protection report</span></span>

<span data-ttu-id="d0398-437">Microsoft Defender for Office 365 中提供了 **URL** 威胁防护报告。</span><span class="sxs-lookup"><span data-stu-id="d0398-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="d0398-438">有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="d0398-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="d0398-439">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="d0398-439">User reported messages report</span></span>

<span data-ttu-id="d0398-440">用户 **报告的邮件** 报告显示有关用户使用报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、网络钓鱼尝试或良好邮件 [的电子邮件的信息](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="d0398-440">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="d0398-441">每封邮件的详细信息可用，包括传递原因，例如为组织配置的垃圾邮件策略例外或邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="d0398-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="d0398-442">若要查看详细信息，请选择用户报告列表中的某个项目，然后查看"摘要"和"详细信息"选项卡 **上** 的信息。 </span><span class="sxs-lookup"><span data-stu-id="d0398-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

!["用户报告的邮件"报告显示用户标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试的邮件。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="d0398-444">若要查看此报告，在 [Microsoft 365 Defender](https://security.microsoft.com)门户中，转到报告电子邮件 \> **&协作** \> **电子邮件&报告** \> **用户报告的邮件**。</span><span class="sxs-lookup"><span data-stu-id="d0398-444">To view this report, in the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span>

- <span data-ttu-id="d0398-445">转到报告 \> **电子邮件&协作** \> **电子邮件&报告** \> **用户报告的邮件**。</span><span class="sxs-lookup"><span data-stu-id="d0398-445">Go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span></span>

![在 Microsoft 365 Defender 门户中，选择报告电子邮件 \> &协作 电子邮件 \> &报告 \> 用户报告的邮件](../../media/user-reported-messages.png)

> [!IMPORTANT]
> <span data-ttu-id="d0398-447">为了使"用户报告的消息"报告正常工作，必须为用户报告环境启用Office 365日志记录。</span><span class="sxs-lookup"><span data-stu-id="d0398-447">In order for the User reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="d0398-448">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="d0398-448">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="d0398-449">有关详细信息，请参阅打开[Microsoft 365 审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-449">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="d0398-450">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="d0398-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="d0398-451">若要查看和使用本文中所述的报告，你需要是 Microsoft 365 Defender 门户中以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="d0398-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="d0398-452">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="d0398-452">**Organization Management**</span></span>
- <span data-ttu-id="d0398-453">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="d0398-453">**Security Administrator**</span></span>
- <span data-ttu-id="d0398-454">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="d0398-454">**Security Reader**</span></span>
- <span data-ttu-id="d0398-455">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="d0398-455">**Global Reader**</span></span>

<span data-ttu-id="d0398-456">有关详细信息，请参阅 Defender 门户[中Microsoft 365权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-456">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="d0398-457">注意：将用户添加到 Microsoft 365 管理中心中的相应 Azure Active Directory 角色会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="d0398-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d0398-458">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-458">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="d0398-459">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="d0398-459">What if the reports aren't showing data?</span></span>

<span data-ttu-id="d0398-460">如果报告中未显示数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="d0398-460">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="d0398-461">若要了解更多信息，请参阅 [防范威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="d0398-461">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0398-462">相关主题</span><span class="sxs-lookup"><span data-stu-id="d0398-462">Related topics</span></span>

[<span data-ttu-id="d0398-463">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="d0398-463">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="d0398-464">Microsoft 365 Defender 门户中的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="d0398-464">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="d0398-465">在 Defender 门户中查看Microsoft 365流报告</span><span class="sxs-lookup"><span data-stu-id="d0398-465">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="d0398-466">查看 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="d0398-466">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
