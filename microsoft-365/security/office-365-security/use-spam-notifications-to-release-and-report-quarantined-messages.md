---
title: Office 36 中的最终用户垃圾邮件通知
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
description: 当管理员在反垃圾邮件策略中启用最终用户垃圾邮件通知后，邮件收件人将收到有关其隔离邮件的定期通知。
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895055"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="e58de-103">Office 365 中的最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="e58de-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="e58de-104">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection （EOP）组织中，隔离会在 Office 365 组织中保留可能有害或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="e58de-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="e58de-105">有关详细信息，请参阅[Office 365 中的隔离](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e58de-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e58de-106">默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="e58de-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="e58de-107">当管理员[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md)后，邮件收件人将收到有关被隔离为垃圾邮件、批量电子邮件或（截止到4月，2020）的网络钓鱼的邮件的定期通知。</span><span class="sxs-lookup"><span data-stu-id="e58de-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="e58de-108">在10月2019，我们删除了直接从最终用户的垃圾邮件通知中释放隔离邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="e58de-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="e58de-109">相反，用户现在可以转到 Office 365 安全 & 合规中心来释放隔离邮件（直接或通过单击通知中的 "**查看**"）。</span><span class="sxs-lookup"><span data-stu-id="e58de-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="e58de-110">有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="e58de-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="e58de-111">被隔离为高可信度网络钓鱼、恶意软件或通过邮件流规则（也称为传输规则）的邮件仅适用于管理员。</span><span class="sxs-lookup"><span data-stu-id="e58de-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="e58de-112">有关详细信息，请参阅[在 Office 365 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="e58de-112">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="e58de-113">最终用户垃圾邮件通知包含每个隔离邮件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="e58de-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="e58de-114">**发件人**：隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e58de-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="e58de-115">**Subject**：隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="e58de-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="e58de-116">**日期**：邮件被隔离的日期和时间（以 UTC 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e58de-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="e58de-117">**阻止发件人**：单击此链接可将发件人添加到阻止发件人列表。</span><span class="sxs-lookup"><span data-stu-id="e58de-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="e58de-118">**查看**：单击此链接可转到 Security & 合规性中心中的隔离，您可以在其中释放、删除或报告隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="e58de-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)
