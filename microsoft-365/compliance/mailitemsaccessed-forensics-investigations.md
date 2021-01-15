---
title: 使用“高级审核”来调查被盗用的帐户
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用 MailItemsAccessed 邮箱审核操作对被盗用的用户账户进行司法鉴定调查。
ms.openlocfilehash: 15379a5c24ee222cf097e94d46dc46de0e385820
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868000"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a><span data-ttu-id="7a713-103">使用“高级审核”来调查被盗用的帐户</span><span class="sxs-lookup"><span data-stu-id="7a713-103">Use Advanced Audit to investigate compromised accounts</span></span>

<span data-ttu-id="7a713-104">被盗用的用户账户（也称为“*账户接管*”）是攻击的一种类型，攻击者获取用户账户的访问权限并作为用户操作。</span><span class="sxs-lookup"><span data-stu-id="7a713-104">A compromised user account (also called an *account takeover*) is a type of attack when an attacker gains access to a user account and operates as the user.</span></span> <span data-ttu-id="7a713-105">这些类型的攻击造成的损害有时比攻击者所需要的更大。</span><span class="sxs-lookup"><span data-stu-id="7a713-105">These types of attacks sometimes cause more damage than the attacker may have intended.</span></span> <span data-ttu-id="7a713-106">调查被盗电子邮件账户时，必须假设泄露的邮件数据要比通过跟踪攻击者实际存在所指示的数量要多。</span><span class="sxs-lookup"><span data-stu-id="7a713-106">When investigating compromised email accounts, you have to assume that more mail data was compromised than may be indicated by tracing the attacker's actual presence.</span></span> <span data-ttu-id="7a713-107">根据电子邮件中的数据类型，需要假定敏感信息被盗用或面临着监管罚款，除非能够证明敏感信息未泄露。</span><span class="sxs-lookup"><span data-stu-id="7a713-107">Depending on the type of data in email messages, you have to assume that sensitive information was compromised or face regulatory fines unless you can prove that sensitive information wasn't exposed.</span></span> <span data-ttu-id="7a713-108">例如，如果有证据表明患者健康信息（PHI）被公开，受 HIPAA 监管的组织面临巨额罚款。</span><span class="sxs-lookup"><span data-stu-id="7a713-108">For example, HIPAA-regulated organizations face significant fines if there is evidence that patient health information (PHI) was exposed.</span></span> <span data-ttu-id="7a713-109">在这些情况中，攻击者很可能对患者健康信息感兴趣，但是组织仍然必须汇报数据泄漏，除非他们提供相应证明。</span><span class="sxs-lookup"><span data-stu-id="7a713-109">In these cases, attackers are unlikely to be interested in PHI, but organizations still must report data breaches unless they can prove otherwise.</span></span>

<span data-ttu-id="7a713-110">为帮助调查被盗的电子邮件账户，我们现在通过 *MailItemsAccessed* 邮箱审核活动审核由邮件协议和客户端进行的邮件数据存取。</span><span class="sxs-lookup"><span data-stu-id="7a713-110">To help you with investigating compromise email accounts, we're now auditing accesses of mail data by mail protocols and clients with the *MailItemsAccessed* mailbox auditing action.</span></span> <span data-ttu-id="7a713-111">此新审核的操作将可帮助调查人员更好地了解电子邮件数据泄露，并有助于确定可能被盗取指定邮件项的泄漏范围。</span><span class="sxs-lookup"><span data-stu-id="7a713-111">This new audited action will help investigators better understand email data breaches and help you identify the scope of compromises to specific mail items that may been compromised.</span></span> <span data-ttu-id="7a713-112">使用此新审核活动的目标是司法见证可防御性，以有助于断定特定的邮件数据未被盗取。</span><span class="sxs-lookup"><span data-stu-id="7a713-112">The goal of using this new auditing action is forensics defensibility to help assert that a specific piece of mail data was not compromised.</span></span> <span data-ttu-id="7a713-113">如果攻击者获得了对特定邮件的访问权限，Exchange Online 将审核该事件，即使没有迹象表明该邮件项已被实际阅读。</span><span class="sxs-lookup"><span data-stu-id="7a713-113">If an attacker gained access to a specific piece of mail, Exchange Online audits the event even though there is no indication that the mail item was actually read.</span></span>

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a><span data-ttu-id="7a713-114">MailItemsAccessed 邮箱审核操作</span><span class="sxs-lookup"><span data-stu-id="7a713-114">The MailItemsAccessed mailbox auditing action</span></span>

<span data-ttu-id="7a713-115">新的 MailItemsAccessed 操作是新“[高级审核](advanced-audit.md)”功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="7a713-115">The new MailItemsAccessed action is part of the new [Advanced Audit](advanced-audit.md) functionality.</span></span> <span data-ttu-id="7a713-116">它是“[Exchange 邮箱审核](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions)”的一部分，并默认为分配了 Office 365 或 Microsoft 365 E5 许可证的用户或拥有 Microsoft 365 E5 合规加载项订阅的组织启用。</span><span class="sxs-lookup"><span data-stu-id="7a713-116">It's part of [Exchange mailbox auditing](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions) and is enabled by default for users that are assigned an Office 365 or Microsoft 365 E5 license or for organizations with a Microsoft 365 E5 Compliance add-on subscription.</span></span>

