---
title: Microsoft Defender for Office 365
description: 使用高级搜寻开始搜索电子邮件威胁
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965138"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="e373c-104">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e373c-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e373c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e373c-105">**Applies to:**</span></span>
- <span data-ttu-id="e373c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e373c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e373c-107">想要开始使用高级搜索搜索电子邮件威胁？</span><span class="sxs-lookup"><span data-stu-id="e373c-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="e373c-108">请尝试使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e373c-108">Try this:</span></span>

<span data-ttu-id="e373c-109">[Microsoft Defender for Office 365文章](/microsoft-365/security/office-365-security/defender-for-office-365)的[“入门”](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started)部分具有如下所示的逻辑早期配置块：</span><span class="sxs-lookup"><span data-stu-id="e373c-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="e373c-110">使用名称中的"Anti"配置所有内容。</span><span class="sxs-lookup"><span data-stu-id="e373c-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="e373c-111">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="e373c-111">Anti-malware</span></span>
   - <span data-ttu-id="e373c-112">防钓鱼</span><span class="sxs-lookup"><span data-stu-id="e373c-112">Anti-phishing</span></span>
   - <span data-ttu-id="e373c-113">反垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="e373c-113">Anti-spam</span></span>
2. <span data-ttu-id="e373c-114">设置名称中保险箱"值的所有内容。</span><span class="sxs-lookup"><span data-stu-id="e373c-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="e373c-115">安全链接</span><span class="sxs-lookup"><span data-stu-id="e373c-115">Safe Links</span></span>
   - <span data-ttu-id="e373c-116">安全附件</span><span class="sxs-lookup"><span data-stu-id="e373c-116">Safe Attachments</span></span>
3. <span data-ttu-id="e373c-117">保护工作负载（例如</span><span class="sxs-lookup"><span data-stu-id="e373c-117">Defend the workloads (ex.</span></span> <span data-ttu-id="e373c-118">SharePoint联机、OneDrive和Teams) 。</span><span class="sxs-lookup"><span data-stu-id="e373c-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="e373c-119">使用零时差自动清除进行保护。</span><span class="sxs-lookup"><span data-stu-id="e373c-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="e373c-120">以及一 [链接](../office-365-security/protect-against-threats.md) 一起跳入，在"第 1 天"进行配置。</span><span class="sxs-lookup"><span data-stu-id="e373c-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="e373c-121">**入门** 最后一步是通过 **0 小时自动清除清除**（也称为 ZAP）保护用户。</span><span class="sxs-lookup"><span data-stu-id="e373c-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="e373c-122">了解你为 ZAP 提供可疑或恶意邮件、发送后成功这一操作是否非常重要。</span><span class="sxs-lookup"><span data-stu-id="e373c-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="e373c-123">快速导航到执行查询语言以搜索问题是聚合这两个安全中心的一个优势。</span><span class="sxs-lookup"><span data-stu-id="e373c-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="e373c-124">安全团队可以通过在此处执行下一步（在搜寻高级搜寻 [](https://security.microsoft.com/advanced-hunting)下）监视 ZAP \> **错过事件**。</span><span class="sxs-lookup"><span data-stu-id="e373c-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="e373c-125">在"高级搜寻"页上，单击"查询 **"。**</span><span class="sxs-lookup"><span data-stu-id="e373c-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="e373c-126">将下面的查询复制到查询窗口中。</span><span class="sxs-lookup"><span data-stu-id="e373c-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="e373c-127">选择 **"运行查询"。**</span><span class="sxs-lookup"><span data-stu-id="e373c-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="&quot;高级搜寻&quot; (在&quot;搜寻) 在查询面板顶部选择&quot;查询&quot;下，并运行 Kusto 查询以捕获过去 7 天内的 ZAP 操作。":::

<span data-ttu-id="e373c-129">来自此查询的数据将在查询自身下方的结果面板中显示。</span><span class="sxs-lookup"><span data-stu-id="e373c-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="e373c-130">结果包括可自定义结果集内的信息，如"DeviceName"、"AccountDisplayName"和"<3>pTime"。</span><span class="sxs-lookup"><span data-stu-id="e373c-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="e373c-131">也可以为记录导出结果。</span><span class="sxs-lookup"><span data-stu-id="e373c-131">Results can also be exported for your records.</span></span> <span data-ttu-id="e373c-132">如果您再次需要查询，请选择 **保存** > **“另存为”**，然后将查询添加到查询，共享或社区查询列表中。</span><span class="sxs-lookup"><span data-stu-id="e373c-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="e373c-133">相关信息</span><span class="sxs-lookup"><span data-stu-id="e373c-133">Related information</span></span>
- [<span data-ttu-id="e373c-134">高级搜寻最佳做法</span><span class="sxs-lookup"><span data-stu-id="e373c-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e373c-135">概述 - 高级搜寻</span><span class="sxs-lookup"><span data-stu-id="e373c-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
