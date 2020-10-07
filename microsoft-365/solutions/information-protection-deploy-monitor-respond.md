---
title: 监视和响应组织中的数据隐私事件
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
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
description: 使用审核和通知策略和数据主体请求来监视和响应个人数据事件。
ms.openlocfilehash: 296220ac8b34d9ce10c783194b78ca344e746b84
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377195"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="1b4c2-103">监视和响应组织中的数据隐私事件</span><span class="sxs-lookup"><span data-stu-id="1b4c2-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="1b4c2-104">Microsoft 365 功能可帮助您在您的组织中监视、调查数据隐私事件并在 operationalize 相关功能时对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="1b4c2-105">对于上述每种情况，拥有过程、过程和其他文档可能也非常重要，这也是证明合规性的合规性。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="1b4c2-106">具体包括：</span><span class="sxs-lookup"><span data-stu-id="1b4c2-106">These include:</span></span> 

- <span data-ttu-id="1b4c2-107">审核和警报策略</span><span class="sxs-lookup"><span data-stu-id="1b4c2-107">Auditing and alert policies</span></span>
- <span data-ttu-id="1b4c2-108">数据主体请求 (包括内容搜索和电子数据展示) </span><span class="sxs-lookup"><span data-stu-id="1b4c2-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="1b4c2-109">其他调查工具和报告</span><span class="sxs-lookup"><span data-stu-id="1b4c2-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="1b4c2-110">影响监控和响应工具的使用的数据隐私法规</span><span class="sxs-lookup"><span data-stu-id="1b4c2-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="1b4c2-111">下面的示例列出了可能与信息治理控制相关的数据隐私法规：</span><span class="sxs-lookup"><span data-stu-id="1b4c2-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="1b4c2-112">LGPD 文章46</span><span class="sxs-lookup"><span data-stu-id="1b4c2-112">LGPD Article 46</span></span>
- <span data-ttu-id="1b4c2-113">LGPD 文章48</span><span class="sxs-lookup"><span data-stu-id="1b4c2-113">LGPD Article 48</span></span>
- <span data-ttu-id="1b4c2-114">GDPR 文章 (5) # B2 1) # B4 f) </span><span class="sxs-lookup"><span data-stu-id="1b4c2-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="1b4c2-115">GDPR 文章 (15) # B2 1) # B4 e) </span><span class="sxs-lookup"><span data-stu-id="1b4c2-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="1b4c2-116">HIPAA-高科技 (45 C.F.R。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="1b4c2-117">164.308 () # B2 1) # B4 ii) # B6 D) # A8</span><span class="sxs-lookup"><span data-stu-id="1b4c2-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="1b4c2-118">HIPAA-高科技 (45 C.F.R。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="1b4c2-119">164.308 () # B2 6) # B4 ii) </span><span class="sxs-lookup"><span data-stu-id="1b4c2-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="1b4c2-120">HIPAA-高科技 (45 C.F.R。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="1b4c2-121">164.312 (b) # A2</span><span class="sxs-lookup"><span data-stu-id="1b4c2-121">164.312(b))</span></span>
- <span data-ttu-id="1b4c2-122">CCPA (1798.105 (c) # A3</span><span class="sxs-lookup"><span data-stu-id="1b4c2-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="1b4c2-123">有关详细信息，请参阅 [评估数据隐私风险和标识敏感信息](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="1b4c2-124">通常情况下，数据隐私管理法规要求进行监视和响应：</span><span class="sxs-lookup"><span data-stu-id="1b4c2-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="1b4c2-125">有关与存储、共享和处理个人数据相关的活动的审核、警报和报告</span><span class="sxs-lookup"><span data-stu-id="1b4c2-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="1b4c2-126">对数据主体请求 (DSR) 的能力，在某些情况下，执行调查和其他管理措施以遵守此类请求。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="1b4c2-127">您的组织可能还希望出于其他目的（如其他合规性需求或业务原因）执行监视和响应活动。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="1b4c2-128">在整体监控和响应规划、实施和管理的过程中，建立用于数据隐私的监控和响应方案。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="1b4c2-129">为了帮助您开始使用 Microsoft 365 中的监控和响应方案来获取数据隐私法规，本文列出了 Microsoft 365 中的有用功能，以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="1b4c2-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="1b4c2-130">对于不同的数据类型和源，可使用哪种日常监控、调查和报告技术？</span><span class="sxs-lookup"><span data-stu-id="1b4c2-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="1b4c2-131">处理数据主体请求 (Dsr) 和任何补救措施（如 anonymization、密文和删除）将需要哪些机制。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="1b4c2-132">安全与合规中心中的审核和警报策略</span><span class="sxs-lookup"><span data-stu-id="1b4c2-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="1b4c2-133">有关设置审核、高级审核和通知策略的相关文章，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="1b4c2-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="1b4c2-134">统一审核</span><span class="sxs-lookup"><span data-stu-id="1b4c2-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="1b4c2-135">邮箱审核</span><span class="sxs-lookup"><span data-stu-id="1b4c2-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="1b4c2-136">高级审核</span><span class="sxs-lookup"><span data-stu-id="1b4c2-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="1b4c2-137">警报策略</span><span class="sxs-lookup"><span data-stu-id="1b4c2-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="1b4c2-138">GDPR 和 CCPA 的数据主体请求</span><span class="sxs-lookup"><span data-stu-id="1b4c2-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="1b4c2-139">有关 [GDPR 和 CCPA 的数据主体请求](../compliance/gdpr-dsr-office365.md) ，请参阅有关在 Microsoft 365 中响应 DSR 的信息。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="1b4c2-140">在 Microsoft Stream 中管理已删除的用户</span><span class="sxs-lookup"><span data-stu-id="1b4c2-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="1b4c2-141">对于 Microsoft Stream，当从 Azure Active Directory (Azure AD) 中删除用户时，如果其名称与之前发布的流视频相关联，则他们的电子邮件地址仍与该视频相关联。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="1b4c2-142">请参阅 [从 Microsoft Stream 管理已删除的用户](https://docs.microsoft.com/stream/managing-deleted-users) 以将其删除。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="1b4c2-143">其他调查工具</span><span class="sxs-lookup"><span data-stu-id="1b4c2-143">Additional investigative tools</span></span>

<span data-ttu-id="1b4c2-144">以下是在组织中监视、调查和修正与数据隐私相关的事件时可能有用的两个附加工具：</span><span class="sxs-lookup"><span data-stu-id="1b4c2-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="1b4c2-145">[内幕风险管理在 microsoft 365 中](../compliance/insider-risk-management.md)，Microsoft 合规性管理中心的一项功能，通过使您能够检测、调查和对组织中的危险活动采取措施来帮助最大限度地减少内部风险。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="1b4c2-146">Microsoft [365 中的数据调查](../compliance/overview-data-investigations.md)是 Microsoft 合规性管理中心的一项功能，用于在 microsoft 365 中搜索敏感、恶意或放错位置的数据，然后调查执行相应操作以修正事件所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="1b4c2-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
