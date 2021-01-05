---
title: 监视和响应组织中数据隐私事件
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用审核和警报策略和数据主体请求来监视和响应个人数据事件。
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749583"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="7f78a-103">监视和响应组织中数据隐私事件</span><span class="sxs-lookup"><span data-stu-id="7f78a-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="7f78a-104">Microsoft 365 功能可用于帮助你在操作相关功能时监视、调查和响应组织中数据隐私事件。</span><span class="sxs-lookup"><span data-stu-id="7f78a-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="7f78a-105">拥有每个流程、过程和其他文档对证明监管机构的合规性也很重要。</span><span class="sxs-lookup"><span data-stu-id="7f78a-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="7f78a-106">具体包括：</span><span class="sxs-lookup"><span data-stu-id="7f78a-106">These include:</span></span> 

- <span data-ttu-id="7f78a-107">审核和警报策略</span><span class="sxs-lookup"><span data-stu-id="7f78a-107">Auditing and alert policies</span></span>
- <span data-ttu-id="7f78a-108">数据主体请求 (包括内容搜索和电子数据展示) </span><span class="sxs-lookup"><span data-stu-id="7f78a-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="7f78a-109">其他调查工具和报告</span><span class="sxs-lookup"><span data-stu-id="7f78a-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="7f78a-110">影响监视和响应工具使用的数据隐私法规</span><span class="sxs-lookup"><span data-stu-id="7f78a-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="7f78a-111">下面是可能与信息治理控制相关的数据隐私法规的示例列表：</span><span class="sxs-lookup"><span data-stu-id="7f78a-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="7f78a-112">LGPD 文章 46</span><span class="sxs-lookup"><span data-stu-id="7f78a-112">LGPD Article 46</span></span>
- <span data-ttu-id="7f78a-113">LGPD 文章 48</span><span class="sxs-lookup"><span data-stu-id="7f78a-113">LGPD Article 48</span></span>
- <span data-ttu-id="7f78a-114">GDPR 文章 (5)  (1)  (f) </span><span class="sxs-lookup"><span data-stu-id="7f78a-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="7f78a-115">GDPR (15)  (1)  (e) </span><span class="sxs-lookup"><span data-stu-id="7f78a-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="7f78a-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="7f78a-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="7f78a-117">164.308 ()  (1)  (ii)  (D) ) </span><span class="sxs-lookup"><span data-stu-id="7f78a-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="7f78a-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="7f78a-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="7f78a-119">164.308 ()  (6)  (ii) </span><span class="sxs-lookup"><span data-stu-id="7f78a-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="7f78a-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="7f78a-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="7f78a-121">164.312 (b) ) </span><span class="sxs-lookup"><span data-stu-id="7f78a-121">164.312(b))</span></span>
- <span data-ttu-id="7f78a-122">CCPA (1798.105 (c) ) </span><span class="sxs-lookup"><span data-stu-id="7f78a-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="7f78a-123">有关详细信息，请参阅"[评估数据隐私风险并识别敏感信息"。](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="7f78a-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="7f78a-124">数据隐私法规通常要求进行以下监视和响应：</span><span class="sxs-lookup"><span data-stu-id="7f78a-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="7f78a-125">审核、警报和报告与个人数据的存储、共享和处理相关的活动</span><span class="sxs-lookup"><span data-stu-id="7f78a-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="7f78a-126">能够响应 DSR (数据主体) 在某些情况下，执行调查和其他管理措施以遵守此类请求。</span><span class="sxs-lookup"><span data-stu-id="7f78a-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="7f78a-127">您的组织可能还希望出于其他目的（如其他合规性需求或出于业务原因）执行监视和响应活动。</span><span class="sxs-lookup"><span data-stu-id="7f78a-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="7f78a-128">为数据隐私建立监控和响应方案应作为整体监视和响应规划、实施和管理的一部分完成。</span><span class="sxs-lookup"><span data-stu-id="7f78a-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="7f78a-129">为了帮助你开始使用 Microsoft 365 中针对数据隐私法规的监视和响应方案，本文列出了 Microsoft 365 中用于回答以下问题的有用功能：</span><span class="sxs-lookup"><span data-stu-id="7f78a-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="7f78a-130">对于不同的数据类型和来源，可以使用哪类日常监视、调查和报告技术？</span><span class="sxs-lookup"><span data-stu-id="7f78a-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="7f78a-131">需要哪些机制来处理 DSR 请求 (DSR) 任何修正操作（如匿名化、修订和删除）。</span><span class="sxs-lookup"><span data-stu-id="7f78a-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="7f78a-132">安全与合规中心中的审核和警报策略</span><span class="sxs-lookup"><span data-stu-id="7f78a-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="7f78a-133">请参阅以下文章以设置审核、高级审核和警报策略：</span><span class="sxs-lookup"><span data-stu-id="7f78a-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="7f78a-134">统一审核</span><span class="sxs-lookup"><span data-stu-id="7f78a-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="7f78a-135">邮箱审核</span><span class="sxs-lookup"><span data-stu-id="7f78a-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="7f78a-136">高级审核</span><span class="sxs-lookup"><span data-stu-id="7f78a-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="7f78a-137">警报策略</span><span class="sxs-lookup"><span data-stu-id="7f78a-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="7f78a-138">针对 GDPR 和 CCPA 的数据主体请求</span><span class="sxs-lookup"><span data-stu-id="7f78a-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="7f78a-139">有关在 Microsoft 365 中响应 DSR 的信息，请参阅 GDPR 和 [CCPA](../compliance/gdpr-dsr-office365.md) 的数据主体请求。</span><span class="sxs-lookup"><span data-stu-id="7f78a-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="7f78a-140">在 Microsoft Stream 中管理已删除的用户</span><span class="sxs-lookup"><span data-stu-id="7f78a-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="7f78a-141">对于 Microsoft Stream，从 Azure Active Directory (Azure AD) 中删除用户时，如果用户姓名与之前发布 Stream 视频相关联，则其电子邮件地址仍与该视频相关联。</span><span class="sxs-lookup"><span data-stu-id="7f78a-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="7f78a-142">请参阅 ["管理 Microsoft Stream 中删除](https://docs.microsoft.com/stream/managing-deleted-users) 的已删除用户"。</span><span class="sxs-lookup"><span data-stu-id="7f78a-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="7f78a-143">内部风险管理作为调查工具</span><span class="sxs-lookup"><span data-stu-id="7f78a-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="7f78a-144">[Microsoft 365](../compliance/insider-risk-management.md) 中的内部风险管理是 Microsoft 合规性管理中心的一项功能，通过让你能够检测、调查和对组织中存在风险的活动采取行动，可帮助你最大程度地降低内部风险。</span><span class="sxs-lookup"><span data-stu-id="7f78a-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
