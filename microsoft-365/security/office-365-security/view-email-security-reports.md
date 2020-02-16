---
title: 查看安全&amp;合规性中心中的电子邮件安全报告、受到威胁的用户、加密、威胁保护状态、恶意软件检测、热门恶意软件、垃圾邮件检测、发送和接收的电子邮件、用户报告的消息、阅读报告、检测、安全数据、安全信息
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
description: 了解如何查找和使用组织的电子邮件安全报告。 安全&amp;合规性中心中提供了电子邮件安全报告。
ms.openlocfilehash: fba10207fe0b7a8e02aa96f9c8513e1e5b2cd61f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084538"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="5503a-104">查看安全&amp;合规性中心中的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="5503a-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="5503a-105">[安全&amp;合规性中心](https://protection.office.com)中提供了多种报告，可帮助您了解电子邮件安全功能（如 Office 365 中的反垃圾邮件、反恶意软件和加密功能如何保护组织）。</span><span class="sxs-lookup"><span data-stu-id="5503a-105">A variety of reports are available in the [Security &amp; Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="5503a-106">如果您具有[所需的权限](#what-permissions-are-needed-to-view-these-reports)，则可以转到 "**报告** \> " &amp; **仪表板**，在安全合规中心中查看这些报告。</span><span class="sxs-lookup"><span data-stu-id="5503a-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![可在其中查看高级威胁防护的工作方式的仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="5503a-108">您的电子邮件安全报告包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="5503a-108">Your email security reports include the following:</span></span>
- [<span data-ttu-id="5503a-109">已泄露的用户报告（**新！**）</span><span class="sxs-lookup"><span data-stu-id="5503a-109">Compromised Users report (**NEW!**)</span></span>](#compromised-users-report-new)
- [<span data-ttu-id="5503a-110">加密报告</span><span class="sxs-lookup"><span data-stu-id="5503a-110">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="5503a-111">威胁防护状态</span><span class="sxs-lookup"><span data-stu-id="5503a-111">Threat Protection Status report</span></span>](#threat-protection-status-report) 
- [<span data-ttu-id="5503a-112">恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="5503a-112">Malware Detections report</span></span>](#malware-detections-report) 
- [<span data-ttu-id="5503a-113">主要恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="5503a-113">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="5503a-114">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="5503a-114">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="5503a-115">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="5503a-115">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="5503a-116">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="5503a-116">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="5503a-117">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="5503a-117">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="5503a-118">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="5503a-118">User-reported messages report</span></span>](#user-reported-messages-report)


## <a name="compromised-users-report-new"></a><span data-ttu-id="5503a-119">已泄露的用户报告（**新！**）</span><span class="sxs-lookup"><span data-stu-id="5503a-119">Compromised Users report (**NEW!**)</span></span> 

<span data-ttu-id="5503a-120">此报告可供任何具有 Exchange Online Protection 的用户使用，并显示标记为可疑用户或受限制用户的用户帐户数。在帐户中，数据特别有用。输入指示用户帐户可能有问题的任何状态，甚至威胁.</span><span class="sxs-lookup"><span data-stu-id="5503a-120">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="5503a-121">通过频繁使用，已损坏的用户报告可以发现处于可疑或受限制状态的帐户中的峰值、甚至是趋势，从而提供证据可能存在安全和租户的 wellness 问题。</span><span class="sxs-lookup"><span data-stu-id="5503a-121">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![已泄露的用户会在 Office 365 中进行报告。](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="5503a-123">加密报告</span><span class="sxs-lookup"><span data-stu-id="5503a-123">Encryption report</span></span>

<span data-ttu-id="5503a-124">**加密报告**显示有关通过组织策略或通过最终用户控件进行加密的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="5503a-124">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="5503a-125">您组织的安全团队可以使用此报告中的信息来标识模式，并主动应用或调整敏感电子邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="5503a-125">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="5503a-126">若要查看此报告，请在安全 & 合规性中心中，转到 "**报告** \> **" 仪表板** \> **加密报告**。</span><span class="sxs-lookup"><span data-stu-id="5503a-126">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![加密报告](../../media/encryptionreport-defaultview.png) 

<span data-ttu-id="5503a-128">当报告第一次打开时，您将看到有关过去七（7）天的电子邮件上使用的加密方法的数据。</span><span class="sxs-lookup"><span data-stu-id="5503a-128">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="5503a-129">通过单击屏幕右上角的 "**筛选器**"，可以更改报告中显示的日期范围和详细信息。</span><span class="sxs-lookup"><span data-stu-id="5503a-129">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![加密报告筛选器](../../media/encryptionreport-filters.png)   

<span data-ttu-id="5503a-131">您还可以使用 "**向下分页**" 菜单查看通过加密模板（或方法）的数据。</span><span class="sxs-lookup"><span data-stu-id="5503a-131">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![加密方法或模板](../../media/encryptionreport-breakdownby.png)

<span data-ttu-id="5503a-133">您还可以使用 "**查看数据方式**" 菜单更改视图，以查看前五个收件人域的加密邮件数。</span><span class="sxs-lookup"><span data-stu-id="5503a-133">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![加密报告按菜单查看数据](../../media/encryptionreport-viewdataby.png)

<span data-ttu-id="5503a-135">通过新的加密报告的灵活性，您可以查看趋势并采取适当的操作。</span><span class="sxs-lookup"><span data-stu-id="5503a-135">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="5503a-136">例如，如果您看到用户加密了大量的电子邮件，您可能希望添加加密策略以对某些用例自动进行加密。</span><span class="sxs-lookup"><span data-stu-id="5503a-136">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="5503a-137">（若要获取有关此的帮助，请参阅[定义邮件流规则以对 Office 365 中的电子邮件进行加密](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。）另一个示例是，如果有许多可用的加密模板，但没有用户正在使用它们，则可以考察用户是否需要针对该功能的培训。</span><span class="sxs-lookup"><span data-stu-id="5503a-137">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span> 

<span data-ttu-id="5503a-138">使用此报告使组织的安全和合规性团队能够监视邮件加密的使用情况，以及是否需要进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="5503a-138">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="5503a-139">若要了解有关加密的详细信息，请参阅[Office 365 中的电子邮件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="5503a-139">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="5503a-140">威胁防护状态</span><span class="sxs-lookup"><span data-stu-id="5503a-140">Threat Protection Status report</span></span>

<span data-ttu-id="5503a-141">**威胁防护状态**报告是一个智能报告，显示 Exchange Online Protection 检测到并阻止的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5503a-141">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="5503a-142">此报告可用于查看标识为恶意软件的电子邮件或一段时间内的网络钓鱼尝试（最长为90天），并使安全管理员能够确定趋势或确定策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="5503a-142">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="5503a-143">拥有[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)或[Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) （EOP）的客户可以使用威胁防护状态报告;但是，在 ATP 客户的威胁防护状态报告中显示的信息可能包含不同的 EOP 客户可能看到的数据。</span><span class="sxs-lookup"><span data-stu-id="5503a-143">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="5503a-144">例如，EOP 客户可以查看有关在电子邮件中检测到的恶意软件的信息，但不是关于[在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到的恶意文件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)的信息，这是与 ATP 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="5503a-144">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="5503a-145">（[了解有关 ATP 报告的详细信息](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。）</span><span class="sxs-lookup"><span data-stu-id="5503a-145">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>
  
<span data-ttu-id="5503a-146">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **威胁防护状态**。</span><span class="sxs-lookup"><span data-stu-id="5503a-146">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![威胁防护状态](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="5503a-148">当您首次打开 "威胁 Protection 状态报告" 时，报告默认显示过去七天的数据;不过，您可以单击 "**筛选器**" 并将日期范围更改为最多90天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5503a-148">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="5503a-149">（如果使用的是试用订阅，则可能限制为30天的数据。）</span><span class="sxs-lookup"><span data-stu-id="5503a-149">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="5503a-150">此报告对查看组织的[Exchange Online Protection 功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)和长期趋势分析的有效性和影响非常有用。</span><span class="sxs-lookup"><span data-stu-id="5503a-150">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span> 
  
![威胁防护状态报告筛选器](../../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="5503a-152">您还可以选择查看标识为恶意的电子邮件的数据、被标识为网络钓鱼尝试的电子邮件，或确定为包含恶意软件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5503a-152">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![威胁防护状态报告视图选项](../../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="5503a-154">恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="5503a-154">Malware Detections report</span></span>

<span data-ttu-id="5503a-155">**恶意软件检测**报告将显示检测到多少传入邮件和传出邮件，以包含贵组织的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="5503a-155">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="5503a-156">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **恶意软件检测**。</span><span class="sxs-lookup"><span data-stu-id="5503a-156">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![恶意软件检测报告示例](../../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="5503a-158">与其他报告（如 "[威胁防护状态报告](#threat-protection-status-report)"）类似，报告默认显示过去七天的数据。</span><span class="sxs-lookup"><span data-stu-id="5503a-158">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="5503a-159">不过，您可以选择**筛选器**来更改日期范围。</span><span class="sxs-lookup"><span data-stu-id="5503a-159">However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="5503a-160">主要恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="5503a-160">Top Malware report</span></span>

<span data-ttu-id="5503a-161">**上面的恶意软件**报告显示[Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)检测到的各种类型的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="5503a-161">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span> 
  
<span data-ttu-id="5503a-162">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> "**热门恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="5503a-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC-EOP 主要恶意软件](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="5503a-164">当您将鼠标指针悬停在饼图中时，您可以看到某种类型的恶意软件的名称以及检测到该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="5503a-164">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="5503a-165">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="5503a-165">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![此报告显示为你的组织检测到的主要恶意软件](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="5503a-167">在图表下方，你将看到检测到的恶意软件的列表以及检测到该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="5503a-167">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="5503a-168">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="5503a-168">Top Senders and Recipients report</span></span>

<span data-ttu-id="5503a-169">**最上面的发件人和收件人**报告是显示主要电子邮件发件人的饼形图。</span><span class="sxs-lookup"><span data-stu-id="5503a-169">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="5503a-170">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **顶部的发件人和收件人**。</span><span class="sxs-lookup"><span data-stu-id="5503a-170">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![若要查看此报告，请在&amp;安全合规性中心中， \>转\>到 "报告" 仪表板主要发件人和收件人](../../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="5503a-172">当您将鼠标指针悬停在饼图中时，您可以看到发送或接收的邮件数。</span><span class="sxs-lookup"><span data-stu-id="5503a-172">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="5503a-173">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="5503a-173">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="5503a-174">使用 "**显示数据**" 列表选择是查看主要发件人、收件人、垃圾邮件收件人和恶意软件收件人的数据。</span><span class="sxs-lookup"><span data-stu-id="5503a-174">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="5503a-175">您还可以查看[Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop)检测到的恶意软件的接收人。</span><span class="sxs-lookup"><span data-stu-id="5503a-175">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span> 
  
![使用 "显示数据" 列表查看特定信息](../../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="5503a-177">在图表下方，你将看到首要的电子邮件发件人或收件人，以及在给定时间段内发送或接收的邮件数。</span><span class="sxs-lookup"><span data-stu-id="5503a-177">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-detections-report"></a><span data-ttu-id="5503a-178">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="5503a-178">Spoof Detections report</span></span>

<span data-ttu-id="5503a-179">**欺骗检测**报告显示检测到的欺骗邮件的数量以及这些邮件被视为 "好" （欺骗邮件出于合理商业原因而完成）。</span><span class="sxs-lookup"><span data-stu-id="5503a-179">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="5503a-180">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **欺骗邮件**。</span><span class="sxs-lookup"><span data-stu-id="5503a-180">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![在安全&amp;合规性中心中，转到\> " \>报告" 仪表板欺骗邮件](../../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="5503a-182">当您将鼠标指针悬停在图表中的某一天时，您可以看到通过的欺骗邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="5503a-182">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="5503a-183">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="5503a-183">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="5503a-184">若要了解有关反欺骗保护的详细信息，请参阅[Office 365 中的反欺骗保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection)。</span><span class="sxs-lookup"><span data-stu-id="5503a-184">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="5503a-185">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="5503a-185">Spam Detections report</span></span>

<span data-ttu-id="5503a-186">**垃圾邮件检测**报告显示 Exchange Online 阻止的所有垃圾邮件内容。</span><span class="sxs-lookup"><span data-stu-id="5503a-186">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="5503a-187">邮件按每封邮件计数，而不是按收件人计数。</span><span class="sxs-lookup"><span data-stu-id="5503a-187">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="5503a-188">例如，如果电子邮件发送给组织中的100收件人，则会将其计为一封邮件。</span><span class="sxs-lookup"><span data-stu-id="5503a-188">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>
  
<span data-ttu-id="5503a-189">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **垃圾邮件检测**。</span><span class="sxs-lookup"><span data-stu-id="5503a-189">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![若要查看此报告，请在&amp;安全合规性中心中， \>转\>到 "报告" 仪表板 EOP 垃圾邮件检测](../../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="5503a-191">当您将鼠标指针悬停在图表中的某一天时，您可以看到该日已被阻止的项目数，以及这些项目的分类方式。</span><span class="sxs-lookup"><span data-stu-id="5503a-191">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="5503a-192">例如，您可以查看筛选出的垃圾邮件的数量，以及来自阻止的 Internet 协议（IP）地址的项目数。</span><span class="sxs-lookup"><span data-stu-id="5503a-192">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="5503a-193">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="5503a-193">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![垃圾邮件检测报告可告知您阻止或筛选出的垃圾邮件数](../../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="5503a-195">在图表下方，你将看到检测到的垃圾邮件项目的列表。</span><span class="sxs-lookup"><span data-stu-id="5503a-195">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="5503a-196">选择一个项目以查看其他信息，例如垃圾邮件项目是否为入站或出站、其邮件 ID 及其收件人。</span><span class="sxs-lookup"><span data-stu-id="5503a-196">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="5503a-197">若要了解有关反垃圾邮件保护的详细信息，请参阅[Office 365 电子邮件反垃圾邮件保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)。</span><span class="sxs-lookup"><span data-stu-id="5503a-197">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="5503a-198">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="5503a-198">Sent and received email report</span></span>

<span data-ttu-id="5503a-199">**已发送和已接收的电子邮件**报告是一个智能报告，显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为 "正常" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5503a-199">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="5503a-200">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **发送和接收电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="5503a-200">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![若要查看此报告，请在&amp;安全合规性中心中， \>转\>到 "报告" 仪表板发送和接收电子邮件](../../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="5503a-202">当您将鼠标指针悬停在图表中的某一天时，可以看到传入的邮件数以及这些邮件的分类方式。</span><span class="sxs-lookup"><span data-stu-id="5503a-202">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="5503a-203">例如，您可以查看检测到包含恶意软件的邮件数，以及被标识为垃圾邮件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="5503a-203">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="5503a-204">单击（或点击）报表以在新的浏览器窗口中打开它，您可以在其中获取报表的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="5503a-204">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="5503a-205">您可以使用 "**分解依据**" 列表按类型或按方向（传入和传出）查看信息。</span><span class="sxs-lookup"><span data-stu-id="5503a-205">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![使用 "分解依据" 列表按类型或方向查看信息](../../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="5503a-207">在图表下方，您将看到一个电子邮件类别的列表，如**GoodMail**、 **SpamContentFiltered**等。</span><span class="sxs-lookup"><span data-stu-id="5503a-207">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="5503a-208">选择类别以查看其他信息，例如对恶意软件所执行的操作以及电子邮件是传入的还是传出的。</span><span class="sxs-lookup"><span data-stu-id="5503a-208">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![此报告告诉你有关反恶意软件、反垃圾邮件和其他邮件检测](../../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="5503a-210">若要了解有关电子邮件智能的详细信息，请参阅[Office 365 中的邮件流智能](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="5503a-210">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>
  
## <a name="user-reported-messages-report"></a><span data-ttu-id="5503a-211">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="5503a-211">User-reported messages report</span></span>

<span data-ttu-id="5503a-212">"**用户报告的邮件**" 报告显示用户通过使用[报告邮件外接程序](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)报告为垃圾邮件、网络钓鱼尝试或良好邮件的电子邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="5503a-212">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>
  
<span data-ttu-id="5503a-213">详细信息可用于每封邮件，包括传递原因、为您的组织配置的垃圾邮件策略例外或邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="5503a-213">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="5503a-214">若要查看详细信息，请在 "用户报告" 列表中选择一个项目，然后查看 "**摘要**" 和 "**详细信息**" 选项卡上的信息。</span><span class="sxs-lookup"><span data-stu-id="5503a-214">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
!["用户报告的邮件" 报告显示用户标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试的邮件。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="5503a-216">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="5503a-216">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="5503a-217">转到 "**威胁管理** \> **仪表板** \> **用户报告的邮件**"。</span><span class="sxs-lookup"><span data-stu-id="5503a-217">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="5503a-218">转到 "**威胁管理** \> "**查看** \> **用户报告的邮件**。</span><span class="sxs-lookup"><span data-stu-id="5503a-218">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![在 "安全&amp;合规性中心" 中， \>选择\> "威胁管理" 查看用户报告的消息](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="5503a-220">为了使用户报告的邮件报告正常工作，必须为您的 Office 365 环境**打开审核日志记录**。</span><span class="sxs-lookup"><span data-stu-id="5503a-220">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="5503a-221">这通常由在 Exchange Online 中分配了审核日志角色的人完成。</span><span class="sxs-lookup"><span data-stu-id="5503a-221">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="5503a-222">有关详细信息，请参阅[打开或关闭 Office 365 审核日志搜索](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="5503a-222">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="5503a-223">查看这些报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="5503a-223">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="5503a-224">为了查看和使用本文中介绍的报告，**必须为安全&amp;合规中心和 Exchange 管理中心分配适当的角色**。</span><span class="sxs-lookup"><span data-stu-id="5503a-224">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="5503a-225">对于安全&amp;合规中心，您必须具有以下分配的角色之一：</span><span class="sxs-lookup"><span data-stu-id="5503a-225">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="5503a-226">组织管理</span><span class="sxs-lookup"><span data-stu-id="5503a-226">Organization Management</span></span>
    - <span data-ttu-id="5503a-227">安全管理员（可在 Azure Active Directory 管理中心中进行分配（[https://aad.portal.azure.com](https://aad.portal.azure.com)）</span><span class="sxs-lookup"><span data-stu-id="5503a-227">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="5503a-228">安全读取者</span><span class="sxs-lookup"><span data-stu-id="5503a-228">Security Reader</span></span>

- <span data-ttu-id="5503a-229">对于 Exchange Online，必须在 Exchange 管理中心（[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)）或 PowerShell cmdlet 中分配以下角色之一（请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)）：</span><span class="sxs-lookup"><span data-stu-id="5503a-229">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="5503a-230">组织管理</span><span class="sxs-lookup"><span data-stu-id="5503a-230">Organization Management</span></span>
    - <span data-ttu-id="5503a-231">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="5503a-231">View-only Organization Management</span></span>
    - <span data-ttu-id="5503a-232">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="5503a-232">View-Only Recipients role</span></span>
    - <span data-ttu-id="5503a-233">合规性管理</span><span class="sxs-lookup"><span data-stu-id="5503a-233">Compliance Management</span></span>

<span data-ttu-id="5503a-234">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="5503a-234">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="5503a-235">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5503a-235">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="5503a-236">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="5503a-236">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="5503a-237">如果报告不显示数据，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="5503a-237">What if the reports aren't showing data?</span></span>

<span data-ttu-id="5503a-238">如果您未在报告中看到数据，请仔细检查您的策略设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="5503a-238">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="5503a-239">若要了解详细信息，请参阅[在 Office 365 中防御威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。</span><span class="sxs-lookup"><span data-stu-id="5503a-239">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5503a-240">相关主题</span><span class="sxs-lookup"><span data-stu-id="5503a-240">Related topics</span></span>

[<span data-ttu-id="5503a-241">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="5503a-241">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[<span data-ttu-id="5503a-242">Office 365 安全&amp;合规中心中的报告和见解</span><span class="sxs-lookup"><span data-stu-id="5503a-242">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[<span data-ttu-id="5503a-243">在安全&amp;合规中心中创建报表的日程安排</span><span class="sxs-lookup"><span data-stu-id="5503a-243">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[<span data-ttu-id="5503a-244">在安全&amp;合规中心中设置和下载自定义报告</span><span class="sxs-lookup"><span data-stu-id="5503a-244">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