<span data-ttu-id="7a713-117">MailItemsAccessed 邮箱审核操作包含所有邮件协议：POP、IMAP、 MAPI、EWS、Exchange ActiveSync 和 REST。</span><span class="sxs-lookup"><span data-stu-id="7a713-117">The MailItemsAccessed mailbox auditing action covers all mail protocols: POP, IMAP, MAPI, EWS, Exchange ActiveSync, and REST.</span></span> <span data-ttu-id="7a713-118">还包含了两种存取邮件的类型：*同步* 和 *绑定*。</span><span class="sxs-lookup"><span data-stu-id="7a713-118">It also covers both types of accessing mail: *sync* and *bind*.</span></span>

### <a name="auditing-sync-access"></a><span data-ttu-id="7a713-119">审核同步访问权限</span><span class="sxs-lookup"><span data-stu-id="7a713-119">Auditing sync access</span></span>

<span data-ttu-id="7a713-120">仅当邮箱由适用于 Windows 或 Mac 的桌面版 Outlook 客户端存取时，才记录同步操作。</span><span class="sxs-lookup"><span data-stu-id="7a713-120">Sync operations are only recorded when a mailbox is accessed by a desktop version of the Outlook client for Windows or Mac.</span></span> <span data-ttu-id="7a713-121">同步操作期间，这些客户端通常从云端下载大型邮件项至本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7a713-121">During the sync operation, these clients typically download a large set of mail items from the cloud to a local computer.</span></span> <span data-ttu-id="7a713-122">同步操作的审核量非常大。</span><span class="sxs-lookup"><span data-stu-id="7a713-122">The audit volume for sync operations is huge.</span></span> <span data-ttu-id="7a713-123">因此我们取代生成同步的各邮件项的审核记录，我们只针对含有被同步项的邮件文件夹生成审核事件。</span><span class="sxs-lookup"><span data-stu-id="7a713-123">So, instead of generating an audit record for each mail item that's synched, we just generate an audit event for the mail folder containing items that were synched.</span></span> <span data-ttu-id="7a713-124">这假设已同步文件夹中的 *所有* 邮件项已被盗用。</span><span class="sxs-lookup"><span data-stu-id="7a713-124">This makes the assumption that *all* mail items in the synched folder have been compromised.</span></span> <span data-ttu-id="7a713-125">访问权限类型会记录在审核记录的 OperationProperties 字段中。</span><span class="sxs-lookup"><span data-stu-id="7a713-125">The access type is recorded in the OperationProperties field of the audit record.</span></span> 

