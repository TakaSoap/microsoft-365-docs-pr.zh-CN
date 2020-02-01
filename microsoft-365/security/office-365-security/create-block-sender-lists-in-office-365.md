---
title: 在 Office 365 中创建阻止发件人列表
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 阻止发件人列表选项包括 Outlook 阻止的发件人、反垃圾邮件发件人/域阻止列表、IP 阻止列表和 Exchange 邮件流规则（传输规则）。
ms.openlocfilehash: fb5228bca7ac0c98a2aafd9d7b582e370698649a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599539"
---
# <a name="create-block-sender-lists-in-office-365"></a><span data-ttu-id="b33ad-103">在 Office 365 中创建阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="b33ad-103">Create block sender lists in Office 365</span></span>

<span data-ttu-id="b33ad-104">有时，有必要阻止发件人发来的不需要的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b33ad-104">Sometimes it's necessary to block unwanted email from senders.</span></span> <span data-ttu-id="b33ad-105">有几种方法可供选择。</span><span class="sxs-lookup"><span data-stu-id="b33ad-105">There are several methods available to choose from.</span></span> <span data-ttu-id="b33ad-106">这些选项包括 Outlook 阻止的发件人、反垃圾邮件发件人/域阻止列表、IP 阻止列表和 Exchange 邮件流规则（也称为传输规则）。</span><span class="sxs-lookup"><span data-stu-id="b33ad-106">These options include Outlook Blocked Senders, Anti-Spam Sender/Domain Block Lists, IP Block Lists, and Exchange mail flow rules (also known as transport rules).</span></span>

> [!NOTE]
> <span data-ttu-id="b33ad-107">虽然可以使用组织阻止列表来解决漏报（丢失的垃圾邮件），但还应将那些候选人提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b33ad-107">While organization block lists can be used to address false negatives (missed spam), those candidates should also be submitted to Microsoft for analysis.</span></span> <span data-ttu-id="b33ad-108">使用阻止列表管理漏报会显著增加管理开销。</span><span class="sxs-lookup"><span data-stu-id="b33ad-108">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="b33ad-109">如果要使用阻止列表来实现此目的，则在准备好时，还需要保留将[垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)的文章。</span><span class="sxs-lookup"><span data-stu-id="b33ad-109">If you will use a block list for this purpose, you will need to also keep the article for [submitting spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), at the ready.</span></span>

<span data-ttu-id="b33ad-110">配置被阻止的发件人列表的适当方法取决于影响的范围。</span><span class="sxs-lookup"><span data-stu-id="b33ad-110">The proper method to configure blocked sender lists varies depending on the scope of the impact.</span></span> <span data-ttu-id="b33ad-111">对于单用户影响，正确的解决方案可以是使用 Outlook 阻止的发件人，但如果多个用户或所有用户受到影响，则其他选项之一更合适。</span><span class="sxs-lookup"><span data-stu-id="b33ad-111">For single user impact, the right solution could be to use Outlook Blocked Senders, but if multiple users or all users are being impacted, one of the other options would be more appropriate.</span></span>

## <a name="options-from-least-to-broadest-scope"></a><span data-ttu-id="b33ad-112">从最小到最广泛的范围的选项</span><span class="sxs-lookup"><span data-stu-id="b33ad-112">Options from least to broadest scope</span></span>

<span data-ttu-id="b33ad-113">创建阻止列表时，一定要根据影响的范围（将影响多少人）选择适当的方法，以使其与阻止方法的广度相匹配。</span><span class="sxs-lookup"><span data-stu-id="b33ad-113">When creating a Block list it's important to pick the appropriate method based on the scope of the impact (how many people will be impacted), so that it matches the breadth of the blocking method.</span></span> <span data-ttu-id="b33ad-114">下面列出的选项按作用域和广度进行排序。</span><span class="sxs-lookup"><span data-stu-id="b33ad-114">The options listed below are ranked by both scope and breadth.</span></span> <span data-ttu-id="b33ad-115">列表从窄到范围，但阅读完整建议的*细节*。</span><span class="sxs-lookup"><span data-stu-id="b33ad-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

- <span data-ttu-id="b33ad-116">Outlook 阻止的发件人</span><span class="sxs-lookup"><span data-stu-id="b33ad-116">Outlook Blocked Senders</span></span>
- <span data-ttu-id="b33ad-117">反垃圾邮件策略：发件人/域阻止列表</span><span class="sxs-lookup"><span data-stu-id="b33ad-117">Anti-Spam policy: Sender/Domain Block lists</span></span>
- <span data-ttu-id="b33ad-118">Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="b33ad-118">Exchange mail flow rules</span></span>
- <span data-ttu-id="b33ad-119">反垃圾邮件策略： IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="b33ad-119">Anti-Spam policy: IP Block Lists</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="b33ad-120">使用 Outlook 阻止的发件人</span><span class="sxs-lookup"><span data-stu-id="b33ad-120">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="b33ad-121">如果只有少量用户受到影响，则应使用 Outlook 阻止的发件人，因为这只会影响向其发送邮件。</span><span class="sxs-lookup"><span data-stu-id="b33ad-121">When only a small number of users are impacted, that's when Outlook Blocked Senders should be used, because this will only impact mail being sent to them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b33ad-122">如果不需要的邮件是来自可信且可识别的来源的新闻快递，则取消订阅该电子邮件是另一个选项，阻止用户将来收到该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b33ad-122">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from getting the emails in the future.</span></span>

