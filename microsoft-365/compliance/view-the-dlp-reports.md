---
title: 查看数据丢失防护报告
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 使用 Office 365 中的 DLP 报告查看 DLP 策略匹配项、替代或误报的数量，并查看它们是否随着时间的推移呈上升或下降趋势。
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928386"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="ad177-103">查看数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="ad177-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="ad177-104">在 DLP (策略 (数据丢失防护) ，您需要验证它们是否正常工作，并帮助您保持合规性。</span><span class="sxs-lookup"><span data-stu-id="ad177-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="ad177-105">使用安全与合规中心中的 DLP 报告 &amp; ，可以快速查看：</span><span class="sxs-lookup"><span data-stu-id="ad177-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="ad177-106">**DLP 策略匹配** 此报告显示随着时间的推移 DLP 策略匹配项的计数。</span><span class="sxs-lookup"><span data-stu-id="ad177-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="ad177-107">可以按日期、位置、策略或操作筛选报告。</span><span class="sxs-lookup"><span data-stu-id="ad177-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="ad177-108">可以使用此报告：</span><span class="sxs-lookup"><span data-stu-id="ad177-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="ad177-109">在测试模式下运行 DLP 策略时调整或优化这些策略。</span><span class="sxs-lookup"><span data-stu-id="ad177-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="ad177-110">您可以查看与内容匹配的特定规则。</span><span class="sxs-lookup"><span data-stu-id="ad177-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="ad177-111">重点关注特定的时间段，并了解峰值和发展趋势的原因。</span><span class="sxs-lookup"><span data-stu-id="ad177-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="ad177-112">发现违反组织的 DLP 策略的业务流程。</span><span class="sxs-lookup"><span data-stu-id="ad177-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="ad177-113">通过查看对内容应用的操作，了解 DLP 策略的任何业务影响。</span><span class="sxs-lookup"><span data-stu-id="ad177-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="ad177-114">通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="ad177-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="ad177-115">查看顶级用户列表，并重复为贵组织的事件做贡献的用户。</span><span class="sxs-lookup"><span data-stu-id="ad177-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="ad177-116">查看组织中最热门敏感信息类型的列表。</span><span class="sxs-lookup"><span data-stu-id="ad177-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="ad177-117">**DLP 事件** 此报告还会显示一段时间的策略匹配，如策略匹配报告。</span><span class="sxs-lookup"><span data-stu-id="ad177-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="ad177-118">但是，策略匹配报告在规则级别显示匹配项;例如，如果电子邮件匹配三个不同的规则，则策略匹配报告显示三个不同的行项目。</span><span class="sxs-lookup"><span data-stu-id="ad177-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="ad177-119">相比之下，事件报告在项目级别显示匹配项;例如，如果电子邮件与三个不同的规则匹配，则事件报告将显示该内容的单个行项。</span><span class="sxs-lookup"><span data-stu-id="ad177-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="ad177-120">由于报告计数的聚合方式不同，因此策略匹配报告更适用于标识特定规则的匹配项并微调 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="ad177-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="ad177-121">事件报告更适用于标识 DLP 策略存在问题的特定内容部分。</span><span class="sxs-lookup"><span data-stu-id="ad177-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="ad177-122">**DLP 误报和重写** 如果您的 DLP 策略允许用户覆盖该策略或报告误报，则此报告显示随着时间的推移此类实例的计数。</span><span class="sxs-lookup"><span data-stu-id="ad177-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="ad177-123">可以按日期、位置或策略筛选报告。</span><span class="sxs-lookup"><span data-stu-id="ad177-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="ad177-124">可以使用此报告：</span><span class="sxs-lookup"><span data-stu-id="ad177-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="ad177-125">通过查看哪些策略导致大量误报来调整或优化 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="ad177-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="ad177-126">查看用户在通过覆盖策略解析策略提示时提交的理由。</span><span class="sxs-lookup"><span data-stu-id="ad177-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="ad177-127">通过引发大量用户替代，发现 DLP 策略与有效业务流程冲突的地方。</span><span class="sxs-lookup"><span data-stu-id="ad177-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="ad177-128">所有 DLP 报告都可以显示最近四个月时间段的数据。</span><span class="sxs-lookup"><span data-stu-id="ad177-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="ad177-129">最新数据最多可能需要 24 小时才能显示在报告中。</span><span class="sxs-lookup"><span data-stu-id="ad177-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="ad177-130">可以在安全与合规中心报告仪表板 &amp; \> **中查找** \> **这些报告**。</span><span class="sxs-lookup"><span data-stu-id="ad177-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP 策略匹配报告](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="ad177-132">查看用户提交的替代理由</span><span class="sxs-lookup"><span data-stu-id="ad177-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="ad177-133">如果您的 DLP 策略允许用户覆盖它，您可以使用误报和替代报告查看策略提示中用户提交的文本。</span><span class="sxs-lookup"><span data-stu-id="ad177-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![DLP 误报和重写报告详细信息的"理由"字段](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="ad177-135">对见解和建议采取措施</span><span class="sxs-lookup"><span data-stu-id="ad177-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="ad177-136">报告可以显示见解和建议，你可以单击红色警告图标查看有关潜在问题的详细信息并采取可能的补救措施。</span><span class="sxs-lookup"><span data-stu-id="ad177-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![单击见解图标以查看详细信息和要采取的操作](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="ad177-138">DLP 报告的权限</span><span class="sxs-lookup"><span data-stu-id="ad177-138">Permissions for DLP reports</span></span>

<span data-ttu-id="ad177-139">若要在安全与合规&查看 DLP 报告，您必须获得以下权限：</span><span class="sxs-lookup"><span data-stu-id="ad177-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="ad177-140">**Exchange 管理** 中心中的安全读者角色。</span><span class="sxs-lookup"><span data-stu-id="ad177-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="ad177-141">默认情况下，此角色分配给 Exchange 管理中心中的组织管理和安全读者角色组。</span><span class="sxs-lookup"><span data-stu-id="ad177-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="ad177-142">**安全与合规中心中的** "仅查看 DLP 合规性&角色。</span><span class="sxs-lookup"><span data-stu-id="ad177-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="ad177-143">默认情况下，此角色分配给安全与合规中心中的合规性管理员、组织管理、安全管理员和安全读者&组。</span><span class="sxs-lookup"><span data-stu-id="ad177-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="ad177-144">**Exchange 管理中心中的** "仅查看收件人"角色。</span><span class="sxs-lookup"><span data-stu-id="ad177-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="ad177-145">默认情况下，此角色分配给 Exchange 管理中心中的合规性管理、组织View-Only组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="ad177-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="ad177-146">查找 DLP 报表的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ad177-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="ad177-147">若要使用安全 &amp; 合规中心的大多数 cmdlet，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ad177-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="ad177-148">使用远程 &amp; PowerShell 连接到安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="ad177-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. <span data-ttu-id="ad177-149">使用以下任一 [安全 &amp; 与合规中心 cmdlet](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ad177-149">Use any of these [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell)</span></span>
    
<span data-ttu-id="ad177-150">但是，DLP 报告需要从 Office 365（包括 Exchange Online）提取数据。</span><span class="sxs-lookup"><span data-stu-id="ad177-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="ad177-151">因此，DLP 报告 cmdlet 在 Exchange Online Powershell 中可用，而不是在安全与合规中心 &amp; Powershell 中提供。</span><span class="sxs-lookup"><span data-stu-id="ad177-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="ad177-152">因此，若要使用适用于 DLP 报告的 cmdlet，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ad177-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="ad177-153">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ad177-153">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="ad177-154">对 DLP 报告使用以下任意 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ad177-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="ad177-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="ad177-155">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [<span data-ttu-id="ad177-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="ad177-156">Get-DlpDetailReport</span></span>](/powershell/module/exchange/get-dlpdetailreport)
