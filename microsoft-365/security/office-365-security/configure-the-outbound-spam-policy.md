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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 EOP 服务中查看、创建、修改和删除Exchange Online Protection (垃圾邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ebff0a93acd505532773fbf5d714268df220c9a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822005"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="6d598-103">在 EOP 中配置出站垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="6d598-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6d598-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="6d598-104">**Applies to**</span></span>
- [<span data-ttu-id="6d598-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6d598-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6d598-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="6d598-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6d598-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d598-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6d598-108">在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，则自动检查通过 EOP 发送的出站电子邮件是否包含垃圾邮件和异常发送活动。</span><span class="sxs-lookup"><span data-stu-id="6d598-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="6d598-109">来自组织中用户的出站垃圾邮件通常指示帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="6d598-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="6d598-110">无论垃圾邮件可信度或 SCL) ，可疑出站邮件都标记为垃圾邮件 (并通过高风险传送池进行路由，以帮助保护服务[](high-risk-delivery-pool-for-outbound-messages.md) (的信誉，即使 Microsoft 365 源电子邮件服务器不受 IP 阻止列表) 限制。</span><span class="sxs-lookup"><span data-stu-id="6d598-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="6d598-111">管理员将自动收到可疑的出站电子邮件活动的通知，并且会通过警报策略阻止 [用户](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6d598-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="6d598-112">EOP 使用出站垃圾邮件策略作为组织对垃圾邮件的整体防御的一部分。</span><span class="sxs-lookup"><span data-stu-id="6d598-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="6d598-113">有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="6d598-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="6d598-114">管理员可以查看、编辑和配置 (，但不能) 默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="6d598-115">更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="6d598-116">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="6d598-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="6d598-117">您可以在安全中心或 PowerShell Microsoft 365为邮箱位于 (Exchange Online 中的 Microsoft 365 组织配置出站垃圾邮件Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-117">You can configure outbound spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="6d598-118">EOP 中的出站垃圾邮件策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="6d598-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="6d598-119">**出站垃圾邮件筛选策略**：指定出站垃圾邮件筛选裁定和通知选项的操作。</span><span class="sxs-lookup"><span data-stu-id="6d598-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="6d598-120">**出站垃圾邮件筛选器** 规则：指定策略 (策略应用于出站垃圾邮件) 策略的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="6d598-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="6d598-121">在安全中心管理出站垃圾邮件管理时，这两个元素的区别并不明显：</span><span class="sxs-lookup"><span data-stu-id="6d598-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the security center:</span></span>

- <span data-ttu-id="6d598-122">创建策略时，实际上是同时创建出站垃圾邮件筛选规则和相关出站垃圾邮件筛选策略，对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="6d598-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6d598-123">修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="6d598-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="6d598-124">所有其他设置修改关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="6d598-125">删除策略时，将删除出站垃圾邮件筛选器规则和相关出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="6d598-126">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="6d598-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6d598-127">有关详细信息，请参阅本文Exchange Online [PowerShell 或独立 EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)配置出站垃圾邮件策略一节。</span><span class="sxs-lookup"><span data-stu-id="6d598-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="6d598-128">每个组织都有一个名为"默认"的内置出站垃圾邮件策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="6d598-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="6d598-129">即使与策略关联的收件人筛选器没有出站垃圾邮件筛选规则， (应用于组织) 所有收件人。</span><span class="sxs-lookup"><span data-stu-id="6d598-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="6d598-130">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="6d598-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="6d598-131">你创建的任何自定义策略的优先级始终高于名为“默认”的策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="6d598-132">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="6d598-133">若要提高出站垃圾邮件筛选的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6d598-134">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="6d598-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6d598-135">在 <https://security.microsoft.com> 打开安全中心。</span><span class="sxs-lookup"><span data-stu-id="6d598-135">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="6d598-136">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://security.microsoft.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="6d598-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="6d598-137">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6d598-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6d598-138">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6d598-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6d598-139">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="6d598-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6d598-140">若要添加、修改和删除出站垃圾邮件策略，您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="6d598-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6d598-141">若要对出站垃圾邮件策略进行只读访问，您需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="6d598-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6d598-142">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="6d598-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="6d598-143">**注意**：</span><span class="sxs-lookup"><span data-stu-id="6d598-143">**Notes**:</span></span>

  - <span data-ttu-id="6d598-144">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="6d598-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6d598-145">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="6d598-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="6d598-146">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="6d598-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="6d598-147">有关针对出站垃圾邮件策略的建议设置，请参阅 [EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="6d598-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="6d598-148">名为"电子邮件发送限制已超出、检测到可疑电子邮件发送模式"和"限制发送电子邮件的用户"的默认警报策略已经向 **TenantAdmins** (全局管理员 **)** 组的成员发送有关异常出站电子邮件活动和因出站垃圾邮件被阻止的用户的电子邮件通知。 [](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6d598-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="6d598-149">有关详细信息，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="6d598-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="6d598-150">我们建议您使用这些警报策略，而不是出站垃圾邮件策略中的通知选项。</span><span class="sxs-lookup"><span data-stu-id="6d598-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a><span data-ttu-id="6d598-151">使用安全中心创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d598-151">Use the security center to create outbound spam policies</span></span>

<span data-ttu-id="6d598-152">在安全中心创建自定义出站垃圾邮件策略的同时，会使用相同的名称创建垃圾邮件筛选规则和相关垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-152">Creating a custom outbound spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="6d598-153">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="6d598-153">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6d598-154">在"**反垃圾邮件策略"页上**，单击" ![ 创建图标""创建策略"，然后从下拉列表中选择"出 ](../../media/m365-cc-sc-create-icon.png) 站"。</span><span class="sxs-lookup"><span data-stu-id="6d598-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="6d598-155">将打开策略向导。</span><span class="sxs-lookup"><span data-stu-id="6d598-155">The policy wizard opens.</span></span> <span data-ttu-id="6d598-156">在“**命名策略页面**”上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6d598-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="6d598-157">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="6d598-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="6d598-158">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="6d598-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="6d598-159">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6d598-160">在出现的“**用户、组和域**”页面上，标识策略应用于的内部收件人（收件人条件）：</span><span class="sxs-lookup"><span data-stu-id="6d598-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="6d598-161">**用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="6d598-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="6d598-162">**组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="6d598-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="6d598-163">**域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="6d598-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="6d598-164">单击相应的框，开始键入值，然后从结果中选择所需的值。</span><span class="sxs-lookup"><span data-stu-id="6d598-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="6d598-165">根据需要多次重复此过程。</span><span class="sxs-lookup"><span data-stu-id="6d598-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="6d598-166">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="6d598-166">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="6d598-168">“删除”。</span><span class="sxs-lookup"><span data-stu-id="6d598-168">next to the value.</span></span>

   <span data-ttu-id="6d598-169">对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="6d598-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="6d598-170">对于用户，请自行输入星号 (\*) 以查看所有可用值。</span><span class="sxs-lookup"><span data-stu-id="6d598-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="6d598-171">同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="6d598-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6d598-172">不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="6d598-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="6d598-173">**排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。</span><span class="sxs-lookup"><span data-stu-id="6d598-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="6d598-174">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="6d598-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6d598-175">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6d598-176">在打开 **的** "保护设置"页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6d598-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="6d598-177">**邮件** 限制：本节中的设置配置来自以下邮箱的出站 **Exchange Online** 限制：</span><span class="sxs-lookup"><span data-stu-id="6d598-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="6d598-178">**设置外部邮件限制**：每小时的最大外部收件人数。</span><span class="sxs-lookup"><span data-stu-id="6d598-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="6d598-179">**设置内部邮件限制**：每小时内部收件人的最大数量。</span><span class="sxs-lookup"><span data-stu-id="6d598-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="6d598-180">**设置每日邮件限制**：每天的最大收件人总数。</span><span class="sxs-lookup"><span data-stu-id="6d598-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="6d598-181">有效值为 0 到 10000。</span><span class="sxs-lookup"><span data-stu-id="6d598-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="6d598-182">默认值为 0，表示使用服务默认值。</span><span class="sxs-lookup"><span data-stu-id="6d598-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="6d598-183">有关详细信息，请参阅发送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="6d598-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="6d598-184">在框中输入值，或使用框上的增加/减少箭头。</span><span class="sxs-lookup"><span data-stu-id="6d598-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="6d598-185">**对达到邮件限制的用户** 施加的限制：当超出"保护设置"部分的任何限制时，从下拉列表中选择一个操作。</span><span class="sxs-lookup"><span data-stu-id="6d598-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="6d598-186">对于所有操作，在"用户限制发送电子邮件通知策略" (中和现在冗余的"如果发件人因发送出站垃圾邮件设置被阻止，则通知这些用户和组"中指定的收件人) 接收电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="6d598-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="6d598-187">**限制用户发送邮件，直到第二天**：此为默认值。</span><span class="sxs-lookup"><span data-stu-id="6d598-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="6d598-188">将发送电子邮件通知，用户将无法再发送任何邮件，直到第二天，基于 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="6d598-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="6d598-189">管理员无法覆盖此阻止。</span><span class="sxs-lookup"><span data-stu-id="6d598-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="6d598-190">名为"用户 **被限制** 发送电子邮件"的活动提醒会 (通知管理员，并通知管理员在"查看警报"页上) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="6d598-191">还会通知策略中"如果发件人因发送出站垃圾邮件而受阻，则通知特定人员"设置中指定的任何收件人。</span><span class="sxs-lookup"><span data-stu-id="6d598-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="6d598-192">用户将无法发送其他任何邮件，直到第二天，基于 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="6d598-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="6d598-193">管理员无法覆盖此阻止。</span><span class="sxs-lookup"><span data-stu-id="6d598-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="6d598-194">**限制用户** 发送邮件：发送电子邮件通知，将用户添加到安全中心中的受限用户，并且用户无法发送电子邮件，直到管理员将用户从受限用户 <https://security.microsoft.com/restrictedusers> 中删除。 管理员从列表中删除用户后，该天不会再次限制该用户。</span><span class="sxs-lookup"><span data-stu-id="6d598-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the security center, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="6d598-195">有关说明，请参阅 [在发送垃圾邮件后从受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="6d598-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="6d598-196">**无操作，仅** 警报：发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="6d598-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="6d598-197">**转发规则**：使用本节中的设置控制自动电子邮件转发，Exchange Online **邮箱** 转发给外部发件人。</span><span class="sxs-lookup"><span data-stu-id="6d598-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="6d598-198">有关详细信息，请参阅在邮件中[控制自动外部电子邮件Microsoft 365。](external-email-forwarding.md)</span><span class="sxs-lookup"><span data-stu-id="6d598-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="6d598-199">禁用自动转发后，如果外部发件人向已就地转发的邮箱发送电子邮件 (收件人将收到未送达报告) 也称为 NDR 或退回邮件。</span><span class="sxs-lookup"><span data-stu-id="6d598-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="6d598-200">如果邮件由内部发件人发送，并且转发方法是邮箱转发 (也称为 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) _SMTP_) ，则内部发件人将获取 NDR。</span><span class="sxs-lookup"><span data-stu-id="6d598-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="6d598-201">如果转发由于收件箱规则而发生，则内部发件人不会收到 NDR。</span><span class="sxs-lookup"><span data-stu-id="6d598-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="6d598-202">从"自动转发规则"下拉列表 **中选择下列** 操作之一：</span><span class="sxs-lookup"><span data-stu-id="6d598-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="6d598-203">**自动 - 系统控制**：允许出站垃圾邮件筛选控制自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="6d598-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="6d598-204">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="6d598-204">This is the default value.</span></span>
     - <span data-ttu-id="6d598-205">**On**：策略不会禁用自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="6d598-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="6d598-206">**关闭**：策略禁用所有自动外部电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="6d598-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="6d598-207">**通知**：使用 部分中的设置配置其他收件人，这些收件人应接收可疑出站电子邮件的副本和通知：</span><span class="sxs-lookup"><span data-stu-id="6d598-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="6d598-208">**向这些用户** 和组发送超过这些限制的可疑出站副本：此设置将指定的收件人添加到可疑出站邮件的"Bcc"字段中。</span><span class="sxs-lookup"><span data-stu-id="6d598-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="6d598-209">此设置仅适用于默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="6d598-210">它不能用于您创建的自定义出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="6d598-211">若要启用此设置，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="6d598-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="6d598-212">在出现的框中，单击该框，输入有效的电子邮件地址，然后按 Enter 或选择显示在框下方的完整值。</span><span class="sxs-lookup"><span data-stu-id="6d598-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="6d598-213">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="6d598-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="6d598-214">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="6d598-214">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="6d598-216">“删除”。</span><span class="sxs-lookup"><span data-stu-id="6d598-216">next to the value.</span></span>

   - <span data-ttu-id="6d598-217">**如果发件人因发送出站垃圾邮件被阻止，则通知这些用户和组**</span><span class="sxs-lookup"><span data-stu-id="6d598-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="6d598-218">此设置正在被出站垃圾邮件策略弃用。</span><span class="sxs-lookup"><span data-stu-id="6d598-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="6d598-219">名为"[](../../compliance/alert-policies.md)限制发送电子邮件的用户"的默认警报策略已在用户因超过"收件人限制"部分的限制而被阻止 **时，向** **TenantAdmins** (全局管理员) 组的成员发送电子邮件通知。 </span><span class="sxs-lookup"><span data-stu-id="6d598-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="6d598-220">**强烈建议使用警报** 策略，而不是出站垃圾邮件策略中的此设置来通知管理员和其他用户。</span><span class="sxs-lookup"><span data-stu-id="6d598-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="6d598-221">有关说明，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="6d598-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="6d598-222">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6d598-223">在出现的“**审阅**”页面上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="6d598-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="6d598-224">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="6d598-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="6d598-225">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="6d598-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="6d598-226">完成后，单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="6d598-227">在出现的确认页面上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a><span data-ttu-id="6d598-228">使用安全中心查看出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d598-228">Use the security center to view outbound spam policies</span></span>

1. <span data-ttu-id="6d598-229">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="6d598-229">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6d598-230">在 **“反垃圾邮件”策略** 页面上，查找以下值之一:</span><span class="sxs-lookup"><span data-stu-id="6d598-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="6d598-231">类型 **值为** " **自定义出站垃圾邮件策略"**</span><span class="sxs-lookup"><span data-stu-id="6d598-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="6d598-232">Name 值为"**反垃圾邮件出站策略" (默认)**</span><span class="sxs-lookup"><span data-stu-id="6d598-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="6d598-233">反垃圾邮件策略列表中将显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="6d598-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="6d598-234">**名称**</span><span class="sxs-lookup"><span data-stu-id="6d598-234">**Name**</span></span>
   - <span data-ttu-id="6d598-235">**状态**</span><span class="sxs-lookup"><span data-stu-id="6d598-235">**Status**</span></span>
   - <span data-ttu-id="6d598-236">**优先级**</span><span class="sxs-lookup"><span data-stu-id="6d598-236">**Priority**</span></span>
   - <span data-ttu-id="6d598-237">**类型**</span><span class="sxs-lookup"><span data-stu-id="6d598-237">**Type**</span></span>

3. <span data-ttu-id="6d598-238">当您通过单击该名称选择出站垃圾邮件策略时，策略设置将显示在一个飞出控件中。</span><span class="sxs-lookup"><span data-stu-id="6d598-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="6d598-239">使用安全中心修改出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d598-239">Use the security center to modify outbound spam policies</span></span>

1. <span data-ttu-id="6d598-240">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="6d598-240">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6d598-241">在 **"反垃圾邮件策略"** 页上，通过单击名称从列表中选择出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="6d598-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="6d598-242">您创建的自定义策略，其中"类型"**列中的值为\*\*\*\*"自定义出站垃圾邮件策略"。**</span><span class="sxs-lookup"><span data-stu-id="6d598-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="6d598-243">名为"反垃圾邮件出站策略"的默认策略 **(默认) 。**</span><span class="sxs-lookup"><span data-stu-id="6d598-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="6d598-244">在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="6d598-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="6d598-245">有关设置详细信息，请参阅本文中的上一个使用安全中心 [创建出站](#use-the-security-center-to-create-outbound-spam-policies) 垃圾邮件策略部分。</span><span class="sxs-lookup"><span data-stu-id="6d598-245">For more information about the settings, see the previous [Use the security center to create outbound spam policies](#use-the-security-center-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="6d598-246">对于默认出站垃圾邮件策略，"应用于"部分 (该策略应用于所有) ，并且无法重命名该策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="6d598-247">若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。</span><span class="sxs-lookup"><span data-stu-id="6d598-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="6d598-248">启用或禁用自定义出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d598-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="6d598-249">不能禁用默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="6d598-250">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="6d598-250">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6d598-251">在 **"反垃圾邮件策略"** 页上，单击名称，从列表中选择"类型"值为"自定义出站垃圾邮件策略"的策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6d598-252">在出现的策略详细信息浮出控件顶部，你将看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="6d598-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="6d598-253">**策略关闭**：若要打开策略，请单击![“打开”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="6d598-254">**策略打开**：若要关闭策略，请单击![“关闭”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="6d598-255">在出现的确认对话框中，单击“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="6d598-256">单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="6d598-257">返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="6d598-258">设置自定义出站垃圾邮件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="6d598-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="6d598-259">默认情况下，出站垃圾邮件策略的优先级基于它们在新策略中创建的顺序 (策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="6d598-260">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="6d598-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6d598-261">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="6d598-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6d598-262">若要更改策略的优先级，请单击策略属性中的“**提高优先级**”或“**降低优先级**”（不能直接修改安全中心中的“**优先级**”数字）。</span><span class="sxs-lookup"><span data-stu-id="6d598-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="6d598-263">只有当你有多个策略时，更改策略的优先级才有意义。</span><span class="sxs-lookup"><span data-stu-id="6d598-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="6d598-264">**注意**：</span><span class="sxs-lookup"><span data-stu-id="6d598-264">**Notes**:</span></span>

- <span data-ttu-id="6d598-265">在安全中心内，只能在创建出站垃圾邮件策略后更改该策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="6d598-265">In the security center, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="6d598-266">在 PowerShell 中，可以在创建垃圾邮件筛选规则时替代默认优先级（这可能会影响现有规则的优先级）。</span><span class="sxs-lookup"><span data-stu-id="6d598-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="6d598-267">出站垃圾邮件策略按照第一个策略的优先级值为) 0 (的显示顺序进行处理。</span><span class="sxs-lookup"><span data-stu-id="6d598-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="6d598-268">默认出站垃圾邮件策略的优先级值为 **"** 最低"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="6d598-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="6d598-269">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="6d598-269">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6d598-270">在 **"反垃圾邮件策略"** 页上，通过单击名称从列表中选择"类型"值为"自定义出站垃圾邮件策略"的策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6d598-271">在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：</span><span class="sxs-lookup"><span data-stu-id="6d598-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="6d598-272">优先级值为 **0** 的出站垃圾邮件策略仅提供 **"减少优先级"** 选项。</span><span class="sxs-lookup"><span data-stu-id="6d598-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="6d598-273">优先级值最低的出站垃圾邮件策略 (例如 **，3**) 只有"增加 **优先级"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="6d598-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="6d598-274">如果你有三个或多个出站垃圾邮件策略，则优先级最高和最低值之间的策略同时具有"增加优先级"和"**减少优先级"** 选项。</span><span class="sxs-lookup"><span data-stu-id="6d598-274">If you have three or more outbound spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="6d598-275">单击![“提高优先级”图标](../../media/m365-cc-sc-increase-icon.png)“**提高优先级**”或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png)“**降低优先级**”以更改“**优先级**”值。</span><span class="sxs-lookup"><span data-stu-id="6d598-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="6d598-276">完成后，单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="6d598-277">使用安全中心删除自定义出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d598-277">Use the security center to remove custom outbound spam policies</span></span>

<span data-ttu-id="6d598-278">使用安全中心删除自定义出站垃圾邮件策略时，垃圾邮件筛选规则及相应的垃圾邮件筛选策略都将删除。</span><span class="sxs-lookup"><span data-stu-id="6d598-278">When you use the security center to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="6d598-279">不能删除默认出站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="6d598-280">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="6d598-280">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6d598-281">在 **"反垃圾邮件策略"** 页上，单击名称，从列表中选择"类型"值为"自定义出站垃圾邮件策略"的策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="6d598-282">在出现的策略详细信息浮出控件顶部，单击![“更多操作”图标](../../media/m365-cc-sc-more-actions-icon.png)“**更多操作**”\> ![“删除策略”图标](../../media/m365-cc-sc-delete-icon.png)“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="6d598-283">在出现的确认对话框中，单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="6d598-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="6d598-284">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d598-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="6d598-285">如前所述，出站垃圾邮件策略由出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则组成。</span><span class="sxs-lookup"><span data-stu-id="6d598-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="6d598-286">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，出站垃圾邮件筛选器策略和出站垃圾邮件筛选规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="6d598-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="6d598-287">您可以使用 **\* -HostedOutboundSpamFilterPolicy** cmdlet 管理出站垃圾邮件筛选器策略，使用 **\* -HostedOutboundSpamFilterRule** cmdlet 管理出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="6d598-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="6d598-288">在 PowerShell 中，首先创建出站垃圾邮件筛选策略，然后创建出站垃圾邮件筛选器规则，以标识该规则应用于的策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6d598-289">在 PowerShell 中，可以分别修改出站垃圾邮件筛选策略和出站垃圾邮件筛选规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="6d598-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="6d598-290">从 PowerShell 中删除出站垃圾邮件筛选策略时，不会自动删除相应的出站垃圾邮件筛选规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="6d598-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="6d598-291">使用 PowerShell 创建出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d598-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="6d598-292">在 PowerShell 中创建出站垃圾邮件策略的过程包括两个步骤：</span><span class="sxs-lookup"><span data-stu-id="6d598-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6d598-293">创建出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="6d598-294">创建出站垃圾邮件筛选器规则，该规则指定该规则适用的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="6d598-295">**注意**：</span><span class="sxs-lookup"><span data-stu-id="6d598-295">**Notes**:</span></span>

   - <span data-ttu-id="6d598-296">您可以创建一个新的出站垃圾邮件筛选器规则，并为其分配现有的未关联的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="6d598-297">出站垃圾邮件筛选器规则不能与多个出站垃圾邮件筛选器策略关联。</span><span class="sxs-lookup"><span data-stu-id="6d598-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="6d598-298">可以在 PowerShell 中的新出站垃圾邮件筛选器策略上配置以下设置，这些设置在创建策略之前在安全中心不可用：</span><span class="sxs-lookup"><span data-stu-id="6d598-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
     - <span data-ttu-id="6d598-299">在 `$false` **New-HostedOutboundSpamFilterRule** cmdlet cmdlet 上 ("禁用"的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="6d598-300">在 _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="6d598-301">在将策略分配给出站垃圾邮件筛选器规则之前，在 PowerShell 中新建的出站垃圾邮件筛选器策略在安全中心内不可见。</span><span class="sxs-lookup"><span data-stu-id="6d598-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="6d598-302">步骤 1：使用 PowerShell 创建出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6d598-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="6d598-303">若要创建出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="6d598-304">本示例创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器策略，该策略具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="6d598-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="6d598-305">收件人速率限制仅限于默认值较小的值。</span><span class="sxs-lookup"><span data-stu-id="6d598-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="6d598-306">有关详细信息，请参阅跨邮件[发送Microsoft 365选项](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="6d598-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="6d598-307">达到其中一个限制后，将阻止用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="6d598-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="6d598-308">有关语法和参数的详细信息，请参阅 [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d598-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="6d598-309">步骤 2：使用 PowerShell 创建出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="6d598-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="6d598-310">若要创建出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="6d598-311">本示例创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器规则，该规则具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="6d598-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="6d598-312">名为 Contoso Executives 的出站垃圾邮件筛选器策略与该规则关联。</span><span class="sxs-lookup"><span data-stu-id="6d598-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="6d598-313">此规则应用于“Contoso Executives Group”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="6d598-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="6d598-314">有关语法和参数的详细信息，请参阅 [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="6d598-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="6d598-315">使用 PowerShell 查看出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6d598-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="6d598-316">要返回所有出站垃圾邮件筛选器策略的摘要列表，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="6d598-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="6d598-317">要返回有关特定出站垃圾邮件筛选策略的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="6d598-318">本示例返回名为 Executives 的出站垃圾邮件筛选策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="6d598-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="6d598-319">有关语法和参数的详细信息，请参阅 [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d598-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="6d598-320">使用 PowerShell 查看出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="6d598-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="6d598-321">若要查看现有的出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="6d598-322">要返回所有出站垃圾邮件筛选规则的摘要列表，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="6d598-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="6d598-323">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6d598-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="6d598-324">要返回有关特定出站垃圾邮件筛选规则的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="6d598-325">本示例返回名为 Contoso Executives 的出站垃圾邮件筛选规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="6d598-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="6d598-326">有关语法和参数的详细信息，请参阅 [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="6d598-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="6d598-327">使用 PowerShell 修改出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6d598-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="6d598-328">在 PowerShell 中修改恶意软件筛选器策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 创建出站垃圾邮件筛选器策略一节中所述。</span><span class="sxs-lookup"><span data-stu-id="6d598-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="6d598-329">如果 **Set-HostedOutboundSpamFilterPolicy** cmdlet 没有 _Name_ 参数 (，则不能重命名出站垃圾邮件) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6d598-330">在安全中心重命名出站垃圾邮件策略时，仅重命名出站垃圾邮件筛选器 _规则_。</span><span class="sxs-lookup"><span data-stu-id="6d598-330">When you rename an outbound spam policy in the security center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="6d598-331">若要修改出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6d598-332">有关语法和参数的详细信息，请参阅 [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d598-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="6d598-333">使用 PowerShell 修改出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="6d598-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="6d598-334">在 PowerShell 中修改出站垃圾邮件筛选规则时，唯一不可用的设置是允许您创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="6d598-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6d598-335">若要启用或禁用现有出站垃圾邮件筛选器规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="6d598-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="6d598-336">否则，在 PowerShell 中修改出站垃圾邮件筛选规则时，其他设置将不可用。</span><span class="sxs-lookup"><span data-stu-id="6d598-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="6d598-337">创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 创建出站垃圾邮件筛选规则一节中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="6d598-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="6d598-338">要修改出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6d598-339">有关语法和参数的详细信息，请参阅 [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="6d598-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="6d598-340">使用 PowerShell 启用或禁用出站垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="6d598-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="6d598-341">在 PowerShell 中启用或禁用出站垃圾邮件筛选器规则会启用或禁用整个出站垃圾邮件策略 (出站垃圾邮件筛选器规则，以及分配的出站垃圾邮件筛选器策略) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="6d598-342">不能启用或禁用默认出站垃圾邮件策略 (它始终应用于所有邮件) 。</span><span class="sxs-lookup"><span data-stu-id="6d598-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="6d598-343">若要在 PowerShell 中启用或禁用出站垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="6d598-344">本示例禁用名为"Marketing Department"的出站垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="6d598-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="6d598-345">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="6d598-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="6d598-346">有关语法和参数的详细信息，请参阅 [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="6d598-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="6d598-347">使用 PowerShell 设置出站垃圾邮件筛选规则的优先级</span><span class="sxs-lookup"><span data-stu-id="6d598-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="6d598-p142">可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。</span><span class="sxs-lookup"><span data-stu-id="6d598-p142">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6d598-353">若要在 PowerShell 中设置出站垃圾邮件筛选规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6d598-p143">此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。</span><span class="sxs-lookup"><span data-stu-id="6d598-p143">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="6d598-356">**注意**：</span><span class="sxs-lookup"><span data-stu-id="6d598-356">**Notes**:</span></span>

- <span data-ttu-id="6d598-357">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-HostedOutboundSpamFilterRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="6d598-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="6d598-358">出站默认垃圾邮件筛选策略没有对应的垃圾邮件筛选规则，并且始终具有不可修改的优先级值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="6d598-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="6d598-359">使用 PowerShell 删除出站垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6d598-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="6d598-360">使用 PowerShell 删除出站垃圾邮件筛选策略时，不会删除相应的出站垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="6d598-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="6d598-361">若要在 PowerShell 中删除出站垃圾邮件筛选器策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6d598-362">本示例删除名为 Marketing Department 的出站垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6d598-363">有关语法和参数的详细信息，请参阅 [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d598-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="6d598-364">使用 PowerShell 删除出站垃圾邮件筛选器规则</span><span class="sxs-lookup"><span data-stu-id="6d598-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="6d598-365">使用 PowerShell 删除出站垃圾邮件筛选规则时，不会删除相应的出站垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="6d598-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="6d598-366">若要在 PowerShell 中删除出站垃圾邮件筛选器规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6d598-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="6d598-367">本示例删除名为"Marketing Department"的出站垃圾邮件筛选器规则。</span><span class="sxs-lookup"><span data-stu-id="6d598-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="6d598-368">有关语法和参数的详细信息，请参阅 [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="6d598-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="6d598-369">详细信息</span><span class="sxs-lookup"><span data-stu-id="6d598-369">For more information</span></span>

[<span data-ttu-id="6d598-370">从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="6d598-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="6d598-371">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="6d598-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="6d598-372">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="6d598-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="6d598-373">自动转发的消息报告</span><span class="sxs-lookup"><span data-stu-id="6d598-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
