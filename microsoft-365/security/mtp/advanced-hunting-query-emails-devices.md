---
title: 使用高级搜寻查找跨设备和电子邮件的威胁
description: 研究常见的搜寻场景和示例查询，涵盖设备和电子邮件。
keywords: 高级搜索、Office365 数据、Windows 设备、Office365 电子邮件规范化、电子邮件、威胁搜寻、网络威胁搜寻、搜索、查询、遥测、Microsoft 365、Microsoft 威胁防护
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
ms.openlocfilehash: 0bbcef72fa305819c9f8e0813cfcdfd6c2b0fff3
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234721"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>跨设备和电子邮件搜寻威胁

**适用于：**
- Microsoft 威胁防护



Microsoft 威胁防护中的[高级求职](advanced-hunting-overview.md)使你能够主动地在你的 Windows 设备和 Office 365 电子邮件中寻找威胁。 以下是一些搜寻场景和示例查询，可帮助您了解如何构建涵盖设备和电子邮件的查询。

## <a name="obtain-user-accounts-from-email-addresses"></a>从电子邮件地址获取用户帐户
在[涵盖设备和电子邮件的表](advanced-hunting-schema-tables.md)之间构建查询时，您可能需要从发件人或收件人电子邮件地址获取用户帐户名称。 为此，请使用来自电子邮件地址的*本地主机*：

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

此规范化技术在后续方案中使用。

## <a name="hunting-scenarios"></a>搜寻方案

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>检查来自已知恶意发件人的文件是否在您的设备上
假设您知道发送恶意文件的电子邮件地址，则可以运行此查询来确定您的设备上是否存在来自此发件人的文件。 例如，您可以使用此查询来确定受恶意软件分布活动影响的设备的数量。

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>在收到恶意电子邮件后检查登录尝试
此查询在收到已知恶意电子邮件后的30分钟内找到电子邮件收件人执行的10次最新登录。 您可以使用此查询检查电子邮件收件人的帐户是否已泄露。

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>在收到来自已知恶意发件人的电子邮件后查看 PowerShell 活动
恶意电子邮件通常包含文档和其他巧尽心思构建的附件，这些附件可运行 PowerShell 命令以提供额外的负载。 如果您知道来自已知恶意发件人的电子邮件，则可以使用此查询列出并查看从发件人收到电子邮件后30分钟内发生的 PowerShell 活动。  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
