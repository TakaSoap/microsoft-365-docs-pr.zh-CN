---
title: Microsoft 365 中的最终用户垃圾邮件通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
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
description: 管理员可以在 Exchange Online Protection (EOP) 中了解有关隔离邮件的最终用户垃圾邮件通知。
ms.openlocfilehash: 2786c90f6f5fb66cbb96b0375dacf7793894f72e
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778500"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="1b710-103">使用用户垃圾邮件通知释放和报告隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="1b710-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="1b710-104">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="1b710-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="1b710-105">有关详细信息，请参阅 [EOP 中的隔离邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1b710-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1b710-106">默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1b710-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="1b710-107">当管理员 [启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)时，收件人 (包括启用了自动映射的共享邮箱) 会收到有关其邮件的定期通知，这些邮件被隔离为垃圾邮件、批量电子邮件或 (2020) 的网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="1b710-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="1b710-108">对于共享邮箱，仅对向其授予了对共享邮箱的 FullAccess 权限的用户才支持最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1b710-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="1b710-109">有关详细信息，请参阅 [使用 EAC 编辑共享邮箱委派](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。</span><span class="sxs-lookup"><span data-stu-id="1b710-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="1b710-110">组不支持最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1b710-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="1b710-111">被隔离为高可信度网络钓鱼、恶意软件或邮件流规则的邮件 (也称为传输规则) 仅供管理员使用。</span><span class="sxs-lookup"><span data-stu-id="1b710-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="1b710-112">有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="1b710-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="1b710-113">最终用户垃圾邮件通知包含每个隔离邮件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b710-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="1b710-114">**发件人**：隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1b710-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="1b710-115">**Subject**：隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="1b710-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="1b710-116">**日期**：) 邮件被隔离的日期和时间 (（UTC）。</span><span class="sxs-lookup"><span data-stu-id="1b710-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="1b710-117">**阻止发件人**：单击此链接可将发件人添加到阻止发件人列表。</span><span class="sxs-lookup"><span data-stu-id="1b710-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="1b710-118">有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="1b710-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="1b710-119">**Release**：对于垃圾邮件 (不会) 邮件的网络钓鱼，您可以在此处释放邮件，而无需隔离安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="1b710-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="1b710-120">**查看**：单击此链接可转到 Security & 合规性中心中的隔离，在此 (可以根据邮件被隔离的原因) 查看、释放、删除或报告隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="1b710-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="1b710-121">有关详细信息，请参阅 [在 EOP 中以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1b710-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)
