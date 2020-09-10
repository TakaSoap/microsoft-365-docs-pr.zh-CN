---
title: 通过高级搜寻在设备、电子邮件、应用和标识之间寻找威胁
description: 研究常见的搜寻场景和示例查询，其中包括设备、电子邮件、应用和标识。
keywords: 高级搜索、Office365 数据、Windows 设备、Office365 电子邮件规范化、电子邮件、应用、标识、威胁搜寻、网络威胁搜寻、搜索、查询、遥测、Microsoft 365、Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c24f5891573b8541a97a35d228c57642766fe4a0
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419140"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="0c5d1-104">在设备、电子邮件、应用和标识之间寻找威胁</span><span class="sxs-lookup"><span data-stu-id="0c5d1-104">Hunt for threats across devices, emails, apps, and identities</span></span>

<span data-ttu-id="0c5d1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0c5d1-105">**Applies to:**</span></span>
- <span data-ttu-id="0c5d1-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="0c5d1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0c5d1-107">Microsoft 威胁防护中的[高级求职](advanced-hunting-overview.md)使你能够主动在以下范围内寻找威胁：</span><span class="sxs-lookup"><span data-stu-id="0c5d1-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="0c5d1-108">由 Microsoft Defender ATP 管理的设备</span><span class="sxs-lookup"><span data-stu-id="0c5d1-108">Devices managed by Microsoft Defender ATP</span></span>
- <span data-ttu-id="0c5d1-109">Microsoft 365 处理的电子邮件</span><span class="sxs-lookup"><span data-stu-id="0c5d1-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="0c5d1-110">Microsoft 云应用安全和 Azure ATP 跟踪的云应用活动、身份验证事件和域控制器活动</span><span class="sxs-lookup"><span data-stu-id="0c5d1-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Azure ATP</span></span>

<span data-ttu-id="0c5d1-111">使用此可见性级别，可以快速查找遍历网络各部分的威胁，包括收到电子邮件或 web 的复杂入侵、提升本地权限、获取特权域凭据以及跨设备横向移动。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="0c5d1-112">下面是基于各种搜寻方案的常规技术和示例查询，可帮助您研究在查找此类复杂威胁时如何构建查询。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="0c5d1-113">获取实体信息</span><span class="sxs-lookup"><span data-stu-id="0c5d1-113">Get entity info</span></span>
<span data-ttu-id="0c5d1-114">使用这些查询可了解如何快速获取有关用户帐户、设备和文件的信息。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="0c5d1-115">从电子邮件地址获取用户帐户</span><span class="sxs-lookup"><span data-stu-id="0c5d1-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="0c5d1-116">在 [涵盖设备和电子邮件的表](advanced-hunting-schema-tables.md)之间构建查询时，您可能需要从发件人或收件人电子邮件地址获取用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="0c5d1-117">通常，可以使用 *本地主机* 和电子邮件地址对收件人或发件人地址执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="0c5d1-118">在下面的代码片段中，我们使用 [tostring ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto 函数将本地主机直接提取 `@` 在列中的发件人电子邮件地址之前 `RecipientEmailAddress` 。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="0c5d1-119">下面的查询显示了可以如何使用此代码段：</span><span class="sxs-lookup"><span data-stu-id="0c5d1-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="0c5d1-120">合并 IdentityInfo 表</span><span class="sxs-lookup"><span data-stu-id="0c5d1-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="0c5d1-121">您可以通过合并或联接 [IdentityInfo 表](advanced-hunting-identityinfo-table.md)来获取帐户名称和其他帐户信息。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="0c5d1-122">下面的查询从 [EmailEvents 表](advanced-hunting-emailevents-table.md) 中获取网络钓鱼和恶意软件检测的列表，然后将该信息与表联接起来， `IdentityInfo` 以获取有关每个收件人的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a><span data-ttu-id="0c5d1-123">获取设备信息</span><span class="sxs-lookup"><span data-stu-id="0c5d1-123">Get device information</span></span>
<span data-ttu-id="0c5d1-124">[高级搜寻架构](advanced-hunting-schema-tables.md)在各种表中提供了大量设备信息。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="0c5d1-125">例如， [DeviceInfo 表](advanced-hunting-deviceinfo-table.md) 根据定期聚合的事件数据提供了全面的设备信息。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="0c5d1-126">此查询使用 `DeviceInfo` 表检查是否有可能已损坏的用户 (`<account-name>`) 是否登录到任何设备，然后列出在这些设备上触发的警报。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="0c5d1-127">此查询用于 `kind=inner` 指定 [内部联接](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)，这将阻止对的左侧值进行重复删除 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a><span data-ttu-id="0c5d1-128">搜寻方案</span><span class="sxs-lookup"><span data-stu-id="0c5d1-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="0c5d1-129">列出收到未成功 zapped 的电子邮件的用户登录活动</span><span class="sxs-lookup"><span data-stu-id="0c5d1-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="0c5d1-130">[零小时自动清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md) 在收到恶意电子邮件后对其进行寻址。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="0c5d1-131">如果 ZAP 失败，恶意代码可能最终会在设备上运行并使帐户受到危害。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="0c5d1-132">此查询将检查由 ZAP 未成功处理的电子邮件收件人发出的登录活动。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="0c5d1-133">通过凭据盗用设定的域帐户获取登录尝试</span><span class="sxs-lookup"><span data-stu-id="0c5d1-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="0c5d1-134">此查询首先标识表中的所有凭据访问警报 `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="0c5d1-135">然后，它将合并或联接 `AlertEvidence` 表，它会针对仅加入域的帐户的目标帐户和筛选器的名称进行分析。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="0c5d1-136">最后，它检查 `IdentityLogonEvents` 表以通过加入域的目标帐户获取所有登录活动。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="0c5d1-137">检查来自已知恶意发件人的文件是否在您的设备上</span><span class="sxs-lookup"><span data-stu-id="0c5d1-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="0c5d1-138">假设您知道将恶意文件发送 () 的电子邮件地址 `MaliciousSender@example.com` ，则可以运行此查询来确定您的设备上是否存在来自此发件人的文件。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="0c5d1-139">例如，您可以使用此查询来确定受恶意软件分布活动影响的设备。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="0c5d1-140">在收到恶意电子邮件后检查登录尝试</span><span class="sxs-lookup"><span data-stu-id="0c5d1-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="0c5d1-141">此查询在收到已知恶意电子邮件后的30分钟内找到电子邮件收件人执行的10次最新登录。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="0c5d1-142">您可以使用此查询检查电子邮件收件人的帐户是否已泄露。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="0c5d1-143">在收到来自已知恶意发件人的电子邮件后查看 PowerShell 活动</span><span class="sxs-lookup"><span data-stu-id="0c5d1-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="0c5d1-144">恶意电子邮件通常包含文档和其他巧尽心思构建的附件，这些附件可运行 PowerShell 命令以提供额外的负载。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="0c5d1-145">如果您知道来自已知恶意发件人的电子邮件 (`MaliciousSender@example.com`) ，则可以使用此查询列出并查看从发件人收到电子邮件后30分钟内发生的 PowerShell 活动。</span><span class="sxs-lookup"><span data-stu-id="0c5d1-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="0c5d1-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c5d1-146">Related topics</span></span>
- [<span data-ttu-id="0c5d1-147">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="0c5d1-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c5d1-148">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="0c5d1-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c5d1-149">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="0c5d1-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="0c5d1-150">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="0c5d1-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0c5d1-151">了解架构</span><span class="sxs-lookup"><span data-stu-id="0c5d1-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0c5d1-152">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="0c5d1-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)