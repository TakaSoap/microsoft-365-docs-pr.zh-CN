---
title: 使用 Microsoft 365 数据丢失防护本地扫描程序（预览版）
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 了解如何使用 Microsoft 365 本地扫描仪扫描停止的数据，并执行本地文件共享和本地 SharePoint 文件夹和文档库的安全操作。
ms.openlocfilehash: b2512c47b82ab3624d892d349611dd3f1e5aed3c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289171"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="a857d-103">使用 Microsoft 365 本地扫描仪的数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="a857d-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="a857d-104">为帮助熟悉 DLP 本地功能，以及如何在 DLP 策略中显示这些功能，我们汇集了一些方案供你遵循。</span><span class="sxs-lookup"><span data-stu-id="a857d-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a857d-105">这些 DLP 本地方案不是创建和调整 DLP 策略的正式过程。</span><span class="sxs-lookup"><span data-stu-id="a857d-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="a857d-106">当你需要在常规情况下使用 DLP 策略，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a857d-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>
> - [<span data-ttu-id="a857d-107">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="a857d-107">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
> - [<span data-ttu-id="a857d-108">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="a857d-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
> - [<span data-ttu-id="a857d-109">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="a857d-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
> - [<span data-ttu-id="a857d-110">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="a857d-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="a857d-111">方案：发现与 DLP 规则相匹配的文件</span><span class="sxs-lookup"><span data-stu-id="a857d-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="a857d-112">DLP 本地扫描仪在几个区域出现数据</span><span class="sxs-lookup"><span data-stu-id="a857d-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="a857d-113">活动资源管理器</span><span class="sxs-lookup"><span data-stu-id="a857d-113">Activity explorer</span></span>

 <span data-ttu-id="a857d-114">本地 Microsoft DLP 可检测 DLP 规则匹配项，并报告它们 [活动资源管理器](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)。</span><span class="sxs-lookup"><span data-stu-id="a857d-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span>

#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="a857d-115">Microsoft 365 审核日志</span><span class="sxs-lookup"><span data-stu-id="a857d-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="a857d-116">在公共预览期间，DLP 规则匹配项在审核日志 UI 中可用，请参阅 [在合规中心](search-the-audit-log-in-security-and-compliance.md)  中搜索审核日志，或由 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell 访问。</span><span class="sxs-lookup"><span data-stu-id="a857d-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="a857d-117">AIP</span><span class="sxs-lookup"><span data-stu-id="a857d-117">AIP</span></span>

<span data-ttu-id="a857d-118">发现数据以 csv 格式的本地报告提供，存储在以下格式：</span><span class="sxs-lookup"><span data-stu-id="a857d-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="a857d-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv**。</span><span class="sxs-lookup"><span data-stu-id="a857d-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="a857d-120">查找以下列：</span><span class="sxs-lookup"><span data-stu-id="a857d-120">Look for the following columns:</span></span>

- <span data-ttu-id="a857d-121">DLP 模式</span><span class="sxs-lookup"><span data-stu-id="a857d-121">DLP Mode</span></span>
- <span data-ttu-id="a857d-122">DLP 状态</span><span class="sxs-lookup"><span data-stu-id="a857d-122">DLP Status</span></span>
- <span data-ttu-id="a857d-123">DLP 批注</span><span class="sxs-lookup"><span data-stu-id="a857d-123">DLP Comment</span></span>
- <span data-ttu-id="a857d-124">DLP 规则名称</span><span class="sxs-lookup"><span data-stu-id="a857d-124">DLP Rule Name</span></span>
- <span data-ttu-id="a857d-125">DLP 操作</span><span class="sxs-lookup"><span data-stu-id="a857d-125">DLP Actions</span></span>
- <span data-ttu-id="a857d-126">所有者</span><span class="sxs-lookup"><span data-stu-id="a857d-126">Owner</span></span>
- <span data-ttu-id="a857d-127">当前 NTFS 权限 （SDTFS）</span><span class="sxs-lookup"><span data-stu-id="a857d-127">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="a857d-128">已应用 NTFS 权限 （SDTF）</span><span class="sxs-lookup"><span data-stu-id="a857d-128">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="a857d-129">NTFS 权限类型</span><span class="sxs-lookup"><span data-stu-id="a857d-129">NTFS permissions type</span></span>

### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="a857d-130">方案：强制实施 DLP 规则</span><span class="sxs-lookup"><span data-stu-id="a857d-130">Scenario: Enforce DLP rule</span></span>

<span data-ttu-id="a857d-131">如果要对扫描的文件强制实施 DLP 规则，必须在 AIP 中的内容扫描作业和 DLP 中的策略级别启用强制。</span><span class="sxs-lookup"><span data-stu-id="a857d-131">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>

#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="a857d-132">配置 DLP 以强制实施策略操作</span><span class="sxs-lookup"><span data-stu-id="a857d-132">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="a857d-133">打开 [数据丢失防护页面](https://compliance.microsoft.com/datalossprevention?viewid=policies) 并选择针对在 AIP 中配置本地位置存储库的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="a857d-133">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span>
2. <span data-ttu-id="a857d-134">编辑策略。</span><span class="sxs-lookup"><span data-stu-id="a857d-134">Edit the policy.</span></span>
3. <span data-ttu-id="a857d-135">在" **测试"或打开策略** 页上，选择 **是，然后**。</span><span class="sxs-lookup"><span data-stu-id="a857d-135">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a857d-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a857d-136">See also</span></span>

- [<span data-ttu-id="a857d-137">了解 DLP 本地扫描仪（预览）</span><span class="sxs-lookup"><span data-stu-id="a857d-137">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="a857d-138">开始使用 DLP 本地扫描仪（预览）</span><span class="sxs-lookup"><span data-stu-id="a857d-138">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="a857d-139">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="a857d-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="a857d-140">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="a857d-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a857d-141">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="a857d-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
