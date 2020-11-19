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
- m365initiative-m365-defender
description: Microsoft 365 管理员可以了解如何从勒索软件攻击中恢复。
ms.openlocfilehash: a1369e64821902e3c2a3061acd1bbebeeb6c85ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357093"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="51c12-103">在 Microsoft 365 中从勒索软件攻击中恢复</span><span class="sxs-lookup"><span data-stu-id="51c12-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="51c12-104">即使您在保护组织时采取了任何预防措施，仍可成为 [勒索软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 攻击的牺牲品。</span><span class="sxs-lookup"><span data-stu-id="51c12-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="51c12-105">勒索软件是大型企业，攻击非常复杂。</span><span class="sxs-lookup"><span data-stu-id="51c12-105">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="51c12-106">本文中的步骤将为您提供恢复数据和停止感染的内部传播的最佳机会。</span><span class="sxs-lookup"><span data-stu-id="51c12-106">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="51c12-107">在开始之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="51c12-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="51c12-108">不能保证付款勒索将返回对您的文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="51c12-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="51c12-109">实际上，支付勒索可以使您成为更多勒索软件的目标。</span><span class="sxs-lookup"><span data-stu-id="51c12-109">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="51c12-110">如果你已支付，但在未使用攻击者的解决方案的情况下进行了恢复，请联系你的银行以了解它们是否可以阻止事务。</span><span class="sxs-lookup"><span data-stu-id="51c12-110">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="51c12-111">此外，我们还建议您将勒索软件攻击报告给执法部门、诈骗报告网站和 Microsoft，如本文后面所述。</span><span class="sxs-lookup"><span data-stu-id="51c12-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="51c12-112">快速响应攻击及其后果非常重要。</span><span class="sxs-lookup"><span data-stu-id="51c12-112">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="51c12-113">等待时间越长，可以恢复受影响数据的可能性就越小。</span><span class="sxs-lookup"><span data-stu-id="51c12-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="51c12-114">步骤1：验证备份</span><span class="sxs-lookup"><span data-stu-id="51c12-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="51c12-115">如果您具有脱机备份，则在从您的环境中删除勒索软件有效负载 (恶意软件) **后** ，可能会还原加密的数据。</span><span class="sxs-lookup"><span data-stu-id="51c12-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="51c12-116">如果你没有备份，或者你的备份也受到勒索软件的影响，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="51c12-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="51c12-117">步骤2：禁用 Exchange ActiveSync 和 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="51c12-117">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="51c12-118">此处的关键点是停止勒索软件的数据加密传播。</span><span class="sxs-lookup"><span data-stu-id="51c12-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="51c12-119">如果您怀疑电子邮件为勒索软件加密的目标，请暂时禁用用户对邮箱的访问。</span><span class="sxs-lookup"><span data-stu-id="51c12-119">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="51c12-120">Exchange ActiveSync 在设备和 Exchange Online 邮箱之间同步数据。</span><span class="sxs-lookup"><span data-stu-id="51c12-120">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="51c12-121">若要禁用邮箱的 Exchange ActiveSync，请参阅 [如何在 Exchange Online 中禁用用户的 Exchange activesync](https://support.microsoft.com/help/2795303)。</span><span class="sxs-lookup"><span data-stu-id="51c12-121">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="51c12-122">若要禁用对邮箱的其他类型的访问，请参阅：</span><span class="sxs-lookup"><span data-stu-id="51c12-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="51c12-123">[启用或禁用邮箱的 MAPI](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。</span><span class="sxs-lookup"><span data-stu-id="51c12-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="51c12-124">对用户启用或禁用 POP3 或 IMAP4 访问</span><span class="sxs-lookup"><span data-stu-id="51c12-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="51c12-125">暂停 OneDrive 同步将有助于防止可能受感染的设备更新你的云数据。</span><span class="sxs-lookup"><span data-stu-id="51c12-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="51c12-126">有关详细信息，请参阅 [如何暂停和恢复 OneDrive 中的同步](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="51c12-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="51c12-127">步骤3：从受影响的设备中删除恶意软件</span><span class="sxs-lookup"><span data-stu-id="51c12-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="51c12-128">在所有可疑计算机和设备上运行完全的当前防病毒扫描，以检测和删除与勒索软件相关联的有效负载。</span><span class="sxs-lookup"><span data-stu-id="51c12-128">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="51c12-129">请勿忘记扫描正在同步数据的设备，或映射的网络驱动器的目标。</span><span class="sxs-lookup"><span data-stu-id="51c12-129">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="51c12-130">您可以将 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 或 (用于旧客户端) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。</span><span class="sxs-lookup"><span data-stu-id="51c12-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="51c12-131">另一种方法也可帮助您删除勒索软件或恶意软件，这是 [ (MSRT) 的恶意软件删除工具 ](https://www.microsoft.com/download/details.aspx?id=9905)。</span><span class="sxs-lookup"><span data-stu-id="51c12-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="51c12-132">如果这些选项不起作用，可以尝试让 [Windows Defender 脱机](https://support.microsoft.com/help/17466) 或 [解决检测和删除恶意软件的问题](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="51c12-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="51c12-133">步骤4：在已清理的计算机或设备上恢复文件</span><span class="sxs-lookup"><span data-stu-id="51c12-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="51c12-134">在完成上一步以从环境中删除勒索软件负载时 (这将阻止勒索软件加密或删除文件) ，可以使用 windows 10 中的 Windows 10 和 Windows 8.1 中的 [文件历史记录](https://support.microsoft.com/help/17128) 或 windows 7 中的系统保护尝试恢复您的本地文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="51c12-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="51c12-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="51c12-135">**Notes**:</span></span>

- <span data-ttu-id="51c12-136">有些勒索软件还将加密或删除备份版本，因此不能使用文件历史记录或系统保护来还原文件。</span><span class="sxs-lookup"><span data-stu-id="51c12-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="51c12-137">如果发生这种情况，您需要在不受勒索软件或 OneDrive 影响的外部驱动器或设备上使用备份，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="51c12-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="51c12-138">如果将文件夹同步到 OneDrive，并且未使用最新版本的 Windows，则可能会有一些使用文件历史记录的限制。</span><span class="sxs-lookup"><span data-stu-id="51c12-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="51c12-139">步骤5：在 OneDrive for Business 中恢复文件</span><span class="sxs-lookup"><span data-stu-id="51c12-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="51c12-140">通过 OneDrive for Business 还原文件，可以在过去的30天内将整个 OneDrive 还原到以前的时间点。</span><span class="sxs-lookup"><span data-stu-id="51c12-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="51c12-141">有关详细信息，请参阅 [还原 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。</span><span class="sxs-lookup"><span data-stu-id="51c12-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="51c12-142">步骤6：恢复已删除的电子邮件</span><span class="sxs-lookup"><span data-stu-id="51c12-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="51c12-143">在少数情况下，勒索软件删除了所有电子邮件，您可能可以恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="51c12-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="51c12-144">有关更多信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="51c12-144">For more information, see:</span></span>

- [<span data-ttu-id="51c12-145">恢复用户邮箱中的已删除邮件</span><span class="sxs-lookup"><span data-stu-id="51c12-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="51c12-146">在 Outlook for Windows 中恢复已删除项目</span><span class="sxs-lookup"><span data-stu-id="51c12-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="51c12-147">步骤7：重新启用 Exchange ActiveSync 和 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="51c12-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="51c12-148">在清理了计算机和设备并恢复了数据之后，可以重新启用之前在 [步骤 2](#step-2-disable-exchange-activesync-and-onedrive-sync)中禁用的 Exchange ActiveSync 和 OneDrive 同步。</span><span class="sxs-lookup"><span data-stu-id="51c12-148">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="51c12-149">第8步 (可选) ：阻止特定文件扩展名的 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="51c12-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="51c12-150">恢复后，可以阻止 OneDrive for Business 客户端同步受此勒索软件影响的文件类型。</span><span class="sxs-lookup"><span data-stu-id="51c12-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="51c12-151">有关详细信息，请参阅 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="51c12-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="51c12-152">报告攻击</span><span class="sxs-lookup"><span data-stu-id="51c12-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="51c12-153">联系执法部门</span><span class="sxs-lookup"><span data-stu-id="51c12-153">Contact law enforcement</span></span>

<span data-ttu-id="51c12-154">您应联系当地或联邦法律实施机构。</span><span class="sxs-lookup"><span data-stu-id="51c12-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="51c12-155">例如，如果你处于美国，你可以联系 [FBI local field](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) 或 [Secret Service](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="51c12-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="51c12-156">将报告提交到你的国家/地区的骗局报告网站</span><span class="sxs-lookup"><span data-stu-id="51c12-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="51c12-157">诈骗报告网站提供有关如何阻止和避免诈骗的信息。</span><span class="sxs-lookup"><span data-stu-id="51c12-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="51c12-158">它们还提供了在您受到诈骗攻击时报告的机制。</span><span class="sxs-lookup"><span data-stu-id="51c12-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="51c12-159">澳大利亚： [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="51c12-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="51c12-160">加拿大： [加拿大反欺诈中心](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="51c12-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="51c12-161">法国： [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="51c12-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="51c12-162">德国： [Bundesamt Für Sicherheit in Der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="51c12-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="51c12-163">爱尔兰： [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="51c12-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="51c12-164">新西兰： [消费者事务诈骗](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="51c12-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="51c12-165">英国： [操作欺诈](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="51c12-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="51c12-166">美国：[在保护联机](http://www.onguardonline.gov/)状态</span><span class="sxs-lookup"><span data-stu-id="51c12-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="51c12-167">如果未列出你的国家/地区，请咨询当地或联邦法律实施机构。</span><span class="sxs-lookup"><span data-stu-id="51c12-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="51c12-168">将电子邮件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="51c12-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="51c12-169">您可以使用几种方法之一报告包含勒索软件的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="51c12-169">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="51c12-170">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="51c12-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51c12-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51c12-171">See also</span></span>

- [<span data-ttu-id="51c12-172">软件</span><span class="sxs-lookup"><span data-stu-id="51c12-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="51c12-173">勒索软件响应—要支付还是不支付？</span><span class="sxs-lookup"><span data-stu-id="51c12-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="51c12-174">Norsk Hydro 使用透明度响应勒索软件攻击</span><span class="sxs-lookup"><span data-stu-id="51c12-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="51c12-175">你的 OneDrive 中的勒索软件检测和恢复文件</span><span class="sxs-lookup"><span data-stu-id="51c12-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="51c12-176">Microsoft 安全研究报告</span><span class="sxs-lookup"><span data-stu-id="51c12-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="51c12-177">启用或禁用 Office 文件中的宏</span><span class="sxs-lookup"><span data-stu-id="51c12-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="51c12-178">EOP 和 Microsoft Defender for Office 365 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="51c12-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="51c12-179">值得升级： Windows 10 上的下一代安全性证明可在2017中对勒索软件发作进行恢复</span><span class="sxs-lookup"><span data-stu-id="51c12-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="51c12-180">没有 ma，Samas：此勒索软件的 modus operandi 中有什么？</span><span class="sxs-lookup"><span data-stu-id="51c12-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="51c12-181">Locky 恶意软件，幸运的是要避免它</span><span class="sxs-lookup"><span data-stu-id="51c12-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="51c12-182">MSRT 2016 年7月： Cerber 勒索软件</span><span class="sxs-lookup"><span data-stu-id="51c12-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="51c12-183">Cerberus Cerber 勒索软件的三个头部</span><span class="sxs-lookup"><span data-stu-id="51c12-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="51c12-184"> () Da Vinci 代码影响的 Troldesh 勒索软件</span><span class="sxs-lookup"><span data-stu-id="51c12-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
