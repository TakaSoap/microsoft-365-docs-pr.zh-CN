---
title: 从勒索软件攻击中恢复
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 管理员可以了解如何从勒索软件攻击中恢复。
ms.openlocfilehash: 753171578dc7b76aefadf4b8587e84320d98b912
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794444"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="6e5c2-103">在 Microsoft 365 中从勒索软件攻击中恢复</span><span class="sxs-lookup"><span data-stu-id="6e5c2-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6e5c2-104">即使你采取一切预防措施来保护你的组织，你仍然可能会遭受勒索 [软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 攻击。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="6e5c2-105">勒索软件是一个大企业，攻击非常复杂。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-105">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="6e5c2-106">本文中的步骤将为您提供恢复数据和停止内部感染传播的最佳机会。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-106">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="6e5c2-107">在开始之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="6e5c2-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="6e5c2-108">无法保证支付勒索将返回对文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="6e5c2-109">事实上，支付勒索可能会成为更多勒索软件的目标。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-109">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="6e5c2-110">如果已支付，但在未使用攻击者的解决方案的情况下恢复，请与银行联系，查看他们能否阻止交易。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-110">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="6e5c2-111">我们还建议您将勒索软件攻击报告给执法机构、欺诈报告网站和 Microsoft，如本文稍后所述。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="6e5c2-112">快速响应攻击及其后果非常重要。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-112">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="6e5c2-113">等待的时间越长，恢复受影响数据的可能性就越小。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="6e5c2-114">步骤 1：验证备份</span><span class="sxs-lookup"><span data-stu-id="6e5c2-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="6e5c2-115">如果具有脱机备份，那么在从环境中删除勒索软件有效负载后， (还原) 数据。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="6e5c2-116">如果没有备份，或者备份也受勒索软件影响，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="6e5c2-117">步骤 2：Exchange ActiveSync OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="6e5c2-117">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="6e5c2-118">此处的关键点就是阻止勒索软件传播数据加密。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="6e5c2-119">如果您怀疑电子邮件是勒索软件加密的目标，请暂时禁用用户对邮箱的访问。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-119">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="6e5c2-120">Exchange ActiveSync在设备和 Exchange Online 邮箱之间同步数据。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-120">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="6e5c2-121">若要禁用Exchange ActiveSync，请参阅如何为 Exchange [Online 中的Exchange ActiveSync禁用邮件。](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-121">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="6e5c2-122">若要禁用对邮箱的其他类型的访问，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6e5c2-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="6e5c2-123">[启用或禁用邮箱的 MAPI。](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="6e5c2-124">为用户启用或禁用 POP3 或 IMAP4 访问</span><span class="sxs-lookup"><span data-stu-id="6e5c2-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="6e5c2-125">暂停 OneDrive 同步有助于防止云数据被潜在感染的设备更新。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="6e5c2-126">有关详细信息，请参阅如何在 [OneDrive 中暂停和恢复同步](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="6e5c2-127">步骤 3：从受影响的设备中删除恶意软件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="6e5c2-128">在所有可疑计算机和设备上运行完整的当前防病毒扫描，以检测和删除与勒索软件关联的有效负载。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-128">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="6e5c2-129">不要忘记扫描正在同步数据的设备或映射的网络驱动器的目标。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-129">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="6e5c2-130">你可以将[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)或 (客户端) Microsoft Security Essentials。 [](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="6e5c2-131">此外，还可以帮助你删除勒索软件或恶意软件的替代方法是 [MSRT ](https://www.microsoft.com/download/details.aspx?id=9905) (恶意软件) 。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="6e5c2-132">如果这些选项不起作用，可以尝试Windows Defender [或](https://support.microsoft.com/help/17466) 解决 [检测和删除恶意软件的问题](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="6e5c2-133">步骤 4：在已清理的计算机或设备上恢复文件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="6e5c2-134">完成上一步以从你的环境 (中删除勒索软件负载（这将阻止勒索软件加密或删除你的文件) ）后，可以使用 Windows 10 和 Windows 8.1 中的文件历史记录或 Windows 7 中的系统保护尝试恢复你的本地文件和文件夹。 [](https://support.microsoft.com/help/17128)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="6e5c2-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="6e5c2-135">**Notes**:</span></span>

- <span data-ttu-id="6e5c2-136">某些勒索软件还会加密或删除备份版本，因此你无法使用文件历史记录或系统保护来还原文件。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="6e5c2-137">如果发生这种情况，则需要在不受勒索软件或 OneDrive 影响的外部驱动器或设备上使用备份，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="6e5c2-138">如果文件夹已同步到 OneDrive，并且你未使用最新版本的 Windows，则使用文件历史记录可能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="6e5c2-139">步骤 5：恢复 OneDrive for Business 中的文件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="6e5c2-140">OneDrive for Business 中的文件还原允许你将整个 OneDrive 还原到过去 30 天内以前的时间点。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="6e5c2-141">有关详细信息，请参阅"[还原 OneDrive"。](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="6e5c2-142">步骤 6：恢复已删除的电子邮件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="6e5c2-143">在勒索软件删除所有电子邮件的极少数情况下，你或许可以恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="6e5c2-144">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6e5c2-144">For more information, see:</span></span>

- [<span data-ttu-id="6e5c2-145">恢复用户邮箱中的已删除邮件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="6e5c2-146">在 Outlook for Windows 中恢复已删除项目</span><span class="sxs-lookup"><span data-stu-id="6e5c2-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="6e5c2-147">步骤 7：重新启用Exchange ActiveSync OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="6e5c2-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="6e5c2-148">在清理计算机和设备并恢复数据后，可以重新启用之前在步骤 [2](#step-2-disable-exchange-activesync-and-onedrive-sync)中Exchange ActiveSync禁用的 Exchange ActiveSync 和 OneDrive 同步。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-148">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="6e5c2-149">步骤 8 (可选) ：阻止特定文件扩展名的 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="6e5c2-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="6e5c2-150">恢复后，可以阻止 OneDrive for Business 客户端同步受此勒索软件影响的文件类型。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="6e5c2-151">有关详细信息，请参阅 [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="6e5c2-152">报告攻击</span><span class="sxs-lookup"><span data-stu-id="6e5c2-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="6e5c2-153">联系法律部门</span><span class="sxs-lookup"><span data-stu-id="6e5c2-153">Contact law enforcement</span></span>

<span data-ttu-id="6e5c2-154">应联系当地或联邦执法机构。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="6e5c2-155">例如，如果你在美国，你可以联系[美国审计局本地现场办公室、IC3](https://www.fbi.gov/contact-us/field)[或](http://www.ic3.gov/complaint/default.aspx)[密码服务](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="6e5c2-156">向你国家/地区欺诈报告网站提交报告</span><span class="sxs-lookup"><span data-stu-id="6e5c2-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="6e5c2-157">欺诈报告网站提供有关如何防止和避免欺诈的信息。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="6e5c2-158">它们还提供一些机制，用于报告您是否是欺诈的受攻击者。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="6e5c2-159">澳大利亚 [：SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="6e5c2-160">加拿大： [加拿大反欺诈中心](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="6e5c2-161">法国 [：Agence nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="6e5c2-162">德国 [：Der Informationstechnik 中的 Bundesamt für Sicherheit](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="6e5c2-163">爱尔兰： [一名 Garda Sí一一图卡](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="6e5c2-164">新西兰： [消费者诈骗](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="6e5c2-165">英国： [诉讼欺诈](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="6e5c2-166">美国 [：On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="6e5c2-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="6e5c2-167">如果你的国家/地区未列出，请咨询你的本地或联邦执法机构。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="6e5c2-168">向 Microsoft 提交电子邮件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="6e5c2-169">可以使用多种方法之一报告包含勒索软件的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-169">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="6e5c2-170">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="6e5c2-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e5c2-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e5c2-171">See also</span></span>

- [<span data-ttu-id="6e5c2-172">勒索软件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="6e5c2-173">勒索软件响应- 要付费还是不支付？</span><span class="sxs-lookup"><span data-stu-id="6e5c2-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="6e5c2-174">Norsk 随透明度响应勒索软件攻击</span><span class="sxs-lookup"><span data-stu-id="6e5c2-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="6e5c2-175">勒索软件检测和恢复 OneDrive 中的文件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="6e5c2-176">Microsoft 安全智能报告</span><span class="sxs-lookup"><span data-stu-id="6e5c2-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="6e5c2-177">启用或禁用 Office 文件中宏</span><span class="sxs-lookup"><span data-stu-id="6e5c2-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="6e5c2-178">用于配置 EOP 和 Defender for Office 365 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="6e5c2-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="6e5c2-179">有价值的升级：Windows 10 上的下一代安全性证明可抵御 2017 年勒索软件爆发</span><span class="sxs-lookup"><span data-stu-id="6e5c2-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="6e5c2-180">没有 mas，Samas：此勒索软件模式操作方式是什么？</span><span class="sxs-lookup"><span data-stu-id="6e5c2-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="6e5c2-181">锁定恶意软件，防止其入侵</span><span class="sxs-lookup"><span data-stu-id="6e5c2-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="6e5c2-182">MSRT 2016 年 7 月：Cerber 勒索软件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="6e5c2-183">Cerberus-like Cerber 勒索软件三个头</span><span class="sxs-lookup"><span data-stu-id="6e5c2-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="6e5c2-184">受 Da Vinci 代码 () 勒索软件</span><span class="sxs-lookup"><span data-stu-id="6e5c2-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
