---
title: 通过高级搜寻跨设备、电子邮件、应用和标识搜寻威胁
description: 研究常见的搜寻方案和示例查询，这些查询涵盖设备、电子邮件、应用和标识。
keywords: 高级搜寻， Office365 数据， Windows 设备， Office365 电子邮件规范化， 电子邮件， 应用， 标识， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b408f574ab4b89806be9154394f49c00a7fd1e99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932246"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>跨设备、电子邮件、应用和标识搜寻威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[](advanced-hunting-overview.md) Microsoft 365 Defender 中的高级搜寻允许你跨：
- 由 Microsoft Defender for Endpoint 管理的设备
- Microsoft 365 处理的电子邮件
- 由 Microsoft Cloud App Security 和 Microsoft Defender for Identity 跟踪的云应用活动、身份验证事件和域控制器活动

通过此可见性级别，你可以快速搜寻遍历网络各部分的威胁，包括到达电子邮件或 Web 上复杂的入侵、提升本地特权、获取特权域凭据以及横向移动到你的设备。 

下面是基于各种搜寻方案的常规技术和示例查询，可帮助您了解在搜寻此类复杂威胁时如何构造查询。

## <a name="get-entity-info"></a>获取实体信息
使用这些查询了解如何快速获取有关用户帐户、设备和文件的信息。 

### <a name="obtain-user-accounts-from-email-addresses"></a>从电子邮件地址获取用户帐户
在包含 [设备和电子邮件的](advanced-hunting-schema-tables.md)表中构造查询时，可能需要从发件人或收件人电子邮件地址获取用户帐户名。 通常可以使用电子邮件地址中的本地主机为收件人 *或发件人地址* 执行此操作。

在下面的代码段中，我们使用 [tostring () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto 函数从列的收件人电子邮件地址之前提取本地 `@` 主机 `RecipientEmailAddress` 。

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
下面的查询显示了如何使用此代码段：

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>合并 IdentityInfo 表

可以通过合并或加入 IdentityInfo 表获取帐户名 [和其他帐户信息](advanced-hunting-identityinfo-table.md)。 下面的查询从 [EmailEvents](advanced-hunting-emailevents-table.md) 表中获取网络钓鱼和恶意软件检测列表，然后将该信息与该表联接以获取有关每个收件人 `IdentityInfo` 的详细信息。 

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
高级 [搜寻架构](advanced-hunting-schema-tables.md) 在各种表中提供广泛的设备信息。 例如 [，DeviceInfo 表](advanced-hunting-deviceinfo-table.md) 基于定期聚合的事件数据提供全面的设备信息。 此查询使用表检查可能受到威胁的用户 () 登录到任何设备，然后列出在这些设备上触发的 `DeviceInfo` `<account-name>` 警报。

>[!Tip]
> 此查询 `kind=inner` 用于指定 [一个内部](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)联接，以防止对的左侧值进行重复 `DeviceId` 数据删除。

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

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>列出收到未成功删除的电子邮件的用户的登录活动
[零时差自动清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md) 会在收到恶意电子邮件后进行地址处理。 如果 ZAP 失败，恶意代码可能最终在设备上运行，并且帐户会遭到入侵。 此查询将检查由 ZAP 未成功解决的电子邮件的收件人所进行登录活动。

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>获取凭据盗窃所针对的域帐户的登录尝试
此查询首先标识表中的所有凭据访问 `AlertInfo` 警报。 然后，它合并或联接表，该表将只分析目标帐户的名称，并筛选加入 `AlertEvidence` 域的帐户。 最后，它检查表，获取已加入域的目标帐户的所有 `IdentityLogonEvents` 登录活动。

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>检查来自已知恶意发件人的文件是否位于你的设备上
假定你知道发送恶意文件的电子邮件地址 () ，可以运行此查询来确定你的设备上是否存在来自此发件人 `MaliciousSender@example.com` 的文件。 例如，可以使用此查询来标识受恶意软件分发活动影响的设备。

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>查看收到恶意电子邮件后的登录尝试
此查询查找电子邮件收件人收到已知的恶意电子邮件后 30 分钟内执行的 10 个最新登出。 您可以使用此查询来检查电子邮件收件人的帐户是否遭到入侵。

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>查看收到来自已知恶意发件人的电子邮件后的 PowerShell 活动
恶意电子邮件通常包含文档和其他专门设计的附件，这些附件运行 PowerShell 命令以提供其他负载。 如果您知道来自已知恶意发件人 () 的电子邮件，您可以使用此查询列出和查看从发件人收到电子邮件后 30 分钟内发生的 `MaliciousSender@example.com` PowerShell 活动。  

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
