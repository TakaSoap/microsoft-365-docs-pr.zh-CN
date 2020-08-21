---
title: 配置出站垃圾邮件筛选
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在迁移 EOP 组织中的 Exchange Online Protection 中查看、创建、修改和删除 (垃圾邮件) 。
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845974"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="f9891-103">在 EOP 中配置出站垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="f9891-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="f9891-104">在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，通过 EOP 发送的出站电子邮件将自动检查垃圾邮件和异常发送活动。</span><span class="sxs-lookup"><span data-stu-id="f9891-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="f9891-105">来自您组织中用户的出站垃圾邮件通常表示帐户被入入入。</span><span class="sxs-lookup"><span data-stu-id="f9891-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="f9891-106">无论垃圾邮件可信度或 SCL) ，可疑的出站邮件标记为垃圾邮件 (，并通过 [高风险](high-risk-delivery-pool-for-outbound-messages.md) 传送池进行路由，以帮助保护服务的信誉 (即使 Microsoft 365 源电子邮件服务器不使用 IP 阻止列表) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="f9891-107">管理员自动通过警报策略通知可疑出站电子邮件活动和阻止 [的用户](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f9891-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="f9891-108">EOP 使用出站垃圾邮件策略作为组织对垃圾邮件的整体防御的一部分。</span><span class="sxs-lookup"><span data-stu-id="f9891-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="f9891-109">有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f9891-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="f9891-110">管理员可以查看、编辑和配置默认 (出站垃圾邮件) 删除这些操作。</span><span class="sxs-lookup"><span data-stu-id="f9891-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="f9891-111">您也可以创建应用于组织中特定用户、组或域的自定义出站垃圾邮件策略，以进行更细分。</span><span class="sxs-lookup"><span data-stu-id="f9891-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="f9891-112">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="f9891-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="f9891-113">可以在安全 & 合规中心或在具有 Exchange Online 邮箱的 Microsoft 365 (组织中使用 Exchange Online 的 PowerShell 配置出站垃圾邮件策略;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="f9891-114">EOP 中出站垃圾邮件策略的基本要部分是：</span><span class="sxs-lookup"><span data-stu-id="f9891-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="f9891-115">**出站垃圾邮件筛选**策略：指定出站垃圾邮件筛选顶点和通知选项的操作。</span><span class="sxs-lookup"><span data-stu-id="f9891-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="f9891-116">**出站垃圾邮件筛选规则**：指定向出站垃圾邮件筛选策略 (应用策略的) 筛选器。</span><span class="sxs-lookup"><span data-stu-id="f9891-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="f9891-117">在安全电子邮件合规性中心管理出站垃圾邮件策略时，这两个要点两&的区别&不可行：</span><span class="sxs-lookup"><span data-stu-id="f9891-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f9891-118">创建策略时，实际上是对二者使用相同的名称同时创建出站垃圾邮件筛选规则和关联的出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="f9891-119">修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置会修改出站垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="f9891-120">其他所有设置会修改关联的出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="f9891-121">当您删除策略时，出站垃圾邮件筛选规则及相关的出站垃圾邮件筛选策略都将删除。</span><span class="sxs-lookup"><span data-stu-id="f9891-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="f9891-122">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="f9891-123">有关详细信息，请参阅本主题 [后面的"使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 垃圾邮件策略"部分。</span><span class="sxs-lookup"><span data-stu-id="f9891-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="f9891-124">每个组织都有名为"默认"的内置出站垃圾邮件策略，其属性为：</span><span class="sxs-lookup"><span data-stu-id="f9891-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="f9891-125">策略会应用于组织中的所有收件人，即使没有与此策略相关联的 (站垃圾邮件筛选器) 收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="f9891-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="f9891-126">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="f9891-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="f9891-127">你创建的任何自定义策略的优先级始终高于名为“默认”的策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="f9891-128">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="f9891-129">为了提高出站垃圾邮件筛选的有效性，您可以创建自定义出站垃圾邮件策略，它包含应用于特定用户或用户组的更严格设置。</span><span class="sxs-lookup"><span data-stu-id="f9891-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f9891-130">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="f9891-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f9891-131">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="f9891-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f9891-132">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="f9891-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="f9891-133">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f9891-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f9891-134">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f9891-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f9891-135">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="f9891-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f9891-136">必须是下列角色之一的成员，才能添加、修改和删除出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="f9891-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f9891-137">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="f9891-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f9891-138">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="f9891-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f9891-139">对于出站垃圾邮件策略的只读访问权限，您需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="f9891-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f9891-140">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="f9891-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f9891-141">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="f9891-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="f9891-142">有关建议的出站垃圾邮件策略设置，请参阅 [EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="f9891-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="f9891-143">默认[警报策略](../../compliance/alert-policies.md)**"电子邮件发送限制已超出限制"、** 检测到的可疑**电子邮件**发送模式，**以及被限制**发送\*\* (的**"**已存在对于出\*\*站垃圾邮件"活动以及出站) 垃圾邮件而被阻止用户发送电子邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="f9891-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="f9891-144">有关详细信息，请参阅" [验证受限的用户的警报"设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="f9891-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="f9891-145">建议在出站垃圾邮件策略中使用这些警报策略，而不要使用通知选项。</span><span class="sxs-lookup"><span data-stu-id="f9891-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="f9891-146">使用"安全性&中心"创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f9891-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="f9891-147">在安全 & 合规中心内创建自定义出站垃圾邮件策略会同时创建垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="f9891-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f9891-148">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f9891-149">在"**反垃圾邮件设置"** 页面上，单击"**创建出站策略"。**</span><span class="sxs-lookup"><span data-stu-id="f9891-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="f9891-150">在打开 **的出站垃圾邮件** 筛选策略浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f9891-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f9891-151">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="f9891-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="f9891-152">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="f9891-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="f9891-153"> (可选) **扩展"** 选项"部分配置应接收可疑出站电子邮件的副本和通知的其他用户：</span><span class="sxs-lookup"><span data-stu-id="f9891-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="f9891-154">**向特定人员发送可疑出站电子邮件**副本：此设置将指定用户作为"Bcc"收件人添加到可疑出站邮件。</span><span class="sxs-lookup"><span data-stu-id="f9891-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="f9891-155">此设置仅适用于默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="f9891-156">它不能在您创建的自定义出站垃圾邮件策略中正常工作。</span><span class="sxs-lookup"><span data-stu-id="f9891-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="f9891-157">若要启用此设置：</span><span class="sxs-lookup"><span data-stu-id="f9891-157">To enable this setting:</span></span>

     1. <span data-ttu-id="f9891-158">选中此复选框以启用该设置。</span><span class="sxs-lookup"><span data-stu-id="f9891-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="f9891-159">单击 **"添加人员"。**</span><span class="sxs-lookup"><span data-stu-id="f9891-159">Click **Add people**.</span></span> <span data-ttu-id="f9891-160">在" **添加或删除出现** 下列内容的收件人"浮出控件中：</span><span class="sxs-lookup"><span data-stu-id="f9891-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="f9891-161">输入发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f9891-161">Enter the sender's email address.</span></span> <span data-ttu-id="f9891-162">可以指定多个电子邮件地址，中用分号分隔 (;) 换行一个收件人。</span><span class="sxs-lookup"><span data-stu-id="f9891-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="f9891-163">单击</span><span class="sxs-lookup"><span data-stu-id="f9891-163">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="f9891-165">添加收件人。</span><span class="sxs-lookup"><span data-stu-id="f9891-165">to add the recipients.</span></span>

        <span data-ttu-id="f9891-166">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="f9891-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="f9891-167">你添加的收件人显示在浮 **出控件上的** 收件人列表部分中。</span><span class="sxs-lookup"><span data-stu-id="f9891-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="f9891-168">若要删除收件人，请单击"删除 ![ "按钮 ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="f9891-169">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9891-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="f9891-170">若要禁用此设置，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="f9891-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="f9891-171">**发件人由于发送出站垃圾邮件而被阻止时通知特定人员**：</span><span class="sxs-lookup"><span data-stu-id="f9891-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="f9891-172">此设置的过程中会弃用出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="f9891-173">由于 [因"收件人](../../compliance/alert-policies.md) 限制 **"部分中的** 限制被阻止而被阻止时，"用户被限制发送至 TenantAdmins (全局管理员) "组成员，默认警报策略"用户"策略"受限制"向 **TenantAdmins** (**Global Admins**) **组成员发送电子邮件** 通知。</span><span class="sxs-lookup"><span data-stu-id="f9891-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="f9891-174">强烈建议您在出站垃圾邮件策略中使用该提醒策略而**非在出站垃圾邮件策略中进行此设置，以通知管理员和其他用户**。</span><span class="sxs-lookup"><span data-stu-id="f9891-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="f9891-175">有关说明，请参阅["验证受限的用户的警报设置"。](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="f9891-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="f9891-176"> (可选) 展开 **"收件人** 限制"部分以配置可疑出站电子邮件的限制和操作：</span><span class="sxs-lookup"><span data-stu-id="f9891-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="f9891-177">这些设置仅适用于基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9891-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="f9891-178">**每个用户的最大收件人数**</span><span class="sxs-lookup"><span data-stu-id="f9891-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="f9891-179">有效值为 0 至 10000。</span><span class="sxs-lookup"><span data-stu-id="f9891-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="f9891-180">默认值为 0，表示使用服务默认值。</span><span class="sxs-lookup"><span data-stu-id="f9891-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="f9891-181">有关详细信息，请参阅 [发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="f9891-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="f9891-182">**外部每小时限制**：每小时外部收件人的最大数量限制。</span><span class="sxs-lookup"><span data-stu-id="f9891-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="f9891-183">**内部每小时限制**：每小时的内部收件人的最大数量限制。</span><span class="sxs-lookup"><span data-stu-id="f9891-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="f9891-184">**每日限制：** 每天的最大收件人总数。</span><span class="sxs-lookup"><span data-stu-id="f9891-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="f9891-185">**当用户超过上述限制时执行下列操作**：配置超出任何一个收件人限制 **时要采取** 的操作。</span><span class="sxs-lookup"><span data-stu-id="f9891-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="f9891-186">对于所有操作，在"**被限制发送**电子邮件"提醒策略 (以及现在，如果出站垃圾邮件策略中发送出站**Notify specific people if a sender is blocked due to sending outbound spam**垃圾邮件设置而被阻止，则在冗余的冗余通知中指定的收件人发送电子邮件通知，</span><span class="sxs-lookup"><span data-stu-id="f9891-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="f9891-187">**限制用户向以下一天发送邮件**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="f9891-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="f9891-188">系统会发送电子邮件通知，用户将无法基于 UTC 时间在第二天内发送其他任何邮件。</span><span class="sxs-lookup"><span data-stu-id="f9891-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="f9891-189">管理员无法覆盖此阻止。</span><span class="sxs-lookup"><span data-stu-id="f9891-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="f9891-190">名为" **用户"的活动提醒** ，已阻止通过电子邮件 (和"查看 **提醒"页面上** 收到) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="f9891-191">如果由于发送了策略 **中的出站垃圾邮件设置而** 阻止发件人，则在"通知特定人员"中指定的任何收件人也会收到通知。</span><span class="sxs-lookup"><span data-stu-id="f9891-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="f9891-192">用户将无法根据 UTC 时间在第二天内发送其他任何信息。</span><span class="sxs-lookup"><span data-stu-id="f9891-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="f9891-193">管理员无法覆盖此阻止。</span><span class="sxs-lookup"><span data-stu-id="f9891-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="f9891-194">**限制用户发送邮件**：发送电子邮件通知，用户会被添加到安全 & 合规**中心的[受限 <https://sip.protection.office.com/restrictedusers> 用户]** 门户，并且用户无法发送电子邮件，直至管理员从"受限**的用户"** 门户将其删除为"管理员从列表中删除用户后，该用户在当天不会受到限制。</span><span class="sxs-lookup"><span data-stu-id="f9891-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="f9891-195">有关说明，请参阅 [发送垃圾邮件后从受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="f9891-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="f9891-196">**无操作，仅提醒**：发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f9891-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="f9891-197"> (可选) **展开自动转发** "部分来控制用户对外部发件人的自动电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="f9891-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="f9891-198">有关自动转发的详细信息，请参阅配置 [电子邮件转发](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)。</span><span class="sxs-lookup"><span data-stu-id="f9891-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f9891-199">2020 年 9 月之前，这些设置将提供，但不是强制实施。</span><span class="sxs-lookup"><span data-stu-id="f9891-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="f9891-200">这些设置仅适用于基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9891-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="f9891-201">此设置不影响自动转发给内部收件人。</span><span class="sxs-lookup"><span data-stu-id="f9891-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="f9891-202">可用值有：</span><span class="sxs-lookup"><span data-stu-id="f9891-202">The available values are:</span></span>

   - <span data-ttu-id="f9891-203">**自动 - 系统控制：允许**出站垃圾邮件筛选控制自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="f9891-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="f9891-204">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="f9891-204">This is the default value.</span></span>

   - <span data-ttu-id="f9891-205">**启用**：策略不会禁用自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="f9891-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="f9891-206">**关闭**：策略禁用所有自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="f9891-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="f9891-207"> (") 展开" **应用到"** 部分，以确定向其应用策略的内部发件人。</span><span class="sxs-lookup"><span data-stu-id="f9891-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="f9891-208">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="f9891-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f9891-209">同一个条件或例外的多个值使用“或”逻辑（例如，_\<sender1\>_ 或 _\<sender2\>_）。</span><span class="sxs-lookup"><span data-stu-id="f9891-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="f9891-210">不同的条件或例外使用“和”逻辑（例如，_\<sender1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="f9891-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="f9891-211">若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。</span><span class="sxs-lookup"><span data-stu-id="f9891-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="f9891-212">若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="f9891-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="f9891-213">**发件人域是**：指定组织中一个或多个配置的接受域中的发件人。</span><span class="sxs-lookup"><span data-stu-id="f9891-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="f9891-214">单击 **“添加标记”** 框，以查看并选择域。</span><span class="sxs-lookup"><span data-stu-id="f9891-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="f9891-215">如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。</span><span class="sxs-lookup"><span data-stu-id="f9891-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="f9891-216">**发件人是**：指定您的组织中一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="f9891-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="f9891-217">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="f9891-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="f9891-218">请再次单击 **"添加标记** "框，选择其他发件人。</span><span class="sxs-lookup"><span data-stu-id="f9891-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="f9891-219">**发件人为以下组的成员**：指定您所在组织的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="f9891-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="f9891-220">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="f9891-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="f9891-221">请再次单击 **"添加标记** "框，选择其他发件人。</span><span class="sxs-lookup"><span data-stu-id="f9891-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="f9891-222">**下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。</span><span class="sxs-lookup"><span data-stu-id="f9891-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="f9891-223">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="f9891-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="f9891-224">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="f9891-225">使用安全与&合规中心查看出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f9891-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="f9891-226">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f9891-227">在" **反垃圾邮件设置"页面上** ，单击" ![ 展开" ](../../media/scc-expand-icon.png) 图标可展开出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="f9891-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="f9891-228">名为"出站 **垃圾邮件筛选策略"的默认策略**。</span><span class="sxs-lookup"><span data-stu-id="f9891-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="f9891-229">您创建的自定义策略，其中"类型"**列中的值为**"**自定义出站垃圾邮件策略"。**</span><span class="sxs-lookup"><span data-stu-id="f9891-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="f9891-230">策略设置显示在出现的展开策略详细信息中，或者可以单击"编辑策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="f9891-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="f9891-231">使用安全&合规中心修改出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f9891-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="f9891-232">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f9891-233">在" **反垃圾邮件设置"页面上** ，单击" ![ 展开" ](../../media/scc-expand-icon.png) 图标可展开出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="f9891-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="f9891-234">名为"出站 **垃圾邮件筛选策略"的默认策略**。</span><span class="sxs-lookup"><span data-stu-id="f9891-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="f9891-235">您创建的自定义策略，其中"类型"**列中的值为**"**自定义出站垃圾邮件策略"。**</span><span class="sxs-lookup"><span data-stu-id="f9891-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="f9891-236">单击 **“编辑策略”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-236">Click **Edit policy**.</span></span>

<span data-ttu-id="f9891-237">对于自定义出站垃圾邮件策略，显示的浮出控件中的可用设置与使用安全 & 合规中心创建出站 [垃圾邮件策略部分中介绍的可用设置完全](#use-the-security--compliance-center-to-create-outbound-spam-policies) 相同。</span><span class="sxs-lookup"><span data-stu-id="f9891-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="f9891-238">对于默认的出站垃圾邮件策略 **（名为"出站垃圾邮件筛选**策略"）使用 **"** 应用到"部分 (无法选择该策略应用于每个用户) ，且无法重命名此策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="f9891-239">若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。</span><span class="sxs-lookup"><span data-stu-id="f9891-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="f9891-240">启用或禁用出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f9891-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="f9891-241">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f9891-242">在"**反垃圾邮件设置"页面上**，单击" ![ 展开" ](../../media/scc-expand-icon.png) 图标展开已创建的自定义策略 ("类型"**列中的**值为"**自定义出站垃圾邮件策略") 。**</span><span class="sxs-lookup"><span data-stu-id="f9891-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="f9891-243">在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。</span><span class="sxs-lookup"><span data-stu-id="f9891-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="f9891-244">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="f9891-244">Move the toggle to the left to disable the policy:</span></span> ![切换开关关闭](../../media/scc-toggle-off.png)

   <span data-ttu-id="f9891-246">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="f9891-246">Move the toggle to the right to enable the policy:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="f9891-248">不能禁用默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="f9891-249">设置自定义出站垃圾邮件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="f9891-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="f9891-250">默认情况下，出站垃圾邮件策略根据在新策略中创建的顺序来获得优先级，而 (新策略的优先级低于早先策略的) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="f9891-251">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="f9891-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f9891-252">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="f9891-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="f9891-253">自定义出站垃圾邮件策略按处理它们的顺序显示 (第一个策略的 **优先级值为** 0) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f9891-254">名为"出站垃圾邮件筛选 **策略"的默认出站垃圾邮件** 策略的优先级值为 **"最低**"，无法更改。</span><span class="sxs-lookup"><span data-stu-id="f9891-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="f9891-255">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="f9891-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="f9891-256">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f9891-257">在"**反垃圾邮件设置"** 页面中，查找"类型"列中的值为"自定义**出站\*\*\*\*垃圾邮件策略"的策略**。</span><span class="sxs-lookup"><span data-stu-id="f9891-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="f9891-258">注意 **“优先级”** 列中的值：</span><span class="sxs-lookup"><span data-stu-id="f9891-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="f9891-259">优先级最高的自定义出站垃圾邮件策略的"向下箭 ![ 头"图标为 ](../../media/ITPro-EAC-DownArrowIcon.png) **0。**</span><span class="sxs-lookup"><span data-stu-id="f9891-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="f9891-260">优先级最低的自定义出站垃圾邮件策略的"向上箭 ![ 头"图标 ](../../media/ITPro-EAC-UpArrowIcon.png) \*\* (\*\* 例如，向上箭 ![ 头图标 ](../../media/ITPro-EAC-UpArrowIcon.png) **3**) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="f9891-261">如果您有三个或更多个自定义出站垃圾邮件策略，则最高优先级和最低优先级之间的策略的值为值"向上箭头"图标 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (例如，"向下箭头"图标 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="f9891-262">单击</span><span class="sxs-lookup"><span data-stu-id="f9891-262">Click</span></span> ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="f9891-264">或</span><span class="sxs-lookup"><span data-stu-id="f9891-264">or</span></span> ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="f9891-266">在优先级列表中上移或下移自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="f9891-267">使用安全与&中心删除出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f9891-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="f9891-268">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f9891-269">在" **反垃圾邮件设置"页面上** ，单击 ![ "展开" ](../../media/scc-expand-icon.png) 图标展开要删除的自定义策略 \*\* ("类型"\*\* 列是" **自定义出站垃圾邮件策略** ") 。</span><span class="sxs-lookup"><span data-stu-id="f9891-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="f9891-270">在随即显示的展开策略详细信息中，单击 **“删除策略”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="f9891-271">在随即显示的警告对话框中，单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="f9891-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="f9891-272">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="f9891-273">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f9891-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="f9891-274">如前所述，出站垃圾邮件策略由出站垃圾邮件筛选策略和出站垃圾邮件筛选规则提供。</span><span class="sxs-lookup"><span data-stu-id="f9891-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="f9891-275">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，出站垃圾邮件筛选策略与出站垃圾邮件筛选规则之间的区别显而然。</span><span class="sxs-lookup"><span data-stu-id="f9891-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="f9891-276">您可以使用\*\* \* -HostedOutboundSpamFilterPolicy cmdlet 管理出站垃圾邮件筛选器**策略，您可以使用** \* -HostedOutboundSpamFilterRule cmdlet 管理出站垃圾邮件\*\*筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="f9891-277">在 PowerShell 中，先创建出站垃圾邮件筛选策略，然后创建出站垃圾邮件筛选规则，以标识向应用此规则的策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f9891-278">在 PowerShell 中，分别修改出站垃圾邮件筛选策略和出站垃圾邮件筛选规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="f9891-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="f9891-279">从 PowerShell 删除出站垃圾邮件筛选策略时，不会自动删除相应的出站垃圾邮件筛选规则，反之亦不行。</span><span class="sxs-lookup"><span data-stu-id="f9891-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="f9891-280">使用 PowerShell 创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="f9891-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="f9891-281">在 PowerShell 中创建出站垃圾邮件策略的过程分为两步：</span><span class="sxs-lookup"><span data-stu-id="f9891-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f9891-282">创建出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="f9891-283">创建出站垃圾邮件筛选规则，它可指定该规则应用于的出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="f9891-284">**注意**：</span><span class="sxs-lookup"><span data-stu-id="f9891-284">**Notes**:</span></span>

- <span data-ttu-id="f9891-285">您可以新建一个出站垃圾邮件筛选规则，并向其分配未关联的现有出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="f9891-286">出站垃圾邮件筛选规则不能与多个出站垃圾邮件筛选策略相关联。</span><span class="sxs-lookup"><span data-stu-id="f9891-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="f9891-287">您可以在 PowerShell 中对新的出站垃圾邮件筛选策略配置以下设置（在安全 & 合规中心内，直至创建策略后，才能配置这些设置：）</span><span class="sxs-lookup"><span data-stu-id="f9891-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f9891-288">在_Enabled_ `$false` **New-HostedOutboundSpamFilterRule cmdlet 服务器上 (启用对已禁用的新**) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="f9891-289">在创建策略期间 _ (，_ 要) _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet) 邮箱设置优先级) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="f9891-290">在 PowerShell 中创建的新出站垃圾邮件筛选策略在安全 & 合规中心内不可见，除非您将策略分配到垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="f9891-291">第 1 步：使用 PowerShell 创建出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="f9891-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="f9891-292">若要创建出站垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="f9891-293">本示例将使用以下设置创建名为"Contoso Executives"的新出站垃圾邮件筛选策略：</span><span class="sxs-lookup"><span data-stu-id="f9891-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="f9891-294">收件人速率限制限于小于默认值。</span><span class="sxs-lookup"><span data-stu-id="f9891-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="f9891-295">有关详细信息，请参阅 Microsoft [365 中的发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="f9891-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="f9891-296">达到其中一个限制后，将阻止用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f9891-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="f9891-297">若要详细了解语法和参数，请参阅[New-HostedOutboundSpamFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="f9891-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="f9891-298">第 2 步：使用 PowerShell 创建出站垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="f9891-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="f9891-299">若要创建出站垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="f9891-300">下面的示例使用以下设置新建名为"Contoso Executives"的出站垃圾邮件筛选规则：</span><span class="sxs-lookup"><span data-stu-id="f9891-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="f9891-301">名为"Contoso Executives"的出站垃圾邮件筛选策略与此规则关联。</span><span class="sxs-lookup"><span data-stu-id="f9891-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="f9891-302">此规则应用于“Contoso Executives Group”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="f9891-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="f9891-303">若要详细了解语法和参数，请参阅[New-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="f9891-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="f9891-304">使用 PowerShell 查看出站垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="f9891-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="f9891-305">若要返回所有出站垃圾邮件筛选策略的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f9891-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="f9891-306">若要返回有关特定出站垃圾邮件筛选策略的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="f9891-307">本示例返回名为"Executives"的出站垃圾邮件筛选策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="f9891-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="f9891-308">若要详细了解语法和参数，请参阅[Get-HostedOutboundSpamFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="f9891-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="f9891-309">使用 PowerShell 查看出站垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="f9891-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="f9891-310">若要查看现有出站垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="f9891-311">若要返回所有出站垃圾邮件筛选规则的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f9891-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="f9891-312">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f9891-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="f9891-313">若要返回特定出站垃圾邮件筛选规则的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="f9891-314">本示例返回名为"Contoso Executives"的出站垃圾邮件筛选规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="f9891-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="f9891-315">有关语法和参数的详细信息，请参阅[Get-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="f9891-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="f9891-316">使用 PowerShell 修改出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="f9891-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="f9891-317">在 PowerShell 中修改恶意软件筛选策略时可用的设置与您创建策略时可用的设置相同，如本主题前面部分所述 [：使用 PowerShell 创建本主题前面部分](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 的出站垃圾邮件筛选策略部分。</span><span class="sxs-lookup"><span data-stu-id="f9891-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="f9891-318">无法在 **Set-HostedOutboundSpamFilterPolicy** cmdlet 没有 _Name_ 参数 (重命名出站垃圾邮件筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f9891-319">在安全中心中重命名出站 &垃圾邮件策略时，只是重命名出站垃圾邮件筛选 _规则_。</span><span class="sxs-lookup"><span data-stu-id="f9891-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="f9891-320">若要修改出站垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f9891-321">若要详细了解语法和参数，请参阅["Set-HostedOutboundSpamFilterPolicy"。](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="f9891-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="f9891-322">使用 PowerShell 修改出站垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="f9891-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="f9891-323">在 PowerShell 中修改出站垃圾邮件筛选规则时，唯一不可用的设置 _是可以_ 创建已禁用规则的 Enabled 参数。</span><span class="sxs-lookup"><span data-stu-id="f9891-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f9891-324">若要启用或禁用现有出站垃圾邮件筛选规则，请参阅下一部分。</span><span class="sxs-lookup"><span data-stu-id="f9891-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="f9891-325">否则，在 PowerShell 中修改出站垃圾邮件筛选规则时，将无法使用其他任何设置。</span><span class="sxs-lookup"><span data-stu-id="f9891-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="f9891-326">创建规则时可用的设置，与步骤 [2：使用 PowerShell 创建本主题前面部分中](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 介绍的出站垃圾邮件筛选规则部分相同。</span><span class="sxs-lookup"><span data-stu-id="f9891-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="f9891-327">若要修改出站垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f9891-328">若要详细了解语法和参数，请参阅 [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="f9891-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="f9891-329">使用 PowerShell 启用或禁用出站垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="f9891-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="f9891-330">在 PowerShell 中启用或禁用出站垃圾邮件筛选规则会启用或禁用整个出站垃圾邮件策略 (出站垃圾邮件筛选规则和分配的出站垃圾邮件筛选策略) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="f9891-331">您无法启用或禁用默认出站垃圾邮件策略， (它始终应用于包含该邮件的) 。</span><span class="sxs-lookup"><span data-stu-id="f9891-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="f9891-332">若要在 PowerShell 中启用或禁用出站垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="f9891-333">本示例禁用名为"Marketing Department"的出站垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f9891-334">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f9891-335">若要详细了解语法和参数，请参阅 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="f9891-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="f9891-336">使用 PowerShell 设置出站垃圾邮件筛选规则的优先级</span><span class="sxs-lookup"><span data-stu-id="f9891-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="f9891-337">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="f9891-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f9891-338">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="f9891-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f9891-339">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="f9891-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f9891-340">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="f9891-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f9891-341">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="f9891-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f9891-342">若要在 PowerShell 中设置出站垃圾邮件筛选规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f9891-343">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="f9891-343">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="f9891-344">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="f9891-344">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="f9891-345">若要在创建新规则时设置它的优先级，请改为对**New-HostedOutboundSpamFilterRule** cmdlet 使用_Priority_参数。</span><span class="sxs-lookup"><span data-stu-id="f9891-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="f9891-346">出站默认垃圾邮件筛选策略没有相应的垃圾邮件筛选规则，且始终有不可修改的优先级值 **"最低"。**</span><span class="sxs-lookup"><span data-stu-id="f9891-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="f9891-347">使用 PowerShell 删除出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="f9891-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="f9891-348">当您使用 PowerShell 删除出站垃圾邮件筛选策略时，不会删除相应的出站垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="f9891-349">若要在 PowerShell 中删除出站垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f9891-350">本示例删除名为"Marketing Department"的出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f9891-351">若要详细了解语法和参数，请参阅[Remove-HostedOutboundSpamFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="f9891-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="f9891-352">使用 PowerShell 删除出站垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="f9891-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="f9891-353">使用 PowerShell 删除出站垃圾邮件筛选规则时，不会删除相应的出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="f9891-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="f9891-354">若要在 PowerShell 中删除出站垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f9891-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="f9891-355">本示例删除名为"Marketing Department"的出站垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="f9891-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f9891-356">若要详细了解语法和参数，请参阅[Remove-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="f9891-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f9891-357">详细信息</span><span class="sxs-lookup"><span data-stu-id="f9891-357">For more information</span></span>

[<span data-ttu-id="f9891-358">从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="f9891-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="f9891-359">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="f9891-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="f9891-360">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="f9891-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="f9891-361">自动转发的消息报告</span><span class="sxs-lookup"><span data-stu-id="f9891-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
