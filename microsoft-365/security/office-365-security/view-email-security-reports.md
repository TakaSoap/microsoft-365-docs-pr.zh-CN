---
title: 查看安全与合规中心内的电子邮件安全报告
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
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
ms.openlocfilehash: dfee1fa2c6e515bfc10ed7a633584c54763fdec4
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819457"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="aebfa-104">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="aebfa-105">[安全 & 合规性中心](https://protection.office.com)中提供了多种报告，可帮助您了解电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能如何保护您的组织）。</span><span class="sxs-lookup"><span data-stu-id="aebfa-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="aebfa-106">如果您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports)，则可以转到 "**报告**" \> **仪表板**，在安全 & 合规中心中查看这些报告。</span><span class="sxs-lookup"><span data-stu-id="aebfa-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span>

![Security & 合规中心中的报告仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="aebfa-108">您的电子邮件安全报告包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="aebfa-108">Your email security reports include the following:</span></span>

- <span data-ttu-id="aebfa-109">[URL 威胁防护报告](#url-threat-protection-report-new)（**新！**）</span><span class="sxs-lookup"><span data-stu-id="aebfa-109">[URL Threat Protection report](#url-threat-protection-report-new) (**NEW!**)</span></span>
- [<span data-ttu-id="aebfa-110">已泄露用户报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-110">Compromised Users report</span></span>](#compromised-users-report)
- [<span data-ttu-id="aebfa-111">加密报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-111">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="aebfa-112">威胁防护状态</span><span class="sxs-lookup"><span data-stu-id="aebfa-112">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="aebfa-113">恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-113">Malware Detections report</span></span>](#malware-detections-report)
- [<span data-ttu-id="aebfa-114">主要恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-114">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="aebfa-115">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-115">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="aebfa-116">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-116">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="aebfa-117">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-117">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="aebfa-118">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-118">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="aebfa-119">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-119">User-reported messages report</span></span>](#user-reported-messages-report)

## <a name="url-threat-protection-report-new"></a><span data-ttu-id="aebfa-120">URL 威胁防护报告（**新！**）</span><span class="sxs-lookup"><span data-stu-id="aebfa-120">URL Threat Protection report (**NEW!**)</span></span>

<span data-ttu-id="aebfa-121">任何人都可以使用 URL 威胁防护报告：</span><span class="sxs-lookup"><span data-stu-id="aebfa-121">The URL Threat Protection report is available to anyone with:</span></span>

- <span data-ttu-id="aebfa-122">Exchange Online Protection*和*高级威胁防护外接程序（计划 1*或*计划2）</span><span class="sxs-lookup"><span data-stu-id="aebfa-122">An Exchange Online Protection, *and* Advanced Threat Protection add-on (Plan 1 *or* Plan 2)</span></span>
- <span data-ttu-id="aebfa-123">Microsoft 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="aebfa-123">A Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="aebfa-124">这是一个具有两个聚合视图的 "单击中心" 报告。</span><span class="sxs-lookup"><span data-stu-id="aebfa-124">This is a 'click-centric' report that has two aggregated views.</span></span>

1. <span data-ttu-id="aebfa-125">第一个视图是*URL 单击保护操作*，它重点显示由租户中的用户单击的 URL 的数目，以及单击的结果。</span><span class="sxs-lookup"><span data-stu-id="aebfa-125">The first view is by *URL click-protection action*, which is focused on showing the number of URL clicks by users within the tenant, and the result of the click.</span></span> <span data-ttu-id="aebfa-126">A 单击此处指示用户已通过阻止页面单击到恶意网站（可由管理员在安全链接策略中禁用）。</span><span class="sxs-lookup"><span data-stu-id="aebfa-126">A click here indicates that the user has clicked through the block page to the malicious website (this can be disabled by the administrator within a Safe Links policy).</span></span>

2. <span data-ttu-id="aebfa-127">第二个视图是*URL 单击 "按应用程序*"，它显示了在当今支持安全链接的不同应用程序（如在电子邮件客户端或 Microsoft Word 中）单击的 url 的数目。</span><span class="sxs-lookup"><span data-stu-id="aebfa-127">The second view is *URL click by applications*, which shows the number of URLs click in different applications that support Safe Links today, such as in an email client or in Microsoft Word.</span></span> <span data-ttu-id="aebfa-128">两个聚合视图中的数据每4小时刷新一次。</span><span class="sxs-lookup"><span data-stu-id="aebfa-128">Data in both aggregated views are refreshed once every 4 hours.</span></span>

<span data-ttu-id="aebfa-129">URL 威胁防护报告的详细信息表提供了在租户内发生的所有点击的近实时视图，其中包括诸如*username*、 *URL*、*网络邮件 ID* （如果从电子邮件中单击该 URL）的调查信息，以及有关调查和分析的其他有用信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-129">The details table of the URL Threat Protection report provides a near-real-time view of all clicks that happen within the tenant, and it includes investigative information such as *username*, *URL*, the *network message ID* (if the URL was clicked from an email), and other valuable pieces of information useful for investigations and analyses.</span></span>

<span data-ttu-id="aebfa-130">默认情况下，报告仅显示通过安全链接阻止的 Url 单击时的数据，但也可以查看筛选器中的 "通过选择*允许的 url* " 复选框的所有 URL 单击的信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-130">By default, the report only shows data on clicks from URLs that were blocked by Safe Links, but it is also possible to see information for all URL clicks through selecting *Allowed URLs* checkbox in the filters.</span></span>

<span data-ttu-id="aebfa-131">如果应用了 "安全链接策略" 的用户已选中 "不*跟踪用户单击*" 选项，则此报告将不会有单击的数据。</span><span class="sxs-lookup"><span data-stu-id="aebfa-131">This report will not have data of clicks from users where the Safe Links policy applied has the *Do not track user clicks* option selected.</span></span>

![操作中的 URL 威胁防护报告的图形。](../../media/tp-URLThreatProRpt1.PNG)

## <a name="compromised-users-report"></a><span data-ttu-id="aebfa-133">已泄露用户报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-133">Compromised Users report</span></span>

<span data-ttu-id="aebfa-134">此报告可供任何具有 Exchange Online Protection 的用户使用，并显示标记为可疑用户或受限制用户的用户帐户数。在帐户中，数据尤其有用的是表明用户帐户可能有问题或甚至已泄露的状态。</span><span class="sxs-lookup"><span data-stu-id="aebfa-134">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="aebfa-135">通过频繁使用，已损坏的用户报告可以发现处于可疑或受限制状态的帐户中的峰值、甚至是趋势，从而提供证据可能存在安全和租户的 wellness 问题。</span><span class="sxs-lookup"><span data-stu-id="aebfa-135">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![已泄露的用户报告显示在 Microsoft 365 中。](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="aebfa-137">加密报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-137">Encryption report</span></span>

<span data-ttu-id="aebfa-138">**加密报告**显示有关通过组织策略或通过最终用户控件进行加密的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-138">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="aebfa-139">您组织的安全团队可以使用此报告中的信息来标识模式，并主动应用或调整敏感电子邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="aebfa-139">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="aebfa-140">若要查看此报告，请在安全 & 合规性中心中，转到 "**报告**" \> **仪表板** \> **加密报告**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-140">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![加密报告](../../media/encryptionreport-defaultview.png)

<span data-ttu-id="aebfa-142">当报告第一次打开时，您将看到有关过去七（7）天的电子邮件上使用的加密方法的数据。</span><span class="sxs-lookup"><span data-stu-id="aebfa-142">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="aebfa-143">通过单击屏幕右上角的 "**筛选器**"，可以更改报告中显示的日期范围和详细信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-143">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![加密报告筛选器](../../media/encryptionreport-filters.png)

<span data-ttu-id="aebfa-145">您还可以使用 "**向下分页**" 菜单查看通过加密模板（或方法）的数据。</span><span class="sxs-lookup"><span data-stu-id="aebfa-145">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![加密方法或模板](../../media/encryptionreport-breakdownby.png)

<span data-ttu-id="aebfa-147">您还可以使用 "**查看数据方式**" 菜单更改视图，以查看前五个收件人域的加密邮件数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-147">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![加密报告按菜单查看数据](../../media/encryptionreport-viewdataby.png)

<span data-ttu-id="aebfa-149">通过新的加密报告的灵活性，您可以查看趋势并采取适当的操作。</span><span class="sxs-lookup"><span data-stu-id="aebfa-149">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="aebfa-150">例如，如果您看到用户加密了大量的电子邮件，您可能希望添加加密策略以对某些用例自动进行加密。</span><span class="sxs-lookup"><span data-stu-id="aebfa-150">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="aebfa-151">（若要获取有关信息，请参阅[定义邮件流规则以在 Microsoft 365 中对电子邮件进行加密](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。）另一个示例是，如果有许多可用的加密模板，但没有用户正在使用它们，则可以考察用户是否需要针对该功能的培训。</span><span class="sxs-lookup"><span data-stu-id="aebfa-151">(To get help with that, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span>

<span data-ttu-id="aebfa-152">使用此报告使组织的安全和合规性团队能够监视邮件加密的使用情况，以及是否需要进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="aebfa-152">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="aebfa-153">若要了解有关加密的详细信息，请参阅[Microsoft 365 中的电子邮件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="aebfa-153">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="aebfa-154">威胁防护状态</span><span class="sxs-lookup"><span data-stu-id="aebfa-154">Threat Protection Status report</span></span>

<span data-ttu-id="aebfa-155">**威胁防护状态**报告是一个智能报告，显示 Exchange Online Protection 检测到并阻止的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aebfa-155">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="aebfa-156">此报告可用于查看标识为恶意软件的电子邮件或一段时间内的网络钓鱼尝试（最长为90天），并使安全管理员能够确定趋势或确定策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="aebfa-156">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="aebfa-157">拥有[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)或[Exchange Online Protection](exchange-online-protection-overview.md) （EOP）的客户可以使用威胁防护状态报告;但是，在 ATP 客户的威胁防护状态报告中显示的信息可能包含不同的 EOP 客户可能看到的数据。</span><span class="sxs-lookup"><span data-stu-id="aebfa-157">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](exchange-online-protection-overview.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="aebfa-158">例如，EOP 客户可以查看有关在电子邮件中检测到的恶意软件的信息，但不是关于[在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到的恶意文件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)的信息，这是与 ATP 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="aebfa-158">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="aebfa-159">（[了解有关 ATP 报告的详细信息](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。）</span><span class="sxs-lookup"><span data-stu-id="aebfa-159">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>

<span data-ttu-id="aebfa-160">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，转到 "**报告**" \> **仪表板** \> **威胁防护状态**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-160">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![威胁防护状态](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)

<span data-ttu-id="aebfa-162">当您首次打开 "威胁 Protection 状态报告" 时，报告默认显示过去七天的数据;不过，您可以单击 "**筛选器**" 并将日期范围更改为最多90天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-162">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="aebfa-163">（如果使用的是试用订阅，则可能限制为30天的数据。）</span><span class="sxs-lookup"><span data-stu-id="aebfa-163">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="aebfa-164">此报告对查看组织的[Exchange Online Protection 功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)和长期趋势分析的有效性和影响非常有用。</span><span class="sxs-lookup"><span data-stu-id="aebfa-164">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span>

![威胁防护状态报告筛选器](../../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)

<span data-ttu-id="aebfa-166">您还可以选择查看标识为恶意的电子邮件的数据、被标识为网络钓鱼尝试的电子邮件，或确定为包含恶意软件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aebfa-166">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>

![威胁防护状态报告视图选项](../../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)

## <a name="malware-detections-report"></a><span data-ttu-id="aebfa-168">恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-168">Malware Detections report</span></span>

<span data-ttu-id="aebfa-169">**恶意软件检测**报告将显示检测到多少传入邮件和传出邮件，以包含贵组织的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="aebfa-169">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span>

<span data-ttu-id="aebfa-170">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，转到 "**报告**" \> **仪表板** \> **恶意软件检测**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-170">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>

![恶意软件检测报告示例](../../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)

<span data-ttu-id="aebfa-172">与其他报告（如 "[威胁防护状态报告](#threat-protection-status-report)"）类似，报告默认显示过去七天的数据。</span><span class="sxs-lookup"><span data-stu-id="aebfa-172">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="aebfa-173">不过，您可以选择**筛选器**来更改日期范围。</span><span class="sxs-lookup"><span data-stu-id="aebfa-173">However, you can choose **Filters** to change the date range.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="aebfa-174">主要恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-174">Top Malware report</span></span>

<span data-ttu-id="aebfa-175">**上面的恶意软件**报告显示[Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)检测到的各种类型的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="aebfa-175">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span>

<span data-ttu-id="aebfa-176">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，转到 "**报告**" \> **仪表板**" \> **热门恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="aebfa-176">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>

![SCC-EOP 主要恶意软件](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)

<span data-ttu-id="aebfa-178">当您将鼠标指针悬停在饼图中时，您可以看到某种类型的恶意软件的名称以及检测到该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-178">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="aebfa-179">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="aebfa-179">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

![此报告显示为你的组织检测到的主要恶意软件](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)

<span data-ttu-id="aebfa-181">在图表下方，你将看到检测到的恶意软件的列表以及检测到该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-181">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="aebfa-182">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-182">Top Senders and Recipients report</span></span>

<span data-ttu-id="aebfa-183">**最上面的发件人和收件人**报告是显示主要电子邮件发件人的饼形图。</span><span class="sxs-lookup"><span data-stu-id="aebfa-183">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span>

<span data-ttu-id="aebfa-184">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，转到 "**报告**" \> **仪表板**的 \> **主要发件人和收件人**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-184">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>

![若要查看此报告，请在安全 & 合规性中心中，转到 "报告" \> 仪表板 \> 主要发件人和收件人](../../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)

<span data-ttu-id="aebfa-186">当您将鼠标指针悬停在饼图中时，您可以看到发送或接收的邮件数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-186">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="aebfa-187">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="aebfa-187">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

<span data-ttu-id="aebfa-188">使用 "**显示数据**" 列表选择是查看主要发件人、收件人、垃圾邮件收件人和恶意软件收件人的数据。</span><span class="sxs-lookup"><span data-stu-id="aebfa-188">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="aebfa-189">您还可以查看[Exchange Online Protection](exchange-online-protection-overview.md)检测到的恶意软件的接收人。</span><span class="sxs-lookup"><span data-stu-id="aebfa-189">You can also see who received malware that was detected by [Exchange Online Protection](exchange-online-protection-overview.md).</span></span>

![使用 "显示数据" 列表查看特定信息](../../media/bd91449f-7d42-4749-8666-7b44044049b8.png)

<span data-ttu-id="aebfa-191">在图表下方，你将看到首要的电子邮件发件人或收件人，以及在给定时间段内发送或接收的邮件数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-191">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="aebfa-192">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-192">Spoof Detections report</span></span>

<span data-ttu-id="aebfa-193">**欺骗检测**报告显示检测到的欺骗邮件的数量以及这些邮件被视为 "好" （欺骗邮件出于合理商业原因而完成）。</span><span class="sxs-lookup"><span data-stu-id="aebfa-193">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span>

<span data-ttu-id="aebfa-194">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，转到 "**报告**" \> **仪表板** \> **欺骗邮件**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-194">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>

![在安全 & 合规性中心中，转到 "报告" \> 仪表板 \> 欺骗邮件](../../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)

<span data-ttu-id="aebfa-196">当您将鼠标指针悬停在图表中的某一天时，您可以看到通过的欺骗邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="aebfa-196">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="aebfa-197">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="aebfa-197">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="aebfa-198">若要了解有关反欺骗保护的详细信息，请参阅[Microsoft 365 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="aebfa-198">To learn more about anti-spoof protection, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="aebfa-199">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-199">Spam Detections report</span></span>

<span data-ttu-id="aebfa-200">**垃圾邮件检测**报告显示 Exchange Online 阻止的所有垃圾邮件内容。</span><span class="sxs-lookup"><span data-stu-id="aebfa-200">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="aebfa-201">邮件按每封邮件计数，而不是按收件人计数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-201">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="aebfa-202">例如，如果电子邮件发送给组织中的100收件人，则会将其计为一封邮件。</span><span class="sxs-lookup"><span data-stu-id="aebfa-202">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>

<span data-ttu-id="aebfa-203">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，转到 "**报告**" \> **仪表板** \> **垃圾邮件检测**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-203">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>

![若要查看此报告，请在安全 & 合规性中心中，转到 "报告" \> 仪表板 \> EOP "垃圾邮件检测"](../../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)

<span data-ttu-id="aebfa-205">当您将鼠标指针悬停在图表中的某一天时，您可以看到该日已被阻止的项目数，以及这些项目的分类方式。</span><span class="sxs-lookup"><span data-stu-id="aebfa-205">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="aebfa-206">例如，您可以查看筛选出的垃圾邮件的数量，以及来自阻止的 Internet 协议（IP）地址的项目数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-206">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>

<span data-ttu-id="aebfa-207">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="aebfa-207">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

![垃圾邮件检测报告可告知您阻止或筛选出的垃圾邮件数](../../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)

<span data-ttu-id="aebfa-209">在图表下方，你将看到检测到的垃圾邮件项目的列表。</span><span class="sxs-lookup"><span data-stu-id="aebfa-209">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="aebfa-210">选择一个项目以查看其他信息，例如垃圾邮件项目是否为入站或出站、其邮件 ID 及其收件人。</span><span class="sxs-lookup"><span data-stu-id="aebfa-210">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="aebfa-211">若要了解有关反垃圾邮件保护的详细信息，请参阅[Office 365 电子邮件反垃圾邮件保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)。</span><span class="sxs-lookup"><span data-stu-id="aebfa-211">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="aebfa-212">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-212">Sent and received email report</span></span>

<span data-ttu-id="aebfa-213">**已发送和已接收的电子邮件**报告是一个智能报告，显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为 "正常" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aebfa-213">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span>

<span data-ttu-id="aebfa-214">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，转到 "**报告**" \> **仪表板** \> **发送和接收的电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-214">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>

![若要查看此报告，请在安全 & 合规性中心中，转到 "报告" \> 仪表板 \> 发送和接收电子邮件](../../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)

<span data-ttu-id="aebfa-216">当您将鼠标指针悬停在图表中的某一天时，可以看到传入的邮件数以及这些邮件的分类方式。</span><span class="sxs-lookup"><span data-stu-id="aebfa-216">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="aebfa-217">例如，您可以查看检测到包含恶意软件的邮件数，以及被标识为垃圾邮件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="aebfa-217">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>

<span data-ttu-id="aebfa-218">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="aebfa-218">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

<span data-ttu-id="aebfa-219">您可以使用 "**分解依据**" 列表按类型或按方向（传入和传出）查看信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-219">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span>

![使用 "分解依据" 列表按类型或方向查看信息](../../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)

<span data-ttu-id="aebfa-221">在图表下方，您将看到一个电子邮件类别的列表，如**GoodMail**、 **SpamContentFiltered**等。</span><span class="sxs-lookup"><span data-stu-id="aebfa-221">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="aebfa-222">选择类别以查看其他信息，例如对恶意软件所执行的操作以及电子邮件是传入的还是传出的。</span><span class="sxs-lookup"><span data-stu-id="aebfa-222">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>

![此报告告诉你有关反恶意软件、反垃圾邮件和其他邮件检测](../../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="aebfa-224">若要了解有关电子邮件智能的详细信息，请参阅[Microsoft 365 中的邮件流智能](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="aebfa-224">To learn more about email intelligence, see [Mail flow intelligence in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="aebfa-225">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="aebfa-225">User-reported messages report</span></span>

<span data-ttu-id="aebfa-226">"**用户报告的邮件**" 报告显示用户通过使用[报告邮件外接程序](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)报告为垃圾邮件、网络钓鱼尝试或良好邮件的电子邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-226">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="aebfa-227">详细信息可用于每封邮件，包括传递原因、为您的组织配置的垃圾邮件策略例外或邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="aebfa-227">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="aebfa-228">若要查看详细信息，请在 "用户报告" 列表中选择一个项目，然后查看 "**摘要**" 和 "**详细信息**" 选项卡上的信息。</span><span class="sxs-lookup"><span data-stu-id="aebfa-228">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

!["用户报告的邮件" 报告显示用户标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试的邮件。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="aebfa-230">若要查看此报告，请在[安全 & 合规性中心](https://protection.office.com)中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="aebfa-230">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="aebfa-231">转到 "**威胁管理** \> **仪表板** \> **用户报告的邮件**"。</span><span class="sxs-lookup"><span data-stu-id="aebfa-231">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="aebfa-232">转到 "**威胁管理**" \> **查看** \> **用户报告的邮件**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-232">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![在安全 & 合规性中心中，选择 "威胁管理" \> 查看 \> 用户报告的消息](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="aebfa-234">为了使用户报告的邮件报告正常工作，必须为您的 Office 365 环境**打开审核日志记录**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-234">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="aebfa-235">这通常由在 Exchange Online 中分配了审核日志角色的人完成。</span><span class="sxs-lookup"><span data-stu-id="aebfa-235">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="aebfa-236">有关详细信息，请参阅[打开或关闭 Microsoft 365 审核日志搜索](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="aebfa-236">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="aebfa-237">查看这些报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="aebfa-237">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="aebfa-238">若要查看和使用本文中所述的报告，**您必须为安全 & 合规中心和 Exchange 管理中心分配适当的角色**。</span><span class="sxs-lookup"><span data-stu-id="aebfa-238">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security & Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="aebfa-239">对于 "安全 & 合规中心"，您必须具有以下分配的角色之一：</span><span class="sxs-lookup"><span data-stu-id="aebfa-239">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  <span data-ttu-id="aebfa-240">-组织管理-安全管理员（可在 Azure Active Directory 管理中心中分配（ [https://aad.portal.azure.com](https://aad.portal.azure.com) ）-安全读取器</span><span class="sxs-lookup"><span data-stu-id="aebfa-240">-Organization Management -Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)) -Security Reader</span></span>

- <span data-ttu-id="aebfa-241">对于 Exchange Online，必须在 Exchange 管理中心（）或 PowerShell cmdlet 中分配以下角色之一 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) （请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)）：</span><span class="sxs-lookup"><span data-stu-id="aebfa-241">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  <span data-ttu-id="aebfa-242">-组织管理-仅查看组织管理-仅查看收件人角色合规性管理</span><span class="sxs-lookup"><span data-stu-id="aebfa-242">-Organization Management -View-only Organization Management -View-Only Recipients role -Compliance Management</span></span>

<span data-ttu-id="aebfa-243">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="aebfa-243">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="aebfa-244">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="aebfa-244">Permissions in the Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)
 
- [<span data-ttu-id="aebfa-245">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="aebfa-245">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="aebfa-246">如果报告不显示数据，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="aebfa-246">What if the reports aren't showing data?</span></span>

<span data-ttu-id="aebfa-247">如果您未在报告中看到数据，请仔细检查您的策略设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="aebfa-247">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="aebfa-248">若要了解详细信息，请参阅[在 Microsoft 365 中防御威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。</span><span class="sxs-lookup"><span data-stu-id="aebfa-248">To learn more, see [Protect against threats in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aebfa-249">相关主题</span><span class="sxs-lookup"><span data-stu-id="aebfa-249">Related topics</span></span>

[<span data-ttu-id="aebfa-250">Microsoft 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="aebfa-250">Microsoft 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

[<span data-ttu-id="aebfa-251">安全 & 合规中心中的报告和见解</span><span class="sxs-lookup"><span data-stu-id="aebfa-251">Reports and insights in the Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
