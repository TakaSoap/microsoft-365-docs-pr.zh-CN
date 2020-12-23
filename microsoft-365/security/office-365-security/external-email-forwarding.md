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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: f75504941e8481d35458ad2ae6b5e8a72c5e8c8c
ms.sourcegitcommit: a49338bde6923b13132c7b9e4c6bb75c14163c72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2020
ms.locfileid: "49728184"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="9b836-103">在 Microsoft 365 中控制自动外部电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="9b836-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9b836-104">作为管理员，您可能有公司要求限制或控制自动转发给组织外部 (外部收件人的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="9b836-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="9b836-105">电子邮件转发可能是一项有用的功能，但也可能由于信息泄露而带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="9b836-105">Email forwarding can be a useful feature, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="9b836-106">攻击者可能会使用此信息来攻击你的组织或合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="9b836-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="9b836-107">以下类型的自动转发在 Microsoft 365 中可用：</span><span class="sxs-lookup"><span data-stu-id="9b836-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="9b836-108">用户可以配置 [收件箱规则，](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 以自动将邮件转发给外部 (或由于帐户遭到入侵而) 。</span><span class="sxs-lookup"><span data-stu-id="9b836-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="9b836-109">管理员可以 [配置邮箱转发](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (_也称为 SMTP_) ，以自动将邮件转发给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="9b836-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="9b836-110">管理员可以选择是直接转发邮件，还是将转发的邮件副本保留到邮箱中。</span><span class="sxs-lookup"><span data-stu-id="9b836-110">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="9b836-111">您可以使用出站垃圾邮件筛选器策略来控制自动转发到外部收件人。</span><span class="sxs-lookup"><span data-stu-id="9b836-111">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="9b836-112">有三种设置可用：</span><span class="sxs-lookup"><span data-stu-id="9b836-112">Three settings are available:</span></span>

- <span data-ttu-id="9b836-113">**自动**：阻止自动外部转发。</span><span class="sxs-lookup"><span data-stu-id="9b836-113">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="9b836-114">邮件的内部自动转发将继续工作。</span><span class="sxs-lookup"><span data-stu-id="9b836-114">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="9b836-115">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="9b836-115">This is the default setting.</span></span>
- <span data-ttu-id="9b836-116">**On**： 允许且不允许自动外部转发。</span><span class="sxs-lookup"><span data-stu-id="9b836-116">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="9b836-117">**关闭**：自动外部转发处于禁用状态，并且将导致未送达报告 (也称为 NDR 或退回邮件) 发件人。</span><span class="sxs-lookup"><span data-stu-id="9b836-117">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="9b836-118">有关如何配置这些设置的说明，请参阅"在 EOP 中配置出[站垃圾邮件筛选"。](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="9b836-118">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9b836-119">禁用自动转发会禁用将 (重定向到) 地址 (或) 转发用户的任何收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="9b836-119">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="9b836-120">出站垃圾邮件筛选器策略中的设置不会影响内部用户之间的自动转发邮件。</span><span class="sxs-lookup"><span data-stu-id="9b836-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="9b836-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="9b836-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="9b836-122">出站垃圾邮件筛选器策略设置如何与其他自动电子邮件转发控件一起工作</span><span class="sxs-lookup"><span data-stu-id="9b836-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="9b836-123">作为管理员，您可能已经配置了其他控件以允许或阻止自动电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="9b836-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="9b836-124">例如：</span><span class="sxs-lookup"><span data-stu-id="9b836-124">For example:</span></span>

- <span data-ttu-id="9b836-125">[允许或](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 阻止自动电子邮件转发到部分或所有外部域的远程域。</span><span class="sxs-lookup"><span data-stu-id="9b836-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="9b836-126">Exchange 邮件流规则中的条件和操作 [ (](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 传输规则) 检测并阻止自动转发给外部收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="9b836-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="9b836-127">远程域设置和邮件流规则独立于出站垃圾邮件筛选器策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="9b836-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="9b836-128">例如：</span><span class="sxs-lookup"><span data-stu-id="9b836-128">For example:</span></span>

- <span data-ttu-id="9b836-129">允许远程域自动转发，但阻止出站垃圾邮件筛选器策略中的自动转发。</span><span class="sxs-lookup"><span data-stu-id="9b836-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="9b836-130">本示例中，自动转发的邮件被阻止。</span><span class="sxs-lookup"><span data-stu-id="9b836-130">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="9b836-131">您可以在出站垃圾邮件筛选器策略中允许自动转发，但使用邮件流规则或远程域设置来阻止自动转发的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9b836-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="9b836-132">本示例中，邮件流规则或远程域设置将阻止自动转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="9b836-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="9b836-133">此功能独立允许您 (例如，) 允许出站垃圾邮件筛选器策略中的自动转发，但使用远程域来控制用户可以将邮件转发到的外部域。</span><span class="sxs-lookup"><span data-stu-id="9b836-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="9b836-134">阻止的电子邮件转发邮件</span><span class="sxs-lookup"><span data-stu-id="9b836-134">The blocked email forwarding message</span></span>

<span data-ttu-id="9b836-135">当检测到邮件被检测为自动转发，并且组织策略阻止该活动时，邮件会在包含以下信息的 NDR 中返回到发件人：</span><span class="sxs-lookup"><span data-stu-id="9b836-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
