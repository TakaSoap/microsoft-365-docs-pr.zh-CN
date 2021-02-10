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
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的防钓鱼保护功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f42ea3159dc5ed975852aaca10ce6f344b71d749
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175627"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="dad6f-103">Microsoft 365 中的防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="dad6f-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dad6f-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="dad6f-104">**Applies to**</span></span>
- [<span data-ttu-id="dad6f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dad6f-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="dad6f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="dad6f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="dad6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dad6f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="dad6f-108">*网络钓鱼* 是一种电子邮件攻击，它尝试窃取看似来自合法或受信任的发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="dad6f-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="dad6f-109">存在网络钓鱼的特定类别。</span><span class="sxs-lookup"><span data-stu-id="dad6f-109">There are specific categories of phishing.</span></span> <span data-ttu-id="dad6f-110">例如：</span><span class="sxs-lookup"><span data-stu-id="dad6f-110">For example:</span></span>

- <span data-ttu-id="dad6f-111">**网络钓鱼使用** 专门针对目标收件人定制的集中的自定义内容 (通常，在攻击者对收件人重新进行重新) 。</span><span class="sxs-lookup"><span data-stu-id="dad6f-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="dad6f-112">**为了达到** 最大效果，将项目定向到组织中主管或其他高价值目标。</span><span class="sxs-lookup"><span data-stu-id="dad6f-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="dad6f-113">**商业电子邮件泄露 (BEC)** 使用伪造的受信任发件人 (财务官、客户、受信任合作伙伴等 ) 来欺骗收件人批准付款、转移资金或泄露客户数据。</span><span class="sxs-lookup"><span data-stu-id="dad6f-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="dad6f-114">**对数据** 进行加密并要求付款以解密数据的勒索软件几乎总是从网络钓鱼邮件中开始。</span><span class="sxs-lookup"><span data-stu-id="dad6f-114">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="dad6f-115">反网络钓鱼保护无法帮助您解密加密文件，但它可以帮助检测与勒索软件活动关联的初始网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="dad6f-115">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="dad6f-116">有关从勒索软件攻击中恢复详细信息，请参阅 Microsoft [365](recover-from-ransomware.md)中的"从勒索软件攻击中恢复"。</span><span class="sxs-lookup"><span data-stu-id="dad6f-116">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="dad6f-117">随着攻击的复杂性不断增加，经过培训的用户甚至难以识别复杂的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="dad6f-117">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="dad6f-118">幸运的是，Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的附加功能可以提供帮助。</span><span class="sxs-lookup"><span data-stu-id="dad6f-118">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="dad6f-119">EOP 中的防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="dad6f-119">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="dad6f-120">EOP (，即没有 Microsoft Defender for Office 365) 的 Microsoft 365 组织包含可帮助保护组织免受网络钓鱼威胁的功能：</span><span class="sxs-lookup"><span data-stu-id="dad6f-120">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="dad6f-121">**欺骗智能**：审查来自内外部域发件人的欺骗邮件，并允许或阻止这些发件人。</span><span class="sxs-lookup"><span data-stu-id="dad6f-121">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="dad6f-122">有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="dad6f-122">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="dad6f-123">**EOP** 中的反网络钓鱼策略：打开或关闭欺骗智能，打开或关闭 Outlook 中的未经身份验证的发件人标识，并指定阻止的欺骗 (移动到垃圾邮件文件夹或隔离邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="dad6f-123">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="dad6f-124">有关详细信息，请参阅在 [EOP 中配置防钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="dad6f-124">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="dad6f-125">**隐式电子邮件** 身份验证：EOP 通过发件人信誉、发件人历史记录、收件人历史记录、行为分析和其他高级技术增强入站电子邮件 ([SPF、DKIM](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和 [](use-dkim-to-validate-outbound-email.md)[DMARC](use-dmarc-to-validate-email.md)) 的标准电子邮件身份验证检查，以帮助识别伪造的发件人。</span><span class="sxs-lookup"><span data-stu-id="dad6f-125">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="dad6f-126">有关详细信息，请参阅 [Microsoft 365 中的电子邮件身份验证](email-validation-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="dad6f-126">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="dad6f-127">Microsoft Defender for Office 365 中的其他防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="dad6f-127">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="dad6f-128">Microsoft Defender for Office 365 包含更多更高级的防钓鱼功能：</span><span class="sxs-lookup"><span data-stu-id="dad6f-128">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="dad6f-129">**适用于 Office 365 的 Microsoft Defender** 中的反网络钓鱼策略：创建新的自定义策略、配置反模拟设置 (保护用户和域免受模拟) 、邮箱智能设置和可调整的高级网络钓鱼阈值的影响。</span><span class="sxs-lookup"><span data-stu-id="dad6f-129">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="dad6f-130">有关详细信息，请参阅在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="dad6f-130">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="dad6f-131">有关 EOP 中的反网络钓鱼策略与 Office 365 Defender 中的反钓鱼策略之间的差异详细信息，请参阅 Microsoft [365](set-up-anti-phishing-policies.md)中的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="dad6f-131">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="dad6f-132">**活动视图**：机器学习和其他启发式方法可标识和分析针对整个服务和组织的协调网络钓鱼攻击所涉及的邮件。</span><span class="sxs-lookup"><span data-stu-id="dad6f-132">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="dad6f-133">有关详细信息，请参阅 [Microsoft Defender for Office 365 中的市场活动视图](campaigns.md)。</span><span class="sxs-lookup"><span data-stu-id="dad6f-133">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="dad6f-134">**攻击模拟器**：管理员可以创建假网络钓鱼邮件，并将其作为教育工具发送给内部用户。</span><span class="sxs-lookup"><span data-stu-id="dad6f-134">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="dad6f-135">有关详细信息，请参阅 [Microsoft Defender for Office 365 中的攻击模拟器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="dad6f-135">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="dad6f-136">其他防钓鱼资源</span><span class="sxs-lookup"><span data-stu-id="dad6f-136">Other anti-phishing resources</span></span>

- <span data-ttu-id="dad6f-137">对于最终用户： [保护自己免受网络钓鱼计划和其他形式的联机欺诈的攻击](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。</span><span class="sxs-lookup"><span data-stu-id="dad6f-137">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="dad6f-138">[Microsoft 365 如何验证"自"地址以防止钓鱼](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="dad6f-138">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
