---
title: 配置出站垃圾邮件筛选
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
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。
ms.openlocfilehash: 27f79252d2d08c374784064ac6a12bc4cc7725ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637720"
---
# <a name="configure-outbound-spam-filtering"></a><span data-ttu-id="f92a9-103">配置出站垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="f92a9-103">Configure outbound spam filtering</span></span>

<span data-ttu-id="f92a9-104">如果您是具有 Exchange Online 邮箱的 Microsoft 365 客户或没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）客户，则会自动检查通过 EOP 发送的出站电子邮件是否包含垃圾邮件和异常发送活动。</span><span class="sxs-lookup"><span data-stu-id="f92a9-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="f92a9-105">您组织中的用户的出站垃圾邮件通常表示已损坏的帐户。</span><span class="sxs-lookup"><span data-stu-id="f92a9-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="f92a9-106">可疑的出站邮件被标记为垃圾邮件（无论垃圾邮件可信度或 SCL），并通过[高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)进行路由，以帮助保护服务的声誉（即，将 Microsoft 365 源电子邮件服务器从 IP 阻止列表中注销）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="f92a9-107">系统会自动通知管理员可疑的出站电子邮件活动，并通过[通知策略](../../compliance/alert-policies.md)阻止用户。</span><span class="sxs-lookup"><span data-stu-id="f92a9-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="f92a9-108">EOP 使用出站垃圾邮件策略作为组织的整体防御垃圾邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="f92a9-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="f92a9-109">有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="f92a9-110">管理员可以查看、编辑和配置（但不能删除）默认的出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="f92a9-111">为了更细致，您还可以创建适用于组织中的特定用户、组或域的自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="f92a9-112">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="f92a9-113">您可以在 Security & 合规性中心或 PowerShell （Exchange Online PowerShell for Microsoft 365 客户;）中配置出站垃圾邮件策略。适用于独立 EOP 客户的 Exchange Online Protection PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="f92a9-114">Security & 合规性中心与 Exchange online PowerShell 或 Exchange Online Protection PowerShell 中的出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-114">Outbound spam policies in the Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="f92a9-115">EOP 中的出站垃圾邮件策略的基本元素为：</span><span class="sxs-lookup"><span data-stu-id="f92a9-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="f92a9-116">**出站垃圾邮件筛选器策略**：指定出站垃圾邮件筛选 verdicts 和通知选项的操作。</span><span class="sxs-lookup"><span data-stu-id="f92a9-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="f92a9-117">**出站垃圾邮件筛选器规则**：指定出站垃圾邮件筛选器策略的优先级和收件人筛选器（策略应用于的人）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="f92a9-118">在安全 & 合规中心中管理出站垃圾邮件策略时，这两个元素之间的差异并不明显：</span><span class="sxs-lookup"><span data-stu-id="f92a9-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f92a9-119">在安全 & 合规中心创建出站垃圾邮件策略时，实际上是创建出站垃圾邮件筛选器规则，同时为两者使用相同的名称创建相关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="f92a9-120">在安全 & 合规中心中修改出站垃圾邮件策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改出站垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="f92a9-121">所有其他设置修改关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="f92a9-122">从安全 & 合规中心删除出站垃圾邮件策略时，将删除出站垃圾邮件筛选器规则和关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="f92a9-123">在 Exchange Online PowerShell 或独立 Exchange Online Protection PowerShell 中，出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则之间的差异很明显。</span><span class="sxs-lookup"><span data-stu-id="f92a9-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="f92a9-124">您可以使用\*\* \*-set-hostedcontentfilterpolicy\*\* cmdlet 管理出站垃圾邮件筛选器策略，还可以使用\*\* \*-disable-hostedcontentfilterrule\*\* cmdlet 管理出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="f92a9-125">在 PowerShell 中，先创建出站垃圾邮件筛选器策略，然后创建出站垃圾邮件筛选器规则，以标识应用该规则的策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="f92a9-126">在 PowerShell 中，可以单独修改出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="f92a9-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="f92a9-127">从 PowerShell 删除出站垃圾邮件筛选器策略时，不会自动删除相应的出站垃圾邮件筛选器规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f92a9-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="f92a9-128">默认出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-128">Default outbound spam policy</span></span>

