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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 包含潜在危险或不需要的邮件的隔离。
ms.openlocfilehash: 8a978ece029de06bcb7b434de730b0baea33a5e1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794324"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="1a69b-103">EOP 中的隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="1a69b-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1a69b-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织或独立 Exchange Online Protection (EOP) 组织中，可以使用隔离来保留潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="1a69b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="1a69b-105">如果发现任何附件包含恶意软件，反恶意软件策略将自动隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="1a69b-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="1a69b-106">有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1a69b-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="1a69b-107">默认情况下，反垃圾邮件策略隔离网络钓鱼邮件，将垃圾邮件和批量电子邮件发送到用户的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="1a69b-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="1a69b-108">但是，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1a69b-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="1a69b-109">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1a69b-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="1a69b-110">用户和管理员可以使用隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="1a69b-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="1a69b-111">管理员可以为所有用户使用所有类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="1a69b-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="1a69b-112">只有管理员才能处理被隔离为恶意软件、高可信度网络钓鱼的邮件，或者由于邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="1a69b-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1a69b-113">有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="1a69b-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="1a69b-114">如果自 2020 年 4 月网络钓鱼起，邮件被隔离为垃圾邮件、批量电子邮件或 (，用户可以处理作为收件人的隔离邮件) 邮件。</span><span class="sxs-lookup"><span data-stu-id="1a69b-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="1a69b-115">有关详细信息，请参阅在 EOP 中查找并释放作为 [用户隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1a69b-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="1a69b-116">为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的网络钓鱼电子邮件筛选裁定配置不同的操作。 </span><span class="sxs-lookup"><span data-stu-id="1a69b-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="1a69b-117">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1a69b-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="1a69b-118">管理员和用户可以在隔离时向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="1a69b-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="1a69b-119">有关隔离功能详细信息，请参阅隔离 [常见问题解答](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="1a69b-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
