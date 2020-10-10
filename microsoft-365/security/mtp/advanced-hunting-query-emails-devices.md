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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9f5468ccb853bbbe126198a14f7b824d953a2738
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412630"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>在设备、电子邮件、应用和标识之间寻找威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

Microsoft 威胁防护中的[高级求职](advanced-hunting-overview.md)使你能够主动在以下范围内寻找威胁：
- 由 Microsoft Defender ATP 管理的设备
- Microsoft 365 处理的电子邮件
- Microsoft 云应用安全和 Azure ATP 跟踪的云应用活动、身份验证事件和域控制器活动

使用此可见性级别，可以快速查找遍历网络各部分的威胁，包括收到电子邮件或 web 的复杂入侵、提升本地权限、获取特权域凭据以及跨设备横向移动。 

下面是基于各种搜寻方案的常规技术和示例查询，可帮助您研究在查找此类复杂威胁时如何构建查询。

## <a name="get-entity-info"></a>获取实体信息
使用这些查询可了解如何快速获取有关用户帐户、设备和文件的信息。 

### <a name="obtain-user-accounts-from-email-addresses"></a>从电子邮件地址获取用户帐户
在 [涵盖设备和电子邮件的表](advanced-hunting-schema-tables.md)之间构建查询时，您可能需要从发件人或收件人电子邮件地址获取用户帐户名称。 通常，可以使用 *本地主机* 和电子邮件地址对收件人或发件人地址执行此操作。

在下面的代码片段中，我们使用 [tostring ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto 函数将本地主机直接提取 `@` 在列中的发件人电子邮件地址之前 `RecipientEmailAddress` 。

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
下面的查询显示了可以如何使用此代码段：

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>合并 IdentityInfo 表

您可以通过合并或联接 [IdentityInfo 表](advanced-hunting-identityinfo-table.md)来获取帐户名称和其他帐户信息。 下面的查询从 [EmailEvents 表](advanced-hunting-emailevents-table.md) 中获取网络钓鱼和恶意软件检测的列表，然后将该信息与表联接起来， `IdentityInfo` 以获取有关每个收件人的详细信息。 

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

### <a name="get-device-information"></a>获取设备信息
[高级搜寻架构](advanced-hunting-schema-tables.md)在各种表中提供了大量设备信息。 例如， [DeviceInfo 表](advanced-hunting-deviceinfo-table.md) 根据定期聚合的事件数据提供了全面的设备信息。 此查询使用 `DeviceInfo` 表检查是否有可能已损坏的用户 (`<account-name>`) 是否登录到任何设备，然后列出在这些设备上触发的警报。

>[!Tip]
> 此查询用于 `kind=inner` 指定 [内部联接](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)，这将阻止对的左侧值进行重复删除 `DeviceId` 。

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

## <a name="hunting-scenarios"></a>搜寻方案

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>列出收到未成功 zapped 的电子邮件的用户登录活动
[零小时自动清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md) 在收到恶意电子邮件后对其进行寻址。 如果 ZAP 失败，恶意代码可能最终会在设备上运行并使帐户受到危害。 此查询将检查由 ZAP 未成功处理的电子邮件收件人发出的登录活动。

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>通过凭据盗用设定的域帐户获取登录尝试
此查询首先标识表中的所有凭据访问警报 `AlertInfo` 。 然后，它将合并或联接 `AlertEvidence` 表，它会针对仅加入域的帐户的目标帐户和筛选器的名称进行分析。 最后，它检查 `IdentityLogonEvents` 表以通过加入域的目标帐户获取所有登录活动。

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>检查来自已知恶意发件人的文件是否在您的设备上
假设您知道将恶意文件发送 () 的电子邮件地址 `MaliciousSender@example.com` ，则可以运行此查询来确定您的设备上是否存在来自此发件人的文件。 例如，您可以使用此查询来确定受恶意软件分布活动影响的设备。

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>在收到恶意电子邮件后检查登录尝试
此查询在收到已知恶意电子邮件后的30分钟内找到电子邮件收件人执行的10次最新登录。 您可以使用此查询检查电子邮件收件人的帐户是否已泄露。

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>在收到来自已知恶意发件人的电子邮件后查看 PowerShell 活动
恶意电子邮件通常包含文档和其他巧尽心思构建的附件，这些附件可运行 PowerShell 命令以提供额外的负载。 如果您知道来自已知恶意发件人的电子邮件 (`MaliciousSender@example.com`) ，则可以使用此查询列出并查看从发件人收到电子邮件后30分钟内发生的 PowerShell 活动。  

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
