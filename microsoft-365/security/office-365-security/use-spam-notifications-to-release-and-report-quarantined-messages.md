---
title: Microsoft 365 中的最终用户垃圾邮件通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中隔离邮件的最终用户垃圾邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287541"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="1ffc0-103">使用用户垃圾邮件通知释放并报告隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="1ffc0-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ffc0-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="1ffc0-104">**Applies to**</span></span>
- [<span data-ttu-id="1ffc0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ffc0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1ffc0-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="1ffc0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1ffc0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ffc0-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="1ffc0-108">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="1ffc0-109">有关详细信息，请参阅 [EOP 中的隔离邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1ffc0-110">默认情况下，最终用户垃圾邮件通知在反垃圾邮件策略中处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="1ffc0-111">当管理员启用[](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)最终用户垃圾邮件通知时， (（包括启用了自动映射的共享邮箱）的) 将收到有关自 202) 0 年 4 月网络钓鱼以来被隔离为垃圾邮件、批量电子邮件或 (的邮件的定期通知。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="1ffc0-112">对于共享邮箱，仅向共享邮箱授予 FullAccess 权限的用户支持最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="1ffc0-113">有关详细信息，请参阅使用 [EAC 编辑共享邮箱委派](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-113">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="1ffc0-114">组不支持最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="1ffc0-115">被隔离为高可信度网络钓鱼、恶意软件或邮件流规则 (也称为传输规则) 仅对管理员可用。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="1ffc0-116">有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="1ffc0-117">最终用户垃圾邮件通知包含每个隔离邮件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="1ffc0-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="1ffc0-118">**发件人**：隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="1ffc0-119">**主题**：隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="1ffc0-120">**日期**：以 UTC 格式 (邮件) 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="1ffc0-121">**阻止发件人**：单击此链接将发件人添加到阻止的发件人列表。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="1ffc0-122">有关详细信息，请参阅"[阻止邮件发件人"。](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="1ffc0-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="1ffc0-123">**Release**： For spam (not phishing) messages， you can release the message here without going to Quarantine the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1ffc0-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="1ffc0-124">**Review**： Click this link to go quarantine in the Security & Compliance Center， where you can (depending the message was quarantined) view， release， delete or report your quarantined messages.</span><span class="sxs-lookup"><span data-stu-id="1ffc0-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="1ffc0-125">有关详细信息，请参阅查找隔离邮件，并释放隔离邮件 [作为 EOP 中的用户](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="1ffc0-127">阻止的发件人仍可以向您发送邮件。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="1ffc0-128">来自此发件人的任何发送到邮箱的邮件将立即移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="1ffc0-129">来自此发件人的未来邮件将转到您的"垃圾邮件"文件夹或最终用户隔离邮箱。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="1ffc0-130">如果要在到达时删除这些邮件，而不是隔离它们，请使用邮件流规则 [ (](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 也称为传输规则) 到达时删除邮件。</span><span class="sxs-lookup"><span data-stu-id="1ffc0-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>