<span data-ttu-id="f92a9-129">每个组织都有一个名为 Default 的内置出站垃圾邮件策略，其中包含以下属性：</span><span class="sxs-lookup"><span data-stu-id="f92a9-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="f92a9-130">名为 "默认" 的出站垃圾邮件筛选器策略将应用于组织中的所有收件人，即使没有与该策略关联的出站垃圾邮件筛选器规则（收件人筛选器）也是如此。</span><span class="sxs-lookup"><span data-stu-id="f92a9-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="f92a9-131">名为“默认”的策略有无法修改的自定义优先级值 **“最低”**（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="f92a9-132">你创建的任何自定义策略的优先级始终高于名为“默认”的策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="f92a9-133">名为“默认”的策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="f92a9-134">若要提高出站垃圾邮件筛选的有效性，可以使用应用于特定用户或用户组的更严格的设置来创建自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f92a9-135">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="f92a9-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f92a9-136">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="f92a9-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f92a9-137">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="f92a9-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="f92a9-138">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f92a9-139">若要连接到独立 Exchange Online Protection，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f92a9-140">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="f92a9-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f92a9-141">若要添加、修改和删除出站垃圾邮件策略，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="f92a9-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f92a9-142">若要对出站垃圾邮件策略进行只读访问，您需要是**安全读者**角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="f92a9-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="f92a9-143">有关安全 & 合规中心中的角色组的详细信息，请参阅[security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f92a9-144">有关出站垃圾邮件策略的建议设置，请参阅[EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="f92a9-145">已**超过电子邮件发送限制**的默认[警报策略](../../compliance/alert-policies.md)，**检测到可疑的电子邮件发送模式**，并且**限制发送电子邮件的用户**已将电子邮件通知发送给**TenantAdmins** （**全局管理员**）组的成员，这是关于异常出站电子邮件活动和由于出站垃圾邮件而阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="f92a9-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="f92a9-146">有关详细信息，请参阅[验证受限制用户的通知设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="f92a9-147">我们建议您使用这些通知策略，而不是在出站垃圾邮件策略中的通知选项。</span><span class="sxs-lookup"><span data-stu-id="f92a9-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="f92a9-148">使用安全 & 合规性中心创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="f92a9-149">在安全 & 合规中心中创建自定义出站垃圾邮件策略将同时为两者创建垃圾邮件筛选器规则和关联的垃圾邮件筛选器策略，同时使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="f92a9-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f92a9-150">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f92a9-151">在 "**反垃圾邮件设置**" 页上，单击 "**创建出站策略**"。</span><span class="sxs-lookup"><span data-stu-id="f92a9-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="f92a9-152">在打开的**出站垃圾邮件筛选器策略**飞出后，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f92a9-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f92a9-153">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="f92a9-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="f92a9-154">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="f92a9-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="f92a9-155">Optional展开 "**通知**" 部分，配置应接收可疑出站电子邮件的副本和通知的其他用户：</span><span class="sxs-lookup"><span data-stu-id="f92a9-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="f92a9-156">向**特定人员发送可疑的出站电子邮件的副本**：此设置将指定的用户添加为可疑的出站邮件的密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="f92a9-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="f92a9-157">要启用此设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f92a9-157">To enable this setting:</span></span>

     <span data-ttu-id="f92a9-158">a.</span><span class="sxs-lookup"><span data-stu-id="f92a9-158">a.</span></span> <span data-ttu-id="f92a9-159">选中该复选框以启用该设置。</span><span class="sxs-lookup"><span data-stu-id="f92a9-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="f92a9-160">b.</span><span class="sxs-lookup"><span data-stu-id="f92a9-160">b.</span></span> <span data-ttu-id="f92a9-161">单击 "**添加人员**"。</span><span class="sxs-lookup"><span data-stu-id="f92a9-161">Click **Add people**.</span></span> <span data-ttu-id="f92a9-162">在显示的 "**添加或删除收件人**" 浮出控件中：</span><span class="sxs-lookup"><span data-stu-id="f92a9-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="f92a9-163">c.</span><span class="sxs-lookup"><span data-stu-id="f92a9-163">c.</span></span> <span data-ttu-id="f92a9-164">输入发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f92a9-164">Enter the sender's email address.</span></span> <span data-ttu-id="f92a9-165">可以指定用分号分隔的多个电子邮件地址（;)或每行一个收件人。</span><span class="sxs-lookup"><span data-stu-id="f92a9-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="f92a9-166">d.</span><span class="sxs-lookup"><span data-stu-id="f92a9-166">d.</span></span> <span data-ttu-id="f92a9-167">单击</span><span class="sxs-lookup"><span data-stu-id="f92a9-167">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="f92a9-169">添加收件人。</span><span class="sxs-lookup"><span data-stu-id="f92a9-169">to add the recipients.</span></span>

        <span data-ttu-id="f92a9-170">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="f92a9-171">您添加的收件人将显示在浮出控件的 "**收件人列表**" 部分。</span><span class="sxs-lookup"><span data-stu-id="f92a9-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="f92a9-172">若要删除收件人，请![单击 "](../../media/scc-remove-icon.png)删除" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f92a9-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="f92a9-173">e.</span><span class="sxs-lookup"><span data-stu-id="f92a9-173">e.</span></span> <span data-ttu-id="f92a9-174">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="f92a9-175">若要禁用此设置，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="f92a9-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="f92a9-176">**如果发件人因发送出站垃圾邮件而被阻止，请通知特定人员**：</span><span class="sxs-lookup"><span data-stu-id="f92a9-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="f92a9-177">当用户因超出 "**收件人限制**" 部分中的限制而被阻止时，名为 "**用户限制发往发送电子邮件**" 的默认[通知策略](../../compliance/alert-policies.md)将已向**TenantAdmins** （**全局管理员**）组的成员发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f92a9-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="f92a9-178">我们建议您在出站垃圾邮件策略中使用通知策略而不是此设置来通知管理员和其他用户。</span><span class="sxs-lookup"><span data-stu-id="f92a9-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="f92a9-179">有关说明，请参阅[验证受限制用户的通知设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="f92a9-180">要启用此设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f92a9-180">To enable this setting:</span></span>

     <span data-ttu-id="f92a9-181">a.</span><span class="sxs-lookup"><span data-stu-id="f92a9-181">a.</span></span> <span data-ttu-id="f92a9-182">选中该复选框以启用该设置。</span><span class="sxs-lookup"><span data-stu-id="f92a9-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="f92a9-183">b.</span><span class="sxs-lookup"><span data-stu-id="f92a9-183">b.</span></span> <span data-ttu-id="f92a9-184">单击 "**添加人员**"。</span><span class="sxs-lookup"><span data-stu-id="f92a9-184">Click **Add people**.</span></span> <span data-ttu-id="f92a9-185">在显示的 "**添加或删除收件人**" 浮出控件中：</span><span class="sxs-lookup"><span data-stu-id="f92a9-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="f92a9-186">c.</span><span class="sxs-lookup"><span data-stu-id="f92a9-186">c.</span></span> <span data-ttu-id="f92a9-187">输入发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f92a9-187">Enter the sender's email address.</span></span> <span data-ttu-id="f92a9-188">可以指定用分号分隔的多个电子邮件地址（;)或每行一个收件人。</span><span class="sxs-lookup"><span data-stu-id="f92a9-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="f92a9-189">d.</span><span class="sxs-lookup"><span data-stu-id="f92a9-189">d.</span></span> <span data-ttu-id="f92a9-190">单击</span><span class="sxs-lookup"><span data-stu-id="f92a9-190">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="f92a9-192">添加收件人。</span><span class="sxs-lookup"><span data-stu-id="f92a9-192">to add the recipients.</span></span>

        <span data-ttu-id="f92a9-193">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="f92a9-194">您添加的收件人将显示在浮出控件的 "**收件人列表**" 部分。</span><span class="sxs-lookup"><span data-stu-id="f92a9-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="f92a9-195">若要删除收件人，请![单击 "](../../media/scc-remove-icon.png)删除" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f92a9-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="f92a9-196">e.</span><span class="sxs-lookup"><span data-stu-id="f92a9-196">e.</span></span> <span data-ttu-id="f92a9-197">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="f92a9-198">若要禁用此设置，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="f92a9-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="f92a9-199">Optional展开 "**收件人限制**" 部分，为可疑的出站电子邮件配置限制和操作：</span><span class="sxs-lookup"><span data-stu-id="f92a9-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="f92a9-200">这些设置仅适用于基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f92a9-200">These settings are only applicable to cloud-based mailboxes.</span></span>
     
   - <span data-ttu-id="f92a9-201">**每个用户的最大收件人数**</span><span class="sxs-lookup"><span data-stu-id="f92a9-201">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="f92a9-202">有效的值为0到10000。</span><span class="sxs-lookup"><span data-stu-id="f92a9-202">A valid value is 0 to 10000.</span></span> <span data-ttu-id="f92a9-203">默认值为0，表示使用服务默认值。</span><span class="sxs-lookup"><span data-stu-id="f92a9-203">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="f92a9-204">有关详细信息，请参阅[在 Microsoft 365 选项中发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-204">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="f92a9-205">**外部小时限制**：每个小时的最大外部收件人数。</span><span class="sxs-lookup"><span data-stu-id="f92a9-205">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="f92a9-206">**内部每小时限制**：每小时最大内部收件人数。</span><span class="sxs-lookup"><span data-stu-id="f92a9-206">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="f92a9-207">**每日限制**：每天的最大收件人总数。</span><span class="sxs-lookup"><span data-stu-id="f92a9-207">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="f92a9-208">**当用户超过以上限制时的操作**：配置超出任何一个**收件人限制**时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f92a9-208">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="f92a9-209">对于所有操作，用户在 "**限制发送电子邮件**通知策略" （如果在出站垃圾邮件策略中发送出站垃圾邮件通知，由于在出站垃圾邮件通知中**发送出站垃圾**邮件设置而被阻止）中指定的收件人不会发送电子邮件通知策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-209">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="f92a9-210">**限制用户在以下日期之前发送邮件**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="f92a9-210">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="f92a9-211">发送电子邮件通知，用户在下一天（基于 UTC 时间）之前，将无法发送更多的邮件。</span><span class="sxs-lookup"><span data-stu-id="f92a9-211">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="f92a9-212">管理员无法替代此块。</span><span class="sxs-lookup"><span data-stu-id="f92a9-212">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="f92a9-213">名为**用户限制为 "发送电子邮件**的活动通知" 通知管理员（通过电子邮件和**查看 "通知**" 页面）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-213">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="f92a9-214">**如果发件人因在策略中发送出站垃圾邮件设置而被阻止**，则在 "通知特定人员" 中指定的任何收件人也会收到通知。</span><span class="sxs-lookup"><span data-stu-id="f92a9-214">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="f92a9-215">在下一天，用户将不能再根据 UTC 时间发送更多的邮件。</span><span class="sxs-lookup"><span data-stu-id="f92a9-215">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="f92a9-216">管理员无法替代此块。</span><span class="sxs-lookup"><span data-stu-id="f92a9-216">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="f92a9-217">**限制用户发送邮件**：发送电子邮件通知，则会将用户添加到 Security & 合规性中心中的 **[受限用户]<https://sip.protection.office.com/restrictedusers> **门户中，并且在管理员将邮件从**受限制的用户**门户中删除之前，用户将无法发送电子邮件。管理员将用户从列表中删除后，该用户将不会再次限制该用户这一天。</span><span class="sxs-lookup"><span data-stu-id="f92a9-217">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="f92a9-218">有关说明，请参阅[发送垃圾电子邮件后，从受限用户门户中删除用户](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-218">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="f92a9-219">**不执行任何操作，仅通知**：发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f92a9-219">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="f92a9-220">需要展开 "**应用于**" 部分，以标识应用该策略的内部发件人。</span><span class="sxs-lookup"><span data-stu-id="f92a9-220">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="f92a9-221">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="f92a9-221">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f92a9-222">同一条件或异常的多个值使用或逻辑（例如， _ \<sender1\> _或_ \<sender2\>_）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-222">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="f92a9-223">不同的条件或例外使用和逻辑（例如， _ \<sender1\> _和_ \<group 1\>的 member_）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-223">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="f92a9-224">若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。</span><span class="sxs-lookup"><span data-stu-id="f92a9-224">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="f92a9-225">若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-225">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="f92a9-226">**发件人域为**：在 Office 365 中的一个或多个已配置的接受域中指定发件人。</span><span class="sxs-lookup"><span data-stu-id="f92a9-226">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="f92a9-227">单击 **“添加标记”** 框，以查看并选择域。</span><span class="sxs-lookup"><span data-stu-id="f92a9-227">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="f92a9-228">如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。</span><span class="sxs-lookup"><span data-stu-id="f92a9-228">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="f92a9-229">**发件人为**：指定组织中的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="f92a9-229">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="f92a9-230">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="f92a9-230">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="f92a9-231">再次单击 "**添加标记**" 框以选择 "其他发件人"。</span><span class="sxs-lookup"><span data-stu-id="f92a9-231">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="f92a9-232">**发件人是以下成员**：指定组织中的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="f92a9-232">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="f92a9-233">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="f92a9-233">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="f92a9-234">再次单击 "**添加标记**" 框以选择 "其他发件人"。</span><span class="sxs-lookup"><span data-stu-id="f92a9-234">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="f92a9-235">**下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。</span><span class="sxs-lookup"><span data-stu-id="f92a9-235">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="f92a9-236">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="f92a9-236">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="f92a9-237">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-237">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="f92a9-238">使用安全 & 合规性中心查看出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-238">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="f92a9-239">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f92a9-240">在 "**反垃圾邮件设置**" 页上![，单击](../../media/scc-expand-icon.png) "展开图标" 以展开出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="f92a9-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="f92a9-241">名为 "**出站垃圾邮件筛选器策略**" 的默认策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="f92a9-242">您创建的自定义策略，在该策略中，"**类型**" 列中的值是**自定义出站垃圾邮件策略**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="f92a9-243">策略设置将显示在显示的展开策略详细信息中，也可以单击 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="f92a9-243">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="f92a9-244">使用安全 & 合规性中心修改出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-244">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="f92a9-245">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-245">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f92a9-246">在 "**反垃圾邮件设置**" 页上![，单击](../../media/scc-expand-icon.png) "展开图标" 以展开出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="f92a9-246">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="f92a9-247">名为 "**出站垃圾邮件筛选器策略**" 的默认策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-247">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="f92a9-248">您创建的自定义策略，在该策略中，"**类型**" 列中的值是**自定义出站垃圾邮件策略**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-248">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="f92a9-249">单击 **“编辑策略”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-249">Click **Edit policy**.</span></span>

<span data-ttu-id="f92a9-250">对于自定义出站垃圾邮件策略，显示的浮出控件中的可用设置与[使用 Security & 合规中心创建出站垃圾邮件策略](#use-the-security--compliance-center-to-create-outbound-spam-policies)部分中所述的相同。</span><span class="sxs-lookup"><span data-stu-id="f92a9-250">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="f92a9-251">对于名为 "**出站垃圾邮件筛选器策略**" 的默认出站垃圾邮件策略，"**应用**于" 部分不可用（策略适用于每个人），无法重命名策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-251">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="f92a9-252">若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。</span><span class="sxs-lookup"><span data-stu-id="f92a9-252">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="f92a9-253">启用或禁用出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-253">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="f92a9-254">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f92a9-255">在 "**反垃圾邮件设置**" 页上![，单击](../../media/scc-expand-icon.png) "展开图标" 以展开您创建的自定义策略（"**类型**" 列中的值是 "**自定义出站垃圾邮件策略**"）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="f92a9-256">在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。</span><span class="sxs-lookup"><span data-stu-id="f92a9-256">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="f92a9-257">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="f92a9-257">Move the toggle to the left to disable the policy:</span></span> ![切换开关关闭](../../media/scc-toggle-off.png)

   <span data-ttu-id="f92a9-259">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="f92a9-259">Move the toggle to the right to enable the policy:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="f92a9-261">您不能禁用默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-261">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="f92a9-262">设置自定义出站垃圾邮件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="f92a9-262">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="f92a9-263">默认情况下，会为出站垃圾邮件策略指定优先级，这取决于它们的创建顺序（较旧的策略相比，较新的策略优先级较低）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-263">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="f92a9-264">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-264">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f92a9-265">没有两个策略可以有相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="f92a9-265">No two policies can have the same priority.</span></span>

<span data-ttu-id="f92a9-266">自定义出站垃圾邮件策略按其处理顺序显示（第一个策略的**优先级**值为0）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-266">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f92a9-267">名为 "**出站垃圾邮件筛选器策略**" 的默认出站垃圾邮件策略的优先级值为**最低**，无法进行更改。</span><span class="sxs-lookup"><span data-stu-id="f92a9-267">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="f92a9-268">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-268">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="f92a9-269">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-269">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f92a9-270">在 "**反垃圾邮件设置**" 页上，找到 "**类型**" 列中的值为 "**自定义出站垃圾邮件策略**" 的策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-270">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="f92a9-271">注意 **“优先级”** 列中的值：</span><span class="sxs-lookup"><span data-stu-id="f92a9-271">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="f92a9-272">具有最高优先级的自定义出站垃圾邮件策略![的值为](../../media/ITPro-EAC-DownArrowIcon.png)向下箭头图标**0**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-272">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="f92a9-273">优先级最低的自定义出站垃圾邮件策略具有值![向上箭头图标](../../media/ITPro-EAC-UpArrowIcon.png) **n** （例如， ![向上箭头图标](../../media/ITPro-EAC-UpArrowIcon.png) **3**）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-273">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="f92a9-274">如果有三个或更多自定义出站垃圾邮件策略，则在最高和最低![优先级之间的](../../media/ITPro-EAC-UpArrowIcon.png)![策略具有值](../../media/ITPro-EAC-DownArrowIcon.png)向上箭头图标向下![箭头图标**n** （例如，向上箭头图标](../../media/ITPro-EAC-UpArrowIcon.png)![向下箭头图标](../../media/ITPro-EAC-DownArrowIcon.png) **2**）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-274">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="f92a9-275">单击</span><span class="sxs-lookup"><span data-stu-id="f92a9-275">Click</span></span> ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="f92a9-277">或</span><span class="sxs-lookup"><span data-stu-id="f92a9-277">or</span></span> ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="f92a9-279">在 "优先级" 列表中向上或向下移动自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-279">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="f92a9-280">使用安全 & 合规性中心删除出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-280">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="f92a9-281">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-281">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f92a9-282">在 "**反垃圾邮件设置**" 页上![，单击](../../media/scc-expand-icon.png) "展开图标" 以展开要删除的自定义策略（"**类型**" 列是 "**自定义出站垃圾邮件策略**"）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-282">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="f92a9-283">在随即显示的展开策略详细信息中，单击 **“删除策略”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-283">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="f92a9-284">在随即显示的警告对话框中，单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-284">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="f92a9-285">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-285">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="f92a9-286">使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-286">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="f92a9-287">使用 PowerShell 创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="f92a9-288">在 PowerShell 中创建出站垃圾邮件策略的过程分为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="f92a9-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f92a9-289">创建出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-289">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="f92a9-290">创建用于指定应用规则的出站垃圾邮件筛选器策略的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="f92a9-291">**注意**：</span><span class="sxs-lookup"><span data-stu-id="f92a9-291">**Notes**:</span></span>

- <span data-ttu-id="f92a9-292">您可以创建新的出站垃圾邮件筛选器规则，并向其分配现有的未关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="f92a9-293">一个出站垃圾邮件筛选器规则不能与多个出站垃圾邮件筛选器策略相关联。</span><span class="sxs-lookup"><span data-stu-id="f92a9-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="f92a9-294">您可以在 PowerShell 中的新出站垃圾邮件筛选器策略中配置以下设置，这些设置在安全 & 合规性中心中不可用，直到您创建了策略：</span><span class="sxs-lookup"><span data-stu-id="f92a9-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f92a9-295">将新策略创建为禁用（在**HostedOutboundSpamFilterRule** cmdlet 上_启用_ `$false` ）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="f92a9-296">在**HostedOutboundSpamFilterRule** cmdlet 上创建（_优先级_ _ \<编号\>_）过程中设置策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="f92a9-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="f92a9-297">在 PowerShell 中创建的新的出站垃圾邮件筛选器策略在安全 & 合规性中心中不可见，除非您将策略分配给垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="f92a9-298">步骤1：使用 PowerShell 创建出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="f92a9-299">若要创建出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="f92a9-300">本示例将使用以下设置创建名为 Contoso 行政主管的新出站垃圾邮件筛选器策略：</span><span class="sxs-lookup"><span data-stu-id="f92a9-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="f92a9-301">收件人速率限制限制为默认值的较小值。</span><span class="sxs-lookup"><span data-stu-id="f92a9-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="f92a9-302">有关详细信息，请参阅[在 Microsoft 365 选项中发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-302">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="f92a9-303">达到其中一个限制后，用户将被阻止发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f92a9-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="f92a9-304">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="f92a9-305">步骤2：使用 PowerShell 创建出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="f92a9-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="f92a9-306">若要创建出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="f92a9-307">本示例使用以下设置创建名为 Contoso 行政主管的新出站垃圾邮件筛选器规则：</span><span class="sxs-lookup"><span data-stu-id="f92a9-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="f92a9-308">名为 "Contoso 行政主管" 的出站垃圾邮件筛选器策略与规则相关联。</span><span class="sxs-lookup"><span data-stu-id="f92a9-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="f92a9-309">此规则应用于“Contoso Executives Group”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="f92a9-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="f92a9-310">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="f92a9-311">使用 PowerShell 查看出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="f92a9-312">若要返回所有出站垃圾邮件筛选器策略的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f92a9-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="f92a9-313">若要返回有关特定出站垃圾邮件筛选器策略的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="f92a9-314">本示例将返回名为 "主管" 的出站垃圾邮件筛选器策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="f92a9-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="f92a9-315">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="f92a9-316">使用 PowerShell 查看出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="f92a9-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="f92a9-317">若要查看现有的出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="f92a9-318">若要返回所有出站垃圾邮件筛选器规则的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f92a9-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="f92a9-319">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f92a9-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="f92a9-320">若要返回有关特定出站垃圾邮件筛选器规则的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="f92a9-321">本示例将返回名为 Contoso 行政主管的出站垃圾邮件筛选器规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="f92a9-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="f92a9-322">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="f92a9-323">使用 PowerShell 修改出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="f92a9-324">按照本主题前面的 "[步骤1：使用 PowerShell 创建出站垃圾邮件筛选器策略](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)" 一节中所述，在 PowerShell 中修改恶意软件筛选器策略时，可以使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="f92a9-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="f92a9-325">**注意**：不能重命名出站垃圾邮件筛选器策略（ **HostedOutboundSpamFilterPolicy** cmdlet 没有_Name_参数）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-325">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f92a9-326">当您在安全 & 合规中心中重命名出站垃圾邮件策略时，您只是重命名出站垃圾邮件筛选器_规则_。</span><span class="sxs-lookup"><span data-stu-id="f92a9-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="f92a9-327">若要修改出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f92a9-328">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="f92a9-329">使用 PowerShell 修改出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="f92a9-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="f92a9-330">在 PowerShell 中修改出站垃圾邮件筛选器规则时，唯一不可用的设置是允许您创建已禁用规则的_启用_参数。</span><span class="sxs-lookup"><span data-stu-id="f92a9-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f92a9-331">若要启用或禁用现有的出站垃圾邮件筛选器规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="f92a9-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="f92a9-332">否则，在 PowerShell 中修改出站垃圾邮件筛选器规则时，没有其他设置可用。</span><span class="sxs-lookup"><span data-stu-id="f92a9-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="f92a9-333">按照本主题前面的 "[步骤2：使用 PowerShell 创建出站垃圾邮件筛选器规则](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)" 一节中所述，创建规则时，可以使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="f92a9-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="f92a9-334">若要修改出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f92a9-335">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="f92a9-336">使用 PowerShell 启用或禁用出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="f92a9-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="f92a9-337">启用或禁用 PowerShell 中的出站垃圾邮件筛选器规则可启用或禁用整个出站垃圾邮件策略（出站垃圾邮件筛选器规则和分配的出站垃圾邮件筛选器策略）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="f92a9-338">您不能启用或禁用默认出站垃圾邮件策略（始终应用于所有收件人）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="f92a9-339">若要在 PowerShell 中启用或禁用出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="f92a9-340">本示例禁用名为 "Marketing 部门" 的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f92a9-341">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f92a9-342">有关语法和参数的详细信息，请参阅[Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule)和[Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="f92a9-343">使用 PowerShell 设置出站垃圾邮件筛选器规则的优先级</span><span class="sxs-lookup"><span data-stu-id="f92a9-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="f92a9-344">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="f92a9-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f92a9-345">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="f92a9-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f92a9-346">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="f92a9-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f92a9-347">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="f92a9-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f92a9-348">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="f92a9-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f92a9-349">若要在 PowerShell 中设置出站垃圾邮件筛选器规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f92a9-350">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="f92a9-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="f92a9-351">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="f92a9-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f92a9-352">**注意**：</span><span class="sxs-lookup"><span data-stu-id="f92a9-352">**Notes**:</span></span>

- <span data-ttu-id="f92a9-353">若要在创建时设置新规则的优先级，请改用**HostedOutboundSpamFilterRule** cmdlet 上的_priority_参数。</span><span class="sxs-lookup"><span data-stu-id="f92a9-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="f92a9-354">出站默认垃圾邮件筛选器策略不具有相应的垃圾邮件筛选器规则，它始终具有不可修改的优先级值**下限**。</span><span class="sxs-lookup"><span data-stu-id="f92a9-354">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="f92a9-355">使用 PowerShell 删除出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="f92a9-355">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="f92a9-356">当您使用 PowerShell 删除出站垃圾邮件筛选器策略时，不会删除相应的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-356">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="f92a9-357">若要删除 PowerShell 中的出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-357">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f92a9-358">本示例删除名为 "Marketing 部门" 的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-358">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f92a9-359">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-359">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="f92a9-360">使用 PowerShell 删除出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="f92a9-360">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="f92a9-361">当您使用 PowerShell 删除出站垃圾邮件筛选器规则时，将不会删除相应的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="f92a9-361">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="f92a9-362">若要删除 PowerShell 中的出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f92a9-362">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="f92a9-363">本示例删除名为 "Marketing 部门" 的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="f92a9-363">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f92a9-364">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="f92a9-364">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f92a9-365">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="f92a9-365">For more information</span></span>

[<span data-ttu-id="f92a9-366">从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="f92a9-366">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="f92a9-367">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="f92a9-367">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="f92a9-368">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="f92a9-368">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
