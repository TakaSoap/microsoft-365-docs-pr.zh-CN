---
title: Microsoft 365 中的反网络钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: 默认情况下，Microsoft 365 提供各种针对网络钓鱼攻击的防护，也可以通过 Office 365 高级威胁防护（ATP）中的其他功能进行防护。 本主题介绍可用于在 Microsoft 365 中了解并实施反钓鱼选项和策略的联机资源。
ms.openlocfilehash: bdab6c05fb9be85c2ffb4914390ecc893fdd162b
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949365"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="38b2b-104">Microsoft 365 中的反网络钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="38b2b-104">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="38b2b-105">*网络钓鱼*一种电子邮件攻击，试图窃取看似来自合法或受信任发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="38b2b-105">*Phishing* an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="38b2b-106">存在特定类别的网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="38b2b-106">There are specific categories of phishing.</span></span> <span data-ttu-id="38b2b-107">例如：</span><span class="sxs-lookup"><span data-stu-id="38b2b-107">For example:</span></span>

- <span data-ttu-id="38b2b-108">**Spear 网络钓鱼**使用专门为目标收件人量身定制的专门的自定义内容（通常是攻击者在收件人的侦测之后）。</span><span class="sxs-lookup"><span data-stu-id="38b2b-108">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="38b2b-109">**Whaling**在组织内的主管或其他高价值目标中定向，以实现最大效果。</span><span class="sxs-lookup"><span data-stu-id="38b2b-109">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="38b2b-110">**商业电子邮件泄露（BEC）** 使用伪造的受信任发件人（金融专员、客户、受信任合作伙伴等），努力哄骗收件人批准付款、转让资金或公开客户数据。</span><span class="sxs-lookup"><span data-stu-id="38b2b-110">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="38b2b-111">加密您的数据和要求付款以对其进行解密的**勒索软件**几乎总是会开始在网络钓鱼邮件中。</span><span class="sxs-lookup"><span data-stu-id="38b2b-111">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="38b2b-112">反网络钓鱼防护无法帮助您解密加密文件，但可以帮助检测与勒索软件活动相关联的初始网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="38b2b-112">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="38b2b-113">有关从勒索软件攻击中恢复的详细信息，请参阅[Microsoft 365 中的从勒索软件攻击恢复](recover-from-ransomware.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-113">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="38b2b-114">随着攻击的复杂程度的增加，训练有素的用户更难识别复杂的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="38b2b-114">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="38b2b-115">幸运的是，Exchange Online Protection （EOP）和 Microsoft 365 高级威胁防护（ATP）中的其他功能可以提供帮助。</span><span class="sxs-lookup"><span data-stu-id="38b2b-115">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft 365 Advanced Threat Protection (ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="38b2b-116">EOP 中的反网络钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="38b2b-116">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="38b2b-117">EOP （即，没有 ATP 的 Microsoft 365 组织）包含的功能可以帮助您的组织防御网络钓鱼威胁：</span><span class="sxs-lookup"><span data-stu-id="38b2b-117">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="38b2b-118">**欺骗智能**：审查来自内外部域发件人的欺骗邮件，并允许或阻止这些发件人。</span><span class="sxs-lookup"><span data-stu-id="38b2b-118">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="38b2b-119">有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-119">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="38b2b-120">**EOP 中的反网络钓鱼策略**：启用或禁用欺骗智能，在 Outlook 中打开或关闭未经身份验证的发件人标识，以及指定阻止的欺骗性发件人的操作（移动到 "垃圾邮件" 文件夹或隔离）。</span><span class="sxs-lookup"><span data-stu-id="38b2b-120">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="38b2b-121">有关详细信息，请参阅[在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-121">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="38b2b-122">**隐式电子邮件身份验证**： EOP 增强了入站电子邮件（[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)和[DMARC](use-dmarc-to-validate-email.md)）的标准电子邮件身份验证检查，以及发件人信誉、发件人历史记录、收件人历史记录、行为分析和其他高级技术以帮助标识伪造的发件人</span><span class="sxs-lookup"><span data-stu-id="38b2b-122">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="38b2b-123">有关详细信息，请参阅 [Microsoft 365 中的电子邮件身份验证](email-validation-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-123">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="38b2b-124">Office 365 ATP 中的其他反网络钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="38b2b-124">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="38b2b-125">Office 365 ATP 包含更高级和更高级的反网络钓鱼功能：</span><span class="sxs-lookup"><span data-stu-id="38b2b-125">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="38b2b-126">**ATP 反网络钓鱼策略**：创建新的自定义策略、配置反模拟设置（保护用户和域的模拟）、邮箱智能设置以及可调整的高级网络钓鱼阈值。</span><span class="sxs-lookup"><span data-stu-id="38b2b-126">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="38b2b-127">有关详细信息，请参阅[在 Microsoft 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-127">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="38b2b-128">有关反网络钓鱼策略和 ATP 反网络钓鱼策略之间的差异的详细信息，请参阅[Microsoft 365 中的反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-128">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="38b2b-129">"**活动" 视图**：机器学习和其他试探法可识别和分析针对整个服务和组织的协调的网络钓鱼攻击所涉及的邮件。</span><span class="sxs-lookup"><span data-stu-id="38b2b-129">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="38b2b-130">有关详细信息，请参阅[Office 365 ATP 中的市场活动视图](campaigns.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-130">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="38b2b-131">**攻击模拟器**：管理员可以创建假冒的网络钓鱼邮件，并将其作为教育工具发送给内部用户。</span><span class="sxs-lookup"><span data-stu-id="38b2b-131">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="38b2b-132">有关详细信息，请参阅[Office 365 ATP 中的攻击模拟器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-132">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="38b2b-133">其他反网络钓鱼资源</span><span class="sxs-lookup"><span data-stu-id="38b2b-133">Other anti-phishing resources</span></span>

- <span data-ttu-id="38b2b-134">对于最终用户：[保护自己免受网络仿冒骗术和其他形式的在线欺诈](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-134">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span></span>

- <span data-ttu-id="38b2b-135">[Microsoft 365 如何验证发件人地址以防止仿冒](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="38b2b-135">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>