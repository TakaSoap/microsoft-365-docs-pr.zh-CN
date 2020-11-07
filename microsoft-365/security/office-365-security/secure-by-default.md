---
title: 默认情况下在 Office 365 中安全
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '有关详细信息，请参阅 Exchange Online Protection (EOP 中的默认安全设置) '
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945326"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="5d360-103">默认情况下在 Office 365 中安全</span><span class="sxs-lookup"><span data-stu-id="5d360-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5d360-104">"默认情况下安全" 是一种术语，用于定义尽可能安全的默认设置。</span><span class="sxs-lookup"><span data-stu-id="5d360-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="5d360-105">但是，安全性需要与工作效率平衡。</span><span class="sxs-lookup"><span data-stu-id="5d360-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="5d360-106">这可能包括跨以下各项的平衡：</span><span class="sxs-lookup"><span data-stu-id="5d360-106">This can include balancing across:</span></span>

- <span data-ttu-id="5d360-107">可用性：设置不应以用户工作效率为依据。</span><span class="sxs-lookup"><span data-stu-id="5d360-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="5d360-108">风险：安全性可能会阻止重要活动。</span><span class="sxs-lookup"><span data-stu-id="5d360-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="5d360-109">旧版设置：出于商业原因，可能需要维护某些旧产品和功能的一些配置，即使新的新式设置得到改进也是如此。</span><span class="sxs-lookup"><span data-stu-id="5d360-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="5d360-110">通过 exchange online 中邮箱的 Microsoft 365 组织受到 Exchange Online Protection (EOP) 的保护。</span><span class="sxs-lookup"><span data-stu-id="5d360-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="5d360-111">此保护包括：</span><span class="sxs-lookup"><span data-stu-id="5d360-111">This protection includes:</span></span>

1. <span data-ttu-id="5d360-112">带有可疑恶意软件的电子邮件将自动被隔离，收件人将收到通知。</span><span class="sxs-lookup"><span data-stu-id="5d360-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="5d360-113">请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5d360-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="5d360-114">被标识为 "高可信度" 的网络钓鱼电子邮件将根据反垃圾邮件策略操作进行处理。</span><span class="sxs-lookup"><span data-stu-id="5d360-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="5d360-115">请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5d360-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="5d360-116">由于 Microsoft 想让我们的客户在默认情况下是安全的，因此某些租户替代不会应用于恶意软件或高可信度网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="5d360-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="5d360-117">这些替代包括：</span><span class="sxs-lookup"><span data-stu-id="5d360-117">These overrides include:</span></span>

- <span data-ttu-id="5d360-118"> (反垃圾邮件策略的允许的发件人列表或允许的域列表) </span><span class="sxs-lookup"><span data-stu-id="5d360-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="5d360-119">Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="5d360-119">Outlook Safe senders</span></span>
- <span data-ttu-id="5d360-120"> (连接筛选的 IP 允许列表) </span><span class="sxs-lookup"><span data-stu-id="5d360-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="5d360-121">有关这些覆盖的详细信息，可参阅 [创建安全发件人列表](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="5d360-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="5d360-122">默认情况下安全保护此处的设置不是可以打开或关闭的设置，但我们的筛选功能在框中的工作方式将可能有害或不需要的邮件保留在邮箱之外。</span><span class="sxs-lookup"><span data-stu-id="5d360-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="5d360-123">应将恶意软件和高可信度网络钓鱼发送到隔离区。</span><span class="sxs-lookup"><span data-stu-id="5d360-123">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="5d360-124">只有管理员可以管理被隔离为恶意软件或高可信度的网络钓鱼的邮件，也可以在那里向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="5d360-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="5d360-125">有关详细信息，请参阅 [在 EOP 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="5d360-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="5d360-126">Exceptions</span><span class="sxs-lookup"><span data-stu-id="5d360-126">Exceptions</span></span>

<span data-ttu-id="5d360-127">将绕过所有筛选器的唯一替代包括：</span><span class="sxs-lookup"><span data-stu-id="5d360-127">The only overrides that will bypass all filters include:</span></span>

- <span data-ttu-id="5d360-128">Exchange 传输规则 (ETR) /mail 流规则。</span><span class="sxs-lookup"><span data-stu-id="5d360-128">Exchange Transport Rules (ETR)/mail flow rules.</span></span> <span data-ttu-id="5d360-129">使用邮件流规则在 EOP 中的邮件中设置垃圾邮件可信度级别 (SCL) 。</span><span class="sxs-lookup"><span data-stu-id="5d360-129">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="5d360-130">租户允许/阻止列表：管理租户允许/阻止列表中的 Url 和文件。</span><span class="sxs-lookup"><span data-stu-id="5d360-130">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="5d360-131">这些替代类型适用于：</span><span class="sxs-lookup"><span data-stu-id="5d360-131">These types of overrides are useful for:</span></span>

- <span data-ttu-id="5d360-132">网络钓鱼模拟：模拟攻击可帮助您在真正的攻击影响组织之前识别易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="5d360-132">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="5d360-133">Security/SecOps 邮箱：安全团队使用的专用邮箱)  (好的和坏的中获取未筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="5d360-133">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="5d360-134">然后，团队可以查看它们是否包含恶意内容。</span><span class="sxs-lookup"><span data-stu-id="5d360-134">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="5d360-135">第三方筛选器：某些第三方供应商建议将 EOP (SCL =-1) ，因为第三方筛选器将管理邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="5d360-135">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="5d360-136">Microsoft 不建议关闭 EOP，因为 Defender for Office 365 需要 EOP。</span><span class="sxs-lookup"><span data-stu-id="5d360-136">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="5d360-137">误报：你可能需要允许 Microsoft 仍在通过 [管理员提交](admin-submission.md)进行分析的某些邮件。</span><span class="sxs-lookup"><span data-stu-id="5d360-137">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="5d360-138">与所有替代一样，建议它们是临时性的。</span><span class="sxs-lookup"><span data-stu-id="5d360-138">As with all overrides, it is recommended that they are temporary.</span></span>
