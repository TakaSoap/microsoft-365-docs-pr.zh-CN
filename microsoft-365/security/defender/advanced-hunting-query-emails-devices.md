---
title: 使用高级搜寻跨设备、电子邮件、应用和标识搜寻威胁
description: 研究涉及设备、电子邮件、应用和标识的常见搜寻方案和示例查询。
keywords: 高级搜寻， Office365 数据， Windows 设备， Office365 电子邮件规范化， 电子邮件， 应用， 标识， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: aacd0745ff507356035f8f460ed2b4307e9da6ed
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964869"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="4b12f-104">跨设备、电子邮件、应用和标识搜索威胁</span><span class="sxs-lookup"><span data-stu-id="4b12f-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4b12f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4b12f-105">**Applies to:**</span></span>
- <span data-ttu-id="4b12f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b12f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4b12f-107">[利用 Microsoft 365 Defender](advanced-hunting-overview.md)高级搜寻，你可以跨：</span><span class="sxs-lookup"><span data-stu-id="4b12f-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="4b12f-108">由 Microsoft Defender for Endpoint 管理的设备</span><span class="sxs-lookup"><span data-stu-id="4b12f-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="4b12f-109">由用户处理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b12f-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="4b12f-110">由 Microsoft Defender 和 Microsoft Defender for Identity 跟踪的云应用Microsoft Cloud App Security、身份验证事件和域控制器活动</span><span class="sxs-lookup"><span data-stu-id="4b12f-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="4b12f-111">借助此可见性级别，你可以快速搜寻遍历网络各部分的威胁，包括到达电子邮件或 Web 的复杂的入侵、提升本地特权、获取特权域凭据以及横向移动到整个设备。</span><span class="sxs-lookup"><span data-stu-id="4b12f-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="4b12f-112">下面是基于各种搜寻方案的常规技术和示例查询，可帮助你探索在搜寻此类复杂威胁时如何构造查询。</span><span class="sxs-lookup"><span data-stu-id="4b12f-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="4b12f-113">获取实体信息</span><span class="sxs-lookup"><span data-stu-id="4b12f-113">Get entity info</span></span>
<span data-ttu-id="4b12f-114">使用这些查询了解如何快速获取有关用户帐户、设备和文件的信息。</span><span class="sxs-lookup"><span data-stu-id="4b12f-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="4b12f-115">从电子邮件地址获取用户帐户</span><span class="sxs-lookup"><span data-stu-id="4b12f-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="4b12f-116">构造跨涵盖设备和电子邮件 [的](advanced-hunting-schema-tables.md)表的查询时，你可能需要从发件人或收件人电子邮件地址获取用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="4b12f-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="4b12f-117">通常可以使用电子邮件地址中的本地主机为收件人 *或发件人地址* 进行此操作。</span><span class="sxs-lookup"><span data-stu-id="4b12f-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="4b12f-118">在下面的代码段中，我们使用 [tostring () ](/azure/data-explorer/kusto/query/tostringfunction) Kusto 函数从列 中的 收件人电子邮件地址前提取本地 `@` 主机 `RecipientEmailAddress` 。</span><span class="sxs-lookup"><span data-stu-id="4b12f-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="4b12f-119">下面的查询演示如何使用此代码段：</span><span class="sxs-lookup"><span data-stu-id="4b12f-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="4b12f-120">合并 IdentityInfo 表</span><span class="sxs-lookup"><span data-stu-id="4b12f-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="4b12f-121">可以通过合并或加入 IdentityInfo 表获取帐户名 [和其他帐户信息](advanced-hunting-identityinfo-table.md)。</span><span class="sxs-lookup"><span data-stu-id="4b12f-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="4b12f-122">下面的查询从 [EmailEvents](advanced-hunting-emailevents-table.md) 表获取网络钓鱼和恶意软件检测列表，然后将该信息与该表联接以获取有关每个收件人 `IdentityInfo` 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b12f-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a><span data-ttu-id="4b12f-123">获取设备信息</span><span class="sxs-lookup"><span data-stu-id="4b12f-123">Get device information</span></span>
<span data-ttu-id="4b12f-124">高级 [搜寻架构](advanced-hunting-schema-tables.md) 在各种表中提供广泛的设备信息。</span><span class="sxs-lookup"><span data-stu-id="4b12f-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="4b12f-125">例如 [，DeviceInfo 表](advanced-hunting-deviceinfo-table.md) 基于定期聚合的事件数据提供全面的设备信息。</span><span class="sxs-lookup"><span data-stu-id="4b12f-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="4b12f-126">此查询使用表检查可能受到威胁的用户 () 登录到任何设备，然后列出在这些设备上触发的 `DeviceInfo` `<account-name>` 警报。</span><span class="sxs-lookup"><span data-stu-id="4b12f-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="4b12f-127">此查询 `kind=inner` 用于指定 [一个内部联接](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)，以防止对 的左侧值进行重复 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="4b12f-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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


### <a name="get-file-event-information"></a><span data-ttu-id="4b12f-128">获取文件事件信息</span><span class="sxs-lookup"><span data-stu-id="4b12f-128">Get file event information</span></span>

<span data-ttu-id="4b12f-129">使用以下查询获取有关文件相关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="4b12f-129">Use the following query to get information on file related events.</span></span> 

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceFileEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="get-network-event-information"></a><span data-ttu-id="4b12f-130">获取网络事件信息</span><span class="sxs-lookup"><span data-stu-id="4b12f-130">Get network event information</span></span>

