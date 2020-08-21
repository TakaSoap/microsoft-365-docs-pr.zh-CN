---
title: 已隔离的电子邮件
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
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP 服务器中) 保存潜在危险或不需要的邮件的隔离。
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826797"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="06ae0-103">EOP 中的已隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="06ae0-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="06ae0-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织中或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能可用于保存潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="06ae0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="06ae0-105">如果发现任何附件包含恶意软件，反 *恶意软件策略会自动* 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="06ae0-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="06ae0-106">有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="06ae0-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="06ae0-107">默认情况下，反垃圾邮件策略会隔离网络钓鱼邮件，并将垃圾邮件和批量电子邮件传递到用户的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="06ae0-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="06ae0-108">但是，您还可以创建和自定义反垃圾邮件策略来隔离垃圾邮件和批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06ae0-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="06ae0-109">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="06ae0-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="06ae0-110">用户和管理员均可以使用隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="06ae0-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="06ae0-111">管理员可以处理所有用户的全部类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="06ae0-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="06ae0-112">只有管理员可以处理被隔离为恶意软件或高可信度网络钓鱼的邮件，或者邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="06ae0-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="06ae0-113">有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="06ae0-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="06ae0-114">用户可以处理自 2020 年 4 月起将邮件隔离为垃圾邮件、批量电子邮件或从 2020 年 4 月起作为垃圾邮件、批量电子邮件或 (的邮件隔离在哪) 个隔离邮件中。</span><span class="sxs-lookup"><span data-stu-id="06ae0-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="06ae0-115">有关详细信息，请参阅在 [EOP 中以用户身份查找和释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="06ae0-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="06ae0-116">若要防止用户管理自己的隔离网络钓鱼邮件，管理员可以在反垃圾邮件策略中为钓鱼 **电子邮件** 筛选裁定配置不同的操作。</span><span class="sxs-lookup"><span data-stu-id="06ae0-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="06ae0-117">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="06ae0-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="06ae0-118">管理员和用户可以隔离为 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="06ae0-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="06ae0-119">有关隔离的详细信息，请参阅"隔离[常见问题解答"。](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="06ae0-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
