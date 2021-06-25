---
title: 配置垃圾邮件筛选策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中查看、创建、修改和删除反垃圾邮件策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 81fcfde3442abcb63e04d67df5e6c66a56e3e498
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137759"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="33a7f-103">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-103">Configure anti-spam policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33a7f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="33a7f-104">**Applies to**</span></span>
- [<span data-ttu-id="33a7f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="33a7f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="33a7f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="33a7f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="33a7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33a7f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="33a7f-108">在有 Exchange Online 的 Microsoft 365 组织，或没有 Exchange Online 邮箱的 Exchange Online Protection (EOP) 组织中，EOP 都会自动保护入站电子邮件免受垃圾邮件威胁。</span><span class="sxs-lookup"><span data-stu-id="33a7f-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="33a7f-109">EOP 使用反垃圾邮件策略（亦称为“垃圾邮件筛选策略”或“内容筛选策略”），作为组织全面抵御垃圾邮件的措施的一部分。</span><span class="sxs-lookup"><span data-stu-id="33a7f-109">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="33a7f-110">有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-110">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="33a7f-111">管理员可以查看、编辑和配置（但不能删除）默认反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-111">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="33a7f-112">还可以创建应用于组织中特定用户、组或域的自定义反垃圾邮件策略，以实现更细致的控制。</span><span class="sxs-lookup"><span data-stu-id="33a7f-112">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="33a7f-113">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-113">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="33a7f-114">若要配置反垃圾邮件策略，可以使用 Microsoft 365 Defender 门户，也可以使用 PowerShell（对于拥有 Exchange Online 邮箱的 Microsoft 365 组织为 Exchange Online PowerShell；对于没有 Exchange Online邮箱的组织为独立 EOP PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-114">You can configure anti-spam policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="33a7f-115">反垃圾邮件策略的基本要素如下：</span><span class="sxs-lookup"><span data-stu-id="33a7f-115">The basic elements of an anti-spam policy are:</span></span>

- <span data-ttu-id="33a7f-116">**垃圾邮件筛选策略**：指定根据垃圾邮件筛选裁定执行的操作和通知选项。</span><span class="sxs-lookup"><span data-stu-id="33a7f-116">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="33a7f-117">**垃圾邮件筛选规则**：指定垃圾邮件筛选策略的优先级和收件人筛选器（即对谁应用策略）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-117">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="33a7f-118">在 Microsoft 365 Defender 门户中管理反垃圾邮件策略时，这两个要素之间的区别并不明显：</span><span class="sxs-lookup"><span data-stu-id="33a7f-118">The difference between these two elements isn't obvious when you manage anti-spam polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="33a7f-119">在创建反垃圾邮件策略时，实际上是同时创建了垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="33a7f-119">When you create an anti-spam policy, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="33a7f-120">如果你修改反垃圾邮件策略，与名称、优先级、启用/禁用以及收件人筛选器有关的设置会修改垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-120">When you modify an anti-spam policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="33a7f-121">其他所有设置会修改关联的垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-121">All other settings modify the associated spam filter policy.</span></span>
- <span data-ttu-id="33a7f-122">如果你删除反垃圾邮件策略，垃圾邮件筛选规则和关联的垃圾邮件筛选策略也会随之删除。</span><span class="sxs-lookup"><span data-stu-id="33a7f-122">When you remove an anti-spam policy, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="33a7f-123">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-123">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="33a7f-124">有关详细信息，请参阅本文后面的[使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置反垃圾邮件策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies)部分。</span><span class="sxs-lookup"><span data-stu-id="33a7f-124">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) section later in this article.</span></span>

<span data-ttu-id="33a7f-125">每个组织都有名为“默认”的内置反垃圾邮件策略，它具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="33a7f-125">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="33a7f-126">该策略会应用于组织中的所有收件人，即使没有与此策略关联的垃圾邮件筛选规则（亦称为“收件人筛选器”），也不例外。</span><span class="sxs-lookup"><span data-stu-id="33a7f-126">The policy is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="33a7f-127">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-127">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="33a7f-128">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="33a7f-128">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="33a7f-129">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-129">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="33a7f-130">为了提高垃圾邮件筛选的有效性，可以创建自定义反垃圾邮件策略，它包含应用于特定用户或用户组的更严格设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-130">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33a7f-131">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="33a7f-131">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33a7f-132">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="33a7f-132">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="33a7f-133">若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="33a7f-133">To go directly to the **Anti-spam policies** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="33a7f-134">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-134">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="33a7f-135">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-135">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="33a7f-136">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="33a7f-136">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="33a7f-137">必须是 **“组织管理”** 或 **“安全管理员”** 角色组的成员，才能添加、修改和删除反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-137">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="33a7f-138">若要获得对受限用户门户的只读访问权限，必须成为 **全球读者** 或 **安全读者** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="33a7f-138">For read-only access to anti-spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="33a7f-139">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-139">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="33a7f-140">**注意**：</span><span class="sxs-lookup"><span data-stu-id="33a7f-140">**Notes**:</span></span>

  - <span data-ttu-id="33a7f-141">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="33a7f-141">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="33a7f-142">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-142">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="33a7f-143">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="33a7f-143">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="33a7f-144">有关建议的反垃圾软件策略设置，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-144">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a><span data-ttu-id="33a7f-145">使用 Microsoft 365 Defender 门户创建反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-145">Use the Microsoft 365 Defender portal to create anti-spam policies</span></span>

<span data-ttu-id="33a7f-146">在 Microsoft 365 Defender 门户中创建自定义反垃圾邮件策略，会同时使用相同的名称创建垃圾邮件筛选规则和关联的垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-146">Creating a custom anti-spam policy in the Microsoft 365 Defender portal creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="33a7f-147">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”页面\>“**策略**”部分 \>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33a7f-148">在 **“反垃圾邮件”策略** 页面上点击 ![“创建图标”](../../media/m365-cc-sc-create-icon.png) **“创建策略”**，然后从下拉列表中选择 **“入站”**。</span><span class="sxs-lookup"><span data-stu-id="33a7f-148">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Inbound** from the drop down list.</span></span>

3. <span data-ttu-id="33a7f-149">将打开策略向导。</span><span class="sxs-lookup"><span data-stu-id="33a7f-149">The policy wizard opens.</span></span> <span data-ttu-id="33a7f-150">在“**命名策略页面**”上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="33a7f-150">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="33a7f-151">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="33a7f-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="33a7f-152">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="33a7f-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="33a7f-153">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="33a7f-154">在出现的“**用户、组和域**”页面上，标识策略应用于的内部收件人（收件人条件）：</span><span class="sxs-lookup"><span data-stu-id="33a7f-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="33a7f-155">**用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="33a7f-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="33a7f-156">**组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="33a7f-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="33a7f-157">**域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="33a7f-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="33a7f-158">单击相应的框，开始键入值，然后从结果中选择所需的值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="33a7f-159">根据需要多次重复此过程。</span><span class="sxs-lookup"><span data-stu-id="33a7f-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="33a7f-160">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="33a7f-160">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="33a7f-162">“删除”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-162">next to the value.</span></span>

   <span data-ttu-id="33a7f-163">对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="33a7f-164">对于用户，请自行输入星号 (\*) 以查看所有可用值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="33a7f-165">同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="33a7f-166">不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="33a7f-167">**排除这些用户、组和域**: 若要为策略应用于的内部收件人添加例外 (收件人例外)，请选择此选项并配置例外。</span><span class="sxs-lookup"><span data-stu-id="33a7f-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="33a7f-168">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="33a7f-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="33a7f-169">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="33a7f-170">在出现的“**群发电子邮件阈值和垃圾邮件属性**”页面上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="33a7f-170">On the **Bulk email threshold & spam properties** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="33a7f-171">**群发电子邮件阈值**：针对触发你在下一页上配置“**群发电子邮件**”垃圾邮件筛选裁定指定操作的邮件指定批量投诉级别 (BCL)（大于指定值、不大于或等于）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-171">**Bulk email threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk** spam filtering verdict that you configure on the next page (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="33a7f-172">值越高，邮件就越不理想（是垃圾邮件的可能性就越大）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-172">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="33a7f-173">默认值为 7。</span><span class="sxs-lookup"><span data-stu-id="33a7f-173">The default value is 7.</span></span> <span data-ttu-id="33a7f-174">有关详细信息，请参阅 [EOP 中的批量投诉级别 (BCL)](bulk-complaint-level-values.md)，以及[垃圾邮件与群发电子邮件有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-174">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="33a7f-175">默认情况下，在反垃圾邮件策略中，仅在 PowerShell 中可配置的设置 _MarkAsSpamBulkMail_ 的值为 `On`。</span><span class="sxs-lookup"><span data-stu-id="33a7f-175">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="33a7f-176">此设置极大地影响“**群发电子邮件**”筛选裁定结果：</span><span class="sxs-lookup"><span data-stu-id="33a7f-176">This setting dramatically affects the results of a **Bulk** filtering verdict:</span></span>

     - <span data-ttu-id="33a7f-177">**_MarkAsSpamBulkMail_ 的值为“打开”**：大于阈值的 BCL 将转换为对应于“**垃圾邮件**”筛选裁定的 SCL 6，并会对邮件执行“**群发电子邮件**”筛选裁定对应的操作。</span><span class="sxs-lookup"><span data-stu-id="33a7f-177">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk** filtering verdict is taken on the message.</span></span>
     - <span data-ttu-id="33a7f-178">**_MarkAsSpamBulkMail_ 的值为“关闭”**：虽然邮件已有 BCL 标记，但 _不会_ 根据“**群发电子邮件**”筛选裁定执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="33a7f-178">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk** filtering verdict.</span></span> <span data-ttu-id="33a7f-179">实际上，BCL 阈值和“**群发电子邮件**”筛选裁定操作不相关。</span><span class="sxs-lookup"><span data-stu-id="33a7f-179">In effect, the BCL threshold and **Bulk** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="33a7f-180">“**增加垃圾邮件分数**”、“**标记为垃圾邮件**”<sup>\*</sup>和“**测试模式**”：包含默认关闭的高级垃圾邮件筛选器 (ASF) 设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-180">**Increase spam score**, **Mark as spam**<sup>\*</sup> and **Test mode**: Contains the Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="33a7f-181">ASF 设置即将弃用，其功能正在合并到筛选堆栈的其他部分中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-181">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="33a7f-182">建议在反垃圾邮件策略中保持所有这些 ASF 设置的禁用状态不变。</span><span class="sxs-lookup"><span data-stu-id="33a7f-182">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

     <span data-ttu-id="33a7f-183">若要详细了解这些设置，请参阅 [EOP 中的高级垃圾邮件筛选设置](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-183">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

      <span data-ttu-id="33a7f-184"><sup>\*</sup>“**包含特定语言**”和“**从这些国家/地区**”不是 ASF 设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="33a7f-184"><sup>\*</sup> **Contains specific languages** and **from these countries** are not part of ASF settings.</span></span>

   - <span data-ttu-id="33a7f-185">**包含特定语言**: 点击该框，然后从下拉列表中选择 **“打开”** 或 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="33a7f-185">**Contains specific languages**: Click the box and select **On** or **Off** from the drop down list.</span></span> <span data-ttu-id="33a7f-186">如果将其打开，则将显示一个框。</span><span class="sxs-lookup"><span data-stu-id="33a7f-186">If you turn it on, a box appears.</span></span> <span data-ttu-id="33a7f-187">开始在框中键入语言的名称。</span><span class="sxs-lookup"><span data-stu-id="33a7f-187">Start typing the name of a language in the box.</span></span> <span data-ttu-id="33a7f-188">将显示支持的语言筛选列表。</span><span class="sxs-lookup"><span data-stu-id="33a7f-188">A filtered list of supported languages will appear.</span></span> <span data-ttu-id="33a7f-189">找到要查找的语言后，请将其选中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-189">When you find the language that you're looking for, select it.</span></span> <span data-ttu-id="33a7f-190">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="33a7f-191">若要删除现有值，请单击值旁边的![“删除”图标](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-191">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   - <span data-ttu-id="33a7f-192">**从这些国家/地区** _: 点击该框，然后从下拉列表中选择_ *“打开”*\* 或 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="33a7f-192">**From these countries** _: Click the box and select _ *On*\* or **Off** from the drop down list.</span></span> <span data-ttu-id="33a7f-193">如果将其打开，则将显示一个框。</span><span class="sxs-lookup"><span data-stu-id="33a7f-193">If you turn it on, a box appears.</span></span> <span data-ttu-id="33a7f-194">开始在框中键入国家/地区的名称。</span><span class="sxs-lookup"><span data-stu-id="33a7f-194">Start typing the name of a country in the box.</span></span> <span data-ttu-id="33a7f-195">将显示支持的国家/地区筛选列表。</span><span class="sxs-lookup"><span data-stu-id="33a7f-195">A filtered list of supported countries will appear.</span></span> <span data-ttu-id="33a7f-196">找到要查找的国家/地区后，请将其选中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-196">When you find the country that you're looking for, select it.</span></span> <span data-ttu-id="33a7f-197">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="33a7f-198">若要删除现有值，请单击值旁边的![“删除”图标](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-198">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   <span data-ttu-id="33a7f-199">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-199">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="33a7f-200">在出现的“**操作**”页面上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="33a7f-200">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="33a7f-201">**邮件操作**：选择或查看根据以下垃圾邮件筛选裁定而对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="33a7f-201">**Message actions**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>
     - <span data-ttu-id="33a7f-202">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="33a7f-202">**Spam**</span></span>
     - <span data-ttu-id="33a7f-203">**高可信度垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="33a7f-203">**High confidence spam**</span></span>
     - <span data-ttu-id="33a7f-204">**钓鱼**</span><span class="sxs-lookup"><span data-stu-id="33a7f-204">**Phishing**</span></span>
     - <span data-ttu-id="33a7f-205">**高可信度网络钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="33a7f-205">**High confidence phishing**</span></span>
     - <span data-ttu-id="33a7f-206">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="33a7f-206">**Bulk**</span></span>

     <span data-ttu-id="33a7f-207">下表介绍了可以根据垃圾邮件筛选裁定而执行的操作。</span><span class="sxs-lookup"><span data-stu-id="33a7f-207">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="33a7f-208">复选标记 (</span><span class="sxs-lookup"><span data-stu-id="33a7f-208">A check mark (</span></span> ![复选标记](../../media/checkmark.png)<span data-ttu-id="33a7f-210">）表示操作可以执行（并不是所有操作都适用于所有裁定）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-210">) indicates the action is available (not all actions are available for all verdicts).</span></span>
     - <span data-ttu-id="33a7f-211">复选标记后面的星号 (<sup>\*</sup>) 表示垃圾邮件筛选裁定对应的默认操作。</span><span class="sxs-lookup"><span data-stu-id="33a7f-211">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     <br>

     ****

     |<span data-ttu-id="33a7f-212">操作</span><span class="sxs-lookup"><span data-stu-id="33a7f-212">Action</span></span>|<span data-ttu-id="33a7f-213">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="33a7f-213">Spam</span></span>|<span data-ttu-id="33a7f-214">高</span><span class="sxs-lookup"><span data-stu-id="33a7f-214">High</span></span><br><span data-ttu-id="33a7f-215">置信</span><span class="sxs-lookup"><span data-stu-id="33a7f-215">confidence</span></span><br><span data-ttu-id="33a7f-216">垃圾邮件 (spam)</span><span class="sxs-lookup"><span data-stu-id="33a7f-216">spam</span></span>|<span data-ttu-id="33a7f-217">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="33a7f-217">Phishing</span></span>|<span data-ttu-id="33a7f-218">高</span><span class="sxs-lookup"><span data-stu-id="33a7f-218">High</span></span><br><span data-ttu-id="33a7f-219">置信</span><span class="sxs-lookup"><span data-stu-id="33a7f-219">confidence</span></span><br><span data-ttu-id="33a7f-220">仿冒</span><span class="sxs-lookup"><span data-stu-id="33a7f-220">phishing</span></span>|<span data-ttu-id="33a7f-221">批量邮件</span><span class="sxs-lookup"><span data-stu-id="33a7f-221">Bulk</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="33a7f-222">**将邮件移动到“垃圾邮件”文件夹**：邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-222">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="33a7f-223">![复选标记](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-223">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="33a7f-224">![复选标记](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-224">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|<span data-ttu-id="33a7f-227">![复选标记](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-227">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="33a7f-228">**添加 X 标头**：向邮件头添加 X 标头，并将邮件递送到邮箱。</span><span class="sxs-lookup"><span data-stu-id="33a7f-228">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <p> <span data-ttu-id="33a7f-229">稍后将在 **“添加此 X 标头文本”** 框中，输入 X 标头字段名称（而不是值）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-229">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <p> <span data-ttu-id="33a7f-230">对于 **“垃圾邮件”** 和 **“高可信度垃圾邮件”** 裁定，邮件移动到“垃圾邮件”文件夹。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-230">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)||<span data-ttu-id="33a7f-234">![复选标记](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-234">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="33a7f-235">**在主题行前面追加文本**：向邮件的主题行开头添加文本。</span><span class="sxs-lookup"><span data-stu-id="33a7f-235">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="33a7f-236">邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-236">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <p> <span data-ttu-id="33a7f-237">稍后将在 **“在主题行前面添加此文本作为前缀”** 框中输入文本。</span><span class="sxs-lookup"><span data-stu-id="33a7f-237">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)||![复选标记](../../media/checkmark.png)|
     |<span data-ttu-id="33a7f-242">**将邮件重定向到电子邮件地址**：将邮件发送给其他收件人，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="33a7f-242">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <p> <span data-ttu-id="33a7f-243">稍后将在 **“重定向到此电子邮件地址”** 框中指定收件人。</span><span class="sxs-lookup"><span data-stu-id="33a7f-243">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
     |<span data-ttu-id="33a7f-249">**删除邮件**：无提示删除整个邮件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="33a7f-249">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)||![复选标记](../../media/checkmark.png)|
     |<span data-ttu-id="33a7f-254">**隔离邮件**：将邮件发送到隔离，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="33a7f-254">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <p> <span data-ttu-id="33a7f-255">稍后将在 **“隔离”** 框中指定所需的邮件隔离时长。</span><span class="sxs-lookup"><span data-stu-id="33a7f-255">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|<span data-ttu-id="33a7f-258">![复选标记](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33a7f-258">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
     |<span data-ttu-id="33a7f-261">**无操作**</span><span class="sxs-lookup"><span data-stu-id="33a7f-261">**No action**</span></span>|||||![复选标记](../../media/checkmark.png)|
     |

     > <span data-ttu-id="33a7f-263"><sup>1</sup>在 Exchange Online 中，如果邮箱启用了垃圾邮件规则（默认处于启用状态），邮件会移动到“垃圾邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="33a7f-263"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="33a7f-264">有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-264">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="33a7f-265">在 EOP 保护本地 Exchange 邮箱的混合环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="33a7f-265">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="33a7f-266">有关详细信息，请参阅[在混合环境中将 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-266">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span>
     >
     > <span data-ttu-id="33a7f-267"><sup>2</sup>可以将此使用值用作邮件流规则（亦称为“传输规则”）中的条件来筛选或路由邮件。</span><span class="sxs-lookup"><span data-stu-id="33a7f-267"><sup>2</sup> You can this use value as a condition in mail flow rules to filter or route the message.</span></span>

   - <span data-ttu-id="33a7f-268">**将垃圾邮件保留在隔离区内此天数**：指定在你选择“**隔离邮件**”作为垃圾邮件筛选裁定操作时将邮件放在隔离区内的时长。</span><span class="sxs-lookup"><span data-stu-id="33a7f-268">**Retain spam in quarantine for this many days**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="33a7f-269">在此时间段到期后，邮件就会被删除。</span><span class="sxs-lookup"><span data-stu-id="33a7f-269">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="33a7f-270">默认值为 30 天。</span><span class="sxs-lookup"><span data-stu-id="33a7f-270">The default value is 30 days.</span></span> <span data-ttu-id="33a7f-271">有效值介于 1 和 30 天之间。</span><span class="sxs-lookup"><span data-stu-id="33a7f-271">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="33a7f-272">若要了解隔离，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="33a7f-272">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="33a7f-273">EOP 中隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="33a7f-273">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="33a7f-274">在 EOP 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="33a7f-274">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="33a7f-275">在 EOP 中以用户身份查找和释放已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="33a7f-275">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="33a7f-276">**添加此 X 标头文本**：只有当你选择 **“添加 X 标头”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-276">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="33a7f-277">指定的值是添加到邮件头的标头字段 *名称*。</span><span class="sxs-lookup"><span data-stu-id="33a7f-277">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="33a7f-278">标头字段 *值* 始终为 `This message appears to be spam`。</span><span class="sxs-lookup"><span data-stu-id="33a7f-278">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="33a7f-279">长度上限为 255 个字符，且值不得包含空格或冒号 (:)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-279">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="33a7f-280">例如，如果你输入值 `X-This-is-my-custom-header`，则添加到邮件的 X 标头为 `X-This-is-my-custom-header: This message appears to be spam.`</span><span class="sxs-lookup"><span data-stu-id="33a7f-280">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="33a7f-281">如果你输入的值包含空格或冒号 (:)，输入值会遭忽略，且添加到邮件中的是默认 X 标头 (`X-This-Is-Spam: This message appears to be spam.`)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-281">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="33a7f-282">**在主题行前面添加此文本作为前缀**：只有当你选择 **“在主题行前面追加文本”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-282">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="33a7f-283">输入要添加到邮件主题行开头的文本。</span><span class="sxs-lookup"><span data-stu-id="33a7f-283">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="33a7f-284">**重定向到此电子邮件地址**：只有当你选择 **“将邮件重定向到电子邮件地址”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-284">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="33a7f-285">输入要将邮件递送到的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="33a7f-285">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="33a7f-286">可以输入多个值，用分号 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="33a7f-286">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="33a7f-287">**启用安全提示**：安全提示默认处于启用状态，但你可以通过清除该复选框来禁用它们。</span><span class="sxs-lookup"><span data-stu-id="33a7f-287">**Enable safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the checkbox.</span></span> <span data-ttu-id="33a7f-288">若要详细了解安全提示，请参阅[电子邮件安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-288">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   - <span data-ttu-id="33a7f-289">**启用零时差自动清除 (ZAP)**：ZAP 检测已递送到 Exchange Online 邮箱的邮件，并对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="33a7f-289">**Enable zero-hour auto purge (ZAP)**: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="33a7f-290">有关详细信息，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-290">For more information, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

     <span data-ttu-id="33a7f-291">默认情况下，ZAP 处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="33a7f-291">ZAP is turned on by default.</span></span> <span data-ttu-id="33a7f-292">当启用 ZAP 时，可以使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="33a7f-292">When ZAP is turned on, the following settings are available:</span></span>

     - <span data-ttu-id="33a7f-293">**为钓鱼邮件启用 ZAP**：默认情况下，为钓鱼检测启用 ZAP，但可通过清除复选框来禁用它。</span><span class="sxs-lookup"><span data-stu-id="33a7f-293">**Enable ZAP for phishing messages**: By default, ZAP is enabled for phishing detections, but you can disable it by clearing the checkbox.</span></span>
     - <span data-ttu-id="33a7f-294">**为垃圾邮件启用 ZAP**：默认情况下，为垃圾邮件检测启用 ZAP，但可通过清除复选框来禁用它。</span><span class="sxs-lookup"><span data-stu-id="33a7f-294">**Enable ZAP for spam messages**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the checkbox.</span></span>

   - <span data-ttu-id="33a7f-295">**启用最终用户垃圾邮件通知**：有关详细信息，请参阅本主题后面的 [配置最终用户垃圾邮件通知](#configure-end-user-spam-notifications)部分。</span><span class="sxs-lookup"><span data-stu-id="33a7f-295">**Enable end-user spam notifications**: For more information, see the [Configure end-user spam notifications](#configure-end-user-spam-notifications) section later in this topic.</span></span>

   <span data-ttu-id="33a7f-296">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-296">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="33a7f-297">在出现的“**允许和阻止列表**”浮出控件上，你能够按允许跳过垃圾邮件筛选的电子邮件地址或电子邮件域配置邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="33a7f-297">On the **Allow & block list** flyout that appears, you are able to configure message senders by email address or email domain that are allowed to skip spam filtering.</span></span>

   <span data-ttu-id="33a7f-298">在“**已允许**”部分中，可以配置允许的发件人和允许的域。</span><span class="sxs-lookup"><span data-stu-id="33a7f-298">In the **Allowed** section, you can configure allowed senders and allowed domains.</span></span> <span data-ttu-id="33a7f-299">在“**已阻止**”部分中，可以配置阻止的发件人和阻止的域。</span><span class="sxs-lookup"><span data-stu-id="33a7f-299">In the **Blocked** section, you can add blocked senders and blocked domains.</span></span>

   > [!IMPORTANT]
   >
   > <span data-ttu-id="33a7f-300">在将域添加到允许的域列表之前，请慎重考虑。</span><span class="sxs-lookup"><span data-stu-id="33a7f-300">Think very carefully before you add domains to the allowed domains list.</span></span> <span data-ttu-id="33a7f-301">有关详细信息，请参阅[在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="33a7f-301">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > <span data-ttu-id="33a7f-302">切勿将你自己的[接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)或公共域（例如 microsoft.com 或 office.com）添加到允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-302">Never add your own [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="33a7f-303">如果允许这些域名绕过垃圾邮件过滤，攻击者则可以很容易地将欺骗这些可信域名的消息发送到组织。</span><span class="sxs-lookup"><span data-stu-id="33a7f-303">If these domains are allowed to bypass spam filtering, attackers can easily send messages that spoof these trusted domains into your organization.</span></span>
   >
   > <span data-ttu-id="33a7f-304">通过将域添加到阻止的域列表来手动阻止域并不危险，但这会增加你的管理工作量。</span><span class="sxs-lookup"><span data-stu-id="33a7f-304">Manually blocking domains by adding the domains to the blocked domains list isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="33a7f-305">有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-305">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>
   >
   > <span data-ttu-id="33a7f-306">有时，我们的筛选器会漏掉一封邮件，你不同意筛选裁定，或者我们的系统需要时间来跟进。</span><span class="sxs-lookup"><span data-stu-id="33a7f-306">There will be times when our filters will miss a message, you don't agree with the filtering verdict, or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="33a7f-307">在这些情况下，允许列表和阻止列表可用于覆盖当前筛选裁定。</span><span class="sxs-lookup"><span data-stu-id="33a7f-307">In these cases, the allow list and block list are available to override the current filtering verdicts.</span></span> <span data-ttu-id="33a7f-308">但是，你应该谨慎和临时使用这些列表：冗长列表可能无法管理，我们的筛选堆栈应正在执行它应该执行的操作。</span><span class="sxs-lookup"><span data-stu-id="33a7f-308">But, you should use these lists sparingly and temporarily: longs lists can become unmanageable, and our filtering stack should be doing what it's supposed to be doing.</span></span> <span data-ttu-id="33a7f-309">如果你打算长时间保留允许的域，则应该告知发件人验证其域是否已通过身份验证，如果没有，则设置为“DMARC 拒绝”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-309">If you're going to keep an allowed domain for an extended period of time, you should tell the sender to verify that their domain is authenticated and set to DMARC reject if it's not.</span></span>

   <span data-ttu-id="33a7f-310">将条目添加到任何列表的步骤相同：</span><span class="sxs-lookup"><span data-stu-id="33a7f-310">The steps to add entries to any of the lists are the same:</span></span>

   1. <span data-ttu-id="33a7f-311">单击要配置的列表的链接：</span><span class="sxs-lookup"><span data-stu-id="33a7f-311">Click the link for the list that you want to configure:</span></span>
      - <span data-ttu-id="33a7f-312">**允许的**\>**发件人**：单击“**管理 (nn) 发件人**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-312">**Allowed** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="33a7f-313">**允许的**\>**域**：单击“**允许域**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-313">**Allowed** \> **Domains**: Click **Allow domains**.</span></span>
      - <span data-ttu-id="33a7f-314">**阻止的**\>**发件人**：单击“**管理 (nn) 发件人**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-314">**Blocked** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="33a7f-315">**阻止的**\>**域**：单击“**阻止域**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-315">**Blocked** \> **Domains**: Click **Block domains**.</span></span>

   2. <span data-ttu-id="33a7f-316">在出现的浮出控件中，执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="33a7f-316">In the flyout that appears, do the following steps:</span></span>
      1. <span data-ttu-id="33a7f-317">单击![“创建”图标](../../media/m365-cc-sc-create-icon.png)“**添加发件人**”或“**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-317">Click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Add senders** or **Add domains**.</span></span>
      2. <span data-ttu-id="33a7f-318">在出现的“**添加发件人**”或“**添加域**”浮出控件中，在“**发件人**”框中输入发件人的电子邮件地址，或者在“**域**”框中输入域。</span><span class="sxs-lookup"><span data-stu-id="33a7f-318">In the **Add senders** or **Add domains** flyout that appears, enter the sender's email address in the **Sender** box or the domain in the **Domain** box.</span></span> <span data-ttu-id="33a7f-319">键入时，值将显示在框下方。</span><span class="sxs-lookup"><span data-stu-id="33a7f-319">As you're typing, the value appears below the box.</span></span> <span data-ttu-id="33a7f-320">完成键入电子邮件地址或域后，请选择框下方的值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-320">When you're finished typing the email address or domain, select the value below the box.</span></span>
      3. <span data-ttu-id="33a7f-321">根据需要多次重复上一步。</span><span class="sxs-lookup"><span data-stu-id="33a7f-321">Repeat the previous step as many times as necessary.</span></span> <span data-ttu-id="33a7f-322">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="33a7f-322">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="33a7f-324">“删除”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-324">next to the value.</span></span>

      <span data-ttu-id="33a7f-325">完成后，单击“**添加发件人**”或“**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-325">When you're finished, click **Add senders** or **Add domains**.</span></span>

      <span data-ttu-id="33a7f-326">返回到主浮出控件，页面上列出了你添加的发件人或域。</span><span class="sxs-lookup"><span data-stu-id="33a7f-326">Back on the main flyout, the senders or domains that you added are listed on the page.</span></span> <span data-ttu-id="33a7f-327">若要从此页面中删除条目，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="33a7f-327">To remove an entry from this page, do the following steps:</span></span>

      1. <span data-ttu-id="33a7f-328">从列表中选择一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="33a7f-328">Select one or more entries from the list.</span></span> <span data-ttu-id="33a7f-329">还可使用“**搜索**”框查找列表中的值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-329">You can also use the **Search** box to find values in the list.</span></span>
      2. <span data-ttu-id="33a7f-330">在你选择至少一个条目后，“删除”图标</span><span class="sxs-lookup"><span data-stu-id="33a7f-330">After you select at least one entry, the delete icon</span></span> ![“删除”图标](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="33a7f-332">将会出现。</span><span class="sxs-lookup"><span data-stu-id="33a7f-332">appears.</span></span>
      3. <span data-ttu-id="33a7f-333">单击“删除”图标</span><span class="sxs-lookup"><span data-stu-id="33a7f-333">Click the delete icon</span></span> ![“删除”图标](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="33a7f-335">以删除所选条目。</span><span class="sxs-lookup"><span data-stu-id="33a7f-335">to remove the selected entries.</span></span>

      <span data-ttu-id="33a7f-336">完成后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-336">When you're finished, click **Done**.</span></span>

      <span data-ttu-id="33a7f-337">返回到“**允许和阻止列表**”页面，准备好继续时单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-337">Back on the **Allow & block list** page, click **Next** when you're read to continue.</span></span>

8. <span data-ttu-id="33a7f-338">在出现的“**审阅**”页面上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-338">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="33a7f-339">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-339">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="33a7f-340">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="33a7f-340">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="33a7f-341">完成后，单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-341">When you're finished, click **Create**.</span></span>

9. <span data-ttu-id="33a7f-342">在出现的确认页面上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-342">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a><span data-ttu-id="33a7f-343">使用 Microsoft 365 Defender 门户查看反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-343">Use the Microsoft 365 Defender portal to view anti-spam policies</span></span>

1. <span data-ttu-id="33a7f-344">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”页面\>“**策略**”部分 \>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-344">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33a7f-345">在 **“反垃圾邮件”策略** 页面上，查找以下值之一:</span><span class="sxs-lookup"><span data-stu-id="33a7f-345">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="33a7f-346">“**类型**”值是“**自定义反垃圾邮件策略**”</span><span class="sxs-lookup"><span data-stu-id="33a7f-346">The **Type** value is **Custom anti-spam policy**</span></span>
   - <span data-ttu-id="33a7f-347">“**名称**”值是“**反垃圾邮件入站策略（默认）**”</span><span class="sxs-lookup"><span data-stu-id="33a7f-347">The **Name** value is **Anti-spam inbound policy (Default)**</span></span>

   <span data-ttu-id="33a7f-348">反垃圾邮件策略列表中将显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="33a7f-348">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="33a7f-349">**名称**</span><span class="sxs-lookup"><span data-stu-id="33a7f-349">**Name**</span></span>
   - <span data-ttu-id="33a7f-350">**状态**</span><span class="sxs-lookup"><span data-stu-id="33a7f-350">**Status**</span></span>
   - <span data-ttu-id="33a7f-351">**优先级**</span><span class="sxs-lookup"><span data-stu-id="33a7f-351">**Priority**</span></span>
   - <span data-ttu-id="33a7f-352">**类型**</span><span class="sxs-lookup"><span data-stu-id="33a7f-352">**Type**</span></span>

3. <span data-ttu-id="33a7f-353">单击名称选择反垃圾邮件策略时，策略设置会显示在浮出控件中。</span><span class="sxs-lookup"><span data-stu-id="33a7f-353">When you select an anti-spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a><span data-ttu-id="33a7f-354">使用 Microsoft 365 Defender 门户修改反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-354">Use the Microsoft 365 Defender portal to modify anti-spam policies</span></span>

1. <span data-ttu-id="33a7f-355">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”页面\>“**策略**”部分 \>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-355">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33a7f-356">在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择反垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="33a7f-356">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="33a7f-357">你创建的自定义策略，其中“**类型**”列中的值为“**自定义反垃圾邮件策略**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-357">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="33a7f-358">名为“**反垃圾邮件入站策略（默认）**”的默认策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-358">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="33a7f-359">在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-359">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="33a7f-360">有关设置的详细信息，请参阅本文前面的“[使用 Microsoft 365 Defender 门户创建反垃圾邮件策略](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)”部分。</span><span class="sxs-lookup"><span data-stu-id="33a7f-360">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create anti-spam policies](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) section in this article.</span></span>

   <span data-ttu-id="33a7f-361">对于默认反垃圾邮件策略，没有“**应用于**”部分（该策略应用于所有人），且无法重命名该策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-361">For the default anti-spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="33a7f-362">若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。</span><span class="sxs-lookup"><span data-stu-id="33a7f-362">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="33a7f-363">启用或禁用反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-363">Enable or disable anti-spam policies</span></span>

<span data-ttu-id="33a7f-364">无法禁用默认反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-364">You can't disable the default anti-spam policy.</span></span>

1. <span data-ttu-id="33a7f-365">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”页面\>“**策略**”部分 \>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-365">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33a7f-366">在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择“**类型”** 值为“**自定义反垃圾邮件策略**”的策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-366">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="33a7f-367">在出现的策略详细信息浮出控件顶部，你将看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="33a7f-367">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="33a7f-368">**策略关闭**：若要打开策略，请单击![“打开”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-368">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="33a7f-369">**策略打开**：若要关闭策略，请单击![“关闭”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-369">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="33a7f-370">在出现的确认对话框中，单击“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-370">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="33a7f-371">单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-371">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="33a7f-372">返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-372">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="33a7f-373">设置自定义反垃圾邮件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="33a7f-373">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="33a7f-374">默认情况下，反垃圾邮件策略根据创建顺序来获得优先级（新策略的优先级低于旧策略）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-374">By default, anti-spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="33a7f-375">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-375">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="33a7f-376">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="33a7f-376">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="33a7f-377">若要更改策略的优先级，请单击策略属性中的“**提高优先级**”或“**降低优先级**”（不能直接修改 Microsoft 365 Defender 门户中的“**优先级**”数字）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-377">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="33a7f-378">只有当你有多个策略时，更改策略的优先级才有意义。</span><span class="sxs-lookup"><span data-stu-id="33a7f-378">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="33a7f-379">**注意**：</span><span class="sxs-lookup"><span data-stu-id="33a7f-379">**Notes**:</span></span>

- <span data-ttu-id="33a7f-p143">在 Microsoft 365 Defender 门户中，你只能在创建反垃圾邮件策略后更改其优先级。在 PowerShell 中，你可以在创建垃圾邮件筛选规则时覆盖默认优先级（这可能会影响现有规则的优先级）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-p143">In the Microsoft 365 Defender portal, you can only change the priority of the anti-spam policy after you create it. In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="33a7f-382">反垃圾邮件策略将按其显示顺序进行处理（第一个策略的“**优先级**”值为 0）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-382">Anti-spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="33a7f-383">默认反垃圾邮件策略的优先级值为“**最低**”，你无法更改此值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-383">The default anti-spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="33a7f-384">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”页面\>“**策略**”部分 \>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-384">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33a7f-385">在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择“**类型”** 值为“**自定义反垃圾邮件策略**”的策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-385">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="33a7f-386">在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：</span><span class="sxs-lookup"><span data-stu-id="33a7f-386">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="33a7f-387">“**优先级**”值为 **0** 的反垃圾邮件策略只有“**降低优先级**”选项可用。</span><span class="sxs-lookup"><span data-stu-id="33a7f-387">The anti-spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="33a7f-388">具有最低“**优先级**”值（例如 **3**）的反垃圾邮件策略只有“**提高优先级**”选项可用。</span><span class="sxs-lookup"><span data-stu-id="33a7f-388">The anti-spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="33a7f-389">如果你有三个或更多反垃圾邮件策略，则最高和最低优先级值之间的策略同时有“**提高优先级**”和“**降低优先级**”两个选项可用。</span><span class="sxs-lookup"><span data-stu-id="33a7f-389">If you have three or more anti-spam policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="33a7f-390">单击![“提高优先级”图标](../../media/m365-cc-sc-increase-icon.png)“**提高优先级**”或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png)“**降低优先级**”以更改“**优先级**”值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-390">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="33a7f-391">完成后，单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-391">When you're finished, click **Close** in the policy details flyout.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="33a7f-392">配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="33a7f-392">Configure end-user spam notifications</span></span>

<span data-ttu-id="33a7f-393">如果垃圾邮件筛选裁定隔离了邮件，你可以配置最终用户垃圾邮件通知，让收件人知道向他们发送的邮件发生了什么。</span><span class="sxs-lookup"><span data-stu-id="33a7f-393">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="33a7f-394">若要详细了解这些通知，请参阅 [ EOP 中的最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-394">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="33a7f-395">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”页面\>“**策略**”部分 \>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-395">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33a7f-396">在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择反垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="33a7f-396">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="33a7f-397">你创建的自定义策略，其中“**类型**”列中的值为“**自定义反垃圾邮件策略**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-397">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="33a7f-398">名为“**反垃圾邮件入站策略（默认）**”的默认策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-398">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="33a7f-399">在出现的策略详细信息浮出控件中，单击“**操作**”部分中的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-399">In the policy details flyout that appears, click **Edit** in the **Actions** section.</span></span> <span data-ttu-id="33a7f-400">在出现的“**操作**”浮出控件中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="33a7f-400">In the **Actions** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="33a7f-401">**启用最终用户垃圾邮件通知**：选中此复选框可启用通知，或清除此复选框可禁用通知。</span><span class="sxs-lookup"><span data-stu-id="33a7f-401">**Enable end-user spam notifications**: Select the checkbox to enable notifications or clear the checkbox to disable notifications.</span></span> <span data-ttu-id="33a7f-402">选中该复选框时，将显示以下附加设置：</span><span class="sxs-lookup"><span data-stu-id="33a7f-402">When you select the checkbox, the following additional settings appear:</span></span>

     - <span data-ttu-id="33a7f-403">**发送最终用户垃圾邮件通知的间隔天数**：选择通知发送频率。</span><span class="sxs-lookup"><span data-stu-id="33a7f-403">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="33a7f-404">默认值为 3 天。</span><span class="sxs-lookup"><span data-stu-id="33a7f-404">The default value is 3 days.</span></span> <span data-ttu-id="33a7f-405">可输入介于 1 和 15 天之间的值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-405">You can enter 1 to 15 days.</span></span>

       <span data-ttu-id="33a7f-406">在 24 小时内，有 3 个从以下时间开始计时的最终用户垃圾邮件通知周期：01:00 UTC、08:00 UTC 和 16:00 UTC。</span><span class="sxs-lookup"><span data-stu-id="33a7f-406">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

       > [!NOTE]
       > <span data-ttu-id="33a7f-407">如果我们在上一个周期中错过了通知，则后续周期会推送通知。</span><span class="sxs-lookup"><span data-stu-id="33a7f-407">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="33a7f-408">这可能会在同一天内显示多个通知。</span><span class="sxs-lookup"><span data-stu-id="33a7f-408">This might give the appearance of multiple notifications within the same day.</span></span>

     - <span data-ttu-id="33a7f-409">**语言**：单击下拉列表，并从列表中选择可用语言。</span><span class="sxs-lookup"><span data-stu-id="33a7f-409">**Language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="33a7f-410">默认值是“默认”（即英语）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-410">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="33a7f-411">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-411">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="33a7f-412">返回策略详细信息浮出控件，单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-412">Back on the policy details flyout, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a><span data-ttu-id="33a7f-413">使用 Microsoft 365 Defender 门户删除自定义反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-413">Use the Microsoft 365 Defender portal to remove custom anti-spam policies</span></span>

<span data-ttu-id="33a7f-p151">当你使用 Microsoft 365 Defender 门户删除自定义反垃圾邮件策略时，垃圾邮件筛选规则和相应的垃圾邮件筛选策略都将被删除。无法删除默认反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-p151">When you use the Microsoft 365 Defender portal to remove a custom anti-spam policy, the spam filter rule and the corresponding spam filter policy are both deleted. You can't remove the default anti-spam policy.</span></span>

1. <span data-ttu-id="33a7f-416">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”页面\>“**策略**”部分 \>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-416">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33a7f-417">在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择“**类型”** 值为“**自定义反垃圾邮件策略**”的策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-417">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="33a7f-418">在出现的策略详细信息浮出控件顶部，单击![“更多操作”图标](../../media/m365-cc-sc-more-actions-icon.png)“**更多操作**”\> ![“删除策略”图标](../../media/m365-cc-sc-delete-icon.png)“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-418">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="33a7f-419">在出现的确认对话框中，单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="33a7f-419">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="33a7f-420">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-420">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="33a7f-421">如前文所述，反垃圾邮件策略由垃圾邮件筛选策略和垃圾邮件筛选规则组成。</span><span class="sxs-lookup"><span data-stu-id="33a7f-421">As previously described, an anti-spam policy consists of a spam filter policy and a spam filter rule.</span></span>

<span data-ttu-id="33a7f-422">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，垃圾邮件筛选策略与垃圾邮件筛选规则之间的区别很明显。</span><span class="sxs-lookup"><span data-stu-id="33a7f-422">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="33a7f-423">可以使用 **\*-HostedContentFilterPolicy** cmdlet 管理垃圾邮件筛选策略，并使用 **\*-HostedContentFilterRule** cmdlet 管理垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-423">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="33a7f-424">在 PowerShell 中，先创建垃圾邮件筛选策略，再创建确定向哪个策略应用规则的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-424">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="33a7f-425">在 PowerShell 中，分别修改垃圾邮件筛选策略和垃圾邮件筛选规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-425">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>
- <span data-ttu-id="33a7f-426">如果你通过 PowerShell 删除垃圾邮件筛选策略，相应的垃圾邮件筛选规则不会自动随之删除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="33a7f-426">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

<span data-ttu-id="33a7f-427">以下反垃圾邮件策略设置仅在 PowerShell 中可配置：</span><span class="sxs-lookup"><span data-stu-id="33a7f-427">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="33a7f-428">默认情况下，_MarkAsSpamBulkMail_ 参数的值为 `On`。</span><span class="sxs-lookup"><span data-stu-id="33a7f-428">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="33a7f-429">本文前面的“[使用 Microsoft 365 Defender 门户创建反垃圾邮件策略](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)”部分中介绍了此设置的效果。</span><span class="sxs-lookup"><span data-stu-id="33a7f-429">The effects of this setting were explained in the [Use the Microsoft 365 Defender portal to create anti-spam policies](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) section earlier in this article.</span></span>

- <span data-ttu-id="33a7f-430">以下设置用于最终用户垃圾邮件隔离通知：</span><span class="sxs-lookup"><span data-stu-id="33a7f-430">The following settings for end-user spam quarantine notifications:</span></span>
  - <span data-ttu-id="33a7f-431">_DownloadLink_ 参数：显示或隐藏 Outlook 垃圾邮件报告工具的链接。</span><span class="sxs-lookup"><span data-stu-id="33a7f-431">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>
  - <span data-ttu-id="33a7f-432">_EndUserSpamNotificationCustomSubject_ 参数：可用于自定义通知的主题行。</span><span class="sxs-lookup"><span data-stu-id="33a7f-432">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="33a7f-433">使用 PowerShell 创建反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-433">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="33a7f-434">在 PowerShell 中创建反垃圾邮件策略的过程分为两步：</span><span class="sxs-lookup"><span data-stu-id="33a7f-434">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="33a7f-435">创建垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-435">Create the spam filter policy.</span></span>
2. <span data-ttu-id="33a7f-436">创建垃圾邮件筛选规则，它指定了向哪个垃圾邮件筛选策略应用规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-436">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="33a7f-437">**注意**：</span><span class="sxs-lookup"><span data-stu-id="33a7f-437">**Notes**:</span></span>

- <span data-ttu-id="33a7f-438">可以新建垃圾邮件筛选规则，并向它分配未关联的现有垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-438">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="33a7f-439">垃圾邮件筛选规则不能与多个垃圾邮件筛选策略关联。</span><span class="sxs-lookup"><span data-stu-id="33a7f-439">A spam filter rule can't be associated with more than one spam filter policy.</span></span>
- <span data-ttu-id="33a7f-440">可以在 PowerShell 中对新垃圾邮件筛选策略配置以下设置（在 Microsoft 365 Defender 门户中，只有在创建策略后，才能配置这些设置）：</span><span class="sxs-lookup"><span data-stu-id="33a7f-440">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="33a7f-441">新建禁用的策略（在 **New-HostedContentFilterRule** cmdlet 上 _Enabled_ 为 `$false`）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-441">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="33a7f-442">在创建过程中，在 **New-HostedContentFilterRule** cmdlet 上设置策略优先级（_优先级_ _\<Number\>_）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-442">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="33a7f-443">在 PowerShell 中新建的垃圾邮件筛选策略在 Microsoft 365 Defender 门户内不可见，除非你将策略分配到垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-443">A new spam filter policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="33a7f-444">第 1 步：使用 PowerShell 创建垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-444">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="33a7f-445">若要创建垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-445">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="33a7f-446">下面的示例使用以下设置创建名为“Contoso Executives”的垃圾邮件筛选策略：</span><span class="sxs-lookup"><span data-stu-id="33a7f-446">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="33a7f-447">当垃圾邮件筛选裁定为“垃圾邮件”或“高可信度垃圾邮件”时隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="33a7f-447">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>
- <span data-ttu-id="33a7f-448">BCL 7、8 或 9 触发群发电子邮件垃圾邮件筛选裁定对应的操作。</span><span class="sxs-lookup"><span data-stu-id="33a7f-448">BCL 7, 8, or 9 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

<span data-ttu-id="33a7f-449">若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-449">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="33a7f-450">第 2 步：使用 PowerShell 创建垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="33a7f-450">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="33a7f-451">若要创建垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-451">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="33a7f-452">下面的示例使用以下设置新建名为“Contoso Executives”的垃圾邮件筛选规则：</span><span class="sxs-lookup"><span data-stu-id="33a7f-452">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="33a7f-453">名为“Contoso Executives”的垃圾邮件筛选策略与此规则关联。</span><span class="sxs-lookup"><span data-stu-id="33a7f-453">The spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="33a7f-454">此规则应用于“Contoso Executives Group”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="33a7f-454">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="33a7f-455">若要详细了解语法和参数，请参阅 [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-455">For detailed syntax and parameter information, see [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="33a7f-456">使用 PowerShell 查看垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-456">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="33a7f-457">若要返回所有垃圾邮件筛选策略的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33a7f-457">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="33a7f-458">若要返回特定垃圾邮件筛选策略的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-458">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="33a7f-459">下面的示例返回名为“Executives”的垃圾邮件筛选策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-459">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="33a7f-460">若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-460">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="33a7f-461">使用 PowerShell 查看垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="33a7f-461">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="33a7f-462">若要查看现有垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-462">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="33a7f-463">若要返回所有垃圾邮件筛选规则的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33a7f-463">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="33a7f-464">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33a7f-464">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="33a7f-465">若要返回特定垃圾邮件筛选规则的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-465">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="33a7f-466">下面的示例返回名为“Contoso Executives”的垃圾邮件筛选规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="33a7f-466">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="33a7f-467">若要详细了解语法和参数，请参阅 [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-467">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="33a7f-468">使用 PowerShell 修改垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-468">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="33a7f-469">除了以下几项之外，在 PowerShell 中修改垃圾邮件筛选策略时可用的设置，与本文前面的[第 1 步：使用 PowerShell 创建垃圾邮件筛选策略](#step-1-use-powershell-to-create-a-spam-filter-policy)部分中介绍的可用于创建策略的设置相同。</span><span class="sxs-lookup"><span data-stu-id="33a7f-469">Other than the following items, the same settings are available when you modify a spam filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this article.</span></span>

- <span data-ttu-id="33a7f-470">只有在 PowerShell 中修改垃圾邮件筛选策略时，才能使用 _MakeDefault_ 开关，它可将指定策略转换为默认策略（应用于所有人，优先级值始终为 **“最低”**，且无法删除）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-470">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>
- <span data-ttu-id="33a7f-471">无法重命名垃圾邮件筛选策略（**Set-HostedContentFilterPolicy** cmdlet 没有 _Name_ 参数）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-471">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="33a7f-472">在 Microsoft 365 Defender 门户中重命名反垃圾邮件策略时，只是在重命名垃圾邮件筛选 _规则_。</span><span class="sxs-lookup"><span data-stu-id="33a7f-472">When you rename an anti-spam policy in the Microsoft 365 Defender portal, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="33a7f-473">若要修改垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-473">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="33a7f-474">若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-474">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="33a7f-475">使用 PowerShell 修改垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="33a7f-475">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="33a7f-476">在 PowerShell 中修改垃圾邮件筛选规则时，唯一不可用的设置是，可用于创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="33a7f-476">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="33a7f-477">若要启用或禁用现有垃圾邮件筛选规则，请参阅下一部分。</span><span class="sxs-lookup"><span data-stu-id="33a7f-477">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="33a7f-478">否则，在 PowerShell 中修改垃圾邮件筛选规则时，将无法使用其他任何设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-478">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="33a7f-479">创建规则时可用的设置与本文前面的[第 2 步：使用 PowerShell 创建垃圾邮件筛选规则](#step-2-use-powershell-to-create-a-spam-filter-rule)部分中介绍的设置相同。</span><span class="sxs-lookup"><span data-stu-id="33a7f-479">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="33a7f-480">若要修改垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-480">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="33a7f-481">此示例重命名名为 `{Fabrikam Spam Filter}` 的现有垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-481">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}`.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="33a7f-482">若要详细了解语法和参数，请参阅 [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-482">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="33a7f-483">使用 PowerShell 启用或禁用垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="33a7f-483">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="33a7f-484">在 PowerShell 中启用或禁用垃圾邮件筛选规则会启用或禁用整个反垃圾邮件策略（即垃圾邮件筛选规则和分配的垃圾邮件筛选策略）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-484">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="33a7f-485">无法启用或禁用默认反垃圾邮件策略（它始终应用于所有收件人）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-485">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="33a7f-486">若要在 PowerShell 中启用或禁用垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-486">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="33a7f-487">下面的示例禁用名为“Marketing Department”的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-487">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="33a7f-488">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-488">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="33a7f-489">若要详细了解语法和参数，请参阅 [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-489">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="33a7f-490">使用 PowerShell 设置垃圾邮件筛选规则的优先级</span><span class="sxs-lookup"><span data-stu-id="33a7f-490">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="33a7f-p160">可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。</span><span class="sxs-lookup"><span data-stu-id="33a7f-p160">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="33a7f-496">若要在 PowerShell 中设置垃圾邮件筛选规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-496">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="33a7f-p161">此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。</span><span class="sxs-lookup"><span data-stu-id="33a7f-p161">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="33a7f-499">**注意**：</span><span class="sxs-lookup"><span data-stu-id="33a7f-499">**Notes**:</span></span>

- <span data-ttu-id="33a7f-500">若要在新建规则时设置它的优先级，请改为对 **New-HostedContentFilterRule** cmdlet 使用 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="33a7f-500">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="33a7f-501">默认垃圾邮件筛选策略没有相应的垃圾邮件筛选规则，且始终有不可修改的优先级值 **“最低”**。</span><span class="sxs-lookup"><span data-stu-id="33a7f-501">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="33a7f-502">使用 PowerShell 删除垃圾邮件筛选策略</span><span class="sxs-lookup"><span data-stu-id="33a7f-502">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="33a7f-503">如果使用 PowerShell 删除垃圾邮件筛选策略，不会删除相应的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-503">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="33a7f-504">若要在 PowerShell 中删除垃圾邮件筛选策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-504">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="33a7f-505">下面的示例删除名为“Marketing Department”的垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-505">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="33a7f-506">若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-506">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="33a7f-507">使用 PowerShell 删除垃圾邮件筛选规则</span><span class="sxs-lookup"><span data-stu-id="33a7f-507">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="33a7f-508">使用 PowerShell 删除垃圾邮件筛选规则时，不会删除相应的垃圾邮件筛选策略。</span><span class="sxs-lookup"><span data-stu-id="33a7f-508">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="33a7f-509">若要在 PowerShell 中删除垃圾邮件筛选规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="33a7f-509">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="33a7f-510">下面的示例删除名为“Marketing Department”的垃圾邮件筛选规则。</span><span class="sxs-lookup"><span data-stu-id="33a7f-510">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="33a7f-511">若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="33a7f-511">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="33a7f-512">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="33a7f-512">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="33a7f-513">发送 GTUBE 邮件测试垃圾邮件策略设置</span><span class="sxs-lookup"><span data-stu-id="33a7f-513">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="33a7f-p162">只有当你从中发送 GTUBE 邮件的电子邮件组织不扫描出站垃圾邮件时，才能执行这些步骤。如果不是，则无法发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="33a7f-p162">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam. If it does, you can't send the test message.</span></span>

<span data-ttu-id="33a7f-516">垃圾群发电子邮件的一般测试 (GTUBE) 是文本字符串，可以添加到测试邮件中，用于验证组织的反垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="33a7f-516">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="33a7f-517">GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。</span><span class="sxs-lookup"><span data-stu-id="33a7f-517">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="33a7f-518">在电子邮件中的某一行上，添加以下 GTUBE 文本，不得有任何空格或换行符：</span><span class="sxs-lookup"><span data-stu-id="33a7f-518">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