<span data-ttu-id="b33ad-123">[在 web 上的 outlook](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)和[outlook 客户端](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)上设置此设置的步骤有所不同。</span><span class="sxs-lookup"><span data-stu-id="b33ad-123">The steps to set this up are different between [Outlook on the web](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) and the [Outlook client](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span> <span data-ttu-id="b33ad-124">**当邮件由于被阻止的发件人而成功被阻止时，您将在 X Forefront-反垃圾邮件中看到 SFV： BLK** ，这表明该邮件已被阻止。</span><span class="sxs-lookup"><span data-stu-id="b33ad-124">**When messages are successfully blocked due to Blocked Senders you will see SFV:BLK in the X-Forefront-Antispam-Report** which indicates that the message is being blocked.</span></span>

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a><span data-ttu-id="b33ad-125">使用反垃圾邮件策略发件人/域阻止列表</span><span class="sxs-lookup"><span data-stu-id="b33ad-125">Use Anti-Spam Policy Sender/Domain Block lists</span></span>

<span data-ttu-id="b33ad-126">当多个用户受到影响时，范围将变宽，您需要使用公司范围内的发件人/域阻止列表反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="b33ad-126">When multiple users are being impacted, the scope is wider, and you need to use a company-wide sender/domain block list Anti-Spam policy.</span></span> <span data-ttu-id="b33ad-127">可在[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中找到详细步骤。</span><span class="sxs-lookup"><span data-stu-id="b33ad-127">The detailed steps can be found in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="b33ad-128">通过此方法阻止的任何邮件都将遵循策略中配置的垃圾邮件操作。</span><span class="sxs-lookup"><span data-stu-id="b33ad-128">Any messages blocked through this method will follow the spam action as configured in the policy.</span></span>

<span data-ttu-id="b33ad-129">这些列表的最大限制约为1000个条目;尽管只能将30个条目输入到门户中。</span><span class="sxs-lookup"><span data-stu-id="b33ad-129">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="b33ad-130">必须使用 PowerShell 添加30个以上的条目。</span><span class="sxs-lookup"><span data-stu-id="b33ad-130">You must use PowerShell to add more than 30 entries.</span></span>

## <a name="use-exchange-mail-flow-rules-specific-senders"></a><span data-ttu-id="b33ad-131">使用 Exchange 邮件流规则特定发件人</span><span class="sxs-lookup"><span data-stu-id="b33ad-131">Use Exchange mail flow rules specific senders</span></span>

<span data-ttu-id="b33ad-132">如果需要阻止将邮件发送到特定用户或整个组织中的邮件，则可以使用邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="b33ad-132">If you need to block messages from being sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="b33ad-133">邮件流规则更灵活，因为它们可以触发发件人电子邮件地址或域，以及邮件中的关键词语和其他属性。</span><span class="sxs-lookup"><span data-stu-id="b33ad-133">Mail flow rules are more flexible because they can trigger off the sender Email Address or Domain as well as key words and other properties  in the message.</span></span> <span data-ttu-id="b33ad-134">这种灵活性使您能够创建部分到完整的块。</span><span class="sxs-lookup"><span data-stu-id="b33ad-134">This flexibility will let you create partial- to complete blocks.</span></span> <span data-ttu-id="b33ad-135">有关邮件流规则的详细信息，请参阅[使用邮件流规则在邮件中设置 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b33ad-135">For more information about mail flow rules, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b33ad-136">创建的规则非常简单，因为这*会导致*所使用的条件尽可能具体，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="b33ad-136">It's easy to create rules that are *overly* aggressive, as a result it's important the criteria being used is as specific as possible.</span></span> <span data-ttu-id="b33ad-137">此外，请确保对所创建的规则启用审核并进行测试，以确保一切按预期工作。</span><span class="sxs-lookup"><span data-stu-id="b33ad-137">Also, be sure that you enable auditing on the rule you create and do testing to ensure everything works as expected.</span></span>

## <a name="use-anti-spam-policy-ip-block-lists"></a><span data-ttu-id="b33ad-138">使用反垃圾邮件策略 IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="b33ad-138">Use Anti-Spam Policy IP Block lists</span></span>

<span data-ttu-id="b33ad-139">如果不能使用其他选项之一阻止发件人，*则*可以使用反垃圾邮件策略 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="b33ad-139">When it's not possible to use one of the other options to block a sender, *then* you can use the Anti-Spam Policy IP Block List.</span></span> <span data-ttu-id="b33ad-140">有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b33ad-140">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="b33ad-141">一定要将阻止的 Ip 的数量保持为最小值，以便*不*建议阻止整个 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="b33ad-141">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="b33ad-142">您应该*特别*避免添加属于消费者服务或共享基础结构的 ip 地址范围，还应确保在定期维护过程中查看允许的 ip 地址列表。</span><span class="sxs-lookup"><span data-stu-id="b33ad-142">You should *especially* avoid adding IP address ranges that belong to consumer services or shared infrastructures, and also ensure that you review the list of allowed IP addresses as part of regular maintenance.</span></span> <span data-ttu-id="b33ad-143">**由于允许条目可以打开用于攻击的路由，因此您必须仔细管理此列表，并定期删除不再需要的允许条目。**</span><span class="sxs-lookup"><span data-stu-id="b33ad-143">**Because allows-entries can open up routes for attack, you must closely manage this list and regularly remove the allows-entries that are no longer needed.**</span></span> <span data-ttu-id="b33ad-144">此外，如果您将允许在安全发件人列表中使用，请务必阅读并了解在*[Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)* 中的风险和注意事项。</span><span class="sxs-lookup"><span data-stu-id="b33ad-144">Also, if you will make allows in a Safe-Sender list be sure to read and understand the risks and precautions in *[Create Safe-Sender lists in Office 365](create-safe-sender-lists-in-office-365.md)*.</span></span>
