---
title: 从勒索软件攻击中恢复
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 管理员可以了解如何从勒索软件攻击中恢复。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 242a4a2f43bd91d75caeaeaa0488f23a5ba4319d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203602"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="14fc8-103">在 Microsoft 365 中从勒索软件攻击中恢复</span><span class="sxs-lookup"><span data-stu-id="14fc8-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="14fc8-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="14fc8-104">**Applies to**</span></span>
- [<span data-ttu-id="14fc8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="14fc8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="14fc8-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="14fc8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="14fc8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14fc8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="14fc8-108">即使你采取一切预防措施来保护你的组织，你仍然可能会遭受勒索软件 [攻击](/windows/security/threat-protection/intelligence/ransomware-malware) 。</span><span class="sxs-lookup"><span data-stu-id="14fc8-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="14fc8-109">勒索软件是一个大企业，并且攻击非常复杂。</span><span class="sxs-lookup"><span data-stu-id="14fc8-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="14fc8-110">本文中的步骤将为您提供恢复数据和停止内部感染传播的最佳机会。</span><span class="sxs-lookup"><span data-stu-id="14fc8-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="14fc8-111">在开始之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="14fc8-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="14fc8-112">无法保证支付勒索金额将返回对文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="14fc8-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="14fc8-113">事实上，支付勒索金额可能会成为更多勒索软件的目标。</span><span class="sxs-lookup"><span data-stu-id="14fc8-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="14fc8-114">如果已付款，但在未使用攻击者的解决方案的情况下恢复，请与银行联系，看看他们能否阻止交易。</span><span class="sxs-lookup"><span data-stu-id="14fc8-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="14fc8-115">我们还建议您向执法机构、欺诈报告网站和 Microsoft 报告勒索软件攻击，如本文稍后所述。</span><span class="sxs-lookup"><span data-stu-id="14fc8-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="14fc8-116">快速响应攻击及其后果非常重要。</span><span class="sxs-lookup"><span data-stu-id="14fc8-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="14fc8-117">等待的时间越长，恢复受影响数据的可能性就越小。</span><span class="sxs-lookup"><span data-stu-id="14fc8-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="14fc8-118">步骤 1：验证备份</span><span class="sxs-lookup"><span data-stu-id="14fc8-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="14fc8-119">如果你有脱机备份，你可能会在从环境中删除勒索软件有效负载 (恶意软件) 还原加密数据。</span><span class="sxs-lookup"><span data-stu-id="14fc8-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="14fc8-120">如果没有备份，或者备份也受勒索软件影响，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="14fc8-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="14fc8-121">步骤 2：禁用 Exchange ActiveSync 和 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="14fc8-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="14fc8-122">此处的关键点就是阻止勒索软件传播数据加密。</span><span class="sxs-lookup"><span data-stu-id="14fc8-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="14fc8-123">如果您怀疑电子邮件是勒索软件加密的目标，请暂时禁用用户对邮箱的访问。</span><span class="sxs-lookup"><span data-stu-id="14fc8-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="14fc8-124">Exchange ActiveSync在设备和 Exchange Online 邮箱之间同步数据。</span><span class="sxs-lookup"><span data-stu-id="14fc8-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="14fc8-125">若要禁用Exchange ActiveSync，请参阅[如何为 Exchange Online 中的Exchange ActiveSync禁用邮箱。](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="14fc8-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="14fc8-126">若要禁用对邮箱的其他类型的访问，请参阅：</span><span class="sxs-lookup"><span data-stu-id="14fc8-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="14fc8-127">[为邮箱启用或禁用 MAPI。](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="14fc8-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="14fc8-128">为用户启用或禁用 POP3 或 IMAP4 访问</span><span class="sxs-lookup"><span data-stu-id="14fc8-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="14fc8-129">暂停 OneDrive 同步有助于防止云数据被潜在感染的设备更新。</span><span class="sxs-lookup"><span data-stu-id="14fc8-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="14fc8-130">有关详细信息，请参阅如何在 [OneDrive 中暂停和恢复同步](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="14fc8-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="14fc8-131">步骤 3：从受影响的设备中删除恶意软件</span><span class="sxs-lookup"><span data-stu-id="14fc8-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="14fc8-132">在所有可疑计算机和设备上运行最新的完全防病毒扫描，以检测和删除与勒索软件关联的有效负载。</span><span class="sxs-lookup"><span data-stu-id="14fc8-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="14fc8-133">不要忘记扫描正在同步数据的设备或映射的网络驱动器的目标。</span><span class="sxs-lookup"><span data-stu-id="14fc8-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="14fc8-134">你可以[对Windows Defender旧](https://www.microsoft.com/windows/comprehensive-security) (客户端) Microsoft Security Essentials。 [](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="14fc8-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="14fc8-135">此外，还可以帮助你删除勒索软件或恶意软件的替代方法是[MSRT (恶意软件) 。 ](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="14fc8-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="14fc8-136">如果这些选项不起作用，可以尝试脱机Windows Defender检测并删除[](https://support.microsoft.com/help/17466)恶意软件[时出现问题](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="14fc8-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="14fc8-137">步骤 4：在已清理的计算机或设备上恢复文件</span><span class="sxs-lookup"><span data-stu-id="14fc8-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="14fc8-138">完成上一步以将勒索软件有效负载从你的环境 (这将阻止勒索软件加密或删除文件) 后，可以使用 Windows 10 和 Windows 8.1[](https://support.microsoft.com/help/17128)中的文件历史记录或 Windows 7 中的系统保护尝试恢复本地文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="14fc8-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="14fc8-139">**注意**：</span><span class="sxs-lookup"><span data-stu-id="14fc8-139">**Notes**:</span></span>

- <span data-ttu-id="14fc8-140">某些勒索软件还会加密或删除备份版本，因此你无法使用文件历史记录或系统保护来还原文件。</span><span class="sxs-lookup"><span data-stu-id="14fc8-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="14fc8-141">如果发生这种情况，你需要在不受勒索软件或 OneDrive 影响的外部驱动器或设备上使用备份，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="14fc8-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="14fc8-142">如果文件夹已同步到 OneDrive，并且你未使用最新版本的 Windows，则使用文件历史记录可能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="14fc8-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="14fc8-143">步骤 5：恢复 OneDrive for Business 中的文件</span><span class="sxs-lookup"><span data-stu-id="14fc8-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="14fc8-144">OneDrive for Business 中的文件还原允许你将整个 OneDrive 还原到过去 30 天内以前的时间点。</span><span class="sxs-lookup"><span data-stu-id="14fc8-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="14fc8-145">有关详细信息，请参阅还原[OneDrive。](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="14fc8-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="14fc8-146">步骤 6：恢复已删除的电子邮件</span><span class="sxs-lookup"><span data-stu-id="14fc8-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="14fc8-147">在勒索软件删除所有电子邮件的极少数情况下，你或许可以恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="14fc8-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="14fc8-148">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="14fc8-148">For more information, see:</span></span>

- [<span data-ttu-id="14fc8-149">恢复用户邮箱中的已删除邮件</span><span class="sxs-lookup"><span data-stu-id="14fc8-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="14fc8-150">在 Outlook for Windows 中恢复已删除项目</span><span class="sxs-lookup"><span data-stu-id="14fc8-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="14fc8-151">步骤 7：重新启用 Exchange ActiveSync 和 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="14fc8-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="14fc8-152">在清理计算机和设备并恢复数据后，可以重新启用之前在步骤 [2](#step-2-disable-exchange-activesync-and-onedrive-sync)中禁用的 Exchange ActiveSync 和 OneDrive 同步。</span><span class="sxs-lookup"><span data-stu-id="14fc8-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="14fc8-153">步骤 8 (可选) ：阻止特定文件扩展名的 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="14fc8-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="14fc8-154">恢复后，可以阻止 OneDrive for Business 客户端同步受此勒索软件影响的文件类型。</span><span class="sxs-lookup"><span data-stu-id="14fc8-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="14fc8-155">有关详细信息，请参阅 [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="14fc8-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="14fc8-156">报告攻击</span><span class="sxs-lookup"><span data-stu-id="14fc8-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="14fc8-157">联系执法机构</span><span class="sxs-lookup"><span data-stu-id="14fc8-157">Contact law enforcement</span></span>

<span data-ttu-id="14fc8-158">您应联系当地或联邦执法机构。</span><span class="sxs-lookup"><span data-stu-id="14fc8-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="14fc8-159">例如，如果你在美国，你可以联系["调查](https://www.fbi.gov/contact-us/field)局"本地现场办公室[、IC3 或](http://www.ic3.gov/complaint/default.aspx)[机密服务](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="14fc8-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="14fc8-160">向你国家/地区欺诈报告网站提交报告</span><span class="sxs-lookup"><span data-stu-id="14fc8-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="14fc8-161">欺诈报告网站提供有关如何防止和避免欺诈的信息。</span><span class="sxs-lookup"><span data-stu-id="14fc8-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="14fc8-162">它们还提供报告您是否遭受欺诈的机制。</span><span class="sxs-lookup"><span data-stu-id="14fc8-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="14fc8-163">澳大利亚 [：SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="14fc8-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="14fc8-164">加拿大： [加拿大反欺诈中心](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="14fc8-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="14fc8-165">法国 [：Agence nationale de la sécurité des systcurmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="14fc8-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="14fc8-166">德国 [：Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="14fc8-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="14fc8-167">爱尔兰 [：Garda Sí一一](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="14fc8-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="14fc8-168">新西兰： [消费者诈骗](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="14fc8-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="14fc8-169">英国： [行动欺诈](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="14fc8-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="14fc8-170">美国 [：On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="14fc8-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="14fc8-171">如果你的国家/地区未列出，请向当地或联邦执法机构询问。</span><span class="sxs-lookup"><span data-stu-id="14fc8-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="14fc8-172">将电子邮件提交到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="14fc8-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="14fc8-173">您可以使用多种方法之一报告包含勒索软件的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="14fc8-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="14fc8-174">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="14fc8-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14fc8-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14fc8-175">See also</span></span>

- [<span data-ttu-id="14fc8-176">勒索软件</span><span class="sxs-lookup"><span data-stu-id="14fc8-176">Ransomware</span></span>](/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="14fc8-177">勒索软件响应 - 是否付费？</span><span class="sxs-lookup"><span data-stu-id="14fc8-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="14fc8-178">Norsk 使用透明度响应勒索软件攻击</span><span class="sxs-lookup"><span data-stu-id="14fc8-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="14fc8-179">勒索软件检测和恢复 OneDrive 中的文件</span><span class="sxs-lookup"><span data-stu-id="14fc8-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="14fc8-180">Microsoft 安全智能报告</span><span class="sxs-lookup"><span data-stu-id="14fc8-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="14fc8-181">启用或禁用 Office 文件中宏</span><span class="sxs-lookup"><span data-stu-id="14fc8-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="14fc8-182">用于配置 EOP 和 Defender for Office 365 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="14fc8-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

- [<span data-ttu-id="14fc8-183">有价值的升级：Windows 10 上的下一代安全性证明可以抵御 2017 年勒索软件爆发</span><span class="sxs-lookup"><span data-stu-id="14fc8-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="14fc8-184">没有 mas，Samas：此勒索软件操作方式是什么？</span><span class="sxs-lookup"><span data-stu-id="14fc8-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="14fc8-185">锁定恶意软件，阻止恶意软件</span><span class="sxs-lookup"><span data-stu-id="14fc8-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="14fc8-186">MSRT 2016 年 7 月：Cerber 勒索软件</span><span class="sxs-lookup"><span data-stu-id="14fc8-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="14fc8-187">Cerberus-like Cerber 勒索软件三头</span><span class="sxs-lookup"><span data-stu-id="14fc8-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="14fc8-188">受 (Da Vinci) 影响的) 勒索软件</span><span class="sxs-lookup"><span data-stu-id="14fc8-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)