---
title: 从勒索软件攻击中恢复
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365 管理员可以了解如何从勒索软件攻击中进行恢复。
ms.openlocfilehash: 2f8e5f5deb18cadfaea7acc1cffe73abbc43010b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827829"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="d0bd6-103">从 Microsoft 365 中的勒索软件攻击中恢复</span><span class="sxs-lookup"><span data-stu-id="d0bd6-103">Recover from a ransomware attack in Microsoft 365</span></span>

<span data-ttu-id="d0bd6-104">即使你对组织采取全面预防措，你仍可以受到 [勒索软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 攻击。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="d0bd6-105">勒索软件的业务需要一定的业务，并验证了这一攻击。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="d0bd6-106">本主题中的步骤可为你提供最佳机会来恢复勒索软件加密的数据，并且有助于停止组织中感染的分布。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="d0bd6-107">在开始之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="d0bd6-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="d0bd6-108">无法保证支付勒索会返回对你的文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="d0bd6-109">事实上，支付勒索软件可使你成为更有机索软件的目标。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="d0bd6-110">如果你已支付，但能够成功恢复文件，而无需使用攻击者的解决方案，则应调用银行来查看他们是否会阻止该事务。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="d0bd6-111">我们还建议您如本主题后面所述，向法律强制、发布报告网站和 Microsoft 报告勒索软件攻击。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="d0bd6-112">务必快速响应攻击及其后果。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="d0bd6-113">您等待的时间就长，就是恢复受影响的数据的可能性就就就就是。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="d0bd6-114">步骤 1：验证备份</span><span class="sxs-lookup"><span data-stu-id="d0bd6-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="d0bd6-115">如果您具有脱机备份，则当您从环境中删除勒索软件负载或恶意软件解决方案**after** (预) 数据后，您可能需要还原加密数据。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="d0bd6-116">如果没有备份，或者备份也受勒索软件影响，则可跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="d0bd6-117">步骤 2：禁用 ActiveSync 和 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="d0bd6-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="d0bd6-118">此处的要点是阻止勒索软件对数据加密进行分段的分布。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="d0bd6-119">如果您要将某封电子邮件作为目标，则应临时禁用用户对邮箱的访问。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="d0bd6-120">Exchange ActiveSync用于移动设备同步设备与 Exchange Online 邮箱之间的数据。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="d0bd6-121">若要禁用邮箱的 ActiveSync，请参阅 ["如何在 Exchange Online Exchange ActiveSync用户"禁用此设置](https://support.microsoft.com/help/2795303)。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="d0bd6-122">若要禁用邮箱的其他类型的访问，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d0bd6-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="d0bd6-123">[为邮箱启用或禁用 MAPI。](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="d0bd6-124">对用户启用或禁用 POP3 或 IMAP4 访问</span><span class="sxs-lookup"><span data-stu-id="d0bd6-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="d0bd6-125">暂停 OneDrive 同步有助于防止云数据被潜在感染的设备进行更新。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="d0bd6-126">有关详细信息，请参阅"[如何在 OneDrive 中暂停和恢复同步"。](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="d0bd6-127">步骤 3：从受影响的设备中删除恶意软件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="d0bd6-128">在所有可配置的计算机和设备上使用最新更新运行完整的防病毒扫描，以检测和删除与勒索软件关联的负载。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="d0bd6-129">不要禁记同步数据的设备，或出于 (这些计算机和设备的映射网络驱动器的目标，也不要) 。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="d0bd6-130">可以使用旧 [Windows Defender (](https://www.microsoft.com/windows/comprehensive-security) 的旧版客户端 [) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="d0bd6-131">另外，可帮助你删除勒索软件或恶意软件的备用方法是[MSRT 软件 (工具) 。 ](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="d0bd6-132">如果这些选项不起作用，您可以[尝试尝试使用Windows Defender脱机](https://support.microsoft.com/help/17466)[，或解决与检测和删除恶意软件有关的问题](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="d0bd6-133">步骤 4：恢复已清除计算机或设备上的文件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="d0bd6-134">在你完成上一步骤以从你的环境中删除勒索软件负载 (这样会阻止勒索软件加密或删除文件) ; [你可以在](https://support.microsoft.com/help/17128) Windows 7 中使用 Windows 10 和 Windows 8.1 或 System Protection 中的文件历史记录来尝试恢复你的本地文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="d0bd6-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="d0bd6-135">**Notes**:</span></span>

- <span data-ttu-id="d0bd6-136">某些勒索软件还将加密或删除备份版本，因此无法使用文件历史记录或系统保护来还原文件。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="d0bd6-137">如果发生这种情况，需要在不受勒索软件或 OneDrive 影响的外部驱动器或设备上使用备份，如下一节所述。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="d0bd6-138">如果文件夹同步到 OneDrive，并且你未使用最新版本的 Windows，则与文件历史记录有一些限制。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="d0bd6-139">步骤 5：恢复 OneDrive for Business 中的文件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="d0bd6-140">OneDrive for Business 中的"文件还原"允许将整个 OneDrive 还原到过去 30 天的前一时点。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="d0bd6-141">有关详细信息，请参阅"[还原 OneDrive"。](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="d0bd6-142">步骤 6：恢复已删除的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="d0bd6-143">在少数情况下，勒索软件删除了所有电子邮件，你可能会恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="d0bd6-144">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d0bd6-144">For more information, see:</span></span>

- [<span data-ttu-id="d0bd6-145">恢复用户邮箱中的已删除邮件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="d0bd6-146">在 Outlook for Windows 中恢复已删除项目</span><span class="sxs-lookup"><span data-stu-id="d0bd6-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="d0bd6-147">步骤 7：重新启用 Exchange ActiveSync OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="d0bd6-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="d0bd6-148">在清理计算机和设备并恢复数据后，可重新启用之前在步骤 2 中禁用的 ActiveSync 和 OneDrive [同步](#step-2-disable-activesync-and-onedrive-sync)。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="d0bd6-149">步骤 8 (可选) ：针对特定文件扩展名阻止 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="d0bd6-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="d0bd6-150">恢复后，您可以防止 OneDrive for Business 客户端同步受此勒索软件影响的文件类型。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="d0bd6-151">有关详细信息，请参阅 [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="d0bd6-152">报告攻击</span><span class="sxs-lookup"><span data-stu-id="d0bd6-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="d0bd6-153">联系人法律强制实施</span><span class="sxs-lookup"><span data-stu-id="d0bd6-153">Contact law enforcement</span></span>

<span data-ttu-id="d0bd6-154">您应与当地或法国法律机构联系。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="d0bd6-155">例如，如果你在美国，可以联系 [FBI 本地字段办](https://www.fbi.gov/contact-us/field)公局 [IC3](http://www.ic3.gov/complaint/default.aspx) [或机业服务](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="d0bd6-156">向您所在国家/地区的头报告网站提交报告</span><span class="sxs-lookup"><span data-stu-id="d0bd6-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="d0bd6-157">上标报告网站提供有关如何防护和避免上标的信息。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="d0bd6-158">如果是外围环境的受损人，则它们还提供报告的机制。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="d0bd6-159">澳大利亚 [：SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="d0bd6-160">加拿大 [：加拿大反片 Centre](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="d0bd6-161">法国 [：Agence nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="d0bd6-162">德国 [：Bundesamt fár Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="d0bd6-163">[Ireland：Garda Sáochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="d0bd6-164">新西亚： [消费者信标](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="d0bd6-165">英国： [操作 Fraud](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="d0bd6-166">美国：在线 [防护联机](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="d0bd6-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="d0bd6-167">如果未列出你所在国家/地区，请询问当地或分部法律机构。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="d0bd6-168">将电子邮件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0bd6-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="d0bd6-169">您可以使用多种方法之一报告包含勒索软件的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="d0bd6-170">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bd6-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0bd6-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0bd6-171">See also</span></span>

- [<span data-ttu-id="d0bd6-172">勒索软件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="d0bd6-173">勒索软件响应 — 支付付费用？</span><span class="sxs-lookup"><span data-stu-id="d0bd6-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="d0bd6-174">Norsk Hydro 响应透明度的勒索软件攻击</span><span class="sxs-lookup"><span data-stu-id="d0bd6-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="d0bd6-175">在 OneDrive 中进行勒索软件检测和恢复文件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="d0bd6-176">Microsoft 安全智能报告</span><span class="sxs-lookup"><span data-stu-id="d0bd6-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="d0bd6-177">启用或禁用 Office 文件中的宏</span><span class="sxs-lookup"><span data-stu-id="d0bd6-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="d0bd6-178">EOP 和 Office 365 ATP 安全的建议设置</span><span class="sxs-lookup"><span data-stu-id="d0bd6-178">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="d0bd6-179">值得的升级：Windows 10 上的下一代安全在 2017 年证明复原可以抵御勒索软件发感</span><span class="sxs-lookup"><span data-stu-id="d0bd6-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="d0bd6-180">无 Mas，Samas：此勒索软件操作数中的内容是什么？</span><span class="sxs-lookup"><span data-stu-id="d0bd6-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="d0bd6-181">锁定恶意软件，蓝牙以避免</span><span class="sxs-lookup"><span data-stu-id="d0bd6-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="d0bd6-182">MSRT 2016：Cerber 勒索软件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="d0bd6-183">类似于 Cerberus 的 Cerberus 的三个耳机</span><span class="sxs-lookup"><span data-stu-id="d0bd6-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="d0bd6-184">受 (日感大国 (的) 件勒索软件</span><span class="sxs-lookup"><span data-stu-id="d0bd6-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
