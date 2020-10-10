---
title: 配置和控制外部电子邮件转发、自动转发、5.7.520 访问被拒绝、禁用外部转发、管理员已禁用外部转发、出站反垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: c0a3849d330b508630eb60c7ee24cd8b498a32b8
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417233"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="6fd4a-103">在 Office 365 中配置外部电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="6fd4a-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6fd4a-104">外部转发由 *出站反垃圾邮件策略* 控制，并根据配置的设置范围限定给用户。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="6fd4a-105">当前支持3个设置：</span><span class="sxs-lookup"><span data-stu-id="6fd4a-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="6fd4a-106">**自动** –这是由系统控制的：它允许出站垃圾邮件筛选功能来控制自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-106">**Automatic** – This is system-controlled: It allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="6fd4a-107">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-107">This is the default setting.</span></span>

- <span data-ttu-id="6fd4a-108">**启用** –允许和不限制自动外部转发。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="6fd4a-109">**关** -自动外部转发已禁用，并将导致向最终用户 (NDR) 的未送达报告。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="6fd4a-110">有关如何配置这些设置的详细信息，请参阅 [配置 EOP 中的出站垃圾邮件筛选](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) 。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="6fd4a-111">禁用自动转发也将禁用将邮件重定向到外部地址的收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-111">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="6fd4a-112">控制外部电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="6fd4a-112">Controlling external email forwarding</span></span>

<span data-ttu-id="6fd4a-113">作为组织的管理员，你可能需要对公司要求进行限制或控制能够在组织外部使用收件箱规则或 SMTP 转发自动转发电子邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-113">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="6fd4a-114">电子邮件转发可能是一项非常有用的功能，但也可以通过可能泄露的信息带来风险，即使是向攻击者提供的信息可以被利用来攻击组织或其合作伙伴也是如此。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-114">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="6fd4a-115">Office 365 不允许通过 "收件箱" 规则或 "邮箱" 配置自动进行外部转发，这将提供安全的默认策略。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-115">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="6fd4a-116">但是，管理员可以为组织中的所有用户或部分用户修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-116">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="6fd4a-117">内部用户之间的转发邮件不受此类修改的影响。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-117">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="6fd4a-118">在 Office 365 中禁用自动转发外部地址的过程分阶段进行，详细信息通过 [消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) 发布进行通信。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-118">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="6fd4a-119">若要帮助管理员准备这些更改，请提前修改策略以确保用户不会中断他们的用户。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-119">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="6fd4a-120">有关使用自动转发的用户的详细信息，可以在 [自动转发的邮件报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true)中找到组织中 (收件箱规则或 SMTP 转发) 。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-120">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="6fd4a-121">此策略如何与其他自动转发控件一起使用</span><span class="sxs-lookup"><span data-stu-id="6fd4a-121">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="6fd4a-122">作为管理员，您可能已有其他类型的控件，例如阻止在 [远程域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 中进行自动转发和使用 Exchange 传输规则 (ETR) 。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-122">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="6fd4a-123">这两个控件都独立于此特定功能，例如，如果您允许对远程域进行自动转发，但通过出站垃圾邮件策略阻止自动转发，则会导致自动转发的邮件被阻止。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-123">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="6fd4a-124">同样，如果您在出站垃圾邮件策略中允许自动转发，但在 ETR 或远程域中将其阻止，则这两个控件中的任何一个都将阻止该邮件。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-124">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="6fd4a-125">例如，这使您可以在出站垃圾邮件策略中允许自动转发，并利用远程域来控制用户可以自动转发邮件的域。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-125">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="6fd4a-126">阻止的电子邮件转发邮件</span><span class="sxs-lookup"><span data-stu-id="6fd4a-126">The blocked email forwarding message</span></span>

<span data-ttu-id="6fd4a-127">当检测到邮件自动转发且组织策略 *阻止* 活动的 \*\*未送达报告 (NDR) \*\* 将生成回最终用户。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-127">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="6fd4a-128">报告将指示邮件未送达。</span><span class="sxs-lookup"><span data-stu-id="6fd4a-128">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="6fd4a-129">NDR 将具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="6fd4a-129">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
