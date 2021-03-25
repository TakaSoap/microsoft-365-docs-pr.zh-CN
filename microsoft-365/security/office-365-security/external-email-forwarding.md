---
title: 配置和控制外部电子邮件转发、自动转发、5.7.520 访问被拒绝、禁用外部转发、管理员已禁用外部转发、出站反垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203254"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="07468-103">在 Microsoft 365 中控制自动外部电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="07468-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="07468-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="07468-104">**Applies to**</span></span>
- [<span data-ttu-id="07468-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="07468-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="07468-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="07468-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="07468-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07468-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="07468-108">作为管理员，你可能要求限制或控制自动转发给组织外部收件人 (外部收件人的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="07468-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="07468-109">电子邮件转发可能很有用，但也可能由于信息泄露而带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="07468-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="07468-110">攻击者可能会使用此信息来攻击你的组织或合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="07468-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="07468-111">以下类型的自动转发在 Microsoft 365 中可用：</span><span class="sxs-lookup"><span data-stu-id="07468-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="07468-112">用户可以将 [收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 配置为自动将邮件转发给外部发件人 (或由于帐户遭到入侵) 。</span><span class="sxs-lookup"><span data-stu-id="07468-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="07468-113">管理员可以配置邮箱 [转发 (](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_也称为 SMTP_ 转发) 自动将邮件转发给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="07468-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="07468-114">管理员可以选择是直接转发邮件，还是保留邮箱中转发邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="07468-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="07468-115">您可以使用出站垃圾邮件筛选器策略来控制自动转发给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="07468-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="07468-116">有三种设置可用：</span><span class="sxs-lookup"><span data-stu-id="07468-116">Three settings are available:</span></span>

- <span data-ttu-id="07468-117">**自动**：阻止自动外部转发。</span><span class="sxs-lookup"><span data-stu-id="07468-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="07468-118">内部自动转发邮件将继续工作。</span><span class="sxs-lookup"><span data-stu-id="07468-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="07468-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="07468-119">This is the default setting.</span></span>
- <span data-ttu-id="07468-120">**On：** 允许且不允许自动外部转发。</span><span class="sxs-lookup"><span data-stu-id="07468-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="07468-121">**关闭**：自动外部转发处于禁用状态，将导致向发件人发送 (NDR 或退回邮件) 未送达报告。</span><span class="sxs-lookup"><span data-stu-id="07468-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="07468-122">有关如何配置这些设置的说明，请参阅在 EOP 中配置出 [站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="07468-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="07468-123">禁用自动转发会禁用任何收件箱规则 (将) 重定向到外部地址 (或) 转发邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="07468-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="07468-124">出站垃圾邮件筛选器策略中的设置不会影响内部用户之间的自动转发邮件。</span><span class="sxs-lookup"><span data-stu-id="07468-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="07468-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="07468-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="07468-126">出站垃圾邮件筛选器策略设置如何与其他自动电子邮件转发控件一起工作</span><span class="sxs-lookup"><span data-stu-id="07468-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="07468-127">作为管理员，您可能已经配置了其他控件以允许或阻止自动电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="07468-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="07468-128">例如：</span><span class="sxs-lookup"><span data-stu-id="07468-128">For example:</span></span>

- <span data-ttu-id="07468-129">[允许或](/exchange/mail-flow-best-practices/remote-domains/remote-domains) 阻止自动电子邮件转发到某些或所有外部域的远程域。</span><span class="sxs-lookup"><span data-stu-id="07468-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="07468-130">Exchange 邮件流规则 [中的](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 条件和操作 (传输规则) 检测并阻止自动转发给外部收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="07468-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="07468-131">远程域设置和邮件流规则独立于出站垃圾邮件筛选器策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="07468-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="07468-132">例如：</span><span class="sxs-lookup"><span data-stu-id="07468-132">For example:</span></span>

- <span data-ttu-id="07468-133">允许远程域自动转发，但阻止出站垃圾邮件筛选器策略中的自动转发。</span><span class="sxs-lookup"><span data-stu-id="07468-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="07468-134">本示例中，自动转发的邮件被阻止。</span><span class="sxs-lookup"><span data-stu-id="07468-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="07468-135">允许出站垃圾邮件筛选器策略中的自动转发，但使用邮件流规则或远程域设置阻止自动转发的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="07468-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="07468-136">本示例中，邮件流规则或远程域设置将阻止自动转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="07468-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="07468-137">此功能独立允许您 (例如) 出站垃圾邮件筛选器策略中允许自动转发，但使用远程域控制用户可以将邮件转发到的外部域。</span><span class="sxs-lookup"><span data-stu-id="07468-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="07468-138">阻止的电子邮件转发邮件</span><span class="sxs-lookup"><span data-stu-id="07468-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="07468-139">当邮件被检测为自动转发，并且出站垃圾邮件[](configure-the-outbound-spam-policy.md)筛选器策略阻止该活动时，该邮件将在包含以下信息的 NDR 中返回给发件人：</span><span class="sxs-lookup"><span data-stu-id="07468-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`