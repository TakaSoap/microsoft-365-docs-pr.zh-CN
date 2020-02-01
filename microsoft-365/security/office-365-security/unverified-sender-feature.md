---
title: 未验证发件人
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 若要防止仿冒邮件到达邮箱，Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人，并将可疑邮件标记为垃圾邮件。
ms.openlocfilehash: 0dd8b54d2c8153b4200336d8c0e439f278f7ae77
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598129"
---
# <a name="unverified-sender"></a><span data-ttu-id="00634-103">未验证发件人</span><span class="sxs-lookup"><span data-stu-id="00634-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="00634-104">这些更新现在即将推出，可能对所有用户不可用。</span><span class="sxs-lookup"><span data-stu-id="00634-104">These updates are rolling out now, and might not be available yet for all users.</span></span> <span data-ttu-id="00634-105">Enterprise outlook.com users 支持此功能。</span><span class="sxs-lookup"><span data-stu-id="00634-105">This feature is supported for Enterprise outlook.com users.</span></span> <span data-ttu-id="00634-106">它目前对消费者 outlook.com 不可用。</span><span class="sxs-lookup"><span data-stu-id="00634-106">It is not currently available for consumer outlook.com.</span></span>

<span data-ttu-id="00634-107">若要防止仿冒邮件到达邮箱，Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人，并将可疑邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="00634-107">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00634-108">将邮件标记为 "仿冒骗局" 时，Outlook.com 和 web 上的 Outlook 将在页面顶部显示警告，但仍可打开邮件中的任何链接。</span><span class="sxs-lookup"><span data-stu-id="00634-108">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="00634-109">如何在收件箱中识别可疑邮件？</span><span class="sxs-lookup"><span data-stu-id="00634-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="00634-110">当邮件的发件人无法识别或其身份与 "发件人" 地址中所示的不同时，web 上的 Outlook.com 和 Outlook 显示指示器。</span><span class="sxs-lookup"><span data-stu-id="00634-110">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="00634-111">您将在发件人图像中看到 "？"</span><span class="sxs-lookup"><span data-stu-id="00634-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="00634-112">当 Outlook.com 和 Outlook 网页上的 Outlook 无法使用电子邮件身份验证技术验证发件人的身份时，它们将在发件人照片中显示 "？"。</span><span class="sxs-lookup"><span data-stu-id="00634-112">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![邮件未通过验证](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="00634-114">并不是每个验证失败的邮件都是恶意的。</span><span class="sxs-lookup"><span data-stu-id="00634-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="00634-115">但是，如果您不识别发件人，则应注意与不进行身份验证的邮件进行交互。</span><span class="sxs-lookup"><span data-stu-id="00634-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="00634-116">或者，如果您识别的发件人在发件人图像中通常不包含 '？ '，但突然开始看到它，则可能是发件人哄骗的签名。</span><span class="sxs-lookup"><span data-stu-id="00634-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="00634-117">如何管理哪些邮件会收到未验证的发件人处理</span><span class="sxs-lookup"><span data-stu-id="00634-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="00634-118">如果你是 Office 365 客户，则可以通过 Office 365 安全性 & 合规性中心管理此功能。</span><span class="sxs-lookup"><span data-stu-id="00634-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="00634-119">在安全 & 合规性中心中，全局管理员或安全管理员可以通过反网络钓鱼策略下的反欺骗保护来打开或关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="00634-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="00634-120">此外，还可以使用 Exchange Online PowerShell 中的**AntiPhishPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00634-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="00634-121">有关详细信息，请参阅[Office 365 中的反钓鱼防护](anti-phishing-protection.md)和 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)。</span><span class="sxs-lookup"><span data-stu-id="00634-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![在图形界面中编辑未经身份验证的发件人。](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="00634-123">如果管理员已识别误报，并且发件人不应接收未验证的发件人处理，则可以执行下列操作之一将发件人添加到欺骗智能欺骗允许列表中：</span><span class="sxs-lookup"><span data-stu-id="00634-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="00634-124">通过欺骗性智能洞察力添加域对。</span><span class="sxs-lookup"><span data-stu-id="00634-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="00634-125">有关详细信息，请参阅[演练：欺骗性智能洞察力](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="00634-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="00634-126">通过 Exchange Online PowerShell 中的**将 get-phishfilterpolicy** cmdlet 添加域对。</span><span class="sxs-lookup"><span data-stu-id="00634-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="00634-127">有关详细信息，请参阅[将 get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)和[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="00634-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="00634-128">此外，如果邮件通过邮件流规则（也称为传输规则）、安全域列表（反垃圾邮件策略）或安全发件人列表传递到收件箱，则不会应用未验证的发件人处理。</span><span class="sxs-lookup"><span data-stu-id="00634-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules), Safe Domain List (Anti-Spam Policy), or Safe Sender List.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="00634-129">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="00634-129">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="00634-130">Outlook.com 和 Outlook 在 web 上使用哪些条件来添加 '？ ' 和 ' via ' 属性？</span><span class="sxs-lookup"><span data-stu-id="00634-130">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="00634-131">对于发件人图像中的 "？"： Outlook.com 要求邮件传递 SPF 或 DKIM 身份验证，并接收 dmarc pass 或来自 Office 365 欺骗智能的复合身份验证传递。</span><span class="sxs-lookup"><span data-stu-id="00634-131">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="00634-132">有关详细信息，请参阅[Set UP SPF In office 365，以帮助防止哄骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 验证从您的自定义域在 Office 365 中发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="00634-132">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="00634-133">对于 via 标记：如果 "发件人" 地址中的域不同于 DKIM 签名中的域，或者 SMTP 邮件来自，则 Outlook.com 将在这两个字段之一中显示域（首选 DKIM 签名）。</span><span class="sxs-lookup"><span data-stu-id="00634-133">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="00634-134">如何删除 "？"</span><span class="sxs-lookup"><span data-stu-id="00634-134">How do I remove the '?'</span></span>

<span data-ttu-id="00634-135">对于发件人图像中的 '？ '，作为发件人，应使用 SPF 或 DKIM 对邮件进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="00634-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="00634-136">对于 via 标记：作为发件人，应确保 "DKIM" 签名中的域或 "发件人" 中的 "SMTP 邮件" 与 "发件人" 地址中的域相同，或者是的子域。</span><span class="sxs-lookup"><span data-stu-id="00634-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="00634-137">Outlook.com 和 Outlook 网页版是否对未通过身份验证的每封邮件显示此功能？</span><span class="sxs-lookup"><span data-stu-id="00634-137">Does Outlook.com and Outlook on the web show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="00634-138">不一定。</span><span class="sxs-lookup"><span data-stu-id="00634-138">Not necessarily.</span></span> <span data-ttu-id="00634-139">Outlook.com 和 web 上的 Outlook 在邮件中的其他属性可能会对发件人进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="00634-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00634-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="00634-140">Related topics</span></span>

[<span data-ttu-id="00634-141">帮助保护你的 Outlook.com 电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="00634-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="00634-142">在 Outlook.com 中处理网络钓鱼或欺骗</span><span class="sxs-lookup"><span data-stu-id="00634-142">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="00634-143">在 web 上的 Outlook 中筛选垃圾电子邮件和垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="00634-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