<span data-ttu-id="4b12f-131">使用以下查询获取有关网络相关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="4b12f-131">Use the following query to get information on network related events.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-agent-version-information"></a><span data-ttu-id="4b12f-132">获取设备代理版本信息</span><span class="sxs-lookup"><span data-stu-id="4b12f-132">Get device agent version information</span></span>

<span data-ttu-id="4b12f-133">使用以下查询获取在设备上运行的代理的版本。</span><span class="sxs-lookup"><span data-stu-id="4b12f-133">Use the following query to get the version of the agent running on a device.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="example-query-for-macos-devices"></a><span data-ttu-id="4b12f-134">macOS 设备示例查询</span><span class="sxs-lookup"><span data-stu-id="4b12f-134">Example query for macOS devices</span></span>

<span data-ttu-id="4b12f-135">使用以下示例查询来查看运行 macOS 版本低于加泰罗尼亚语的所有设备。</span><span class="sxs-lookup"><span data-stu-id="4b12f-135">Use the following example query to see all devices running macOS with a version older than Catalina.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OSPlatform == "macOS" and  OSVersion !contains "10.15" and OSVersion !contains "11."
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-status-info"></a><span data-ttu-id="4b12f-136">获取设备状态信息</span><span class="sxs-lookup"><span data-stu-id="4b12f-136">Get device status info</span></span>

<span data-ttu-id="4b12f-137">使用以下查询获取设备的状态。</span><span class="sxs-lookup"><span data-stu-id="4b12f-137">Use the following query to get status of a device.</span></span> <span data-ttu-id="4b12f-138">在下面的示例中，查询将检查设备是否载入。</span><span class="sxs-lookup"><span data-stu-id="4b12f-138">In the following example, the query checks to see if the device is onboarded.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OnboardingStatus != "Onboarded"
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


## <a name="hunting-scenarios"></a><span data-ttu-id="4b12f-139">搜寻方案</span><span class="sxs-lookup"><span data-stu-id="4b12f-139">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="4b12f-140">列出收到未成功删除的电子邮件的用户的登录活动</span><span class="sxs-lookup"><span data-stu-id="4b12f-140">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="4b12f-141">[零时差自动清除 (ZAP ](../office-365-security/zero-hour-auto-purge.md)) 收到恶意电子邮件后进行地址。</span><span class="sxs-lookup"><span data-stu-id="4b12f-141">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="4b12f-142">如果 ZAP 失败，恶意代码最终可能会运行在设备上，并且帐户会遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="4b12f-142">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="4b12f-143">此查询将检查由 ZAP 未成功解决的电子邮件的收件人所进行登录活动。</span><span class="sxs-lookup"><span data-stu-id="4b12f-143">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="4b12f-144">获取凭据盗窃所针对的域帐户的登录尝试</span><span class="sxs-lookup"><span data-stu-id="4b12f-144">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="4b12f-145">此查询首先标识表中的所有凭据访问 `AlertInfo` 警报。</span><span class="sxs-lookup"><span data-stu-id="4b12f-145">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="4b12f-146">然后，它将合并或联接该表，该表将分析目标帐户的名称，并仅筛选 `AlertEvidence` 加入域的帐户。</span><span class="sxs-lookup"><span data-stu-id="4b12f-146">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="4b12f-147">最后，它检查 `IdentityLogonEvents` 表，获取已加入域的目标帐户的所有登录活动。</span><span class="sxs-lookup"><span data-stu-id="4b12f-147">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="4b12f-148">检查你的设备上是否包含来自已知恶意发件人的文件</span><span class="sxs-lookup"><span data-stu-id="4b12f-148">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="4b12f-149">假设您知道向用户发送恶意 () 的电子邮件地址，您可以运行此查询来确定此发件人的文件是否存在 `MaliciousSender@example.com` 于您的设备上。</span><span class="sxs-lookup"><span data-stu-id="4b12f-149">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="4b12f-150">例如，您可以使用此查询来标识受恶意软件分发活动影响的设备。</span><span class="sxs-lookup"><span data-stu-id="4b12f-150">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="4b12f-151">查看收到恶意电子邮件后的登录尝试</span><span class="sxs-lookup"><span data-stu-id="4b12f-151">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="4b12f-152">此查询在电子邮件收件人收到已知的恶意电子邮件后 30 分钟内找到他们最近执行的 10 次登出。</span><span class="sxs-lookup"><span data-stu-id="4b12f-152">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="4b12f-153">可以使用此查询检查电子邮件收件人的帐户是否遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="4b12f-153">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="4b12f-154">收到来自已知恶意发件人的电子邮件后查看 PowerShell 活动</span><span class="sxs-lookup"><span data-stu-id="4b12f-154">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="4b12f-155">恶意电子邮件通常包含文档和其他专门设计的附件，这些附件运行 PowerShell 命令以提供其他有效负载。</span><span class="sxs-lookup"><span data-stu-id="4b12f-155">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="4b12f-156">如果您知道来自已知恶意发件人 () 的电子邮件，您可以使用此查询列出并查看从发件人收到电子邮件后 30 分钟内发生的 `MaliciousSender@example.com` PowerShell 活动。</span><span class="sxs-lookup"><span data-stu-id="4b12f-156">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="4b12f-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="4b12f-157">Related topics</span></span>
- [<span data-ttu-id="4b12f-158">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="4b12f-158">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4b12f-159">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="4b12f-159">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4b12f-160">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="4b12f-160">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4b12f-161">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="4b12f-161">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4b12f-162">了解架构</span><span class="sxs-lookup"><span data-stu-id="4b12f-162">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4b12f-163">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="4b12f-163">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
