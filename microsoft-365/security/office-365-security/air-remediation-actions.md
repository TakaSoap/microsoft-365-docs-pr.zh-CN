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
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955529"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="71c81-104">Office 365 中的自动调查遵循的补救措施</span><span class="sxs-lookup"><span data-stu-id="71c81-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="71c81-105">修正操作</span><span class="sxs-lookup"><span data-stu-id="71c81-105">Remediation actions</span></span>

<span data-ttu-id="71c81-106">Office 365 中的[自动化调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)（AIR）[高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（Office 365 ATP）计划2包括某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="71c81-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="71c81-107">当自动调查运行或完成时，您通常会看到一个或多个需要安全操作团队批准才能继续执行的修正操作。</span><span class="sxs-lookup"><span data-stu-id="71c81-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="71c81-108">下表汇总了 Office 365 ATP 中当前提供的补救措施。</span><span class="sxs-lookup"><span data-stu-id="71c81-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="71c81-109">操作</span><span class="sxs-lookup"><span data-stu-id="71c81-109">Action</span></span> | <span data-ttu-id="71c81-110">说明</span><span class="sxs-lookup"><span data-stu-id="71c81-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="71c81-111">阻止 URL（单击时）</span><span class="sxs-lookup"><span data-stu-id="71c81-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="71c81-112">针对包含恶意 Url 的电子邮件和文档提供保护。</span><span class="sxs-lookup"><span data-stu-id="71c81-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="71c81-113">这样，当用户单击现有 Office 文件或旧电子邮件中的链接时，可以通过[安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)阻止恶意链接和任何相关的网页。</span><span class="sxs-lookup"><span data-stu-id="71c81-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="71c81-114">软删除电子邮件</span><span class="sxs-lookup"><span data-stu-id="71c81-114">Soft delete email</span></span>  |<span data-ttu-id="71c81-115">软删除用户邮箱中的特定电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71c81-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="71c81-116">软删除的邮件将移至用户的 "可恢复的项目" 文件夹中，并将一直保留，直到已删除项目的保留期过期。</span><span class="sxs-lookup"><span data-stu-id="71c81-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="71c81-117">软删除电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="71c81-117">Soft delete email clusters</span></span>  |<span data-ttu-id="71c81-118">软删除与所有用户邮箱中的查询相匹配的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71c81-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="71c81-119">软删除的邮件将移至用户的 "可恢复的项目" 文件夹，并在已删除项目的保留期过期之前保留。</span><span class="sxs-lookup"><span data-stu-id="71c81-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="71c81-120">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="71c81-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="71c81-121">从特定最终用户的邮箱中删除转发规则。</span><span class="sxs-lookup"><span data-stu-id="71c81-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="71c81-122">在 Office 365 ATP 中，不会自动执行任何修正操作。</span><span class="sxs-lookup"><span data-stu-id="71c81-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="71c81-123">仅在组织的安全团队进行审批时才采取更正措施。</span><span class="sxs-lookup"><span data-stu-id="71c81-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="71c81-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="71c81-124">Next steps</span></span>

- [<span data-ttu-id="71c81-125">查看 Office 365 中的自动调查后的挂起或已完成的修正操作</span><span class="sxs-lookup"><span data-stu-id="71c81-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="71c81-126">Office 365 中的自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="71c81-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="71c81-127">相关文章</span><span class="sxs-lookup"><span data-stu-id="71c81-127">Related articles</span></span>

- [<span data-ttu-id="71c81-128">Microsoft Defender 高级威胁防护中的自动调查</span><span class="sxs-lookup"><span data-stu-id="71c81-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="71c81-129">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="71c81-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)