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
ms.openlocfilehash: ec7f9083401fdf7a2114d99ddd2dcc009411e34b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633503"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="68204-104">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="68204-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="68204-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="68204-105">**Applies to:**</span></span>
- <span data-ttu-id="68204-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="68204-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="68204-107">Microsoft 威胁防护中的[高级求职](advanced-hunting-overview.md)使你能够主动地在你的 Windows 设备和 Microsoft 电子邮件中寻找威胁。</span><span class="sxs-lookup"><span data-stu-id="68204-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Microsoft emails.</span></span> <span data-ttu-id="68204-108">以下是一些搜寻场景和示例查询，可帮助您了解如何构建涵盖设备和电子邮件的查询。</span><span class="sxs-lookup"><span data-stu-id="68204-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="68204-109">从电子邮件地址获取用户帐户</span><span class="sxs-lookup"><span data-stu-id="68204-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="68204-110">在[涵盖设备和电子邮件的表](advanced-hunting-schema-tables.md)之间构建查询时，您可能需要从发件人或收件人电子邮件地址获取用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="68204-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="68204-111">为此，请使用来自电子邮件地址的*本地主机*：</span><span class="sxs-lookup"><span data-stu-id="68204-111">To do this use the *local-host* from the email address:</span></span>

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="68204-112">此规范化技术在后续方案中使用。</span><span class="sxs-lookup"><span data-stu-id="68204-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="68204-113">搜寻方案</span><span class="sxs-lookup"><span data-stu-id="68204-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="68204-114">检查来自已知恶意发件人的文件是否在您的设备上</span><span class="sxs-lookup"><span data-stu-id="68204-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="68204-115">假设您知道发送恶意文件的电子邮件地址，则可以运行此查询来确定您的设备上是否存在来自此发件人的文件。</span><span class="sxs-lookup"><span data-stu-id="68204-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="68204-116">例如，您可以使用此查询来确定受恶意软件分布活动影响的设备的数量。</span><span class="sxs-lookup"><span data-stu-id="68204-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="68204-117">在收到恶意电子邮件后检查登录尝试</span><span class="sxs-lookup"><span data-stu-id="68204-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="68204-118">此查询在收到已知恶意电子邮件后的30分钟内找到电子邮件收件人执行的10次最新登录。</span><span class="sxs-lookup"><span data-stu-id="68204-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="68204-119">您可以使用此查询检查电子邮件收件人的帐户是否已泄露。</span><span class="sxs-lookup"><span data-stu-id="68204-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="68204-120">在收到来自已知恶意发件人的电子邮件后查看 PowerShell 活动</span><span class="sxs-lookup"><span data-stu-id="68204-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="68204-121">恶意电子邮件通常包含文档和其他巧尽心思构建的附件，这些附件可运行 PowerShell 命令以提供额外的负载。</span><span class="sxs-lookup"><span data-stu-id="68204-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="68204-122">如果您知道来自已知恶意发件人的电子邮件，则可以使用此查询列出并查看从发件人收到电子邮件后30分钟内发生的 PowerShell 活动。</span><span class="sxs-lookup"><span data-stu-id="68204-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="68204-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="68204-123">Related topics</span></span>
- [<span data-ttu-id="68204-124">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="68204-124">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="68204-125">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="68204-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="68204-126">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="68204-126">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="68204-127">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="68204-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="68204-128">了解架构</span><span class="sxs-lookup"><span data-stu-id="68204-128">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="68204-129">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="68204-129">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
