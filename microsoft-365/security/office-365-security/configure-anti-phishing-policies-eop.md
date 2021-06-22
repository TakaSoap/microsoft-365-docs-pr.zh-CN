---
title: 在 EOP 中配置反网络钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建、修改和删除 Exchange Online Protection (EOP) 组织中可用的反网络钓鱼策略，Exchange Online邮箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dcfba32a5c76915c8c905d55b69712162efac48
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062224"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="3efeb-103">在 EOP 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3efeb-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="3efeb-104">**Applies to**</span></span>
- [<span data-ttu-id="3efeb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3efeb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="3efeb-106">在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，则有一个默认的反网络钓鱼策略，其中包含有限数量的默认情况下启用的反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="3efeb-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="3efeb-107">有关详细信息，请参阅[反钓鱼策略中的“欺骗”设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="3efeb-108">管理员可以查看、编辑和配置 (，但不能) 默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="3efeb-109">更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3efeb-110">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3efeb-111">拥有Exchange Online的组织可以在 Microsoft 365 Defender 门户或 PowerShell 中Exchange Online防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="3efeb-112">独立 EOP 组织只能使用Microsoft 365 Defender门户。</span><span class="sxs-lookup"><span data-stu-id="3efeb-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="3efeb-113">有关创建和修改 Microsoft Defender for Office 365 中提供的更高级反网络钓鱼策略的信息，请参阅在 Microsoft [Defender](configure-mdo-anti-phishing-policies.md)中为 Office 365 配置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

<span data-ttu-id="3efeb-114">防钓鱼策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="3efeb-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="3efeb-115">**防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="3efeb-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="3efeb-116">**防钓鱼** 规则 ：指定策略应用于 (策略的收件人筛选器) 策略的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="3efeb-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="3efeb-117">当你在安全门户中管理防钓鱼策略时，这两个元素Microsoft 365 Defender明显：</span><span class="sxs-lookup"><span data-stu-id="3efeb-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="3efeb-118">创建防钓鱼策略时，实际上是同时使用同一名称创建反网络钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="3efeb-119">修改防钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="3efeb-120">所有其他设置修改关联的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="3efeb-121">删除防钓鱼策略时，会删除防钓鱼规则及相关的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="3efeb-122">在 Exchange Online PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="3efeb-123">有关详细信息，请参阅本文Exchange Online[使用 PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)配置防钓鱼策略一节。</span><span class="sxs-lookup"><span data-stu-id="3efeb-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="3efeb-124">每个组织都有一个名为 Office365 AntiPhish Default 的内置防钓鱼策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="3efeb-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="3efeb-125">即使与策略关联的收件人筛选器没有反网络钓鱼规则， (应用于组织) 所有收件人。</span><span class="sxs-lookup"><span data-stu-id="3efeb-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="3efeb-126">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3efeb-127">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="3efeb-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="3efeb-128">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3efeb-129">若要提高防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3efeb-130">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="3efeb-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3efeb-131">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="3efeb-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="3efeb-132">若要直接转到" **防钓鱼"页面** ，请使用 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="3efeb-133">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="3efeb-134">你无法管理独立 EOP PowerShell 中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="3efeb-135">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="3efeb-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3efeb-136">若要添加、修改和删除防钓鱼策略，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="3efeb-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3efeb-137">若要对防钓鱼策略进行只读访问，你需要是全局读者或 **安全读者角色\*\*\*\*组的成员**。</span><span class="sxs-lookup"><span data-stu-id="3efeb-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3efeb-138">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="3efeb-139">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3efeb-139">**Notes**:</span></span>

  - <span data-ttu-id="3efeb-140">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="3efeb-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3efeb-141">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="3efeb-142">此 **策略中的**"仅查看组织管理"角色 [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)还授予对该功能的只读访问权限 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="3efeb-143">有关建议的反网络钓鱼策略设置，请参阅 [EOP 防钓鱼策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="3efeb-144">最多允许应用更新的策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="3efeb-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="3efeb-145">有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="3efeb-146">使用Microsoft 365 Defender门户创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="3efeb-147">在 Microsoft 365 Defender 门户中创建自定义防钓鱼策略可同时使用同一名称创建反网络钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="3efeb-148">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3efeb-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3efeb-149">在"**防钓鱼"页面上**，单击" ![ 创建"图标" ](../../media/m365-cc-sc-create-icon.png) **创建"。**</span><span class="sxs-lookup"><span data-stu-id="3efeb-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="3efeb-150">将打开策略向导。</span><span class="sxs-lookup"><span data-stu-id="3efeb-150">The policy wizard opens.</span></span> <span data-ttu-id="3efeb-151">在" **策略名称"** 页上，配置这些设置：</span><span class="sxs-lookup"><span data-stu-id="3efeb-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="3efeb-152">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="3efeb-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="3efeb-153">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="3efeb-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="3efeb-154">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3efeb-155">在出现的“**用户、组和域**”页面上，标识策略应用于的内部收件人（收件人条件）：</span><span class="sxs-lookup"><span data-stu-id="3efeb-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="3efeb-156">**用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="3efeb-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="3efeb-157">**组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3efeb-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="3efeb-158">**域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="3efeb-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="3efeb-159">单击相应的框，开始键入值，然后从结果中选择所需的值。</span><span class="sxs-lookup"><span data-stu-id="3efeb-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="3efeb-160">根据需要多次重复此过程。</span><span class="sxs-lookup"><span data-stu-id="3efeb-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="3efeb-161">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="3efeb-161">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="3efeb-163">“删除”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-163">next to the value.</span></span>

   <span data-ttu-id="3efeb-164">对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="3efeb-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="3efeb-165">对于用户，请自行输入星号 (\*) 以查看所有可用值。</span><span class="sxs-lookup"><span data-stu-id="3efeb-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="3efeb-166">同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3efeb-167">不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="3efeb-168">**排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。</span><span class="sxs-lookup"><span data-stu-id="3efeb-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="3efeb-169">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="3efeb-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3efeb-170">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3efeb-171">在出现的 **"网络钓鱼&** 保护"页上，使用"启用欺骗智能"复选框打开或关闭欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="3efeb-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="3efeb-172">默认值位于选定 (上) ，建议保留其打开状态。</span><span class="sxs-lookup"><span data-stu-id="3efeb-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="3efeb-173">您可以在下一页上将操作配置为对阻止的欺骗邮件执行。</span><span class="sxs-lookup"><span data-stu-id="3efeb-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="3efeb-174">若要关闭欺骗智能，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="3efeb-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3efeb-175">如果你的 MX 记录没有指向反欺骗保护，则无需关闭Microsoft 365;改为启用连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="3efeb-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="3efeb-176">有关说明，请参阅[增强的连接器筛选Exchange Online。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="3efeb-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="3efeb-177">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="3efeb-178">在出现的“**操作**”页面上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="3efeb-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="3efeb-179">**如果邮件被检测为欺骗邮件**：只有在上一页上选择了" **启用** 欺骗智能"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="3efeb-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="3efeb-180">在下拉列表中为来自阻止的欺骗性发件人的邮件选择以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="3efeb-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="3efeb-181">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="3efeb-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="3efeb-182">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="3efeb-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="3efeb-183">**安全提示&指示器**：</span><span class="sxs-lookup"><span data-stu-id="3efeb-183">**Safety tips & indicators**:</span></span>
     - <span data-ttu-id="3efeb-184">**显示第一安全提示** 联系人：有关详细信息，请参阅第一个 [联系人安全提示。](set-up-anti-phishing-policies.md#first-contact-safety-tip)</span><span class="sxs-lookup"><span data-stu-id="3efeb-184">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="3efeb-185">**为欺骗** 的未经身份验证的发件人显示 (？) ：如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 <sup>\*</sup> DMARC或复合身份验证，则向 Outlook 的发件人照片框中添加问号。 [](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="3efeb-185">**Show (?) for unauthenticated senders for spoof**<sup>\*</sup>: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="3efeb-186">**显示"via"标记**：如果通过 (chris@contoso.com 通过 fabrikam.com) 将 via 标记添加到"收件人"地址（如果它不同于 DKIM 签名或 <sup>\*</sup> MAIL **FROM** 地址中的域）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-186">**Show "via" tag**<sup>\*</sup>: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

     <span data-ttu-id="3efeb-187">若要打开某个设置，请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="3efeb-187">To turn on a setting, select the check box.</span></span> <span data-ttu-id="3efeb-188">若要将其关闭，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="3efeb-188">To turn it off, clear the check box.</span></span>

     <span data-ttu-id="3efeb-189"><sup>\*</sup> 只有在上一页上选择了" **启用** 欺骗智能"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="3efeb-189"><sup>\*</sup> This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="3efeb-190">有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-190">For more information, see [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).</span></span>

   <span data-ttu-id="3efeb-191">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-191">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="3efeb-192">在出现的“**审阅**”页面上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="3efeb-192">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="3efeb-193">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="3efeb-193">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="3efeb-194">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="3efeb-194">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="3efeb-195">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="3efeb-195">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="3efeb-196">在出现的确认页面上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-196">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="3efeb-197">使用Microsoft 365 Defender门户查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-197">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="3efeb-198">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3efeb-198">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3efeb-199">在 **"防钓鱼"** 页上，策略列表中将显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="3efeb-199">On the **Anti-phishing** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="3efeb-200">**名称**</span><span class="sxs-lookup"><span data-stu-id="3efeb-200">**Name**</span></span>
   - <span data-ttu-id="3efeb-201">**状态**</span><span class="sxs-lookup"><span data-stu-id="3efeb-201">**Status**</span></span>
   - <span data-ttu-id="3efeb-202">**优先级**</span><span class="sxs-lookup"><span data-stu-id="3efeb-202">**Priority**</span></span>
   - <span data-ttu-id="3efeb-203">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="3efeb-203">**Last modified**</span></span>

3. <span data-ttu-id="3efeb-204">当您通过单击该名称选择策略时，策略设置将显示在一个飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="3efeb-204">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="3efeb-205">使用Microsoft 365 Defender门户修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-205">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="3efeb-206">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3efeb-206">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3efeb-207">在 **"防钓鱼"** 页上，通过单击名称从列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-207">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3efeb-208">在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="3efeb-208">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="3efeb-209">有关设置详细信息，请参阅本文前面使用 Microsoft 365 Defender 门户创建[防](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)钓鱼策略一节。</span><span class="sxs-lookup"><span data-stu-id="3efeb-209">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="3efeb-210">对于默认的防钓鱼策略，"用户、组和域"部分不可用 (该策略适用于所有用户) ，并且无法重命名该策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-210">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="3efeb-211">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="3efeb-211">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="3efeb-212">启用或禁用自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-212">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="3efeb-213">无法禁用默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-213">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="3efeb-214">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3efeb-214">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3efeb-215">在 **"防钓鱼"** 页上，通过单击名称从列表中选择自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-215">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3efeb-216">在出现的策略详细信息浮出控件顶部，你将看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="3efeb-216">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="3efeb-217">**策略关闭**：若要打开策略，请单击![“打开”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-217">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="3efeb-218">**策略打开**：若要关闭策略，请单击![“关闭”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-218">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="3efeb-219">在出现的确认对话框中，单击“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-219">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="3efeb-220">单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-220">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="3efeb-221">返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-221">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="3efeb-222">设置自定义防钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="3efeb-222">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="3efeb-223">默认情况下，基于反网络钓鱼策略在 (较旧策略中创建的顺序，反网络钓鱼策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-223">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3efeb-224">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-224">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3efeb-225">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="3efeb-225">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="3efeb-226">若要更改策略的优先级，请单击策略属性中的“**提高优先级**”或“**降低优先级**”（不能直接修改 Microsoft 365 Defender 门户中的“**优先级**”数字）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-226">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="3efeb-227">只有当你有多个策略时，更改策略的优先级才有意义。</span><span class="sxs-lookup"><span data-stu-id="3efeb-227">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="3efeb-228">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3efeb-228">**Notes**:</span></span>

- <span data-ttu-id="3efeb-229">在Microsoft 365 Defender门户中，只能在创建反网络钓鱼策略后更改其优先级。</span><span class="sxs-lookup"><span data-stu-id="3efeb-229">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="3efeb-230">在 PowerShell 中，您可以在创建反网络钓鱼规则策略时替代默认优先级 (这可能会影响现有规则集的) 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-230">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="3efeb-231">反网络钓鱼策略按照其显示顺序进行处理， (策略的优先级值为 0 时) 。 </span><span class="sxs-lookup"><span data-stu-id="3efeb-231">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3efeb-232">默认防钓鱼策略的优先级值为 **"** 最低"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="3efeb-232">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="3efeb-233">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3efeb-233">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3efeb-234">在 **"防钓鱼"** 页上，通过单击名称从列表中选择自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-234">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3efeb-235">在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：</span><span class="sxs-lookup"><span data-stu-id="3efeb-235">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="3efeb-236">优先级值为 **0** **的策略** 只有"**减少优先级"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="3efeb-236">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="3efeb-237">优先级值最低的策略 (例如 **，3**) 只有"增加优先级 **"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="3efeb-237">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="3efeb-238">如果你有三个或多个策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 选项。</span><span class="sxs-lookup"><span data-stu-id="3efeb-238">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="3efeb-239">单击![“提高优先级”图标](../../media/m365-cc-sc-increase-icon.png)“**提高优先级**”或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png)“**降低优先级**”以更改“**优先级**”值。</span><span class="sxs-lookup"><span data-stu-id="3efeb-239">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="3efeb-240">完成后，单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-240">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="3efeb-241">使用Microsoft 365 Defender门户删除自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-241">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="3efeb-242">当你使用 Microsoft 365 Defender 门户删除自定义防钓鱼策略时，防钓鱼规则及相应的防钓鱼策略都将被删除。</span><span class="sxs-lookup"><span data-stu-id="3efeb-242">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="3efeb-243">无法删除默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-243">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="3efeb-244">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3efeb-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3efeb-245">在 **"防钓鱼"** 页上，通过单击名称从列表中选择自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-245">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3efeb-246">在出现的策略详细信息浮出控件顶部，单击![“更多操作”图标](../../media/m365-cc-sc-more-actions-icon.png)“**更多操作**”\> ![“删除策略”图标](../../media/m365-cc-sc-delete-icon.png)“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="3efeb-247">在出现的确认对话框中，单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="3efeb-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="3efeb-248">使用 Exchange Online PowerShell 配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-248">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="3efeb-249">如前所述，防钓鱼策略由防钓鱼策略和防钓鱼规则组成。</span><span class="sxs-lookup"><span data-stu-id="3efeb-249">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="3efeb-250">在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="3efeb-250">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="3efeb-251">您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-251">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="3efeb-252">在 PowerShell 中，首先创建防钓鱼策略，然后创建标识该规则所适用的策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-252">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="3efeb-253">在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="3efeb-253">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="3efeb-254">从 PowerShell 删除防钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="3efeb-254">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="3efeb-255">以下 PowerShell 过程不适用于使用 PowerShell 的独立 EOP Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="3efeb-255">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="3efeb-256">使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-256">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="3efeb-257">在 PowerShell 中创建防钓鱼策略的过程包括两个步骤：</span><span class="sxs-lookup"><span data-stu-id="3efeb-257">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3efeb-258">创建防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-258">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="3efeb-259">创建指定该规则所适用的防钓鱼策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-259">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="3efeb-260">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3efeb-260">**Notes**:</span></span>

- <span data-ttu-id="3efeb-261">你可以创建新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-261">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="3efeb-262">反网络钓鱼规则不能与多个防钓鱼策略关联。</span><span class="sxs-lookup"><span data-stu-id="3efeb-262">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="3efeb-263">可以在 PowerShell 中对新的防钓鱼策略配置以下设置，这些设置在 Microsoft 365 Defender 门户中不可用，除非创建策略：</span><span class="sxs-lookup"><span data-stu-id="3efeb-263">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id="3efeb-264">在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-264">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="3efeb-265">在 _\<Number\>_ **New-AntiPhishRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-265">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="3efeb-266">在 PowerShell 中新建的防钓鱼策略在 Microsoft 365 Defender门户中不可见，除非将策略分配给防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-266">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="3efeb-267">步骤 1：使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-267">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="3efeb-268">若要创建防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-268">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="3efeb-269">本示例将创建一个名为"Research Quarantine"的防钓鱼策略，并具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="3efeb-269">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="3efeb-270">描述为：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-270">The description is: Research department policy.</span></span>
- <span data-ttu-id="3efeb-271">将欺骗的默认操作更改为隔离。</span><span class="sxs-lookup"><span data-stu-id="3efeb-271">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="3efeb-272">有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-272">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="3efeb-273">步骤 2：使用 PowerShell 创建防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="3efeb-273">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="3efeb-274">若要创建防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-274">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3efeb-275">本示例创建一个名为"Research Department"的防钓鱼规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="3efeb-275">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="3efeb-276">该规则与名为"研究隔离"的防钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="3efeb-276">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="3efeb-277">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="3efeb-277">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="3efeb-278">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="3efeb-278">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="3efeb-279">有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-279">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="3efeb-280">使用 PowerShell 查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-280">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="3efeb-281">若要查看现有的防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-281">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3efeb-282">此示例返回所有防钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="3efeb-282">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="3efeb-283">此示例返回名为 Executives 的反网络钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="3efeb-283">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="3efeb-284">有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-284">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="3efeb-285">使用 PowerShell 查看防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="3efeb-285">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="3efeb-286">若要查看现有的防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-286">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3efeb-287">此示例返回所有防钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="3efeb-287">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="3efeb-288">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3efeb-288">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="3efeb-289">此示例返回名为 Contoso Executives 的防钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="3efeb-289">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="3efeb-290">有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-290">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="3efeb-291">使用 PowerShell 修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-291">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="3efeb-292">除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建防钓鱼策略中所述。</span><span class="sxs-lookup"><span data-stu-id="3efeb-292">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="3efeb-293">_MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终最低，并且只有修改 PowerShell 中的防钓鱼策略时) 才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="3efeb-293">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="3efeb-294">如果 **Set-AntiPhishPolicy** cmdlet 没有 Name 参数 (，则不能重命名反网络钓鱼) 。 </span><span class="sxs-lookup"><span data-stu-id="3efeb-294">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3efeb-295">在 Web 门户中重命名防钓鱼Microsoft 365 Defender，只需重命名防钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="3efeb-295">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="3efeb-296">要修改防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-296">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3efeb-297">有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-297">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="3efeb-298">使用 PowerShell 修改防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="3efeb-298">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="3efeb-299">在 PowerShell 中修改防钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="3efeb-299">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3efeb-300">若要启用或禁用现有防钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="3efeb-300">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="3efeb-301">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="3efeb-301">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="3efeb-302">要修改防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-302">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3efeb-303">有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-303">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="3efeb-304">使用 PowerShell 启用或禁用防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="3efeb-304">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="3efeb-305">在 PowerShell 中启用或禁用反网络钓鱼规则可启用或禁用整个防钓鱼策略 (以及分配的防钓鱼策略策略) 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-305">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="3efeb-306">无法启用或禁用默认反网络钓鱼策略 (该策略始终应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="3efeb-306">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="3efeb-307">若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-307">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="3efeb-308">本示例禁用名为"Marketing Department"的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-308">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3efeb-309">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-309">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3efeb-310">有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="3efeb-310">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="3efeb-311">使用 PowerShell 设置防钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="3efeb-311">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="3efeb-p131">可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。</span><span class="sxs-lookup"><span data-stu-id="3efeb-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3efeb-317">若要在 PowerShell 中设置防钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-317">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3efeb-p132">此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。</span><span class="sxs-lookup"><span data-stu-id="3efeb-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3efeb-320">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3efeb-320">**Notes**:</span></span>

- <span data-ttu-id="3efeb-321">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-AntiPhishRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="3efeb-321">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="3efeb-322">默认防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="3efeb-322">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="3efeb-323">使用 PowerShell 删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3efeb-323">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="3efeb-324">使用 PowerShell 删除防钓鱼策略时，不会删除相应的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-324">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="3efeb-325">若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-325">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3efeb-326">此示例删除名为 Marketing Department 的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-326">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3efeb-327">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-327">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="3efeb-328">使用 PowerShell 删除防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="3efeb-328">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="3efeb-329">使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3efeb-329">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="3efeb-330">若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3efeb-330">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="3efeb-331">此示例删除名为 Marketing Department 的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="3efeb-331">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3efeb-332">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="3efeb-332">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3efeb-333">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="3efeb-333">How do you know these procedures worked?</span></span>

<span data-ttu-id="3efeb-334">若要验证您是否已成功在 EOP 中配置防钓鱼策略，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="3efeb-334">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="3efeb-335">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3efeb-335">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="3efeb-336">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="3efeb-336">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="3efeb-337">若要查看更多详细信息，请从列表中选择策略，方法是单击名称并查看出现的飞出内容中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3efeb-337">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="3efeb-338">在 Exchange Online PowerShell 中，将 替换为策略或规则的名称，运行 \<Name\> 以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="3efeb-338">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
