---
title: 从勒索软件攻击中恢复
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365 管理员可以了解如何从勒索软件攻击中恢复。
ms.openlocfilehash: aa606ea3bf3f549645fe26a4aa95066568132243
ms.sourcegitcommit: 72983702a42552a29228d387bb279e8ff2ab59b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "42640014"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a><span data-ttu-id="c7c11-103">在 Office 365 中恢复勒索软件攻击</span><span class="sxs-lookup"><span data-stu-id="c7c11-103">Recover from a ransomware attack in Office 365</span></span>

<span data-ttu-id="c7c11-104">即使您尽一切预防措施来保护您的 Office 365 组织，仍可以将受害者的攻击作为[勒索软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)攻击。</span><span class="sxs-lookup"><span data-stu-id="c7c11-104">Even if you take every precaution to protect your Office 365 organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="c7c11-105">勒索软件是大型企业，攻击的验证非常复杂。</span><span class="sxs-lookup"><span data-stu-id="c7c11-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="c7c11-106">本主题中的步骤将为您提供恢复由勒索软件加密的数据的最佳机会，并帮助停止在 Office 365 组织中进行感染的传播。</span><span class="sxs-lookup"><span data-stu-id="c7c11-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your Office 365 organization.</span></span> <span data-ttu-id="c7c11-107">在开始之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="c7c11-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="c7c11-108">不能保证付款勒索将返回对您的文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c7c11-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="c7c11-109">实际上，支付勒索可以使您成为更多勒索软件的目标。</span><span class="sxs-lookup"><span data-stu-id="c7c11-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="c7c11-110">如果你已支付，但你可以成功恢复文件，而无需使用攻击者的解决方案，则应致电你的银行以了解它们是否可以阻止事务。</span><span class="sxs-lookup"><span data-stu-id="c7c11-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="c7c11-111">此外，我们还建议您将勒索软件攻击报告给执法部门、诈骗报告网站和 Microsoft，如本主题后面所述。</span><span class="sxs-lookup"><span data-stu-id="c7c11-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="c7c11-112">快速响应攻击及其后果非常重要。</span><span class="sxs-lookup"><span data-stu-id="c7c11-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="c7c11-113">等待时间越长，可以恢复受影响数据的可能性就越小。</span><span class="sxs-lookup"><span data-stu-id="c7c11-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="c7c11-114">步骤1：验证备份</span><span class="sxs-lookup"><span data-stu-id="c7c11-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="c7c11-115">如果您具有脱机备份，则在从环境中删除勒索软件有效负载（恶意软件）**后**，可能会还原加密的数据。</span><span class="sxs-lookup"><span data-stu-id="c7c11-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="c7c11-116">如果你没有备份，或者你的备份也受到勒索软件的影响，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="c7c11-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="c7c11-117">步骤2：禁用 ActiveSync 和 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="c7c11-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="c7c11-118">此处的关键点是停止勒索软件的数据加密传播。</span><span class="sxs-lookup"><span data-stu-id="c7c11-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="c7c11-119">如果您怀疑电子邮件是目标，应暂时禁用用户对邮箱的访问。</span><span class="sxs-lookup"><span data-stu-id="c7c11-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="c7c11-120">移动设备使用 Exchange ActiveSync 在设备与 Exchange Online 邮箱之间同步数据。</span><span class="sxs-lookup"><span data-stu-id="c7c11-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="c7c11-121">若要禁用邮箱的 ActiveSync，请参阅 how [to Disable Exchange ActiveSync For Office 365 中的用户](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="c7c11-122">若要禁用对邮箱的其他类型的访问，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c7c11-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="c7c11-123">[启用或禁用邮箱的 MAPI](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="c7c11-124">对用户启用或禁用 POP3 或 IMAP4 访问</span><span class="sxs-lookup"><span data-stu-id="c7c11-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="c7c11-125">暂停 OneDrive 同步将有助于防止可能受感染的设备更新你的云数据。</span><span class="sxs-lookup"><span data-stu-id="c7c11-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="c7c11-126">有关详细信息，请参阅[如何暂停和恢复 OneDrive 中的同步](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="c7c11-127">步骤3：从受影响的设备中删除恶意软件</span><span class="sxs-lookup"><span data-stu-id="c7c11-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="c7c11-128">在所有可疑计算机和设备上运行完整的防病毒扫描，以检测和删除与勒索软件相关联的有效负载。</span><span class="sxs-lookup"><span data-stu-id="c7c11-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="c7c11-129">不要忘记正在同步数据的设备，或映射的网络驱动器的目标（也需要扫描这些计算机和设备）。</span><span class="sxs-lookup"><span data-stu-id="c7c11-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="c7c11-130">您可以使用[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)或（针对较旧版本的客户端） [Microsoft 安全重点](https://www.microsoft.com/download/details.aspx?id=5201)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="c7c11-131">此外，还可帮助您删除勒索软件或恶意软件的另一种方法是[恶意软件删除工具（MSRT）](https://www.microsoft.com/download/details.aspx?id=9905)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="c7c11-132">如果这些选项不起作用，可以尝试让[Windows Defender 脱机](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc)或[解决检测和删除恶意软件的问题](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="c7c11-133">步骤4：在已清理的计算机或设备上恢复文件</span><span class="sxs-lookup"><span data-stu-id="c7c11-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="c7c11-134">完成上一步以从环境中删除勒索软件负载（这将阻止勒索软件加密或删除文件）后，可以使用 windows 10 中的[文件历史记录](https://support.microsoft.com/help/17128/windows-8-file-history)或 windows 7 中的 windows 8.1 或系统保护尝试恢复您的本地文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7c11-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="c7c11-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="c7c11-135">**Notes**:</span></span>

- <span data-ttu-id="c7c11-136">有些勒索软件还将加密或删除备份版本，因此不能使用文件历史记录或系统保护来还原文件。</span><span class="sxs-lookup"><span data-stu-id="c7c11-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="c7c11-137">如果发生这种情况，您需要在不受勒索软件或 OneDrive 影响的外部驱动器或设备上使用备份，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="c7c11-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="c7c11-138">如果将文件夹同步到 OneDrive，并且未使用最新版本的 Windows，则可能会有一些使用文件历史记录的限制。</span><span class="sxs-lookup"><span data-stu-id="c7c11-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="c7c11-139">步骤5：在 OneDrive for Business 中恢复文件</span><span class="sxs-lookup"><span data-stu-id="c7c11-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="c7c11-140">通过 OneDrive for Business 还原文件，可以在过去的30天内将整个 OneDrive 还原到以前的时间点。</span><span class="sxs-lookup"><span data-stu-id="c7c11-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="c7c11-141">有关详细信息，请参阅[还原 OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-141">For more information, see [Restore your OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="c7c11-142">步骤6：恢复已删除的电子邮件</span><span class="sxs-lookup"><span data-stu-id="c7c11-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="c7c11-143">在少数情况下，勒索软件删除了所有电子邮件，您可能可以恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="c7c11-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="c7c11-144">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c7c11-144">For more information, see:</span></span>

- [<span data-ttu-id="c7c11-145">恢复用户邮箱中的已删除邮件</span><span class="sxs-lookup"><span data-stu-id="c7c11-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="c7c11-146">在 Outlook for Windows 中恢复已删除项目</span><span class="sxs-lookup"><span data-stu-id="c7c11-146">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="c7c11-147">步骤7：重新启用 Exchange ActiveSync 和 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="c7c11-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="c7c11-148">在清理了计算机和设备并恢复了数据之后，可以重新启用您之前在[步骤 2](#step-2-disable-activesync-and-onedrive-sync)中禁用的 ActiveSync 和 OneDrive 同步。</span><span class="sxs-lookup"><span data-stu-id="c7c11-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="c7c11-149">步骤8（可选）：阻止针对特定文件扩展名的 OneDrive 同步</span><span class="sxs-lookup"><span data-stu-id="c7c11-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="c7c11-150">恢复后，可以阻止 OneDrive for Business 客户端同步受此勒索软件影响的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c7c11-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="c7c11-151">有关详细信息，请参阅[get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="c7c11-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="c7c11-152">报告攻击</span><span class="sxs-lookup"><span data-stu-id="c7c11-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="c7c11-153">联系执法部门</span><span class="sxs-lookup"><span data-stu-id="c7c11-153">Contact law enforcement</span></span>

<span data-ttu-id="c7c11-154">您应联系当地或联邦法律实施机构。</span><span class="sxs-lookup"><span data-stu-id="c7c11-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="c7c11-155">例如，如果你处于美国，你可以联系[FBI local field](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx)或[Secret Service](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="c7c11-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="c7c11-156">将报告提交到你的国家/地区的骗局报告网站</span><span class="sxs-lookup"><span data-stu-id="c7c11-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="c7c11-157">诈骗报告网站提供有关如何阻止和避免诈骗的信息。</span><span class="sxs-lookup"><span data-stu-id="c7c11-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="c7c11-158">它们还提供了在您受到诈骗攻击时报告的机制。</span><span class="sxs-lookup"><span data-stu-id="c7c11-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="c7c11-159">澳大利亚： [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="c7c11-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="c7c11-160">加拿大：[加拿大反欺诈中心](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="c7c11-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="c7c11-161">法国： [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="c7c11-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="c7c11-162">德国： [Bundesamt Für Sicherheit in Der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="c7c11-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="c7c11-163">爱尔兰： [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="c7c11-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="c7c11-164">新西兰：[消费者事务诈骗](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="c7c11-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="c7c11-165">英国：[操作欺诈](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="c7c11-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="c7c11-166">美国：[在保护联机](http://www.onguardonline.gov/)状态</span><span class="sxs-lookup"><span data-stu-id="c7c11-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="c7c11-167">如果未列出你的国家/地区，请咨询当地或联邦法律实施机构。</span><span class="sxs-lookup"><span data-stu-id="c7c11-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="c7c11-168">将电子邮件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c7c11-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="c7c11-169">您可以按照将[垃圾邮件、非垃圾邮件和网络钓鱼诈骗消息中的说明与 Microsoft 进行分析，](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)报告包含勒索软件的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="c7c11-169">You can report phishing message that contain ransomware by following the instructions in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7c11-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7c11-170">See also</span></span>

- [<span data-ttu-id="c7c11-171">软件</span><span class="sxs-lookup"><span data-stu-id="c7c11-171">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="c7c11-172">勒索软件响应—要支付还是不支付？</span><span class="sxs-lookup"><span data-stu-id="c7c11-172">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="c7c11-173">Norsk Hydro 使用透明度响应勒索软件攻击</span><span class="sxs-lookup"><span data-stu-id="c7c11-173">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="c7c11-174">你的 OneDrive 中的勒索软件检测和恢复文件</span><span class="sxs-lookup"><span data-stu-id="c7c11-174">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="c7c11-175">Microsoft 安全研究报告</span><span class="sxs-lookup"><span data-stu-id="c7c11-175">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="c7c11-176">启用或禁用 Office 文件中的宏</span><span class="sxs-lookup"><span data-stu-id="c7c11-176">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="c7c11-177">EOP 和 Office 365 ATP 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="c7c11-177">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="c7c11-178">值得升级： Windows 10 上的下一代安全性证明可在2017中对勒索软件发作进行恢复</span><span class="sxs-lookup"><span data-stu-id="c7c11-178">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="c7c11-179">没有 ma，Samas：此勒索软件的 modus operandi 中有什么？</span><span class="sxs-lookup"><span data-stu-id="c7c11-179">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="c7c11-180">Locky 恶意软件，幸运的是要避免它</span><span class="sxs-lookup"><span data-stu-id="c7c11-180">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="c7c11-181">MSRT 2016 年7月： Cerber 勒索软件</span><span class="sxs-lookup"><span data-stu-id="c7c11-181">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="c7c11-182">Cerberus Cerber 勒索软件的三个头部</span><span class="sxs-lookup"><span data-stu-id="c7c11-182">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="c7c11-183">Troldesh （即，） Da Vinci 代码影响的勒索软件</span><span class="sxs-lookup"><span data-stu-id="c7c11-183">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
