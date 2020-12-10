---
title: 防钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的反钓鱼保护功能。
ms.openlocfilehash: 5b175a252f95c62a40348a78e694628ee58488bd
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614985"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="7a743-103">Microsoft 365 中的反网络钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="7a743-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7a743-104">*网络钓鱼* 是一种电子邮件攻击，试图窃取来自合法或受信任发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7a743-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="7a743-105">存在特定类别的网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="7a743-105">There are specific categories of phishing.</span></span> <span data-ttu-id="7a743-106">例如：</span><span class="sxs-lookup"><span data-stu-id="7a743-106">For example:</span></span>

- <span data-ttu-id="7a743-107">**Spear 仿冒** 使用专门为目标收件人量身定制的自定义自定义内容 (通常是攻击者) 的收件人的侦测之后。</span><span class="sxs-lookup"><span data-stu-id="7a743-107">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="7a743-108">**Whaling** 在组织内的主管或其他高价值目标中定向，以实现最大效果。</span><span class="sxs-lookup"><span data-stu-id="7a743-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="7a743-109">**业务电子邮件危害 (BEC)** 使用伪造的受信任发件人 (财务总监、客户、受信任的合作伙伴等。向欺骗收件人批准付款、转移资金或暴露客户数据 ) 。</span><span class="sxs-lookup"><span data-stu-id="7a743-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="7a743-110">加密您的数据和要求付款以对其进行解密的 **勒索软件** 几乎总是会开始在网络钓鱼邮件中。</span><span class="sxs-lookup"><span data-stu-id="7a743-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="7a743-111">反网络钓鱼防护无法帮助您解密加密文件，但可以帮助检测与勒索软件活动相关联的初始网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="7a743-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="7a743-112">有关从勒索软件攻击中恢复的详细信息，请参阅 [Microsoft 365 中的从勒索软件攻击恢复](recover-from-ransomware.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="7a743-113">随着攻击的复杂程度的增加，训练有素的用户更难识别复杂的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="7a743-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="7a743-114">幸运的是，Exchange Online Protection (EOP) 以及 Microsoft Defender for Office 365 中的其他功能可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="7a743-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="7a743-115">EOP 中的反网络钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="7a743-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="7a743-116">EOP (即，没有 Microsoft Defender for Office 365 的 Microsoft 365 组织) 包含的功能可以帮助您的组织防御网络钓鱼威胁：</span><span class="sxs-lookup"><span data-stu-id="7a743-116">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="7a743-117">**欺骗智能**：审查来自内外部域发件人的欺骗邮件，并允许或阻止这些发件人。</span><span class="sxs-lookup"><span data-stu-id="7a743-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="7a743-118">有关详细信息，请参阅 [在 EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="7a743-119">**EOP 中的反网络钓鱼策略**：启用或禁用欺骗智能，在 Outlook 中打开或关闭未经身份验证的发件人标识，以及指定阻止的欺骗性发件人的操作 (移至垃圾邮件文件夹或隔离) 。</span><span class="sxs-lookup"><span data-stu-id="7a743-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="7a743-120">有关详细信息，请参阅 [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="7a743-121">**隐式电子邮件身份验证**： EOP 增强了入站电子邮件的标准电子邮件身份验证检查 ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)和 [DMARC](use-dmarc-to-validate-email.md)) 与发件人信誉、发件人历史记录、收件人历史记录、行为分析以及其他可帮助您识别伪造发件人的高级技术</span><span class="sxs-lookup"><span data-stu-id="7a743-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="7a743-122">有关详细信息，请参阅 [Microsoft 365 中的电子邮件身份验证](email-validation-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7a743-123">Microsoft Defender for Office 365 中的其他防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="7a743-123">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="7a743-124">Microsoft Defender for Office 365 包含更高级、更高级的反网络钓鱼功能：</span><span class="sxs-lookup"><span data-stu-id="7a743-124">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="7a743-125">**Microsoft Defender For Office 365 中的反网络钓鱼策略**：创建新的自定义策略、配置反模拟设置 (保护用户和域的模拟) 、邮箱智能设置和可调整的高级网络钓鱼阈值。</span><span class="sxs-lookup"><span data-stu-id="7a743-125">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="7a743-126">有关详细信息，请参阅 [在 Microsoft Defender For Office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-126">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="7a743-127">有关 EOP 中的反网络钓鱼策略与 Office 365 中的反网络钓鱼策略之间的差异的详细信息，请参阅 [Microsoft 365 中的反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-127">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="7a743-128">"**活动" 视图**：机器学习和其他试探法可识别和分析针对整个服务和组织的协调的网络钓鱼攻击所涉及的邮件。</span><span class="sxs-lookup"><span data-stu-id="7a743-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="7a743-129">有关详细信息，请参阅 [Microsoft Defender For Office 365 中的市场活动视图](campaigns.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-129">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="7a743-130">**攻击模拟器**：管理员可以创建假冒的网络钓鱼邮件，并将其作为教育工具发送给内部用户。</span><span class="sxs-lookup"><span data-stu-id="7a743-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="7a743-131">有关详细信息，请参阅 [Microsoft Defender For Office 365 中的攻击模拟器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-131">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="7a743-132">其他反网络钓鱼资源</span><span class="sxs-lookup"><span data-stu-id="7a743-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="7a743-133">对于最终用户： [保护自己免受网络仿冒骗术和其他形式的在线欺诈](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。</span><span class="sxs-lookup"><span data-stu-id="7a743-133">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="7a743-134">[Microsoft 365 如何验证发件人地址以防止仿冒](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="7a743-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
