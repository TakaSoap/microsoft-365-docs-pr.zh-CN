---
title: 使用用户垃圾邮件通知释放和报告隔离的邮件
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
ms.openlocfilehash: 641efc024a2842f30f7754c52f624a9f668851de
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636412"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="438c2-103">使用用户垃圾邮件通知释放和报告隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="438c2-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="438c2-104">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection （EOP）组织中，隔离会在 Microsoft 365 组织中保留可能有害或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="438c2-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="438c2-105">有关详细信息，请参阅 [Office 365 中的隔离功能](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="438c2-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="438c2-106">默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="438c2-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="438c2-107">当管理员[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)时，收件人将收到有关被隔离为垃圾邮件、批量电子邮件或（截止到4月，2020）的网络钓鱼的邮件的定期通知。</span><span class="sxs-lookup"><span data-stu-id="438c2-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="438c2-108">被隔离为高可信度网络钓鱼、恶意软件或通过邮件流规则（也称为传输规则）的邮件仅适用于管理员。</span><span class="sxs-lookup"><span data-stu-id="438c2-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="438c2-109">有关详细信息，请参阅[在 Office 365 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="438c2-109">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="438c2-110">最终用户垃圾邮件通知包含每个隔离邮件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="438c2-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="438c2-111">**发件人**：隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="438c2-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="438c2-112">**Subject**：隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="438c2-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="438c2-113">**日期**：邮件被隔离的日期和时间（以 UTC 为单位）。</span><span class="sxs-lookup"><span data-stu-id="438c2-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="438c2-114">**阻止发件人**：单击此链接可将发件人添加到阻止发件人列表。</span><span class="sxs-lookup"><span data-stu-id="438c2-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="438c2-115">有关详细信息，请参阅[在 Outlook 中阻止邮件发件人](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="438c2-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="438c2-116">**Release**：对于垃圾邮件（不是网络钓鱼）邮件，您可以在此处释放邮件，而无需隔离安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="438c2-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="438c2-117">**查看**：单击此链接可转到 Security & 合规性中心中的隔离，可在其中释放、删除或报告隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="438c2-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="438c2-118">有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="438c2-118">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)
