---
title: Office 365 中的补救措施自动化调查和响应
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 高级威胁防护计划2中的自动调查和响应功能中的补救措施。
ms.openlocfilehash: e75ef1523247cbddcf6cb28d69a889db1de8e42f
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228528"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="72412-104">Office 365 中的自动调查遵循的补救措施</span><span class="sxs-lookup"><span data-stu-id="72412-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions-overview"></a><span data-ttu-id="72412-105">修正操作概述</span><span class="sxs-lookup"><span data-stu-id="72412-105">Remediation actions overview</span></span>

<span data-ttu-id="72412-106">Office 365 中的[自动化调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)高级威胁防护包括某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="72412-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="72412-107">当自动调查运行或完成时，您通常会看到一个或多个需要安全操作团队批准才能继续执行的修正操作。</span><span class="sxs-lookup"><span data-stu-id="72412-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> <span data-ttu-id="72412-108">下表汇总了 Office 365 高级威胁防护中当前可用的补救措施。</span><span class="sxs-lookup"><span data-stu-id="72412-108">The following table summarizes remediation actions currently available in Office 365 Advanced Threat Protection.</span></span> 

|<span data-ttu-id="72412-109">操作</span><span class="sxs-lookup"><span data-stu-id="72412-109">Action</span></span> | <span data-ttu-id="72412-110">说明</span><span class="sxs-lookup"><span data-stu-id="72412-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="72412-111">阻止 URL（单击时）</span><span class="sxs-lookup"><span data-stu-id="72412-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="72412-112">针对包含恶意 Url 的电子邮件和文档进行防护。</span><span class="sxs-lookup"><span data-stu-id="72412-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="72412-113">这样，当用户单击现有 Office 文件或旧电子邮件中的链接时，可以通过[安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)阻止恶意链接和任何相关的网页。</span><span class="sxs-lookup"><span data-stu-id="72412-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="72412-114">软删除电子邮件</span><span class="sxs-lookup"><span data-stu-id="72412-114">Soft delete email</span></span>  |<span data-ttu-id="72412-115">软删除用户邮箱中的特定电子邮件</span><span class="sxs-lookup"><span data-stu-id="72412-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="72412-116">软删除电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="72412-116">Soft delete email clusters</span></span>  |<span data-ttu-id="72412-117">软删除与所有用户邮箱中的查询相匹配的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="72412-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="72412-118">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="72412-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="72412-119">从特定最终用户的邮箱中删除转发规则</span><span class="sxs-lookup"><span data-stu-id="72412-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="72412-120">批准（或拒绝）挂起的操作</span><span class="sxs-lookup"><span data-stu-id="72412-120">Approve (or reject) pending actions</span></span>

![航空调查操作页](../../media/air-investigationactionspage.png)

<span data-ttu-id="72412-122">在查看[调查的详细信息](air-view-investigation-results.md)时，您可以批准或拒绝任何待定的修正操作。</span><span class="sxs-lookup"><span data-stu-id="72412-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="72412-123">我们建议您尽快执行此操作，以便您的自动调查能够完成。</span><span class="sxs-lookup"><span data-stu-id="72412-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72412-124">批准或拒绝修正操作需要适当的权限。</span><span class="sxs-lookup"><span data-stu-id="72412-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="72412-125">查看[使用空中功能所需的权限](office-365-air.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="72412-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="72412-126">选择 "**操作**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="72412-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="72412-127">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="72412-127">Select an item in the list.</span></span> <span data-ttu-id="72412-128">（这将激活 "批准" 和 "拒绝" 按钮。）</span><span class="sxs-lookup"><span data-stu-id="72412-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="72412-129">查看您选择的项目的可用信息，然后批准或拒绝该操作。</span><span class="sxs-lookup"><span data-stu-id="72412-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="72412-130">**批准**可开始进行修正。</span><span class="sxs-lookup"><span data-stu-id="72412-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="72412-131">**拒绝**无需进一步操作</span><span class="sxs-lookup"><span data-stu-id="72412-131">**Reject** takes no further action</span></span>

## <a name="related-articles"></a><span data-ttu-id="72412-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="72412-132">Related articles</span></span>

[<span data-ttu-id="72412-133">了解 Microsoft 威胁防护中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="72412-133">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)