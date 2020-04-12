---
title: Office 365 中的隔离
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Office 365 中的隔离会保留可能有害或不需要的邮件。 管理员和最终用户可以访问隔离。
ms.openlocfilehash: d3db036210886f7a4607f477bba2cf9f450ed90c
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230929"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="a1e49-104">Office 365 中的隔离</span><span class="sxs-lookup"><span data-stu-id="a1e49-104">Quarantine in Office 365</span></span>

<span data-ttu-id="a1e49-105">如果您是在 Exchange Online 中有邮箱或独立 Exchange Online Protection （EOP）客户但没有 Exchange Online 邮箱的 Office 365 客户，则可以使用隔离来保存可能有害的邮件。</span><span class="sxs-lookup"><span data-stu-id="a1e49-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="a1e49-106">如果发现*任何*附件包含恶意软件，反恶意软件策略将自动隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="a1e49-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="a1e49-107">有关详细信息，请参阅[在 Office 365 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e49-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="a1e49-108">默认情况下，反垃圾邮件策略隔离网络钓鱼邮件，并将垃圾邮件和批量电子邮件传递到用户的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a1e49-108">By default, anti-spam policies quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="a1e49-109">不过，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a1e49-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="a1e49-110">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e49-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a1e49-111">用户和管理员都可以使用隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="a1e49-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="a1e49-112">管理员可对所有用户使用所有类型的已隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="a1e49-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="a1e49-113">只有管理员可以处理被隔离为恶意软件、高可信度网络钓鱼的邮件或邮件流规则（也称为传输规则）的结果。</span><span class="sxs-lookup"><span data-stu-id="a1e49-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a1e49-114">有关详细信息，请参阅[在 Office 365 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e49-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="a1e49-115">如果邮件被隔离为垃圾邮件、批量电子邮件或（从2020年4月，）的网络钓鱼，则用户可以使用它们作为收件人的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="a1e49-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="a1e49-116">有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e49-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="a1e49-117">为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的**网络钓鱼电子邮件**筛选判定功能配置不同的操作。</span><span class="sxs-lookup"><span data-stu-id="a1e49-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="a1e49-118">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e49-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="a1e49-119">管理员和用户可以向在隔离中的 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="a1e49-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="a1e49-120">有关隔离的详细信息，请参阅[隔离 FAQ](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e49-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
