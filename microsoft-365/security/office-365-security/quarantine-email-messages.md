---
title: 隔离的电子邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的隔离，其中包含可能存在危险或不需要的邮件。
ms.openlocfilehash: a5e18ff4b1573e8aa2e7c6b58ab291d3dfb84d81
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412414"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="41883-103">EOP 中隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="41883-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="41883-104">在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，隔离功能可用于保留潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="41883-105">如果发现 *任何* 附件包含恶意软件，反恶意软件策略将自动隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="41883-106">有关详细信息，请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="41883-107">默认情况下，反垃圾邮件策略隔离网络钓鱼邮件，并将垃圾邮件和批量电子邮件传递到用户的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="41883-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="41883-108">不过，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="41883-109">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="41883-110">用户和管理员都可以使用隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="41883-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="41883-111">管理员可对所有用户使用所有类型的已隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="41883-112">仅管理员可以处理被隔离为恶意软件、高可信度网络钓鱼或邮件流规则的结果的邮件 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="41883-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="41883-113">有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="41883-114">如果邮件被隔离为垃圾邮件、批量电子邮件或 (从2020年4月) 网络钓鱼，则用户可以使用这些邮件作为收件人。</span><span class="sxs-lookup"><span data-stu-id="41883-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="41883-115">有关详细信息，请参阅 [在 EOP 中以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="41883-116">为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的 **网络钓鱼电子邮件** 筛选判定功能配置不同的操作。</span><span class="sxs-lookup"><span data-stu-id="41883-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="41883-117">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="41883-118">管理员和用户可以向在隔离中的 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="41883-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="41883-119">有关隔离的详细信息，请参阅 [隔离 FAQ](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
