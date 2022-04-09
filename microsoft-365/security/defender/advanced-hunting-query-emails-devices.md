---
title: 通过高级搜寻在设备、电子邮件、应用和标识之间搜寻威胁
description: 研究涵盖设备、电子邮件、应用和标识的常见搜寻方案和示例查询。
keywords: 高级搜寻，Office365 数据，Windows设备，Office365 电子邮件规范化，电子邮件，应用，标识，威胁搜寻，网络威胁搜寻，搜索，查询，遥测，Microsoft 365，Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 099ba7abe53be6269c1d01c0d39d9e5cfbe3557d
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "64731683"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>跨设备、电子邮件、应用和标识搜索威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[Microsoft 365 Defender中的高级搜寻](advanced-hunting-overview.md)可让你主动搜寻威胁：
- 由Microsoft Defender for Endpoint管理的设备
- 由Microsoft 365处理的电子邮件
- 由Microsoft Defender for Cloud Apps和Microsoft Defender for Identity跟踪的云应用活动、身份验证事件和域控制器活动

借助此级别的可见性，可以快速搜寻遍历网络各部分的威胁，包括电子邮件或 Web 上的复杂入侵、提升本地特权、获取特权域凭据，以及横向移动到设备。 

下面是基于各种搜寻方案的常规技术和示例查询，可帮助你探索在搜寻此类复杂威胁时如何构造查询。

## <a name="get-entity-info"></a>获取实体信息
使用这些查询了解如何快速获取有关用户帐户、设备和文件的信息。 

### <a name="obtain-user-accounts-from-email-addresses"></a>从电子邮件地址获取用户帐户
跨 [涵盖设备和电子邮件的表](advanced-hunting-schema-tables.md)构造查询时，可能需要从发件人或收件人电子邮件地址获取用户帐户名称。 通常可以使用电子邮件地址中的 *本地主机* 为收件人或发件人地址执行此操作。

在下面的代码片段中，我们使用 [tostring () ](/azure/data-explorer/kusto/query/tostringfunction) Kusto函数直接从列`RecipientEmailAddress`中的收件人电子邮件地址之前`@`提取本地主机。

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
下面的查询演示如何使用此代码片段：

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>合并 IdentityInfo 表

可以通过合并或加入 [IdentityInfo 表](advanced-hunting-identityinfo-table.md)来获取帐户名称和其他帐户信息。 下面的查询从 [EmailEvents 表](advanced-hunting-emailevents-table.md) 中获取网络钓鱼和恶意软件检测的列表，然后将该信息与表联接 `IdentityInfo` ，以获取有关每个收件人的详细信息。 

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

### <a name="get-device-information"></a>获取设备信息
[高级搜寻架构](advanced-hunting-schema-tables.md)在各种表中提供广泛的设备信息。 例如， [DeviceInfo 表](advanced-hunting-deviceinfo-table.md) 基于定期聚合的事件数据提供全面的设备信息。 此查询使用 `DeviceInfo` 该表检查可能泄露的用户 (`<account-name>`) 是否已登录到任何设备，然后列出在这些设备上触发的警报。

>[!Tip]
> 此查询用于 `kind=inner` 指定 [内部联](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)接，防止删除左侧值 `DeviceId`。

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


### <a name="get-file-event-information"></a>获取文件事件信息

使用以下查询获取有关文件相关事件的信息。 

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


### <a name="get-network-event-information"></a>获取网络事件信息

使用以下查询获取有关网络相关事件的信息。

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

### <a name="get-device-agent-version-information"></a>获取设备代理版本信息

使用以下查询获取在设备上运行的代理的版本。

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


### <a name="example-query-for-macos-devices"></a>macOS 设备的示例查询

使用以下示例查询查看运行 macOS 且版本早于 Catalina 的所有设备。

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

### <a name="get-device-status-info"></a>获取设备状态信息

使用以下查询获取设备的状态。 在以下示例中，查询将检查设备是否已载入。

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


## <a name="hunting-scenarios"></a>搜寻方案

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>列出未成功接收电子邮件的用户的登录活动
[零小时自动清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md) 在收到恶意电子邮件后处理这些电子邮件。 如果 ZAP 失败，恶意代码最终可能会在设备上运行，并使帐户遭到入侵。 此查询检查 ZAP 未成功处理的电子邮件收件人进行的登录活动。

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>获取以凭据盗窃为目标的域帐户的登录尝试
此查询首先标识表中 `AlertInfo` 的所有凭据访问警报。 然后，它将合并或加入 `AlertEvidence` 表，该表分析目标帐户的名称，并仅筛选已加入域的帐户。 最后，它会检查 `IdentityLogonEvents` 表以获取已加入域的目标帐户的所有登录活动。

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>检查来自已知恶意发件人的文件是否在你的设备上
假设知道电子邮件地址 () `MaliciousSender@example.com` 发送恶意文件，则可以运行此查询以确定设备上是否存在此发件人的文件。 例如，可以使用此查询来标识受恶意软件分发活动影响的设备。

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256, DeviceName, DeviceId
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>在收到恶意电子邮件后查看登录尝试
此查询查找电子邮件收件人在收到已知恶意电子邮件后 30 分钟内执行的最新 10 个登录。 可以使用此查询检查电子邮件收件人的帐户是否已泄露。

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>从已知恶意发件人收到电子邮件后查看 PowerShell 活动
恶意电子邮件通常包含文档和其他特别制作的附件，这些附件运行 PowerShell 命令以提供其他有效负载。 如果知道来自已知恶意发件人的电子邮件 () `MaliciousSender@example.com` ，则可以使用此查询列出和查看从发件人收到电子邮件后 30 分钟内发生的 PowerShell 活动。  

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

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
