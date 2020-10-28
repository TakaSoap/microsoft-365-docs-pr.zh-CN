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
ms.openlocfilehash: dff2ea4e144f8f8fcc0f42732141e110effe7e9e
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774089"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="48956-103">在 Microsoft 365 中控制自动外部电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="48956-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="48956-104">作为管理员，您可能有公司要求限制或控制自动转发的邮件给外部收件人 (组织外部的收件人) 。</span><span class="sxs-lookup"><span data-stu-id="48956-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="48956-105">电子邮件转发可能非常有用，但是可能会因信息泄露而带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="48956-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="48956-106">攻击者可使用此信息来攻击您的组织或合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="48956-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="48956-107">Microsoft 365 中提供了以下类型的自动转发：</span><span class="sxs-lookup"><span data-stu-id="48956-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="48956-108">用户可以配置 [收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) ，以便将邮件有意转发给外部发件人 (或作为受到威胁的帐户) 的结果。</span><span class="sxs-lookup"><span data-stu-id="48956-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="48956-109">管理员可以配置 [邮箱转发](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (也称为 SMTP 转发) ，以自动将邮件转发给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="48956-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as SMTP forwarding) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="48956-110">您可以使用出站垃圾邮件筛选器策略来控制自动转发到外部收件人。</span><span class="sxs-lookup"><span data-stu-id="48956-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="48956-111">有三个可用的设置：</span><span class="sxs-lookup"><span data-stu-id="48956-111">Three settings are available:</span></span>

- <span data-ttu-id="48956-112">**自动** ：阻止自动外部转发。</span><span class="sxs-lookup"><span data-stu-id="48956-112">**Automatic** : Automatic external forwarding is blocked.</span></span> <span data-ttu-id="48956-113">邮件的内部自动转发将继续有效。</span><span class="sxs-lookup"><span data-stu-id="48956-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="48956-114">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="48956-114">This is the default setting.</span></span>

- <span data-ttu-id="48956-115">**启用** ：允许和不限制自动外部转发。</span><span class="sxs-lookup"><span data-stu-id="48956-115">**On** : Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="48956-116">**Off** ：禁用自动外部转发，并将导致未送达报告 (也称为 "NDR" 或 "退回邮件") 发件人。</span><span class="sxs-lookup"><span data-stu-id="48956-116">**Off** : Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="48956-117">有关如何配置这些设置的说明，请参阅 [在 EOP 中配置出站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="48956-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="48956-118">禁用自动转发也将禁用将邮件重定向到外部地址的收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="48956-118">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>
> 
>   <span data-ttu-id="48956-119">Office 365 不允许通过收件箱规则或邮箱配置自动进行外部转发，这将提供安全的默认策略。</span><span class="sxs-lookup"><span data-stu-id="48956-119">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mailbox configuration, which provides a secure default policy.</span></span> <span data-ttu-id="48956-120">但是，管理员可以为组织中的所有用户或部分用户修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="48956-120">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="48956-121">创建 [出站垃圾邮件策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies) 并修改自动转发部分，以控制用户自动将电子邮件转发给外部发件人。</span><span class="sxs-lookup"><span data-stu-id="48956-121">Create [outbound spam policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies) and modify the automatic forwarding section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="48956-122">稍后可将其应用于该策略应用于的内部发件人。</span><span class="sxs-lookup"><span data-stu-id="48956-122">This can be later applied to the internal senders that the policy applies to.</span></span> <span data-ttu-id="48956-123">内部用户之间的转发邮件不受此类修改的影响。</span><span class="sxs-lookup"><span data-stu-id="48956-123">Forwarding messages between internal users isn't affected by such a modification.</span></span>
> 
> - <span data-ttu-id="48956-124">您可以查看在 [自动转发的邮件报告](mfi-auto-forwarded-messages-report.md)中自动将邮件转发给外部收件人的用户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="48956-124">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="48956-125">出站垃圾邮件筛选器策略设置如何与其他自动电子邮件转发控件一起使用</span><span class="sxs-lookup"><span data-stu-id="48956-125">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="48956-126">作为管理员，您可能已将其他控件配置为允许或阻止自动电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="48956-126">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="48956-127">例如：</span><span class="sxs-lookup"><span data-stu-id="48956-127">For example:</span></span>

- <span data-ttu-id="48956-128">允许或阻止自动将电子邮件转发到部分或全部外部域的[远程域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="48956-128">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="48956-129">Exchange [邮件流规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 中的条件和操作 (也称为传输规则) ，用于检测并阻止将自动转发的邮件发送给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="48956-129">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="48956-130">远程域设置和邮件流规则与出站垃圾邮件筛选器策略中的设置无关。</span><span class="sxs-lookup"><span data-stu-id="48956-130">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="48956-131">例如：</span><span class="sxs-lookup"><span data-stu-id="48956-131">For example:</span></span>

- <span data-ttu-id="48956-132">您允许远程域的自动转发，但在出站垃圾邮件筛选器策略中阻止自动转发。</span><span class="sxs-lookup"><span data-stu-id="48956-132">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="48956-133">在此示例中，将阻止自动转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="48956-133">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="48956-134">您可以在出站垃圾邮件筛选器策略中允许自动转发，但使用邮件流规则或远程域设置阻止自动转发的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48956-134">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="48956-135">在此示例中，邮件流规则或远程域设置将阻止自动转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="48956-135">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="48956-136">通过此功能，您可以 (例如，) 允许在出站垃圾邮件筛选器策略中自动转发，但使用远程域控制用户可以将邮件转发到的外部域。</span><span class="sxs-lookup"><span data-stu-id="48956-136">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="48956-137">阻止的电子邮件转发邮件</span><span class="sxs-lookup"><span data-stu-id="48956-137">The blocked email forwarding message</span></span>

<span data-ttu-id="48956-138">当检测到邮件自动转发且组织策略 *阻止* 该活动时，会将该邮件以 NDR 的形式返回给发件人，其中包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="48956-138">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
