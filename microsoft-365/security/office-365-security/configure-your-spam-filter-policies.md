---
title: 配置垃圾邮件筛选策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中查看、创建、修改和删除反垃圾邮件策略。
ms.openlocfilehash: 74e33fe394802050ced64c5c3d9e41dcbd2550f0
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616522"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="1a141-103">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-103">Configure anti-spam policies in EOP</span></span>

<span data-ttu-id="1a141-104">在有 Exchange Online 的 Microsoft 365 组织，或没有 Exchange Online 邮箱的 Exchange Online Protection (EOP) 组织中，EOP 都会自动保护入站电子邮件免受垃圾邮件威胁。</span><span class="sxs-lookup"><span data-stu-id="1a141-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="1a141-105">EOP 使用反垃圾邮件策略（亦称为“垃圾邮件筛选策略”或“内容筛选策略”），作为组织全面抵御垃圾邮件的措施的一部分。</span><span class="sxs-lookup"><span data-stu-id="1a141-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="1a141-106">有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-106">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="1a141-107">管理员可以查看、编辑和配置（但不能删除）默认反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="1a141-108">还可以创建应用于组织中特定用户、组或域的自定义反垃圾邮件策略，以实现更细致的控制。</span><span class="sxs-lookup"><span data-stu-id="1a141-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="1a141-109">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="1a141-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="1a141-110">若要配置反垃圾邮件策略，可以使用安全与合规中心，也可以使用 PowerShell（适用于有 Exchange Online 的 Microsoft 365 组织的 Exchange Online PowerShell，或适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="1a141-110">You can configure anti-spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="anti-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="1a141-111">安全与合规中心与 PowerShell 中的反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-111">Anti-spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="1a141-112">EOP 中反垃圾邮件策略的基本要素如下：</span><span class="sxs-lookup"><span data-stu-id="1a141-112">The basic elements of an anti-spam policy in EOP are:</span></span>

- <span data-ttu-id="1a141-113">**垃圾邮件筛选策略**：指定根据垃圾邮件筛选裁定执行的操作和通知选项。</span><span class="sxs-lookup"><span data-stu-id="1a141-113">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="1a141-114">**垃圾邮件筛选规则**：指定垃圾邮件筛选策略的优先级和收件人筛选器（即对谁应用策略）。</span><span class="sxs-lookup"><span data-stu-id="1a141-114">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="1a141-115">在安全与合规中心内管理反垃圾邮件策略时，这两个要素之间的区别并不明显：</span><span class="sxs-lookup"><span data-stu-id="1a141-115">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="1a141-116">在安全与合规中心内创建反垃圾邮件策略时，实际上是同时创建了垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="1a141-116">When you create an anti-spam policy in the Security & Compliance Center, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="1a141-117">如果你在安全与合规中心内修改反垃圾邮件策略，与名称、优先级、启用/禁用以及收件人筛选器有关的设置会修改垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-117">When you modify an anti-spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="1a141-118">其他所有设置会修改关联的垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-118">All other settings modify the associated spam filter policy.</span></span>

- <span data-ttu-id="1a141-119">如果你从安全与合规中心删除反垃圾邮件策略，垃圾邮件筛选规则和关联的垃圾邮件筛选策略也会随之删除。</span><span class="sxs-lookup"><span data-stu-id="1a141-119">When you remove an anti-spam policy from the Security & Compliance Center, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="1a141-120">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，垃圾邮件筛选策略与垃圾邮件筛选规则之间的区别很明显。</span><span class="sxs-lookup"><span data-stu-id="1a141-120">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="1a141-121">可以使用 **\*-HostedContentFilterPolicy** cmdlet 管理垃圾邮件筛选策略，并使用 **\*-HostedContentFilterRule** cmdlet 管理垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-121">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="1a141-122">在 PowerShell 中，先创建垃圾邮件筛选策略，再创建确定向哪个策略应用规则的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-122">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="1a141-123">在 PowerShell 中，分别修改垃圾邮件筛选策略和垃圾邮件筛选规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-123">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>

- <span data-ttu-id="1a141-124">如果你通过 PowerShell 删除垃圾邮件筛选策略，相应的垃圾邮件筛选规则不会自动随之删除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="1a141-124">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-anti-spam-policy"></a><span data-ttu-id="1a141-125">默认反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-125">Default anti-spam policy</span></span>