<span data-ttu-id="7a713-126">参见“[使用 MailItemsAccessed 审核记录进行司法鉴定调查](#use-mailitemsaccessed-audit-records-for-forensic-investigations)”一节的第 2 步了解在审核记录中显示同步访问权限的示例。</span><span class="sxs-lookup"><span data-stu-id="7a713-126">See step 2 in the [Use MailItemsAccessed audit records for forensic investigations](#use-mailitemsaccessed-audit-records-for-forensic-investigations) section for an example of displaying the sync access type in an audit record.</span></span>

### <a name="auditing-bind-access"></a><span data-ttu-id="7a713-127">审核绑定访问权限</span><span class="sxs-lookup"><span data-stu-id="7a713-127">Auditing bind access</span></span>

<span data-ttu-id="7a713-128">绑定操作是对电子邮件所进行的一种单独访问。</span><span class="sxs-lookup"><span data-stu-id="7a713-128">A bind operation is an individual access to an email message.</span></span> <span data-ttu-id="7a713-129">对于绑定访问权限，单独邮件的 InternetMessageId 将记录在审核记录中。</span><span class="sxs-lookup"><span data-stu-id="7a713-129">For bind access, the InternetMessageId of individual messages will be recorded in the audit record.</span></span> <span data-ttu-id="7a713-130">MailItemsAccessed 审核操作记录绑定操作并随后聚合至单独的审核记录中。</span><span class="sxs-lookup"><span data-stu-id="7a713-130">The MailItemsAccessed audit action records bind operations and then aggregates into a single audit record.</span></span> <span data-ttu-id="7a713-131">2分钟间隔内发生的所有绑定操作都聚合在 AuditData 属性内文件夹字段中的一个单独审核记录内。</span><span class="sxs-lookup"><span data-stu-id="7a713-131">All bind operations that occur within a 2-minute interval are aggregated in a single audit record in the Folders field within the AuditData property.</span></span> <span data-ttu-id="7a713-132">所访问的每封邮件都由其 InternetMessageId 标识。</span><span class="sxs-lookup"><span data-stu-id="7a713-132">Each message that was accessed is identified by its InternetMessageId.</span></span> <span data-ttu-id="7a713-133">聚合在记录中的绑定操作数将在 AuditData 属性的 OperationCount 字段中显示。</span><span class="sxs-lookup"><span data-stu-id="7a713-133">The number of bind operations that were aggregated in the record is displayed in the OperationCount field in the AuditData property.</span></span>

<span data-ttu-id="7a713-134">参见“[使用 MailItemsAccessed 审核记录进行司法鉴定调查](#use-mailitemsaccessed-audit-records-for-forensic-investigations)”一节的第 4 步了解在审核记录中显示绑定访问权限的示例。</span><span class="sxs-lookup"><span data-stu-id="7a713-134">See step 4 in the [Use MailItemsAccessed audit records for forensic investigations](#use-mailitemsaccessed-audit-records-for-forensic-investigations) section for an example of displaying the bind access type in an audit record.</span></span>

### <a name="throttling-of-mailitemsaccessed-audit-records"></a><span data-ttu-id="7a713-135">MailItemsAccessed 审核记录的限制</span><span class="sxs-lookup"><span data-stu-id="7a713-135">Throttling of MailItemsAccessed audit records</span></span>

<span data-ttu-id="7a713-136">如果在不到 24 小时内生成超过 1,000 条 MailItemsAccessed 审核记录，Exchange Online 将停止为 MailItemsAccessed 活动生成审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-136">If more than 1,000 MailItemsAccessed audit records are generated in less than 24 hours, Exchange Online will stop generating auditing records for MailItemsAccessed activity.</span></span> <span data-ttu-id="7a713-137">如果邮箱被限制，MailItemsAccessed 活动将在邮箱被限制后不记录达 24 小时。</span><span class="sxs-lookup"><span data-stu-id="7a713-137">When a mailbox is throttled, MailItemsAccessed activity will not be logged for 24 hours after the mailbox was throttled.</span></span> <span data-ttu-id="7a713-138">如果发生这种i情况，邮箱很可能在此期间被盗用。</span><span class="sxs-lookup"><span data-stu-id="7a713-138">If this occurs, there's a potential that mailbox could have been compromised during this period.</span></span> <span data-ttu-id="7a713-139">MailItemsAccessed 活动的记录将在 24 小时候恢复。</span><span class="sxs-lookup"><span data-stu-id="7a713-139">The recording of MailItemsAccessed activity will be resumed following a 24-hour period.</span></span>  

<span data-ttu-id="7a713-140">有关限制的事项，请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="7a713-140">Here's a few things to keep in mind about throttling:</span></span>

- <span data-ttu-id="7a713-141">Exchange Online 中少于 1% 的邮箱被限制</span><span class="sxs-lookup"><span data-stu-id="7a713-141">Less than 1% of all mailboxes in Exchange Online are throttled</span></span>

- <span data-ttu-id="7a713-142">如果邮箱被限制，仅不限制 MailItemsAccessed 活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-142">When a mailbox is throttling, only audit records for MailItemsAccessed activity are not audited.</span></span> <span data-ttu-id="7a713-143">不影响其他邮箱审核操作。</span><span class="sxs-lookup"><span data-stu-id="7a713-143">Other mailbox auditing actions aren't affected.</span></span>

- <span data-ttu-id="7a713-144">仅限制邮箱进行绑定操作。</span><span class="sxs-lookup"><span data-stu-id="7a713-144">Mailboxes are throttled only for Bind operations.</span></span> <span data-ttu-id="7a713-145">同步操作的审核记录不受限制。</span><span class="sxs-lookup"><span data-stu-id="7a713-145">Audit records for sync operations are not throttled.</span></span>

- <span data-ttu-id="7a713-146">如果邮箱被限制，可以假设存在未被记录至审核日志中的 MailItemsAccessed 活动。</span><span class="sxs-lookup"><span data-stu-id="7a713-146">If a mailbox is throttled, you can probably assume there was MailItemsAccessed activity that wasn't recorded in the audit logs.</span></span>

<span data-ttu-id="7a713-147">参见“[使用 MailItemsAccessed 审核记录进行司法鉴定调查](#use-mailitemsaccessed-audit-records-for-forensic-investigations)”一节的第 1 步了解在审核记录中显示 IsThrottled 属性的示例。</span><span class="sxs-lookup"><span data-stu-id="7a713-147">See step 1 in the [Use MailItemsAccessed audit records for forensic investigations](#use-mailitemsaccessed-audit-records-for-forensic-investigations) section for an example of displaying the IsThrottled property in an audit record.</span></span>

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a><span data-ttu-id="7a713-148">使用 MailItemsAccessed 审核记录进行司法鉴定调查</span><span class="sxs-lookup"><span data-stu-id="7a713-148">Use MailItemsAccessed audit records for forensic investigations</span></span>

<span data-ttu-id="7a713-149">Mailbox 审核生成用于存取电子邮件的审核记录，因此可以自信保证电子邮件未被泄露。</span><span class="sxs-lookup"><span data-stu-id="7a713-149">Mailbox auditing generates audit records for access to email messages so that you can be confident that email messages haven't been compromised.</span></span> <span data-ttu-id="7a713-150">因此，在无法确定某些数据已被访问的情况中，我们假设其记录了所有邮件存取活动。</span><span class="sxs-lookup"><span data-stu-id="7a713-150">For this reason, in circumstances where we're not certain that some data has been accessed, we assume that it has by recording all mail access activity.</span></span>

<span data-ttu-id="7a713-151">使用 MailItemsAccessed 审核记录进行司法鉴定目的，通常在解决了数据泄露且攻击者被逐出后进行。</span><span class="sxs-lookup"><span data-stu-id="7a713-151">Using MailItemsAccessed audit records for forensics purposes is typically performed after a data breach has been resolved and the attacker has been evicted.</span></span> <span data-ttu-id="7a713-152">若要开始调查，应确定被盗用的一组邮箱并确定攻击者存取组织中邮箱的时间范围。</span><span class="sxs-lookup"><span data-stu-id="7a713-152">To begin your investigation, you should identify the set of mailboxes that they have been compromised and determine the time frame when attacker had access to mailboxes in your organization.</span></span> <span data-ttu-id="7a713-153">然后可在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 中使用 **Search-UnifiedAuditLog** 或 **Search-MailboxAuditLog** cmdlet 搜索与数据泄漏对应的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-153">Then, you can use the **Search-UnifiedAuditLog** or **Search-MailboxAuditLog** cmdlets in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to search audit records that correspond to the data breach.</span></span> 

<span data-ttu-id="7a713-154">可运行下列之一命令来搜索 MailItemsAccessed 审核记录：</span><span class="sxs-lookup"><span data-stu-id="7a713-154">You can run one of the following commands to search for MailItemsAccessed audit records:</span></span>

<span data-ttu-id="7a713-155">**统一审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-155">**Unified audit log**</span></span>

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

<span data-ttu-id="7a713-156">**邮箱审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-156">**Mailbox audit log**</span></span>

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> <span data-ttu-id="7a713-157">这两个 cmdlet 的一个主要区别是，可使用 **Search-UnifiedAuditLog** cmdlet 来搜索由一个或更多用户所执行活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-157">One primary difference between these two cmdlets in that you can use the **Search-UnifiedAuditLog** cmdlet to search for audit records for activity performed by one or more users.</span></span> <span data-ttu-id="7a713-158">这是因为 *UserIds* 是多值参数。</span><span class="sxs-lookup"><span data-stu-id="7a713-158">That's because *UserIds* is a multi-value parameter.</span></span> <span data-ttu-id="7a713-159">**Search-MailboxAuditLog** cmdlet 搜索单个用户的邮箱审核日志。</span><span class="sxs-lookup"><span data-stu-id="7a713-159">The **Search-MailboxAuditLog** cmdlet searches the mailbox audit log for a single user.</span></span>

<span data-ttu-id="7a713-160">下面是使用 MailItemsAccessed 审核记录来调查被盗用用户的攻击步骤。</span><span class="sxs-lookup"><span data-stu-id="7a713-160">Here are the steps for using MailItemsAccessed audit records to investigate a compromised user attack.</span></span> <span data-ttu-id="7a713-161">各步骤显示 **Search-UnifiedAuditLog** 或 **Search-MailboxAuditLog** cmdlets 的命令语法。</span><span class="sxs-lookup"><span data-stu-id="7a713-161">Each step shows the command syntax for the **Search-UnifiedAuditLog** or **Search-MailboxAuditLog** cmdlets.</span></span>

1. <span data-ttu-id="7a713-162">检查邮箱是否被限制。</span><span class="sxs-lookup"><span data-stu-id="7a713-162">Check whether the mailbox has been throttled.</span></span> <span data-ttu-id="7a713-163">如果是这样，则意味着部分邮箱审核记录将不被记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-163">If so, this would mean that some mailbox auditing records would not have been logged.</span></span> <span data-ttu-id="7a713-164">如果任何审核记录的 "IsThrottled" 为 "True"，则假定 24 小时的期限后生成记录，任何对邮箱的存取未被审核，且所有邮件数据已被盗取。</span><span class="sxs-lookup"><span data-stu-id="7a713-164">In the case that any audit records have the "IsThrottled" is "True," you should assume that for a 24-hour period afterwards that record was generated, that any access to the mailbox was not audited and that all mail data has been compromised.</span></span>

   <span data-ttu-id="7a713-165">如果要搜索邮箱被限制的 MailItemsAccessed 记录，运行下列命令:</span><span class="sxs-lookup"><span data-stu-id="7a713-165">To search for MailItemsAccessed records where the mailbox was throttled, run the following command:</span></span>

   <span data-ttu-id="7a713-166">**统一审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-166">**Unified audit log**</span></span>
 
   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   <span data-ttu-id="7a713-167">**邮箱审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-167">**Mailbox audit log**</span></span>

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. <span data-ttu-id="7a713-168">检查同步活动。</span><span class="sxs-lookup"><span data-stu-id="7a713-168">Check for sync activities.</span></span> <span data-ttu-id="7a713-169">如果攻击者使用电子邮件客户端下载邮箱中的邮件，他们可将计算机与互联网断开并本地存取邮件，而不与服务器交互。</span><span class="sxs-lookup"><span data-stu-id="7a713-169">If an attacker uses an email client to downloaded messages in a mailbox, they can disconnect the computer from the Internet and access the messages locally without interacting with the server.</span></span> <span data-ttu-id="7a713-170">这意味着邮箱审核无法审核这些活动。</span><span class="sxs-lookup"><span data-stu-id="7a713-170">This means that mailbox auditing would not be able to audit these activities.</span></span>

   <span data-ttu-id="7a713-171">若要搜索被同步操作所存取邮件项的 MailItemsAccessed 记录，运行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7a713-171">To search for MailItemsAccessed records where the mail items were accessed by a sync operation, run the following command:</span></span>

   <span data-ttu-id="7a713-172">**统一审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-172">**Unified audit log**</span></span>

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   <span data-ttu-id="7a713-173">**邮箱审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-173">**Mailbox audit log**</span></span>

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. <span data-ttu-id="7a713-174">检查同步活动，以在相同的上下文中发生的任何活动作为攻击者存取邮箱所使用的活动。</span><span class="sxs-lookup"><span data-stu-id="7a713-174">Check sync activities to determine in any of them have occurred in the same context as the one used by the attacker access the mailbox.</span></span> <span data-ttu-id="7a713-175">上下文通过用于存取邮箱和邮件协议的客户端计算机 IP 地址识别和区分。</span><span class="sxs-lookup"><span data-stu-id="7a713-175">Context is identified and differentiated by the IP address of the client computer used to access the mailbox and the mail protocol.</span></span> <span data-ttu-id="7a713-176">有关详细信息，请参阅“[识别不同审核记录的存取上下文](#identifying-the-access-contexts-of-different-audit-records)”一节。</span><span class="sxs-lookup"><span data-stu-id="7a713-176">For more information, see the [Identifying the access contexts of different audit records](#identifying-the-access-contexts-of-different-audit-records) section.</span></span>

   <span data-ttu-id="7a713-177">使用下面列出的属性进行调查。</span><span class="sxs-lookup"><span data-stu-id="7a713-177">Use the properties listed below to investigate.</span></span> <span data-ttu-id="7a713-178">这些属性位于 AuditData 或 OperationProperties 属性中。</span><span class="sxs-lookup"><span data-stu-id="7a713-178">These properties are located in the AuditData or OperationProperties property.</span></span> <span data-ttu-id="7a713-179">如果发生在相同上下文中的任何同步作为攻击者行为，则假定攻击者已同步所有邮件项至其客户端，即整个邮箱可能已被盗取。</span><span class="sxs-lookup"><span data-stu-id="7a713-179">If any of the syncs occur in the same context as the attacker activity, assume the attacker has synced all mail items to their client, which means the entire mailbox has probably been compromised.</span></span>

   |<span data-ttu-id="7a713-180">属性</span><span class="sxs-lookup"><span data-stu-id="7a713-180">Property</span></span>         | <span data-ttu-id="7a713-181">描述</span><span class="sxs-lookup"><span data-stu-id="7a713-181">Description</span></span> |
   |:---------------- | :----------|
   |<span data-ttu-id="7a713-182">ClientInfoString</span><span class="sxs-lookup"><span data-stu-id="7a713-182">ClientInfoString</span></span> | <span data-ttu-id="7a713-183">描述协议、客户端（包含版本）</span><span class="sxs-lookup"><span data-stu-id="7a713-183">Describes protocol, client (includes version)</span></span>|
   |<span data-ttu-id="7a713-184">ClientIPAddress</span><span class="sxs-lookup"><span data-stu-id="7a713-184">ClientIPAddress</span></span>  | <span data-ttu-id="7a713-185">客户端计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7a713-185">IP address of the client machine.</span></span>|
   |<span data-ttu-id="7a713-186">SessionId</span><span class="sxs-lookup"><span data-stu-id="7a713-186">SessionId</span></span>        | <span data-ttu-id="7a713-187">会话 ID 有助于区分攻击者活动与同一账户的日常账户活动（如果账户被盗用）</span><span class="sxs-lookup"><span data-stu-id="7a713-187">Session ID helps to differentiate attacker actions vs day-to-day user activities on the same account (in the case of a compromised account)</span></span>|
   |<span data-ttu-id="7a713-188">UserID</span><span class="sxs-lookup"><span data-stu-id="7a713-188">UserId</span></span>           | <span data-ttu-id="7a713-189">阅读邮件用户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="7a713-189">UPN of the user reading the message.</span></span>|
   |||

4. <span data-ttu-id="7a713-190">检查绑定活动。</span><span class="sxs-lookup"><span data-stu-id="7a713-190">Check for bind activities.</span></span> <span data-ttu-id="7a713-191">执行第 2 步和第 3 步后，可以确信攻击者对电子邮件的所有其他访问，将被捕获至 MailAccessType 属性值为 "Bind" 的 MailItemsAccessed 审核记录中。</span><span class="sxs-lookup"><span data-stu-id="7a713-191">After performing steps 2 and step 3, you can be confident that all other access to email messages by the attacker will be captured in the MailItemsAccessed audit records that have a MailAccessType property with a value of "Bind".</span></span>

   <span data-ttu-id="7a713-192">若要搜索被绑定操作所存取邮件项的 MailItemsAccessed 记录，运行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7a713-192">To search for MailItemsAccessed records where the mail items were accessed by a Bind operation, run the following command.</span></span>

   <span data-ttu-id="7a713-193">**统一审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-193">**Unified audit log**</span></span>

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```
 
   <span data-ttu-id="7a713-194">**邮箱审核日志**</span><span class="sxs-lookup"><span data-stu-id="7a713-194">**Mailbox audit log**</span></span>
   
   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   <span data-ttu-id="7a713-195">被存取的电子邮件通过它们的 internet 邮件 id 进行标识。还可检查任何审核记录与其他攻击者活动拥有相同的上下文。</span><span class="sxs-lookup"><span data-stu-id="7a713-195">Email messages that were accessed are identified by their internet message Id. You can also check to see if any audit records have the same context as the ones for other attacker activity.</span></span> <span data-ttu-id="7a713-196">有关详细信息，请参阅“[识别不同审核记录的存取上下文](#identifying-the-access-contexts-of-different-audit-records)”一节。</span><span class="sxs-lookup"><span data-stu-id="7a713-196">For more information, see the [Identifying the access contexts of different audit records](#identifying-the-access-contexts-of-different-audit-records) section.</span></span>
 
   <span data-ttu-id="7a713-197">可以使用审核数据采用两种方式进行绑定操作：</span><span class="sxs-lookup"><span data-stu-id="7a713-197">You can use the audit data for bind operations in two different ways:</span></span>

     - <span data-ttu-id="7a713-198">访问或收集攻击者访问的所有电子邮件，方法是使用 InternetMessageId 查找这些邮件，然后检查这些邮件是否包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7a713-198">Access or collect all email messages the attacker accessed by using the InternetMessageId to find them and then checking to see if any of those messages contains sensitive information.</span></span>

     - <span data-ttu-id="7a713-199">使用 InternetMessageId 搜索与一组可能敏感的电子邮件相关的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-199">Use the InternetMessageId to search audit records related to a set of potentially sensitive email messages.</span></span> <span data-ttu-id="7a713-200">如果只考虑少数邮件，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="7a713-200">This is useful if you're concerned only about a small number of messages.</span></span>

## <a name="filtering-of-duplicate-audit-records"></a><span data-ttu-id="7a713-201">筛选重复的审核记录</span><span class="sxs-lookup"><span data-stu-id="7a713-201">Filtering of duplicate audit records</span></span>

<span data-ttu-id="7a713-202">一小时内所发生的相同绑定操作的重复审核记录将被依次筛选出，以清除审核噪音。</span><span class="sxs-lookup"><span data-stu-id="7a713-202">Duplicate audit records for the same bind operations that occur within an hour of each other are filtered out to remove auditing noise.</span></span> <span data-ttu-id="7a713-203">同步操作还以一小时的间隔进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7a713-203">Sync operations are also filtered out at one-hour intervals.</span></span> <span data-ttu-id="7a713-204">如果对于同一 InternetMessageId，下表中所述的任何属性不同，则此重复数据删除过程会出现异常。</span><span class="sxs-lookup"><span data-stu-id="7a713-204">The exception to this de-duplication process occurs if, for the same InternetMessageId, any of the properties described in the following table are different.</span></span> <span data-ttu-id="7a713-205">如果这些属性之一与重复操作中的不同，生成新的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-205">If one of these properties is different in a duplicate operation, a new audit record is generated.</span></span> <span data-ttu-id="7a713-206">此流程在下一节中详细描述。</span><span class="sxs-lookup"><span data-stu-id="7a713-206">This process is described in more detail in the next section.</span></span>

| <span data-ttu-id="7a713-207">属性</span><span class="sxs-lookup"><span data-stu-id="7a713-207">Property</span></span>| <span data-ttu-id="7a713-208">描述</span><span class="sxs-lookup"><span data-stu-id="7a713-208">Description</span></span>|
|:--------|:---------|
|<span data-ttu-id="7a713-209">ClientIPAddress</span><span class="sxs-lookup"><span data-stu-id="7a713-209">ClientIPAddress</span></span> | <span data-ttu-id="7a713-210">客户端计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7a713-210">IP address of the client computer.</span></span>|
|<span data-ttu-id="7a713-211">ClientInfoString</span><span class="sxs-lookup"><span data-stu-id="7a713-211">ClientInfoString</span></span>| <span data-ttu-id="7a713-212">用于存取邮箱的客户端协议、客户端。</span><span class="sxs-lookup"><span data-stu-id="7a713-212">The client protocol, client used to access the mailbox.</span></span>| 
|<span data-ttu-id="7a713-213">ParentFolder</span><span class="sxs-lookup"><span data-stu-id="7a713-213">ParentFolder</span></span>    | <span data-ttu-id="7a713-214">所访问的邮件项的完整文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="7a713-214">The full folder path of the mail item that was accessed.</span></span> |
|<span data-ttu-id="7a713-215">Logon_type</span><span class="sxs-lookup"><span data-stu-id="7a713-215">Logon_type</span></span>      | <span data-ttu-id="7a713-216">执行操作用户的登录类型。</span><span class="sxs-lookup"><span data-stu-id="7a713-216">The logon type of the user who performed the action.</span></span> <span data-ttu-id="7a713-217">登录类型（及其相应的 Enum 值）为所有者(0)、管理员 (1)或代理人(2)。</span><span class="sxs-lookup"><span data-stu-id="7a713-217">The logon types (and their corresponding Enum value) are Owner (0), Admin (1), or Delegate (2).</span></span>|
|<span data-ttu-id="7a713-218">MailAccessType</span><span class="sxs-lookup"><span data-stu-id="7a713-218">MailAccessType</span></span>  | <span data-ttu-id="7a713-219">指定访问是绑定还是同步操作。</span><span class="sxs-lookup"><span data-stu-id="7a713-219">Whether the access is a bind or a sync operation.</span></span>|
|<span data-ttu-id="7a713-220">MailboxUPN</span><span class="sxs-lookup"><span data-stu-id="7a713-220">MailboxUPN</span></span>      | <span data-ttu-id="7a713-221">被读取邮件所在邮箱的 UPN。</span><span class="sxs-lookup"><span data-stu-id="7a713-221">The UPN of the mailbox where the message being read is located.</span></span>|
|<span data-ttu-id="7a713-222">User</span><span class="sxs-lookup"><span data-stu-id="7a713-222">User</span></span>            | <span data-ttu-id="7a713-223">阅读邮件用户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="7a713-223">The UPN of the user reading the message.</span></span>|
|<span data-ttu-id="7a713-224">SessionId</span><span class="sxs-lookup"><span data-stu-id="7a713-224">SessionId</span></span>       | <span data-ttu-id="7a713-225">会话 id 有助于同一邮箱中的攻击者行为和日常用户行为（如果是账户被盗用）。有关会话的详细信息，参见“[在 Exchange Online 中的会话内根据上下文考虑攻击者的行为](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801)”。</span><span class="sxs-lookup"><span data-stu-id="7a713-225">The Session Id helps to differentiate attacker actions and day-to-day user activities in the same mailbox (in the case of account compromise) For more information about sessions, see [Contextualizing attacker activity within sessions in Exchange Online](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801).</span></span>|
||||

## <a name="identifying-the-access-contexts-of-different-audit-records"></a><span data-ttu-id="7a713-226">识别不同审核记录的存取上下文</span><span class="sxs-lookup"><span data-stu-id="7a713-226">Identifying the access contexts of different audit records</span></span>

<span data-ttu-id="7a713-227">通常攻击者在邮箱所有者访问邮箱的同时访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="7a713-227">It's common that an attacker may access a mailbox at the same time the mailbox owner is accessing it.</span></span> <span data-ttu-id="7a713-228">为区分攻击者和邮箱所有者的访问，提供了设定访问上下文的审核日志属性。</span><span class="sxs-lookup"><span data-stu-id="7a713-228">To differentiate between access by the attacker and the mailbox owner, there are audit record properties that define the context of the access.</span></span> <span data-ttu-id="7a713-229">如前所述，如果这些属性的值不同时，即使活动在聚合间隔内发生，将生成单独的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-229">As previously explained, when the values for these properties are different, even when the activity occurs within the aggregation interval, separate audit records are generated.</span></span> <span data-ttu-id="7a713-230">在下面示例中，有三个不同的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-230">In the following example, there are three different audit records.</span></span> <span data-ttu-id="7a713-231">每一个通过会话 ID 和 ClientIPAddress 属性进行区分。</span><span class="sxs-lookup"><span data-stu-id="7a713-231">Each one is differentiated by the Session Id and ClientIPAddress properties.</span></span> <span data-ttu-id="7a713-232">另外还识别被存取的邮件。</span><span class="sxs-lookup"><span data-stu-id="7a713-232">The messages that were accessed are also identified.</span></span>

|<span data-ttu-id="7a713-233">审核记录 1</span><span class="sxs-lookup"><span data-stu-id="7a713-233">Audit record 1</span></span>  |<span data-ttu-id="7a713-234">审核记录 2</span><span class="sxs-lookup"><span data-stu-id="7a713-234">Audit record 2</span></span>  |<span data-ttu-id="7a713-235">审核记录 3</span><span class="sxs-lookup"><span data-stu-id="7a713-235">Audit record 3</span></span>|
|---------|---------|---------|
|<span data-ttu-id="7a713-236">ClientIPAddress **1**</span><span class="sxs-lookup"><span data-stu-id="7a713-236">ClientIPAddress **1**</span></span><br/><span data-ttu-id="7a713-237">SessionId **2**</span><span class="sxs-lookup"><span data-stu-id="7a713-237">SessionId **2**</span></span>|<span data-ttu-id="7a713-238">ClientIPAddress **2**</span><span class="sxs-lookup"><span data-stu-id="7a713-238">ClientIPAddress **2**</span></span><br/><span data-ttu-id="7a713-239">SessionId **2**</span><span class="sxs-lookup"><span data-stu-id="7a713-239">SessionId **2**</span></span>|<span data-ttu-id="7a713-240">ClientIPAddress **1**</span><span class="sxs-lookup"><span data-stu-id="7a713-240">ClientIPAddress **1**</span></span><br/><span data-ttu-id="7a713-241">SessionId **3**</span><span class="sxs-lookup"><span data-stu-id="7a713-241">SessionId **3**</span></span>|
|<span data-ttu-id="7a713-242">InternetMessageId **A**</span><span class="sxs-lookup"><span data-stu-id="7a713-242">InternetMessageId **A**</span></span><br/><span data-ttu-id="7a713-243">InternetMessageId **D**</span><span class="sxs-lookup"><span data-stu-id="7a713-243">InternetMessageId **D**</span></span><br/><span data-ttu-id="7a713-244">InternetMessageId **E**</span><span class="sxs-lookup"><span data-stu-id="7a713-244">InternetMessageId **E**</span></span><br/><span data-ttu-id="7a713-245">InternetMessageId **F**</span><span class="sxs-lookup"><span data-stu-id="7a713-245">InternetMessageId **F**</span></span><br/>|<span data-ttu-id="7a713-246">InternetMessageId **A**</span><span class="sxs-lookup"><span data-stu-id="7a713-246">InternetMessageId **A**</span></span><br/><span data-ttu-id="7a713-247">InternetMessageId **C**</span><span class="sxs-lookup"><span data-stu-id="7a713-247">InternetMessageId **C**</span></span>|<span data-ttu-id="7a713-248">InternetMessageId **B**</span><span class="sxs-lookup"><span data-stu-id="7a713-248">InternetMessageId **B**</span></span> |
||||

<span data-ttu-id="7a713-249">如果 [上一节](#filtering-of-duplicate-audit-records) 中的表中列出的任何属性不相同，则会生成单独的审核记录来跟踪新的上下文。</span><span class="sxs-lookup"><span data-stu-id="7a713-249">If any of the properties listed in the table in the [previous section](#filtering-of-duplicate-audit-records) are different, a separate audit record is generated to track the new context.</span></span> <span data-ttu-id="7a713-250">根据活动发生的背景，访问将被排序成单独的审核记录。</span><span class="sxs-lookup"><span data-stu-id="7a713-250">Accesses will be sorted into the separate audit records depending on the context in which the activity took place.</span></span>

<span data-ttu-id="7a713-251">例如，在下列截屏中显示的审核记录中，虽然我们从 EWSEditor 和 OWA 同时存取邮件，根据存取发生的背景，存取活动被整理至不同的审核记录中。</span><span class="sxs-lookup"><span data-stu-id="7a713-251">For example, in audit records shown in the following screenshot, though we are accessing mail from EWSEditor and OWA simultaneously, the access activity is collated in different audit records depending on the context in which the access took place.</span></span> <span data-ttu-id="7a713-252">在这种情况中，上下文通过 ClientInfoString 属性的不同值确定。</span><span class="sxs-lookup"><span data-stu-id="7a713-252">In this case, the context is defined by different values for the ClientInfoString property.</span></span>

![基于上下文的不同审核记录](../media/MailItemsAccessed4.png)

<span data-ttu-id="7a713-254">下面是上一屏幕截图中所显示的命令语法：</span><span class="sxs-lookup"><span data-stu-id="7a713-254">Here is the syntax for the command shown in the previous screenshot:</span></span>

```powershell
Search-MailboxAuditLog -Identity admin -ShowDetails -Operations MailItemsAccessed -ResultSize 2000 | Select LastAccessed,Operation,AuditOperationsCountInAggregatedRecord,ClientInfoString
``` 
