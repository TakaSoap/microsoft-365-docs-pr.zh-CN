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
description: 管理员可以了解如何查看、创建、修改和删除 Exchange Online Protection (EOP) 。
ms.openlocfilehash: 1e25d687ea22c70ba36f7c183b1fd8e578f7fa13
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683327"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="dfbf3-103">在 EOP 中配置出站垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="dfbf3-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dfbf3-104">在具有 Exchange Online 邮箱或独立 Exchange Online Protection (EOP) 组织的 Microsoft 365 组织中，自动检查通过 EOP 发送的出站电子邮件是否包含垃圾邮件和异常发送活动。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="dfbf3-105">来自组织中用户的出站垃圾邮件通常指示帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="dfbf3-106">无论垃圾邮件可信度或 SCL) 如何，可疑出站邮件都会标记为垃圾邮件 (，并通过高风险传递池进行路由，以帮助[](high-risk-delivery-pool-for-outbound-messages.md)保护服务 (的信誉，即使 Microsoft 365 源电子邮件服务器从 IP 阻止列表) 中排除。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="dfbf3-107">管理员将自动收到可疑的出站电子邮件活动通知，并且通过警报策略 [阻止用户](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="dfbf3-108">EOP 使用出站垃圾邮件策略作为组织对垃圾邮件的整体防御的一部分。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="dfbf3-109">有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="dfbf3-110">管理员可以查看、编辑和配置 (，但不能删除) 出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="dfbf3-111">更具体一点，您还可以创建自定义出站垃圾邮件策略，这些策略适用于组织中特定用户、组或域。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="dfbf3-112">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="dfbf3-113">您可以在 &安全与合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置出站垃圾邮件策略;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="dfbf3-114">EOP 中出站垃圾邮件策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="dfbf3-115">**出站垃圾邮件筛选策略**：指定出站垃圾邮件筛选裁定和通知选项的操作。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="dfbf3-116">**出站垃圾邮件筛选器** 规则：指定策略应用于 (发件人的优先级和收件人筛选器) 出站垃圾邮件筛选器策略的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="dfbf3-117">在安全与合规中心内管理出站垃圾邮件策略时，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="dfbf3-118">创建策略时，实际上是同时使用同一名称创建出站垃圾邮件筛选器规则和相关出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="dfbf3-119">修改策略时，与名称、优先级、已启用或禁用以及收件人筛选器相关的设置将修改出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="dfbf3-120">所有其他设置修改关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="dfbf3-121">删除策略时，将删除出站垃圾邮件筛选器规则和相关出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="dfbf3-122">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="dfbf3-123">有关详细信息，请参阅本文稍后介绍的"使用 Exchange Online PowerShell 或独立 [EOP PowerShell 配置出站](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 垃圾邮件策略"部分。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="dfbf3-124">每个组织都有一个名为 Default 的内置出站垃圾邮件策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="dfbf3-125">即使与策略关联的收件人筛选器没有出站垃圾邮件筛选规则，该 (应用于组织) 所有收件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="dfbf3-126">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="dfbf3-127">你创建的任何自定义策略的优先级始终高于名为“默认”的策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="dfbf3-128">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="dfbf3-129">若要提高出站垃圾邮件筛选的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dfbf3-130">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="dfbf3-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dfbf3-131">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="dfbf3-132">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="dfbf3-133">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="dfbf3-134">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="dfbf3-135">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-135">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="dfbf3-136">若要添加、修改和删除出站垃圾邮件策略，您必须是组织 **管理或** 安全管理员角色 **组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-136">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="dfbf3-137">对于出站垃圾邮件策略的只读访问，你需要是全局读者或安全 **读者角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="dfbf3-137">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="dfbf3-138">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-138">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="dfbf3-139">**注意**：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-139">**Notes**:</span></span>

  - <span data-ttu-id="dfbf3-140">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="dfbf3-141">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-141">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="dfbf3-142">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="dfbf3-143">有关针对出站垃圾邮件策略的建议设置，请参阅 [EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-143">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="dfbf3-144">名为"电子邮件发送限制"的默认警报策略已超出"检测到可疑电子邮件发送模式"和"限制发送电子邮件的用户"已向 **TenantAdmins** (全局管理员 **)** 组的成员发送电子邮件通知，这些通知有关异常的出站电子邮件活动和因出站垃圾邮件而阻止的用户。 [](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dfbf3-144">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="dfbf3-145">有关详细信息，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-145">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="dfbf3-146">我们建议您使用这些警报策略，而不是出站垃圾邮件策略中的通知选项。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-146">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="dfbf3-147">使用安全&中心创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-147">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="dfbf3-148">在安全与合规中心内创建自定义出站垃圾邮件&将同时使用同一名称创建垃圾邮件筛选规则和相关垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-148">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="dfbf3-149">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="dfbf3-150">在 **"反垃圾邮件设置**"页上，单击 **"创建出站策略"。**</span><span class="sxs-lookup"><span data-stu-id="dfbf3-150">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="dfbf3-151">在 **随即打开** 的出站垃圾邮件筛选器策略中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-151">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="dfbf3-152">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="dfbf3-153">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-153">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="dfbf3-154"> (可选) 展开"通知"部分以配置应接收可疑出站电子邮件的副本和通知的其他用户：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-154">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="dfbf3-155">**向特定人员发送可疑出** 站电子邮件的副本：此设置将指定用户添加为可疑出站邮件的"Bcc"收件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-155">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="dfbf3-156">此设置仅适用于默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-156">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="dfbf3-157">它不在创建的自定义出站垃圾邮件策略中工作。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-157">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="dfbf3-158">若要启用此设置，</span><span class="sxs-lookup"><span data-stu-id="dfbf3-158">To enable this setting:</span></span>

     1. <span data-ttu-id="dfbf3-159">选中此复选框以启用该设置。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-159">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="dfbf3-160">单击 **"添加人员"。**</span><span class="sxs-lookup"><span data-stu-id="dfbf3-160">Click **Add people**.</span></span> <span data-ttu-id="dfbf3-161">在 **出现的"添加或删除收件人"** 飞出中：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-161">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="dfbf3-162">输入发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-162">Enter the sender's email address.</span></span> <span data-ttu-id="dfbf3-163">可以指定多个电子邮件地址，用分号分隔; () 一个收件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-163">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="dfbf3-164">单击</span><span class="sxs-lookup"><span data-stu-id="dfbf3-164">Click</span></span> ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="dfbf3-166">添加收件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-166">to add the recipients.</span></span>

        <span data-ttu-id="dfbf3-167">根据需要重复执行这些步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-167">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="dfbf3-168">您添加的收件人显示在飞出 **上的** "收件人列表"部分。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-168">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="dfbf3-169">若要删除收件人，请单击" ![ 删除"按钮 ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-169">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="dfbf3-170">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-170">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="dfbf3-171">若要禁用此设置，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-171">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="dfbf3-172">如果发件人因发送出站垃圾邮件被阻止 **，请通知特定人员**：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-172">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="dfbf3-173">此设置正在从出站垃圾邮件策略中弃用。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-173">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="dfbf3-174">当用户 [](../../compliance/alert-policies.md)因超出"收件人限制"部分的限制被阻止时，名为"限制发送电子邮件的用户"的默认警报策略已经向 **TenantAdmins** **(** 全局管理员) 组的成员发送电子邮件通知。 </span><span class="sxs-lookup"><span data-stu-id="dfbf3-174">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="dfbf3-175">**强烈建议使用出** 站垃圾邮件策略中的警报策略，而不是此设置来通知管理员和其他用户。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-175">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="dfbf3-176">有关说明，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-176">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="dfbf3-177"> (可选) 展开 **"收件人限制** "部分以配置可疑出站电子邮件的限制和操作：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-177">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="dfbf3-178">这些设置仅适用于基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-178">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="dfbf3-179">**每个用户的最大收件人数**</span><span class="sxs-lookup"><span data-stu-id="dfbf3-179">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="dfbf3-180">有效值为 0 到 10000。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-180">A valid value is 0 to 10000.</span></span> <span data-ttu-id="dfbf3-181">默认值为 0，表示使用服务默认值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-181">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="dfbf3-182">有关详细信息，请参阅发送 [限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-182">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="dfbf3-183">**外部每小时限制**：每小时的最大外部收件人数。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-183">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="dfbf3-184">**内部每小时限制**：每小时内部收件人的最大数量。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-184">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="dfbf3-185">**每日限制**：每天的最大收件人总数。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-185">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="dfbf3-186">**用户超过上述** 限制时的操作：配置当超过任何一个收件人 **限制时要** 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-186">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="dfbf3-187">对于所有操作，如果用户由于发送出站垃圾邮件策略中的出站垃圾邮件设置而被阻止，则"用户"中指定的收件人将限制其发送电子邮件提醒策略 (以及现在冗余的"通知特定人员"，以接收电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-187">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="dfbf3-188">**限制用户发送邮件，直到第二天**：此为默认值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-188">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="dfbf3-189">将发送电子邮件通知，用户将无法发送任何其他邮件，直到第二天，基于 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-189">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="dfbf3-190">管理员无法覆盖此阻止。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-190">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="dfbf3-191">名为"用户 **被** 限制发送电子邮件"的活动警报会 (通知管理员，并通知管理员在"查看警报"页上) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-191">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="dfbf3-192">如果发件人因在策略中发送出站垃圾邮件设置而被阻止，则通知特定人员中指定的任何收件人也会收到通知。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-192">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="dfbf3-193">用户将无法发送任何其他消息，直到第二天，基于 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-193">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="dfbf3-194">管理员无法覆盖此阻止。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-194">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="dfbf3-195">限制用户发送邮件：发送电子邮件通知，将用户添加到安全 & 合规中心中的[受限用户 **] <https://sip.protection.office.com/restrictedusers>** 门户，并且用户无法发送电子邮件，直到管理员从受限用户门户中删除他们。 管理员从列表中删除用户后，该天不会再次限制该用户。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-195">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="dfbf3-196">有关说明，请参阅发送垃圾邮件后从 [受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-196">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="dfbf3-197">**无操作，仅警报**：发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-197">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="dfbf3-198"> (可选 **) 展开"** 自动转发"部分，以控制用户向外部发件人自动转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-198">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="dfbf3-199">有关详细信息，请参阅 [Microsoft 365 中的控制自动外部电子邮件转发](external-email-forwarding.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-199">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="dfbf3-200">在 2020 年 9 月之前，这些设置可用，但不强制执行。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-200">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="dfbf3-201">这些设置仅适用于基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-201">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="dfbf3-202">禁用自动转发后，如果外部发件人将电子邮件发送到已就地转发的邮箱 (则收件人将收到未送达报告) 也称为 NDR 或退回邮件。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-202">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="dfbf3-203">如果邮件由内部发件人发送，并且转发方法是邮箱转发 (也称为 [](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_SMTP_ 转发) ，则内部发件人将获取 NDR。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-203">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="dfbf3-204">如果转发由于收件箱规则而发生，则内部发件人不会收到 NDR。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-204">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="dfbf3-205">可用值有：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-205">The available values are:</span></span>

   - <span data-ttu-id="dfbf3-206">**自动 - 系统控制**：允许出站垃圾邮件筛选控制自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-206">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="dfbf3-207">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-207">This is the default value.</span></span>
   - <span data-ttu-id="dfbf3-208">**On**： 策略不会禁用自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-208">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="dfbf3-209">**关闭**：策略禁用所有自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-209">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="dfbf3-210"> (必需) 展开"应用于 **"部分以** 标识策略应用于的内部发件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-210">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="dfbf3-211">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-211">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="dfbf3-212">同一个条件或例外的多个值使用“或”逻辑（例如，_\<sender1\>_ 或 _\<sender2\>_）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-212">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="dfbf3-213">不同的条件或例外使用“和”逻辑（例如，_\<sender1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-213">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="dfbf3-214">若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-214">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="dfbf3-215">若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-215">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="dfbf3-216">**发件人域为**：指定组织中一个或多个已配置的接受域中的发件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-216">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="dfbf3-217">单击 **“添加标记”** 框，以查看并选择域。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-217">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="dfbf3-218">如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-218">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="dfbf3-219">**发件人为**：指定您的组织中的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-219">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="dfbf3-220">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="dfbf3-221">再次单击 **"添加标记"** 框以选择其他发件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="dfbf3-222">**发件人是：** 指定组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-222">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="dfbf3-223">单击 **“添加标记”**，然后开始键入内容来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-223">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="dfbf3-224">再次单击 **"添加标记"** 框以选择其他发件人。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-224">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="dfbf3-225">**下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-225">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="dfbf3-226">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-226">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="dfbf3-227">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-227">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="dfbf3-228">使用安全&中心查看出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-228">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="dfbf3-229">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-229">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="dfbf3-230">在 **"反垃圾邮件设置** "页上，单击 ![ "展开"图标 ](../../media/scc-expand-icon.png) 以展开出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-230">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="dfbf3-231">名为"出站 **垃圾邮件筛选器策略"的默认策略**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-231">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="dfbf3-232">您创建的自定义策略，其中 **"** 类型"列中的值为 **"自定义出站垃圾邮件策略"。**</span><span class="sxs-lookup"><span data-stu-id="dfbf3-232">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="dfbf3-233">策略设置将显示在显示的扩展策略详细信息中，或者您可以单击"编辑 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="dfbf3-233">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="dfbf3-234">使用安全&合规中心修改出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-234">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="dfbf3-235">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-235">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="dfbf3-236">在 **"反垃圾邮件设置** "页上，单击 ![ "展开"图标 ](../../media/scc-expand-icon.png) 以展开出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-236">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="dfbf3-237">名为"出站 **垃圾邮件筛选器策略"的默认策略**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-237">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="dfbf3-238">您创建的自定义策略，其中 **"** 类型"列中的值为 **"自定义出站垃圾邮件策略"。**</span><span class="sxs-lookup"><span data-stu-id="dfbf3-238">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="dfbf3-239">单击 **“编辑策略”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-239">Click **Edit policy**.</span></span>

<span data-ttu-id="dfbf3-240">对于自定义出站垃圾邮件策略，显示出站中的可用设置与"使用安全与合规中心&创建出站垃圾邮件策略部分中所述的设置 [相同](#use-the-security--compliance-center-to-create-outbound-spam-policies) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-240">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="dfbf3-241">对于名为"出站垃圾邮件筛选策略"的默认出站垃圾邮件策略，"应用于"部分不可用 (该策略适用于所有) ，并且无法重命名该策略。 </span><span class="sxs-lookup"><span data-stu-id="dfbf3-241">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="dfbf3-242">若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-242">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="dfbf3-243">启用或禁用出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-243">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="dfbf3-244">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="dfbf3-245">在 **"反垃圾邮件设置**"页上，单击"展开"图标以展开您创建的自定义策略 ("类型"列中的值为"自定义出站垃圾邮件策略") 。 ![ ](../../media/scc-expand-icon.png)  </span><span class="sxs-lookup"><span data-stu-id="dfbf3-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="dfbf3-246">在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-246">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="dfbf3-247">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-247">Move the toggle to the left to disable the policy:</span></span> ![切换开关关闭](../../media/scc-toggle-off.png)

   <span data-ttu-id="dfbf3-249">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-249">Move the toggle to the right to enable the policy:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)

<span data-ttu-id="dfbf3-251">无法禁用默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-251">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="dfbf3-252">设置自定义出站垃圾邮件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="dfbf3-252">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="dfbf3-253">默认情况下，出站垃圾邮件策略的优先级基于它们在新策略中的创建顺序 (优先级低于较旧的策略) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-253">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="dfbf3-254">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-254">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="dfbf3-255">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-255">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="dfbf3-256">自定义出站垃圾邮件策略按处理顺序显示， (优先级值为 0) 。 </span><span class="sxs-lookup"><span data-stu-id="dfbf3-256">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="dfbf3-257">名为"出站垃圾邮件筛选器策略 **"** 的默认出站垃圾邮件策略的优先级值为 **"** 最低"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-257">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="dfbf3-258">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-258">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="dfbf3-259">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-259">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="dfbf3-260">在 **"反垃圾邮件设置**"页上，查找"类型"列中的值为 **"自定义出站垃圾邮件策略"的策略**。 </span><span class="sxs-lookup"><span data-stu-id="dfbf3-260">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="dfbf3-261">注意 **“优先级”** 列中的值：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-261">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="dfbf3-262">优先级最高的自定义出站垃圾邮件策略具有值 ![ 向下箭头图标 ](../../media/ITPro-EAC-DownArrowIcon.png) **0。**</span><span class="sxs-lookup"><span data-stu-id="dfbf3-262">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="dfbf3-263">优先级最低的自定义出站垃圾邮件策略的值为"向上箭头"图标 n (例如，向上箭头 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)  ![ 图标 ](../../media/ITPro-EAC-UpArrowIcon.png) **3**) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-263">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="dfbf3-264">如果你有三个或多个自定义出站垃圾邮件策略，则最高优先级和最低优先级之间的策略具有值向上箭头图标向下箭头图标 n (例如，向上箭头图标向下箭头图标 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-264">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="dfbf3-265">单击</span><span class="sxs-lookup"><span data-stu-id="dfbf3-265">Click</span></span> ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="dfbf3-267">或</span><span class="sxs-lookup"><span data-stu-id="dfbf3-267">or</span></span> ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="dfbf3-269">在优先级列表中上移或下移自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-269">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="dfbf3-270">使用安全&中心删除出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-270">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="dfbf3-271">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-271">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="dfbf3-272">在 **"反垃圾邮件设置**"页上，单击"展开"图标以展开要删除的自定义策略 ("类型"列为"自定义出站垃圾邮件策略") 。 ![ ](../../media/scc-expand-icon.png)  </span><span class="sxs-lookup"><span data-stu-id="dfbf3-272">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="dfbf3-273">在随即显示的展开策略详细信息中，单击 **“删除策略”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-273">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="dfbf3-274">在随即显示的警告对话框中，单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-274">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="dfbf3-275">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-275">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="dfbf3-276">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-276">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="dfbf3-277">如前所述，出站垃圾邮件策略由出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则组成。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-277">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="dfbf3-278">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，出站垃圾邮件筛选器策略和出站垃圾邮件筛选规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-278">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="dfbf3-279">您可以使用 **\* -HostedOutboundSpamFilterPolicy** cmdlet 管理出站垃圾邮件筛选器策略，使用 **\* -HostedOutboundSpamFilterRule** cmdlet 管理出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-279">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="dfbf3-280">在 PowerShell 中，首先创建出站垃圾邮件筛选器策略，然后创建出站垃圾邮件筛选器规则，以标识该规则所适用的策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-280">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="dfbf3-281">在 PowerShell 中，可以分别修改出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-281">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="dfbf3-282">从 PowerShell 删除出站垃圾邮件筛选器策略时，不会自动删除相应的出站垃圾邮件筛选规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-282">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="dfbf3-283">使用 PowerShell 创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-283">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="dfbf3-284">在 PowerShell 中创建出站垃圾邮件策略的过程分两步完成：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-284">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="dfbf3-285">创建出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-285">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="dfbf3-286">创建出站垃圾邮件筛选器规则，该规则指定该规则适用的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-286">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="dfbf3-287">**注意**：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-287">**Notes**:</span></span>

- <span data-ttu-id="dfbf3-288">可以创建新的出站垃圾邮件筛选器规则，并为其分配现有的未关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-288">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="dfbf3-289">出站垃圾邮件筛选器规则不能与多个出站垃圾邮件筛选器策略关联。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-289">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="dfbf3-290">可以在 PowerShell 中的新出站垃圾邮件筛选器策略上配置以下设置，这些策略在创建策略之前&安全与合规中心内不可用：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-290">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="dfbf3-291">在 `$false` **New-HostedOutboundSpamFilterRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-291">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="dfbf3-292">在 _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet (设置策略) 优先级) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-292">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="dfbf3-293">在 PowerShell 中新建的出站垃圾邮件筛选器策略在安全与合规中心&，除非将策略分配给垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-293">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="dfbf3-294">步骤 1：使用 PowerShell 创建出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-294">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="dfbf3-295">若要创建出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-295">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="dfbf3-296">此示例创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器策略，该策略具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-296">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="dfbf3-297">收件人速率限制仅限于默认值较小的值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-297">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="dfbf3-298">有关详细信息，请参阅跨 [Microsoft 365 选项的发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-298">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="dfbf3-299">达到其中一个限制后，将阻止用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-299">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="dfbf3-300">有关语法和参数的详细信息，请参阅 [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-300">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="dfbf3-301">步骤 2：使用 PowerShell 创建出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="dfbf3-301">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="dfbf3-302">若要创建出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-302">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="dfbf3-303">此示例使用这些设置创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器规则：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-303">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="dfbf3-304">名为 Contoso Executives 的出站垃圾邮件筛选器策略与该规则关联。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-304">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="dfbf3-305">此规则应用于“Contoso Executives Group”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-305">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="dfbf3-306">有关语法和参数的详细信息，请参阅[New-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="dfbf3-306">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="dfbf3-307">使用 PowerShell 查看出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-307">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="dfbf3-308">要返回所有出站垃圾邮件筛选器策略的摘要列表，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-308">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="dfbf3-309">要返回有关特定出站垃圾邮件筛选策略的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-309">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="dfbf3-310">此示例返回名为 Executives 的出站垃圾邮件筛选器策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-310">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="dfbf3-311">有关语法和参数的详细信息，请参阅 [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-311">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="dfbf3-312">使用 PowerShell 查看出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="dfbf3-312">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="dfbf3-313">若要查看现有的出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-313">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="dfbf3-314">要返回所有出站垃圾邮件筛选规则的摘要列表，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-314">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="dfbf3-315">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-315">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="dfbf3-316">要返回有关特定出站垃圾邮件筛选规则的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-316">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="dfbf3-317">此示例返回名为 Contoso Executives 的出站垃圾邮件筛选规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-317">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="dfbf3-318">有关语法和参数的详细信息，请参阅[Get-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="dfbf3-318">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="dfbf3-319">使用 PowerShell 修改出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-319">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="dfbf3-320">在 PowerShell 中修改恶意软件筛选器策略时，可以使用与在本文前面步骤 [1：](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 使用 PowerShell 创建出站垃圾邮件筛选器策略部分中所述的策略相同的设置。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-320">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="dfbf3-321">如果 **Set-HostedOutboundSpamFilterPolicy** cmdlet 没有 Name 参数 (，则不能重命名出站垃圾邮件筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-321">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="dfbf3-322">在安全与合规中心内重命名出站垃圾邮件&，只是重命名出站垃圾邮件筛选器 _规则_。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-322">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="dfbf3-323">要修改出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-323">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="dfbf3-324">有关语法和参数的详细信息，请参阅 [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-324">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="dfbf3-325">使用 PowerShell 修改出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="dfbf3-325">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="dfbf3-326">在 PowerShell 中修改出站垃圾邮件筛选规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-326">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="dfbf3-327">若要启用或禁用现有出站垃圾邮件筛选规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-327">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="dfbf3-328">否则，在 PowerShell 中修改出站垃圾邮件筛选器规则时，将没有任何其他设置可用。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-328">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="dfbf3-329">当您创建规则（如本文前面所述的步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 创建出站垃圾邮件筛选器规则部分中所述）时，可使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-329">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="dfbf3-330">要修改出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-330">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="dfbf3-331">有关语法和参数的详细信息，请参阅[Set-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="dfbf3-331">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="dfbf3-332">使用 PowerShell 启用或禁用出站垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="dfbf3-332">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="dfbf3-333">在 PowerShell 中启用或禁用出站垃圾邮件筛选器规则可启用或禁用整个出站垃圾邮件策略 (出站垃圾邮件筛选器规则以及分配的出站垃圾邮件筛选器策略) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-333">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="dfbf3-334">不能启用或禁用默认出站垃圾邮件策略 (该策略始终应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-334">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="dfbf3-335">若要在 PowerShell 中启用或禁用出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-335">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="dfbf3-336">本示例禁用名为"Marketing Department"的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-336">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="dfbf3-337">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-337">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="dfbf3-338">有关语法和参数的详细信息，请参阅[Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule)和[Disable-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="dfbf3-338">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="dfbf3-339">使用 PowerShell 设置出站垃圾邮件筛选规则的优先级</span><span class="sxs-lookup"><span data-stu-id="dfbf3-339">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="dfbf3-340">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-340">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="dfbf3-341">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-341">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="dfbf3-342">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-342">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="dfbf3-343">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-343">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="dfbf3-344">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-344">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="dfbf3-345">若要在 PowerShell 中设置出站垃圾邮件筛选器规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-345">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="dfbf3-346">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-346">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="dfbf3-347">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-347">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="dfbf3-348">若要在创建新规则时设置规则的优先级，请改为使用 **New-HostedOutboundSpamFilterRule** cmdlet 的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-348">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="dfbf3-349">出站默认垃圾邮件筛选器策略没有相应的垃圾邮件筛选规则，并且始终具有不可修改的优先级值 **最低**。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-349">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="dfbf3-350">使用 PowerShell 删除出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="dfbf3-350">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="dfbf3-351">使用 PowerShell 删除出站垃圾邮件筛选器策略时，不会删除相应的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-351">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="dfbf3-352">若要在 PowerShell 中删除出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-352">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="dfbf3-353">本示例删除名为"Marketing Department"的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-353">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="dfbf3-354">有关语法和参数的详细信息，请参阅 [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-354">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="dfbf3-355">使用 PowerShell 删除出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="dfbf3-355">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="dfbf3-356">使用 PowerShell 删除出站垃圾邮件筛选规则时，不会删除相应的出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-356">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="dfbf3-357">若要在 PowerShell 中删除出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-357">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="dfbf3-358">本示例删除名为 Marketing Department 的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-358">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="dfbf3-359">有关语法和参数的详细信息，请参阅[Remove-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="dfbf3-359">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="dfbf3-360">详细信息</span><span class="sxs-lookup"><span data-stu-id="dfbf3-360">For more information</span></span>

[<span data-ttu-id="dfbf3-361">从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="dfbf3-361">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="dfbf3-362">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="dfbf3-362">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="dfbf3-363">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="dfbf3-363">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="dfbf3-364">自动转发的消息报告</span><span class="sxs-lookup"><span data-stu-id="dfbf3-364">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