<span data-ttu-id="1a141-126">每个组织都有名为“默认”的内置反垃圾邮件策略，它具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="1a141-126">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="1a141-127">名为“默认”的垃圾邮件筛选策略会应用于组织中的所有收件人，即使没有与此策略关联的垃圾邮件筛选规则（亦称为“收件人筛选器”），也不例外。</span><span class="sxs-lookup"><span data-stu-id="1a141-127">The spam filter policy named Default is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="1a141-128">名为“默认”的策略有无法修改的自定义优先级值 **“最低”**（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="1a141-128">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="1a141-129">你创建的任何自定义策略的优先级始终高于名为“默认”的策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-129">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="1a141-130">名为“默认”的策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-130">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="1a141-131">为了提高垃圾邮件筛选的有效性，可以创建自定义反垃圾邮件策略，它包含应用于特定用户或用户组的更严格设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-131">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1a141-132">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="1a141-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1a141-133">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="1a141-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1a141-134">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="1a141-134">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="1a141-135">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1a141-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1a141-136">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1a141-136">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1a141-137">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="1a141-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1a141-138">必须是 **“组织管理”** 或 **“安全管理员”** 角色组的成员，才能添加、修改和删除反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-138">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1a141-139">必须是 **“安全信息读取者”** 角色组的成员，才能获得对反垃圾邮件策略的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="1a141-139">For read-only access to anti-spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="1a141-140">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1a141-141">有关建议的反恶意软件策略设置，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="1a141-141">For our recommended settings for anti-malware policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="1a141-142">使用安全与合规中心创建反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-142">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="1a141-143">在安全与合规中心内创建自定义反垃圾邮件策略，会同时创建垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="1a141-143">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="1a141-144">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-144">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1a141-145">在 **“反垃圾邮件设置”** 页上，单击 **“创建策略”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-145">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="1a141-146">在随即打开的 **“新建垃圾邮件筛选策略”** 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="1a141-146">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1a141-147">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="1a141-147">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="1a141-148">请勿使用以下字符：`\ % & * + / = ? { } | < > ( ) ; : , [ ] "`。</span><span class="sxs-lookup"><span data-stu-id="1a141-148">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="1a141-149">如果以前在 Exchange 管理中心 (EAC) 内创建了包含这些字符的反垃圾邮件策略，应在 PowerShell 中重命名反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-149">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="1a141-150">有关说明，请参阅本主题稍后将介绍的[使用 PowerShell 修改垃圾邮件筛选规则](#use-powershell-to-modify-spam-filter-rules)部分。</span><span class="sxs-lookup"><span data-stu-id="1a141-150">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="1a141-151">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="1a141-151">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="1a141-152">（可选）展开 **“垃圾邮件和批量操作”** 部分，然后验证或配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="1a141-152">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="1a141-153">**选择要对传入的垃圾邮件和群发电子邮件执行的操作**：选择或审阅根据以下垃圾邮件筛选裁定而对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="1a141-153">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="1a141-154">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-154">**Spam**</span></span>
     - <span data-ttu-id="1a141-155">**高可信度垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-155">**High confidence spam**</span></span>
     - <span data-ttu-id="1a141-156">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-156">**Phishing email**</span></span>
     - <span data-ttu-id="1a141-157">**高可信度钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-157">**High confidence phishing email**</span></span>
     - <span data-ttu-id="1a141-158">**群发电子邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-158">**Bulk email**</span></span>

     <span data-ttu-id="1a141-159">下表介绍了可以根据垃圾邮件筛选裁定而执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1a141-159">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="1a141-160">复选标记 (</span><span class="sxs-lookup"><span data-stu-id="1a141-160">A check mark (</span></span> ![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="1a141-162">) 表示操作可以执行（并不是所有操作都适用于所有垃圾邮件筛选裁定）。</span><span class="sxs-lookup"><span data-stu-id="1a141-162">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="1a141-163">复选标记后面的星号 (<sup>\*</sup>) 表示垃圾邮件筛选裁定对应的默认操作。</span><span class="sxs-lookup"><span data-stu-id="1a141-163">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||<span data-ttu-id="1a141-164">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-164">**Spam**</span></span>|<span data-ttu-id="1a141-165">**高<br/>可信度<br/>垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-165">**High<br/>confidence<br/>spam**</span></span>|<span data-ttu-id="1a141-166">**钓鱼<br/>电子邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-166">**Phishing<br/>email**</span></span>|<span data-ttu-id="1a141-167">**高<br/>可信度<br/>钓鱼<br/>电子邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-167">**High<br/>confidence<br/>phishing<br/>email**</span></span>|<span data-ttu-id="1a141-168">**群发<br/>电子邮件**</span><span class="sxs-lookup"><span data-stu-id="1a141-168">**Bulk<br/>email**</span></span>|
    |<span data-ttu-id="1a141-169">**将邮件移动到“垃圾邮件”文件夹**：邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-169">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="1a141-170">![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-170">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="1a141-171">![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-171">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="1a141-174">![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-174">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="1a141-175">**添加 X 标头**：向邮件头添加 X 标头，并将邮件递送到邮箱。</span><span class="sxs-lookup"><span data-stu-id="1a141-175">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="1a141-176">稍后将在 **“添加此 X 标头文本”** 框中，输入 X 标头字段名称（而不是值）。</span><span class="sxs-lookup"><span data-stu-id="1a141-176">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="1a141-177">对于 **“垃圾邮件”** 和 **“高可信度垃圾邮件”** 裁定，邮件移动到“垃圾邮件”文件夹。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-177">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="1a141-181">![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-181">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="1a141-182">**在主题行前面追加文本**：向邮件的主题行开头添加文本。</span><span class="sxs-lookup"><span data-stu-id="1a141-182">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="1a141-183">邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-183">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="1a141-184">稍后将在 **“在主题行前面添加此文本作为前缀”** 框中输入文本。</span><span class="sxs-lookup"><span data-stu-id="1a141-184">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1a141-189">**将邮件重定向到电子邮件地址**：将邮件发送给其他收件人，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="1a141-189">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="1a141-190">稍后将在 **“重定向到此电子邮件地址”** 框中指定收件人。</span><span class="sxs-lookup"><span data-stu-id="1a141-190">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1a141-196">**删除邮件**：无提示删除整个邮件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="1a141-196">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1a141-201">**隔离邮件**：将邮件发送到隔离，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="1a141-201">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="1a141-202">稍后将在 **“隔离”** 框中指定所需的邮件隔离时长。</span><span class="sxs-lookup"><span data-stu-id="1a141-202">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="1a141-205">![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a141-205">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1a141-208">**无操作**</span><span class="sxs-lookup"><span data-stu-id="1a141-208">**No action**</span></span>|||||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <span data-ttu-id="1a141-210"><sup>1</sup>在 Exchange Online 中，如果邮箱启用了垃圾邮件规则（默认处于启用状态），邮件会移动到“垃圾邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="1a141-210"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1a141-211">有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-211">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span><br/><span data-ttu-id="1a141-212">在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="1a141-212">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="1a141-213">有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-213">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span><br/><br/><span data-ttu-id="1a141-214"><sup>2</sup>可以将此使用值用作邮件流规则（亦称为“传输规则”）中的条件来筛选或路由邮件。</span><span class="sxs-lookup"><span data-stu-id="1a141-214"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="1a141-215">**选择阈值**：指定触发 **“群发电子邮件”** 垃圾邮件筛选裁定的指定操作的邮件批量投诉级别 (BCL)（大于指定值，而不是小于或等于指定值）。</span><span class="sxs-lookup"><span data-stu-id="1a141-215">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="1a141-216">值越高，邮件就越不理想（是垃圾邮件的可能性就越大）。</span><span class="sxs-lookup"><span data-stu-id="1a141-216">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="1a141-217">默认值为 7。</span><span class="sxs-lookup"><span data-stu-id="1a141-217">The default value is 7.</span></span> <span data-ttu-id="1a141-218">有关详细信息，请参阅 [EOP 中的批量投诉级别 (BCL)](bulk-complaint-level-values.md)，以及[垃圾邮件与群发电子邮件有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-218">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="1a141-219">默认情况下，在反垃圾邮件策略中，仅在 PowerShell 中可配置的设置 _MarkAsSpamBulkMail_ 的值为 `On`。</span><span class="sxs-lookup"><span data-stu-id="1a141-219">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="1a141-220">此设置极大地影响 **“群发电子邮件”** 筛选裁定结果：</span><span class="sxs-lookup"><span data-stu-id="1a141-220">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="1a141-221">**_MarkAsSpamBulkMail_ 的值为“On”**：大于阈值的 BCL 转换为对应于 **“垃圾邮件”** 筛选裁定的 SCL 6，并会对邮件执行 **“群发电子邮件”** 筛选裁定对应的操作。</span><span class="sxs-lookup"><span data-stu-id="1a141-221">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="1a141-222">**_MarkAsSpamBulkMail_ 的值为“Off”**：虽然邮件已有 BCL 标记，但_不会_根据 **“群发电子邮件”** 筛选裁定执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="1a141-222">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="1a141-223">实际上，BCL 阈值和 **“群发电子邮件”** 筛选裁定对应的操作不相关。</span><span class="sxs-lookup"><span data-stu-id="1a141-223">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="1a141-224">**隔离**：指定在选择 **“隔离邮件”** 作为垃圾邮件筛选裁定对应的操作时的邮件隔离时长。</span><span class="sxs-lookup"><span data-stu-id="1a141-224">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1a141-225">在此时间段到期后，邮件就会被删除。</span><span class="sxs-lookup"><span data-stu-id="1a141-225">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="1a141-226">默认值为 30 天。</span><span class="sxs-lookup"><span data-stu-id="1a141-226">The default value is 30 days.</span></span> <span data-ttu-id="1a141-227">有效值介于 1 和 30 天之间。</span><span class="sxs-lookup"><span data-stu-id="1a141-227">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="1a141-228">若要了解隔离，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="1a141-228">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="1a141-229">EOP 中隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="1a141-229">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="1a141-230">在 EOP 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="1a141-230">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="1a141-231">在 EOP 中以用户身份查找和释放已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="1a141-231">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="1a141-232">**添加此 X 标头文本**：只有当你选择 **“添加 X 标头”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。</span><span class="sxs-lookup"><span data-stu-id="1a141-232">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1a141-233">指定的值是添加到邮件头的标头字段*名称*。</span><span class="sxs-lookup"><span data-stu-id="1a141-233">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="1a141-234">标头字段*值*始终为 `This message appears to be spam`。</span><span class="sxs-lookup"><span data-stu-id="1a141-234">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="1a141-235">长度上限为 255 个字符，且值不得包含空格或冒号 (:)。</span><span class="sxs-lookup"><span data-stu-id="1a141-235">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="1a141-236">例如，如果你输入值 `X-This-is-my-custom-header`，则添加到邮件的 X 标头为 `X-This-is-my-custom-header: This message appears to be spam.`</span><span class="sxs-lookup"><span data-stu-id="1a141-236">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="1a141-237">如果你输入的值包含空格或冒号 (:)，输入值会遭忽略，且添加到邮件中的是默认 X 标头 (`X-This-Is-Spam: This message appears to be spam.`)。</span><span class="sxs-lookup"><span data-stu-id="1a141-237">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="1a141-238">**在主题行前面添加此文本作为前缀**：只有当你选择 **“在主题行前面追加文本”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。</span><span class="sxs-lookup"><span data-stu-id="1a141-238">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1a141-239">输入要添加到邮件主题行开头的文本。</span><span class="sxs-lookup"><span data-stu-id="1a141-239">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="1a141-240">**重定向到此电子邮件地址**：只有当你选择 **“将邮件重定向到电子邮件地址”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。</span><span class="sxs-lookup"><span data-stu-id="1a141-240">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1a141-241">输入要将邮件递送到的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1a141-241">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="1a141-242">可以输入多个值，用分号 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="1a141-242">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="1a141-243">**安全提示**：“安全提示”默认处于启用状态，但你可以通过取消选中 **“开”** 复选框来禁用它。</span><span class="sxs-lookup"><span data-stu-id="1a141-243">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="1a141-244">若要详细了解安全提示，请参阅 [电子邮件安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-244">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="1a141-245">**零时差自动清除**设置：ZAP 检测已递送到 Exchange Online 邮箱的邮件，并对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="1a141-245">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="1a141-246">若要详细了解 ZAP，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-246">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="1a141-247">**垃圾邮件 ZAP**：ZAP 默认启用垃圾邮件检测，但你可以通过取消选中 **“开”** 复选框来禁用它。</span><span class="sxs-lookup"><span data-stu-id="1a141-247">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="1a141-248">**钓鱼邮件 ZAP**：ZAP 默认启用钓鱼邮件检测，但你可以通过取消选中 **“开”** 复选框来禁用它。</span><span class="sxs-lookup"><span data-stu-id="1a141-248">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="1a141-249">（可选）展开 **“允许列表”** 部分，通过电子邮件地址或电子邮件域配置允许跳过垃圾邮件筛选的邮件发件人：</span><span class="sxs-lookup"><span data-stu-id="1a141-249">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   > <span data-ttu-id="1a141-250">• 在此处添加域之前，请慎重考虑。</span><span class="sxs-lookup"><span data-stu-id="1a141-250">• Think very carefully before you add domains here.</span></span> <span data-ttu-id="1a141-251">有关详细信息，请参阅[在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="1a141-251">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span> <br/><br/> <span data-ttu-id="1a141-252">• 切勿将接受的域（你拥有的域）或公共域（例如，microsoft.com 或 office.com）添加到允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="1a141-252">• Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="1a141-253">这会允许攻击者将不使用垃圾邮件筛选的电子邮件发送到你的组织。</span><span class="sxs-lookup"><span data-stu-id="1a141-253">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span>

   - <span data-ttu-id="1a141-254">**允许发件人**：单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-254">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="1a141-255">在随即显示的 **“允许的发件人列表”** 浮出控件中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1a141-255">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="1a141-256">a.</span><span class="sxs-lookup"><span data-stu-id="1a141-256">a.</span></span> <span data-ttu-id="1a141-257">输入发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1a141-257">Enter the sender's email address.</span></span> <span data-ttu-id="1a141-258">可以指定多个电子邮件地址，用分号 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="1a141-258">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="1a141-259">b.</span><span class="sxs-lookup"><span data-stu-id="1a141-259">b.</span></span> <span data-ttu-id="1a141-260">单击</span><span class="sxs-lookup"><span data-stu-id="1a141-260">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1a141-262">添加发件人。</span><span class="sxs-lookup"><span data-stu-id="1a141-262">to add the senders.</span></span>

      <span data-ttu-id="1a141-263">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="1a141-263">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1a141-264">你添加的发件人显示在浮出控件上的 **“允许的发件人”** 部分中。</span><span class="sxs-lookup"><span data-stu-id="1a141-264">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="1a141-265">若要删除发件人，请单击 ![“删除”图标](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="1a141-265">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1a141-266">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-266">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1a141-267">**允许域**：单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-267">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="1a141-268">在随即显示的 **“允许的域列表”** 浮出控件中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1a141-268">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="1a141-269">a.</span><span class="sxs-lookup"><span data-stu-id="1a141-269">a.</span></span> <span data-ttu-id="1a141-270">输入域。</span><span class="sxs-lookup"><span data-stu-id="1a141-270">Enter the domain.</span></span> <span data-ttu-id="1a141-271">可以指定多个域，用分号 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="1a141-271">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="1a141-272">b.</span><span class="sxs-lookup"><span data-stu-id="1a141-272">b.</span></span> <span data-ttu-id="1a141-273">单击</span><span class="sxs-lookup"><span data-stu-id="1a141-273">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1a141-275">添加域。</span><span class="sxs-lookup"><span data-stu-id="1a141-275">to add the domains.</span></span>

      <span data-ttu-id="1a141-276">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="1a141-276">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1a141-277">你添加的域显示在浮出控件上的 **“允许的域”** 部分中。</span><span class="sxs-lookup"><span data-stu-id="1a141-277">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="1a141-278">若要删除域，请单击 ![“删除”图标](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="1a141-278">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1a141-279">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-279">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="1a141-280">（可选）展开 **“阻止列表”** 部分，通过电子邮件地址或电子邮件域配置始终被标记为“高可信度垃圾邮件”的邮件发件人：</span><span class="sxs-lookup"><span data-stu-id="1a141-280">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="1a141-281">手动阻止域并不危险，但可能会增加管理工作量。</span><span class="sxs-lookup"><span data-stu-id="1a141-281">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="1a141-282">有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-282">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="1a141-283">**阻止发件人**：单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-283">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="1a141-284">在随即显示的 **“阻止的发件人列表”** 浮出控件中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1a141-284">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="1a141-285">a.</span><span class="sxs-lookup"><span data-stu-id="1a141-285">a.</span></span> <span data-ttu-id="1a141-286">输入发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1a141-286">Enter the sender's email address.</span></span> <span data-ttu-id="1a141-287">可以指定多个电子邮件地址，用分号 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="1a141-287">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="1a141-288">不允许使用通配符 (\*)。</span><span class="sxs-lookup"><span data-stu-id="1a141-288">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="1a141-289">b.</span><span class="sxs-lookup"><span data-stu-id="1a141-289">b.</span></span> <span data-ttu-id="1a141-290">单击</span><span class="sxs-lookup"><span data-stu-id="1a141-290">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1a141-292">添加发件人。</span><span class="sxs-lookup"><span data-stu-id="1a141-292">to add the senders.</span></span>

      <span data-ttu-id="1a141-293">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="1a141-293">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1a141-294">你添加的发件人显示在浮出控件上的 **“阻止的发件人”** 部分中。</span><span class="sxs-lookup"><span data-stu-id="1a141-294">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="1a141-295">若要删除发件人，请单击 ![“删除”按钮](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="1a141-295">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1a141-296">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-296">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1a141-297">**阻止域**：单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-297">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="1a141-298">在随即显示的 **“阻止的域列表”** 浮出控件中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1a141-298">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="1a141-299">a.</span><span class="sxs-lookup"><span data-stu-id="1a141-299">a.</span></span> <span data-ttu-id="1a141-300">输入域。</span><span class="sxs-lookup"><span data-stu-id="1a141-300">Enter the domain.</span></span> <span data-ttu-id="1a141-301">可以指定多个域，用分号 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="1a141-301">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="1a141-302">不允许使用通配符 (\*)。</span><span class="sxs-lookup"><span data-stu-id="1a141-302">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="1a141-303">b.</span><span class="sxs-lookup"><span data-stu-id="1a141-303">b.</span></span> <span data-ttu-id="1a141-304">单击</span><span class="sxs-lookup"><span data-stu-id="1a141-304">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1a141-306">添加域。</span><span class="sxs-lookup"><span data-stu-id="1a141-306">to add the domains.</span></span>

      <span data-ttu-id="1a141-307">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="1a141-307">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1a141-308">你添加的域显示在浮出控件上的 **“阻止的域”** 列表中。</span><span class="sxs-lookup"><span data-stu-id="1a141-308">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="1a141-309">若要删除域，请单击 ![“删除”按钮](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="1a141-309">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1a141-310">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-310">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="1a141-311">（可选）展开 **“国际垃圾邮件”** 部分，配置被垃圾邮件筛选阻止的电子邮件语言或源国家/地区：</span><span class="sxs-lookup"><span data-stu-id="1a141-311">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="1a141-312">**筛选用以下语言编写的电子邮件**：此设置默认处于禁用状态（**“状态”：“关”**）。</span><span class="sxs-lookup"><span data-stu-id="1a141-312">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="1a141-313">单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-313">Click **Edit**.</span></span> <span data-ttu-id="1a141-314">在随即显示的 **“国际垃圾邮件设置”** 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="1a141-314">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="1a141-315">**筛选用以下语言编写的电子邮件**：选中此复选框，以启用这项设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-315">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="1a141-316">取消选中此复选框可禁用这项设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-316">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="1a141-317">单击此框，然后开始键入语言*名称*。</span><span class="sxs-lookup"><span data-stu-id="1a141-317">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="1a141-318">此时会显示受支持语言的筛选列表，以及相应的 ISO 639-2 语言代码。</span><span class="sxs-lookup"><span data-stu-id="1a141-318">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="1a141-319">选中找到的所需语言。</span><span class="sxs-lookup"><span data-stu-id="1a141-319">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="1a141-320">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="1a141-320">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="1a141-321">你选择的语言列表显示在浮出控件上。</span><span class="sxs-lookup"><span data-stu-id="1a141-321">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="1a141-322">若要删除语言，请单击</span><span class="sxs-lookup"><span data-stu-id="1a141-322">To delete a language, click</span></span> ![“删除”按钮](../../media/scc-remove-icon.png)<span data-ttu-id="1a141-324">。</span><span class="sxs-lookup"><span data-stu-id="1a141-324">.</span></span>

     <span data-ttu-id="1a141-325">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-325">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1a141-326">**筛选以下国家或地区发送来的电子邮件**：此设置默认处于禁用状态（**“状态”：“关”**）。</span><span class="sxs-lookup"><span data-stu-id="1a141-326">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="1a141-327">若要启用此设置，请单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-327">To enable it, click **Edit**.</span></span> <span data-ttu-id="1a141-328">在随即显示的 **“国际垃圾邮件设置”** 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="1a141-328">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="1a141-329">**筛选以下国家或地区发送来的电子邮件**：选中此复选框，以启用这项设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-329">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="1a141-330">取消选中此复选框可禁用这项设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-330">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="1a141-331">单击此框，然后开始键入国家或地区*名称*。</span><span class="sxs-lookup"><span data-stu-id="1a141-331">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="1a141-332">此时会显示受支持国家/地区的筛选列表，以及相应的 ISO 3166-1 国家/地区代码（由两个字母组成）。</span><span class="sxs-lookup"><span data-stu-id="1a141-332">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="1a141-333">选中找到的所需国家或地区。</span><span class="sxs-lookup"><span data-stu-id="1a141-333">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="1a141-334">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="1a141-334">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="1a141-335">你选择的国家/地区列表显示在浮出控件上。</span><span class="sxs-lookup"><span data-stu-id="1a141-335">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="1a141-336">若要删除国家或地区，请单击</span><span class="sxs-lookup"><span data-stu-id="1a141-336">To delete a country or region, click</span></span> ![“删除”按钮](../../media/scc-remove-icon.png)<span data-ttu-id="1a141-338">。</span><span class="sxs-lookup"><span data-stu-id="1a141-338">.</span></span>

     <span data-ttu-id="1a141-339">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-339">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="1a141-340">可选 **“垃圾邮件属性”** 部分包含默认禁用的高级垃圾邮件筛选 (ASF) 设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-340">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="1a141-341">ASF 设置即将弃用，其功能正在合并到筛选堆栈的其他部分中。</span><span class="sxs-lookup"><span data-stu-id="1a141-341">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="1a141-342">建议在反垃圾邮件策略中保持所有这些 ASF 设置的禁用状态不变。</span><span class="sxs-lookup"><span data-stu-id="1a141-342">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="1a141-343">若要详细了解这些设置，请参阅 [EOP 中的高级垃圾邮件筛选设置](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-343">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="1a141-344">（必需）展开 **“应用于”** 部分，以确定向哪些内部收件人应用策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-344">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="1a141-345">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="1a141-345">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="1a141-346">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="1a141-346">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="1a141-347">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="1a141-347">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="1a141-348">若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。</span><span class="sxs-lookup"><span data-stu-id="1a141-348">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="1a141-349">若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="1a141-349">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="1a141-350">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="1a141-350">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span> <span data-ttu-id="1a141-351">单击 **“添加标记”** 框，以查看并选择域。</span><span class="sxs-lookup"><span data-stu-id="1a141-351">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="1a141-352">如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。</span><span class="sxs-lookup"><span data-stu-id="1a141-352">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="1a141-353">**收件人是**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="1a141-353">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="1a141-354">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="1a141-354">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="1a141-355">若要选择其他收件人，请再次单击 **“添加标记”** 框。</span><span class="sxs-lookup"><span data-stu-id="1a141-355">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="1a141-356">**收件人是以下组的成员**：指定组织中的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="1a141-356">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="1a141-357">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="1a141-357">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="1a141-358">若要选择其他收件人，请再次单击 **“添加标记”** 框。</span><span class="sxs-lookup"><span data-stu-id="1a141-358">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="1a141-359">**下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。</span><span class="sxs-lookup"><span data-stu-id="1a141-359">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="1a141-360">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="1a141-360">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="1a141-361">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-361">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="1a141-362">使用安全与合规中心查看反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-362">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="1a141-363">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-363">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1a141-364">在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开反垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="1a141-364">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="1a141-365">名为 **“默认垃圾邮件筛选策略”** 的默认策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-365">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="1a141-366">你创建的自定义策略，其中 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-366">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="1a141-367">随即出现的展开策略详细信息中显示了重要的策略设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-367">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="1a141-368">若要查看更多详情，请单击 **“编辑策略”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-368">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="1a141-369">使用安全与合规中心修改反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-369">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="1a141-370">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-370">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1a141-371">在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开反垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="1a141-371">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="1a141-372">名为 **“默认垃圾邮件筛选策略”** 的默认策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-372">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="1a141-373">你创建的自定义策略，其中 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-373">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="1a141-374">单击 **“编辑策略”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-374">Click **Edit policy**.</span></span>

<span data-ttu-id="1a141-375">对于自定义反垃圾邮件策略，随即显示的浮出控件中的可配置设置与[使用安全与合规中心创建反垃圾邮件策略](#use-the-security--compliance-center-to-create-anti-spam-policies)部分中介绍的设置完全相同。</span><span class="sxs-lookup"><span data-stu-id="1a141-375">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="1a141-376">对于名为 **“默认垃圾邮件筛选策略”** 的默认反垃圾邮件策略，没有 **“应用于”** 部分（此策略应用于所有人），且无法重命名此策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-376">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="1a141-377">若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。</span><span class="sxs-lookup"><span data-stu-id="1a141-377">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="1a141-378">启用或禁用反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-378">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="1a141-379">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-379">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1a141-380">在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开已创建的自定义策略（**“类型”** 列中的值为 **“自定义反垃圾邮件策略”**）。</span><span class="sxs-lookup"><span data-stu-id="1a141-380">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="1a141-381">在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。</span><span class="sxs-lookup"><span data-stu-id="1a141-381">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="1a141-382">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="1a141-382">Move the toggle to the left to disable the policy:</span></span> ![切换开关关闭](../../media/scc-toggle-off.png)

   <span data-ttu-id="1a141-384">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="1a141-384">Move the toggle to the right to enable the policy:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="1a141-386">无法禁用默认反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-386">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="1a141-387">设置自定义反垃圾邮件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="1a141-387">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="1a141-388">默认情况下，反垃圾邮件策略根据创建顺序来获得优先级（新策略的优先级低于旧策略）。</span><span class="sxs-lookup"><span data-stu-id="1a141-388">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="1a141-389">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="1a141-389">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="1a141-390">没有两个策略可以有相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="1a141-390">No two policies can have the same priority.</span></span>

<span data-ttu-id="1a141-391">自定义反垃圾邮件策略按处理顺序显示（第一个策略的 **“优先级”** 值为“0”）。</span><span class="sxs-lookup"><span data-stu-id="1a141-391">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="1a141-392">名为 **“默认垃圾邮件筛选策略”** 的默认反垃圾邮件策略的优先级值为 **“最低”**，你无法更改此值。</span><span class="sxs-lookup"><span data-stu-id="1a141-392">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="1a141-393">**注意**：在安全与合规中心内，只能更改已创建的反垃圾邮件策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="1a141-393">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="1a141-394">在 PowerShell 中，可以在创建垃圾邮件筛选规则时替代默认优先级（这可能会影响现有规则的优先级）。</span><span class="sxs-lookup"><span data-stu-id="1a141-394">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="1a141-395">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="1a141-395">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="1a141-396">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-396">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1a141-397">在 **“反垃圾邮件设置”** 页上，查找 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”** 的策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-397">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="1a141-398">注意 **“优先级”** 列中的值：</span><span class="sxs-lookup"><span data-stu-id="1a141-398">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="1a141-399">优先级最高的自定义反垃圾邮件策略的值为 ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) **0**。</span><span class="sxs-lookup"><span data-stu-id="1a141-399">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="1a141-400">优先级最低的自定义反垃圾邮件策略的值为 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) **n**（例如，![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) **3**）。</span><span class="sxs-lookup"><span data-stu-id="1a141-400">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="1a141-401">如果有三个或更多个自定义反垃圾邮件策略，介于最高和最低优先级之间的策略的值为 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png)![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) **n**（例如，![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png)![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) **2**）。</span><span class="sxs-lookup"><span data-stu-id="1a141-401">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="1a141-402">单击</span><span class="sxs-lookup"><span data-stu-id="1a141-402">Click</span></span> ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="1a141-404">或</span><span class="sxs-lookup"><span data-stu-id="1a141-404">or</span></span> ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="1a141-406">在优先级列表中上移或下移自定义反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-406">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="1a141-407">配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="1a141-407">Configure end-user spam notifications</span></span>

<span data-ttu-id="1a141-408">如果垃圾邮件筛选裁定隔离了邮件，你可以配置最终用户垃圾邮件通知，让收件人知道向他们发送的邮件发生了什么。</span><span class="sxs-lookup"><span data-stu-id="1a141-408">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="1a141-409">若要详细了解这些通知，请参阅 [ EOP 中的最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1a141-409">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="1a141-410">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-410">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1a141-411">在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开反垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="1a141-411">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="1a141-412">名为 **“默认垃圾邮件筛选策略”** 的默认策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-412">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="1a141-413">你创建的自定义策略，其中 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-413">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="1a141-414">在随即显示的展开策略详细信息中，单击 **“配置最终用户垃圾邮件通知”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-414">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="1a141-415">在随即打开的 **\<Policy Name\>** 对话框中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="1a141-415">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1a141-416">**启用最终用户垃圾邮件通知**：选中此复选框，以启用通知。</span><span class="sxs-lookup"><span data-stu-id="1a141-416">**Enable end-user spam notifications**: Select the checkbobx to enable notifications.</span></span> <span data-ttu-id="1a141-417">取消选中此复选框可禁用通知。</span><span class="sxs-lookup"><span data-stu-id="1a141-417">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="1a141-418">**发送最终用户垃圾邮件通知的间隔天数**：选择通知发送频率。</span><span class="sxs-lookup"><span data-stu-id="1a141-418">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="1a141-419">默认值为 3 天。</span><span class="sxs-lookup"><span data-stu-id="1a141-419">The default value is 3 days.</span></span> <span data-ttu-id="1a141-420">可输入介于 1 和 15 天之间的值。</span><span class="sxs-lookup"><span data-stu-id="1a141-420">You can enter 1 to 15 days.</span></span>

     <span data-ttu-id="1a141-421">在 24 小时内，有 3 个从以下时间开始计时的最终用户垃圾邮件通知周期：01:00 UTC、08:00 UTC 和 16:00 UTC。</span><span class="sxs-lookup"><span data-stu-id="1a141-421">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span> 

     > [!NOTE]
     > <span data-ttu-id="1a141-422">如果我们在上一个周期中错过了通知，则后续周期会推送通知。</span><span class="sxs-lookup"><span data-stu-id="1a141-422">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="1a141-423">这可能会在同一天内显示多个通知。</span><span class="sxs-lookup"><span data-stu-id="1a141-423">This may give the appearance of multiple notifications within the same day.</span></span>

   - <span data-ttu-id="1a141-424">**通知语言**：单击下拉列表，并从列表中选择可用语言。</span><span class="sxs-lookup"><span data-stu-id="1a141-424">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="1a141-425">默认值是 **“默认”**，表示最终用户隔离通知使用 EOP 组织的默认语言。</span><span class="sxs-lookup"><span data-stu-id="1a141-425">The default value is **Default**, which means end-user quarantine notifications use the default language of the EOP organization.</span></span>

   <span data-ttu-id="1a141-426">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-426">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="1a141-427">使用安全与合规中心删除反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-427">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="1a141-428">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-428">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1a141-429">在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开要删除的自定义策略（**“类型”** 列中的值为 **“自定义反垃圾邮件策略”**）。</span><span class="sxs-lookup"><span data-stu-id="1a141-429">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="1a141-430">在随即显示的展开策略详细信息中，单击 **“删除策略”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-430">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="1a141-431">在随即显示的警告对话框中，单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-431">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="1a141-432">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-432">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="1a141-433">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-433">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="1a141-434">以下反垃圾邮件策略设置仅在 PowerShell 中可配置：</span><span class="sxs-lookup"><span data-stu-id="1a141-434">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="1a141-435">默认情况下，_MarkAsSpamBulkMail_ 参数的值为 `On`。</span><span class="sxs-lookup"><span data-stu-id="1a141-435">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="1a141-436">本主题前面的[使用安全与合规中心创建反垃圾邮件策略](#use-the-security--compliance-center-to-create-anti-spam-policies)部分中介绍了此设置的效果。</span><span class="sxs-lookup"><span data-stu-id="1a141-436">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="1a141-437">以下设置用于最终用户垃圾邮件隔离通知：</span><span class="sxs-lookup"><span data-stu-id="1a141-437">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="1a141-438">_DownloadLink_ 参数：显示或隐藏 Outlook 垃圾邮件报告工具的链接。</span><span class="sxs-lookup"><span data-stu-id="1a141-438">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="1a141-439">_EndUserSpamNotificationCustomSubject_ 参数：可用于自定义通知的主题行。</span><span class="sxs-lookup"><span data-stu-id="1a141-439">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="1a141-440">使用 PowerShell 创建反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1a141-440">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="1a141-441">在 PowerShell 中创建反垃圾邮件策略的过程分为两步：</span><span class="sxs-lookup"><span data-stu-id="1a141-441">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="1a141-442">创建垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-442">Create the spam filter policy.</span></span>

2. <span data-ttu-id="1a141-443">创建垃圾邮件筛选规则，它指定了向哪个垃圾邮件筛选策略应用规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-443">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="1a141-444">**注意**：</span><span class="sxs-lookup"><span data-stu-id="1a141-444">**Notes**:</span></span>

- <span data-ttu-id="1a141-445">可以新建垃圾邮件筛选规则，并向它分配未关联的现有垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-445">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="1a141-446">垃圾邮件筛选规则不能与多个垃圾邮件筛选策略关联。</span><span class="sxs-lookup"><span data-stu-id="1a141-446">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="1a141-447">可以在 PowerShell 中对新垃圾邮件筛选策略配置以下设置（在安全与合规中心内，只有在创建策略后，才能配置这些设置）：</span><span class="sxs-lookup"><span data-stu-id="1a141-447">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="1a141-448">新建禁用的策略（在 **New-HostedContentFilterRule** cmdlet 上 _Enabled_ 为 `$false`）。</span><span class="sxs-lookup"><span data-stu-id="1a141-448">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="1a141-449">在创建过程中，在 **New-HostedContentFilterRule** cmdlet 上设置策略优先级（_优先级_ _\<Number\>_）。</span><span class="sxs-lookup"><span data-stu-id="1a141-449">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="1a141-450">在 PowerShell 中新建的垃圾邮件筛选策略在安全与合规中心内不可见，除非你将策略分配到垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-450">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="1a141-451">第 1 步：使用 PowerShell 创建垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="1a141-451">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="1a141-452">若要创建垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-452">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="1a141-453">下面的示例使用以下设置创建名为“Contoso Executives”的垃圾邮件筛选策略：</span><span class="sxs-lookup"><span data-stu-id="1a141-453">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="1a141-454">当垃圾邮件筛选裁定为“垃圾邮件”或“高可信度垃圾邮件”时隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="1a141-454">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="1a141-455">BCL 6 触发“群发电子邮件”垃圾邮件筛选裁定对应的操作。</span><span class="sxs-lookup"><span data-stu-id="1a141-455">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="1a141-456">**New-HostedContentFilterPolicy** 和 **Set-HostedContentFilterPolicy** 包含旧的 _ZapEnabled_ 参数，以及新的 _PhishZapEnabled_ 和 _SpamZapEnabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="1a141-456">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="1a141-457">_ZapEnabled_ 参数已在 2020 年 2 月遭弃用。</span><span class="sxs-lookup"><span data-stu-id="1a141-457">The _ZapEnabled_ parameter was deprecated in February, 2020.</span></span> <span data-ttu-id="1a141-458">_PhishZapEnabled_ 和 _SpamZapEnabled_ 参数用于继承 _ZapEnabled_ 参数的值。</span><span class="sxs-lookup"><span data-stu-id="1a141-458">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="1a141-459">不过，如果你在命令中使用 _PhishZapEnabled_ 和 _SpamZapEnabled_ 参数，或在安全与合规中心内的反垃圾邮件策略中使用 **“垃圾邮件 ZAP”** 或 **“钓鱼邮件 ZAP”** 设置，_ZapEnabled_ 参数的值会遭忽略。</span><span class="sxs-lookup"><span data-stu-id="1a141-459">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="1a141-460">也就是说，请勿使用 _ZapEnabled_ 参数；而是改用 _PhishZapEnabled_ 和 _SpamZapEnabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="1a141-460">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="1a141-461">若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1a141-461">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="1a141-462">第 2 步：使用 PowerShell 创建垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="1a141-462">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="1a141-463">若要创建垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-463">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="1a141-464">下面的示例使用以下设置新建名为“Contoso Executives”的垃圾邮件筛选规则：</span><span class="sxs-lookup"><span data-stu-id="1a141-464">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="1a141-465">名为“Contoso Executives”的垃圾邮件筛选策略与此规则关联。</span><span class="sxs-lookup"><span data-stu-id="1a141-465">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="1a141-466">此规则应用于“Contoso Executives Group”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="1a141-466">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="1a141-467">若要详细了解语法和参数，请参阅 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="1a141-467">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="1a141-468">使用 PowerShell 查看垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="1a141-468">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="1a141-469">若要返回所有垃圾邮件筛选策略的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1a141-469">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="1a141-470">若要返回特定垃圾邮件筛选策略的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-470">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="1a141-471">下面的示例返回名为“Executives”的垃圾邮件筛选策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="1a141-471">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="1a141-472">若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1a141-472">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="1a141-473">使用 PowerShell 查看垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="1a141-473">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="1a141-474">若要查看现有垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-474">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="1a141-475">若要返回所有垃圾邮件筛选规则的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1a141-475">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="1a141-476">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1a141-476">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="1a141-477">若要返回特定垃圾邮件筛选规则的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-477">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="1a141-478">下面的示例返回名为“Contoso Executives”的垃圾邮件筛选规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="1a141-478">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="1a141-479">若要详细了解语法和参数，请参阅 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="1a141-479">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="1a141-480">使用 PowerShell 修改垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="1a141-480">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="1a141-481">除了以下几项之外，在 PowerShell 中修改恶意软件筛选策略时可用的设置，与本主题前面的[第 1 步：使用 PowerShell 创建垃圾邮件筛选策略](#step-1-use-powershell-to-create-a-spam-filter-policy)部分中介绍的可用于创建策略的设置相同。</span><span class="sxs-lookup"><span data-stu-id="1a141-481">Other than the following items, the same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="1a141-482">只有在 PowerShell 中修改垃圾邮件筛选策略时，才能使用 _MakeDefault_ 开关，它可将指定策略转换为默认策略（应用于所有人，优先级值始终为 **“最低”**，且无法删除）。</span><span class="sxs-lookup"><span data-stu-id="1a141-482">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="1a141-483">无法重命名垃圾邮件筛选策略（**Set-HostedContentFilterPolicy** cmdlet 没有 _Name_ 参数）。</span><span class="sxs-lookup"><span data-stu-id="1a141-483">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="1a141-484">在安全与合规中心内重命名反垃圾邮件策略时，只是在重命名垃圾邮件筛选_规则_。</span><span class="sxs-lookup"><span data-stu-id="1a141-484">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="1a141-485">若要修改垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-485">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="1a141-486">若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1a141-486">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="1a141-487">使用 PowerShell 修改垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="1a141-487">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="1a141-488">在 PowerShell 中修改垃圾邮件筛选规则时，唯一不可用的设置是，可用于创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="1a141-488">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="1a141-489">若要启用或禁用现有垃圾邮件筛选规则，请参阅下一部分。</span><span class="sxs-lookup"><span data-stu-id="1a141-489">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="1a141-490">否则，在 PowerShell 中修改垃圾邮件筛选规则时，将无法使用其他任何设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-490">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="1a141-491">创建规则时可用的设置，与本主题前面的[第 2 步：使用 PowerShell 创建垃圾邮件筛选规则](#step-2-use-powershell-to-create-a-spam-filter-rule)部分中介绍的设置相同。</span><span class="sxs-lookup"><span data-stu-id="1a141-491">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="1a141-492">若要修改垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-492">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="1a141-493">下面的示例重命名现有名为“`{Fabrikam Spam Filter}`”的垃圾邮件筛选规则（可能无法在安全与合规中心内重命名）。</span><span class="sxs-lookup"><span data-stu-id="1a141-493">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="1a141-494">若要详细了解语法和参数，请参阅 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="1a141-494">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="1a141-495">使用 PowerShell 启用或禁用垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="1a141-495">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="1a141-496">在 PowerShell 中启用或禁用垃圾邮件筛选规则会启用或禁用整个反垃圾邮件策略（即垃圾邮件筛选规则和分配的垃圾邮件筛选策略）。</span><span class="sxs-lookup"><span data-stu-id="1a141-496">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="1a141-497">无法启用或禁用默认反垃圾邮件策略（它始终应用于所有收件人）。</span><span class="sxs-lookup"><span data-stu-id="1a141-497">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="1a141-498">若要在 PowerShell 中启用或禁用垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-498">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="1a141-499">下面的示例禁用名为“Marketing Department”的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-499">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1a141-500">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-500">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1a141-501">若要详细了解语法和参数，请参阅 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="1a141-501">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="1a141-502">使用 PowerShell 设置垃圾邮件筛选规则的优先级</span><span class="sxs-lookup"><span data-stu-id="1a141-502">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="1a141-503">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="1a141-503">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="1a141-504">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="1a141-504">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="1a141-505">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="1a141-505">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="1a141-506">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="1a141-506">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="1a141-507">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="1a141-507">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="1a141-508">若要在 PowerShell 中设置垃圾邮件筛选规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-508">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="1a141-509">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="1a141-509">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="1a141-510">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="1a141-510">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="1a141-511">**注意**：</span><span class="sxs-lookup"><span data-stu-id="1a141-511">**Notes**:</span></span>

- <span data-ttu-id="1a141-512">若要在新建规则时设置它的优先级，请改为对 **New-HostedContentFilterRule** cmdlet 使用 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="1a141-512">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="1a141-513">默认垃圾邮件筛选策略没有相应的垃圾邮件筛选规则，且始终有不可修改的优先级值 **“最低”**。</span><span class="sxs-lookup"><span data-stu-id="1a141-513">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="1a141-514">使用 PowerShell 删除垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="1a141-514">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="1a141-515">如果使用 PowerShell 删除垃圾邮件筛选策略，不会删除相应的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-515">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="1a141-516">若要在 PowerShell 中删除垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-516">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="1a141-517">下面的示例删除名为“Marketing Department”的垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-517">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="1a141-518">若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1a141-518">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="1a141-519">使用 PowerShell 删除垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="1a141-519">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="1a141-520">使用 PowerShell 删除垃圾邮件筛选规则时，不会删除相应的垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="1a141-520">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="1a141-521">若要在 PowerShell 中删除垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1a141-521">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="1a141-522">下面的示例删除名为“Marketing Department”的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="1a141-522">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1a141-523">若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="1a141-523">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1a141-524">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="1a141-524">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="1a141-525">发送 GTUBE 邮件测试垃圾邮件策略设置</span><span class="sxs-lookup"><span data-stu-id="1a141-525">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="1a141-526">只有当你从中发送 GTUBE 邮件的电子邮件组织不扫描出站垃圾邮件时，才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="1a141-526">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="1a141-527">如果扫描，测试邮件便无法发送。</span><span class="sxs-lookup"><span data-stu-id="1a141-527">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="1a141-528">垃圾群发电子邮件的一般测试 (GTUBE) 是文本字符串，可以添加到测试邮件中，用于验证组织的反垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="1a141-528">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="1a141-529">GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。</span><span class="sxs-lookup"><span data-stu-id="1a141-529">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="1a141-530">在电子邮件中的某一行上，添加以下 GTUBE 文本，不得有任何空格或换行符：</span><span class="sxs-lookup"><span data-stu-id="1a141-530">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="1a141-531">允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="1a141-531">Allow/Block Lists</span></span>

<span data-ttu-id="1a141-532">有时候，筛选器会缺少邮件，或者我们的系统需要花费时间捕获邮件。</span><span class="sxs-lookup"><span data-stu-id="1a141-532">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="1a141-533">在这种情况下，反垃圾邮件策略提供了一个“允许”列表和一个“阻止”列表，可用于推翻现行裁决。</span><span class="sxs-lookup"><span data-stu-id="1a141-533">In this cases, the antispam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="1a141-534">应谨慎使用此选项，因为列表可能变得不可管理，而且由于我们的筛选堆栈应该做它应该做的事情，因此只能暂时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="1a141-534">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="1a141-535">在某些情况下，组织可能会不同意服务提供的结论。</span><span class="sxs-lookup"><span data-stu-id="1a141-535">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="1a141-536">在这种情况下, 你可能希望永久保留“允许”或“阻止”列表。</span><span class="sxs-lookup"><span data-stu-id="1a141-536">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="1a141-537">但是，如果你想要将一个域放在“允许”列表中一段时间，则应告知发件人确保其域已通过验证，并将其设置为“DMARC 拒绝”（如果不是）。</span><span class="sxs-lookup"><span data-stu-id="1a141-537">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
