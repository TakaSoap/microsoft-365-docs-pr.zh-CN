---
title: 使用 Exchange Online 和安全与合规中心来遵守 SEC 规则 17a-4
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 配置 Exchange Online 与合规中心，帮助满足 CFTC Rule 1.31(c)-(d)、 FINRA Rule 4511 和 SEC Rule 17a-4 的法规要求。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127299"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="60043-103">使用 Exchange Online 和安全与合规中心来遵守 SEC 规则 17a-4</span><span class="sxs-lookup"><span data-stu-id="60043-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="60043-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="60043-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="60043-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="60043-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="60043-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="60043-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="60043-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="60043-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="60043-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="60043-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="60043-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="60043-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="60043-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="60043-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="60043-111">为了帮助这些组织更好地了解如何利用安全与合规中心来履行其对 Exchange Online 的监管义务，特别是与规则 17a-4 要求相关的监管义务，我们已与 Cohasset Associates 合作发布了一份评估报告。</span><span class="sxs-lookup"><span data-stu-id="60043-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="60043-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="60043-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="60043-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="60043-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="60043-114">下载 Cohasset 评估报告</span><span class="sxs-lookup"><span data-stu-id="60043-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="60043-115">可[在此处下载 Cohasset 评估报告](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)。</span><span class="sxs-lookup"><span data-stu-id="60043-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Cohasset Associates 可下载评估的标题页](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="60043-117">此评估专门针对 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="60043-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="60043-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="60043-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="60043-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="60043-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="60043-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="60043-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="60043-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="60043-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="60043-122">使用保留锁定是推荐配置的关键</span><span class="sxs-lookup"><span data-stu-id="60043-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="60043-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="60043-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="60043-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="60043-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="60043-125">在规定的保留期内保留，不能缩短，只能增加。</span><span class="sxs-lookup"><span data-stu-id="60043-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="60043-126">不可变，即在要求的保留期间，不能覆盖、删除或更改记录。</span><span class="sxs-lookup"><span data-stu-id="60043-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="60043-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="60043-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="60043-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="60043-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="60043-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="60043-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="60043-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="60043-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="60043-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="60043-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="60043-132">策略的保留期限只能增加，不能缩短。</span><span class="sxs-lookup"><span data-stu-id="60043-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="60043-133">可以将用户添加到策略，但不能删除用户。</span><span class="sxs-lookup"><span data-stu-id="60043-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="60043-134">管理员无法删除保留策略。</span><span class="sxs-lookup"><span data-stu-id="60043-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="60043-135">保留锁定可有助于满足 SEC 17a-4 法规要求。</span><span class="sxs-lookup"><span data-stu-id="60043-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="60043-136">如何设置保留锁定</span><span class="sxs-lookup"><span data-stu-id="60043-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="60043-137">你可以使用 PowerShell 来锁定保留策略。</span><span class="sxs-lookup"><span data-stu-id="60043-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="60043-138">有关详细信息，请参阅[使用保留锁定遵从合规性要求](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)。</span><span class="sxs-lookup"><span data-stu-id="60043-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="60043-139">已知限制</span><span class="sxs-lookup"><span data-stu-id="60043-139">Known limitations</span></span>

<span data-ttu-id="60043-140">目前，Exchange Online 有一些限制：</span><span class="sxs-lookup"><span data-stu-id="60043-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="60043-141">线程通信不适用于 Teams 聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="60043-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="60043-142">不会为 Teams 聊天和频道消息保留赞。</span><span class="sxs-lookup"><span data-stu-id="60043-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="60043-143">项目级审核现已在 Microsoft 365 组邮箱中可用。</span><span class="sxs-lookup"><span data-stu-id="60043-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="60043-144">有关详细信息，请参阅[管理邮箱审核](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="60043-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
