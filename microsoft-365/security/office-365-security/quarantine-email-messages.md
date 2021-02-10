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
description: 管理员可以了解 Exchange Online Protection (EOP) 具有潜在危险或不需要的邮件的隔离。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b111ea0d07453ef4280ec9e57247c8215420074
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167403"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="2dbff-103">EOP 中的隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="2dbff-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2dbff-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="2dbff-104">**Applies to**</span></span>
- [<span data-ttu-id="2dbff-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2dbff-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
-   [<span data-ttu-id="2dbff-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2dbff-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
-   [<span data-ttu-id="2dbff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2dbff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="2dbff-108">在具有 Exchange Online 邮箱的 Microsoft 365 组织或独立 Exchange Online Protection (EOP) 组织中，可以使用隔离来保留潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="2dbff-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="2dbff-109">如果发现任何附件包含恶意软件，反恶意软件策略将自动隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="2dbff-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="2dbff-110">有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2dbff-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="2dbff-111">默认情况下，反垃圾邮件策略隔离网络钓鱼邮件，将垃圾邮件和批量电子邮件发送到用户的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="2dbff-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="2dbff-112">但是，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2dbff-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="2dbff-113">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2dbff-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="2dbff-114">用户和管理员可以使用隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="2dbff-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="2dbff-115">管理员可以为所有用户使用所有类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="2dbff-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="2dbff-116">只有管理员才能处理被隔离为恶意软件、高可信度网络钓鱼或邮件流规则的邮件 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="2dbff-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="2dbff-117">有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="2dbff-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="2dbff-118">如果自 2020 年 4 月钓鱼邮件起被隔离为垃圾邮件、批量电子邮件或邮件 (，用户可以处理作为收件人的隔离) 邮件。</span><span class="sxs-lookup"><span data-stu-id="2dbff-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="2dbff-119">有关详细信息，请参阅 [查找并释放隔离邮件作为 EOP 中的用户](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="2dbff-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="2dbff-120">为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的网络钓鱼电子邮件筛选裁定配置不同的操作。 </span><span class="sxs-lookup"><span data-stu-id="2dbff-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="2dbff-121">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2dbff-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="2dbff-122">管理员和用户可以在隔离时向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="2dbff-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="2dbff-123">有关隔离的更多详细信息，请参阅隔离 [常见问题解答](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="2dbff-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
