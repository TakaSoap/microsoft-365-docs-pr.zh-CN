---
title: 在 Microsoft Defender for Office 365
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
description: 管理员可以了解如何创建、修改和删除 Microsoft Defender for Office 365 组织提供的高级防钓鱼Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd69e00b0e8929752341bf3d2b0abde88921066b
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061889"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4423e-103">在 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4423e-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4423e-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4423e-104">**Applies to**</span></span>
- [<span data-ttu-id="4423e-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4423e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4423e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4423e-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4423e-107">Microsoft Defender for [Office 365](defender-for-office-365.md)中的反网络钓鱼策略可帮助保护组织免受基于恶意模拟的网络钓鱼攻击和其他类型的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="4423e-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="4423e-108">有关 Exchange Online Protection (EOP) 中的反网络钓鱼策略与 Microsoft Defender for Office 365 中的防钓鱼策略之间的差异，请参阅反网络钓鱼[防护](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4423e-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="4423e-109">管理员可以查看、编辑和配置 (，但不能) 默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="4423e-110">更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="4423e-111">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="4423e-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="4423e-112">可以在 Defender 中配置反网络钓鱼策略，Office 365在 Microsoft 365 Defender 门户或 Exchange Online PowerShell 中配置。</span><span class="sxs-lookup"><span data-stu-id="4423e-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="4423e-113">有关在 Exchange Online Protection (中可用的反网络钓鱼策略（即没有 Defender for Office 365) 的组织）中配置更多限制的信息，请参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="4423e-114">防钓鱼策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="4423e-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="4423e-115">**防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="4423e-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="4423e-116">**防钓鱼** 规则 ：指定策略应用于 (策略的收件人筛选器) 策略的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="4423e-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="4423e-117">当你在安全门户中管理防钓鱼策略时，这两个元素Microsoft 365 Defender明显：</span><span class="sxs-lookup"><span data-stu-id="4423e-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="4423e-118">创建策略时，实际上是同时使用同一名称创建防钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="4423e-119">修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="4423e-120">所有其他设置修改关联的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="4423e-121">删除策略时，将删除防钓鱼规则和相关反钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="4423e-122">在 Exchange Online PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="4423e-123">有关详细信息，请参阅本文Exchange Online[使用 PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)配置防钓鱼策略一节。</span><span class="sxs-lookup"><span data-stu-id="4423e-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="4423e-124">每个 Defender for Office 365 组织都有一个名为 Office365 AntiPhish Default 的内置防钓鱼策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="4423e-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="4423e-125">即使与策略关联的收件人筛选器没有反网络钓鱼规则， (应用于组织) 所有收件人。</span><span class="sxs-lookup"><span data-stu-id="4423e-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="4423e-126">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="4423e-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="4423e-127">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="4423e-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="4423e-128">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="4423e-129">若要提高 Office 365 的 Defender 中的防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4423e-130">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="4423e-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4423e-131">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="4423e-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="4423e-132">若要直接转到" **防钓鱼"页面** ，请使用 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="4423e-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="4423e-133">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4423e-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4423e-134">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="4423e-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4423e-135">若要添加、修改和删除防钓鱼策略，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="4423e-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4423e-136">若要对防钓鱼策略进行只读访问，你需要是全局读者或 **安全读者角色\*\*\*\*组的成员** <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="4423e-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="4423e-137">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="4423e-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="4423e-138">**注意**：</span><span class="sxs-lookup"><span data-stu-id="4423e-138">**Notes**:</span></span>

  - <span data-ttu-id="4423e-139">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="4423e-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4423e-140">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4423e-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="4423e-141">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="4423e-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="4423e-142">有关 Defender for Office 365 中的反网络钓鱼策略建议设置，请参阅 Defender 中的反网络钓鱼策略，了解Office 365[设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="4423e-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="4423e-143">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="4423e-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="4423e-144">有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="4423e-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="4423e-145">使用Microsoft 365 Defender门户创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="4423e-146">在 Microsoft 365 Defender 门户中创建自定义防钓鱼策略可同时使用同一名称创建反网络钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="4423e-147">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4423e-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="4423e-148">在"**防钓鱼"页面上**，单击" ![ 创建"图标" ](../../media/m365-cc-sc-create-icon.png) **创建"。**</span><span class="sxs-lookup"><span data-stu-id="4423e-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="4423e-149">将打开策略向导。</span><span class="sxs-lookup"><span data-stu-id="4423e-149">The policy wizard opens.</span></span> <span data-ttu-id="4423e-150">在" **策略名称"** 页上，配置这些设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="4423e-151">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4423e-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="4423e-152">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="4423e-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="4423e-153">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4423e-154">在出现的“**用户、组和域**”页面上，标识策略应用于的内部收件人（收件人条件）：</span><span class="sxs-lookup"><span data-stu-id="4423e-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="4423e-155">**用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="4423e-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="4423e-156">**组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="4423e-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="4423e-157">**域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="4423e-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="4423e-158">单击相应的框，开始键入值，然后从结果中选择所需的值。</span><span class="sxs-lookup"><span data-stu-id="4423e-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="4423e-159">根据需要多次重复此过程。</span><span class="sxs-lookup"><span data-stu-id="4423e-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="4423e-160">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="4423e-160">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="4423e-162">“删除”。</span><span class="sxs-lookup"><span data-stu-id="4423e-162">next to the value.</span></span>

   <span data-ttu-id="4423e-163">对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="4423e-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="4423e-164">对于用户，请自行输入星号 (\*) 以查看所有可用值。</span><span class="sxs-lookup"><span data-stu-id="4423e-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="4423e-165">同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="4423e-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="4423e-166">不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="4423e-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="4423e-167">**排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。</span><span class="sxs-lookup"><span data-stu-id="4423e-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="4423e-168">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="4423e-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="4423e-169">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4423e-170">在出现的 **"网络钓鱼&** 保护"页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="4423e-171">**网络钓鱼电子邮件阈值**：使用滑块选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="4423e-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="4423e-172">**1 - 标准** (此值为默认值。) </span><span class="sxs-lookup"><span data-stu-id="4423e-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="4423e-173">**2 - 主动**</span><span class="sxs-lookup"><span data-stu-id="4423e-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="4423e-174">**3 - 更主动**</span><span class="sxs-lookup"><span data-stu-id="4423e-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="4423e-175">**4 - 最积极**</span><span class="sxs-lookup"><span data-stu-id="4423e-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="4423e-176">有关详细信息，请参阅 Microsoft Defender for Office 365 中的反网络钓鱼策略[中的高级网络钓鱼Office 365。](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="4423e-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="4423e-177">**模拟**：这些设置是策略的一个条件，用于标识特定发件人，以单独 (或按域) 在入站邮件的发件人地址中查找邮件。</span><span class="sxs-lookup"><span data-stu-id="4423e-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="4423e-178">有关详细信息，请参阅 Microsoft Defender for Office 365 中的防钓鱼[策略中的模拟Office 365。](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="4423e-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="4423e-179">在每个防钓鱼策略中，最多可指定 60 个受保护 (发件人电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="4423e-180">不能在多个策略中指定同一受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="4423e-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="4423e-181">如果发件人和收件人之前通过电子邮件进行通信，则用户模拟保护不起作用。</span><span class="sxs-lookup"><span data-stu-id="4423e-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="4423e-182">如果发件人和收件人从未通过电子邮件进行通信，则邮件将被标识为模拟尝试。</span><span class="sxs-lookup"><span data-stu-id="4423e-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="4423e-183">**允许用户保护**：默认值为 off， (未) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="4423e-184">若要打开它，请选中该复选框，然后单击"管理 (**nn")  (显示**) "链接。</span><span class="sxs-lookup"><span data-stu-id="4423e-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="4423e-185">在 **出现的"管理发件人以执行模拟保护** "飞出中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4423e-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="4423e-186">**内部发件人：单击** ![ 添加内部图标 ](../../media/m365-cc-sc-add-internal-icon.png) **选择内部**。</span><span class="sxs-lookup"><span data-stu-id="4423e-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="4423e-187">In the **Add internal senders** flyout that appears， click in the box and select an internal user from the list.</span><span class="sxs-lookup"><span data-stu-id="4423e-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="4423e-188">可以通过键入用户，然后从结果中选择用户来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="4423e-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="4423e-189">您可以使用大部分标识符 (名称、显示名称、别名、电子邮件地址、帐户名等) ，但结果显示名称显示相应的标识符。</span><span class="sxs-lookup"><span data-stu-id="4423e-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="4423e-190">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="4423e-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4423e-191">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="4423e-191">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="4423e-193">“删除”。</span><span class="sxs-lookup"><span data-stu-id="4423e-193">next to the value.</span></span>

         <span data-ttu-id="4423e-194">完成后，单击"添加 **"**</span><span class="sxs-lookup"><span data-stu-id="4423e-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="4423e-195">**外部发件人：单击** ![ 添加外部图标 ](../../media/m365-cc-sc-create-icon.png) **选择外部**。</span><span class="sxs-lookup"><span data-stu-id="4423e-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="4423e-196">在出现的 **"添加外部** 发件人"飞出框中，在"添加名称"框中输入显示名称 和电子邮件地址，然后单击"添加 **"。** </span><span class="sxs-lookup"><span data-stu-id="4423e-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="4423e-197">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="4423e-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4423e-198">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="4423e-198">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="4423e-200">“删除”。</span><span class="sxs-lookup"><span data-stu-id="4423e-200">next to the value.</span></span>

         <span data-ttu-id="4423e-201">完成后，单击"添加 **"**</span><span class="sxs-lookup"><span data-stu-id="4423e-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="4423e-202">返回到" **管理发件人进行模拟"** 飞出，您可以通过从列表中选择一个或多个条目来删除条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="4423e-203">可以使用"搜索"图标"搜索 ![ "框 ](../../media/m365-cc-sc-create-icon.png) **搜索** 条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="4423e-204">至少选择一个条目后，将显示"删除所选用户"图标"删除所选用户"图标，您可以使用该图标删除 ![ ](../../media/m365-cc-sc-remove-selected-users-icon.png) 所选条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="4423e-205">完成后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="4423e-206">**启用域保护**：默认值为 off， (未) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="4423e-207">若要打开它，请选中该复选框，然后配置出现的以下一个或两个设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="4423e-208">**包括我拥有域**：若要打开此设置，请选中复选框。</span><span class="sxs-lookup"><span data-stu-id="4423e-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="4423e-209">若要查看您拥有的域，请单击"**查看我的域"。**</span><span class="sxs-lookup"><span data-stu-id="4423e-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="4423e-210">包括 **自定义域**：若要启用此设置，请选中该复选框，然后单击出现的"管理 (**nn**) 自定义 () 链接。</span><span class="sxs-lookup"><span data-stu-id="4423e-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="4423e-211">在出现的 **"管理用于模拟保护的** 自定义域"飞出控件中，单击" ![ 添加域"图标" ](../../media/m365-cc-sc-create-icon.png) **添加域"。**</span><span class="sxs-lookup"><span data-stu-id="4423e-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="4423e-212">在出现的 **"添加自定义** 域"飞出控件中，在"域"框中单击，输入值，然后按 Enter 或选择显示在该框下方的值。</span><span class="sxs-lookup"><span data-stu-id="4423e-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="4423e-213">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="4423e-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4423e-214">若要删除现有值，请单击值旁边的![“删除”图标](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="4423e-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="4423e-215">完成后，单击"添加 **域"**</span><span class="sxs-lookup"><span data-stu-id="4423e-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="4423e-216">在所有防钓鱼策略中最多可以有 50 个域。</span><span class="sxs-lookup"><span data-stu-id="4423e-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="4423e-217">返回到"管理用于模拟 **的自定义** 域"飞出控件，您可以通过从列表中选择一个或多个条目来删除条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="4423e-218">可以使用"搜索"图标"搜索 ![ "框 ](../../media/m365-cc-sc-create-icon.png) **搜索** 条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="4423e-219">选择至少一个条目后，将显示"删除域"图标"删除"图标，您可以使用该图标删除 ![ ](../../media/m365-cc-sc-delete-icon.png) 所选条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="4423e-220">添加 **受信任** 发件人和域：单击"管理 **(nn**) 受信任发件人" () 和域 () ，为策略指定模拟保护例外。</span><span class="sxs-lookup"><span data-stu-id="4423e-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="4423e-221">在 **出现的"管理用于模拟保护的** 自定义域"飞出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="4423e-222">**发件人：** 验证是否 **选择了"发件人** "选项卡，然后单击" ![ 添加发件人图标 ](../../media/m365-cc-sc-create-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="4423e-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="4423e-223">在出现的 **"添加受信任** 发件人"飞出框中，输入电子邮件地址，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="4423e-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="4423e-224">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="4423e-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4423e-225">若要删除现有条目，请单击 ![ 该条目 ](../../media/m365-cc-sc-close-icon.png) 的"删除图标"。</span><span class="sxs-lookup"><span data-stu-id="4423e-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="4423e-226">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="4423e-227">**域**：选择" **域"** 选项卡，然后单击 ![ "添加域图标 ](../../media/m365-cc-sc-create-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="4423e-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="4423e-228">在出现的 **"添加受信任的** 域"飞出框中，单击"域"框中，输入一个值，然后按 Enter 或选择显示在该框下方的值。</span><span class="sxs-lookup"><span data-stu-id="4423e-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="4423e-229">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="4423e-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4423e-230">若要删除现有值，请单击值旁边的![“删除”图标](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="4423e-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="4423e-231">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="4423e-232">返回到"管理用于模拟 **的** 自定义域"飞出控件，您可以通过从列表中选择一个或多个条目来从"发件人"和"域"选项卡中删除条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="4423e-233">可以使用"搜索"图标"搜索 ![ "框 ](../../media/m365-cc-sc-create-icon.png) **搜索** 条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="4423e-234">选择至少一个条目后，将显示"删除"图标，可用于删除所选条目。</span><span class="sxs-lookup"><span data-stu-id="4423e-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="4423e-235">完成后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="4423e-236">**启用邮箱智能**：默认值在选中 (时) ，建议保留它。</span><span class="sxs-lookup"><span data-stu-id="4423e-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="4423e-237">若要将其关闭，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="4423e-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="4423e-238">**启用基于智能的模拟** 保护：仅在选中"启用邮箱智能"时 (此设置) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="4423e-239">此设置允许邮箱智能对标识为模拟尝试的邮件采取措施。</span><span class="sxs-lookup"><span data-stu-id="4423e-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="4423e-240">您可以在下一页的"如果 **邮箱智能检测到模拟** 的用户"设置中指定要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4423e-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="4423e-241">建议通过选中复选框来打开此设置。</span><span class="sxs-lookup"><span data-stu-id="4423e-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="4423e-242">若要关闭此设置，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="4423e-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="4423e-243">**欺骗**：在此部分中，使用" **启用欺骗** 智能"复选框打开或关闭欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="4423e-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="4423e-244">默认值位于选定 (上) ，建议保留其打开状态。</span><span class="sxs-lookup"><span data-stu-id="4423e-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="4423e-245">在下一页的"如果邮件被检测为欺骗"设置中，指定对来自被阻止的欺骗发件人的邮件要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="4423e-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="4423e-246">若要关闭欺骗智能，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="4423e-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4423e-247">如果你的 MX 记录没有指向反欺骗保护，则无需关闭Microsoft 365;改为启用连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="4423e-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="4423e-248">有关说明，请参阅[增强的连接器筛选Exchange Online。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="4423e-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="4423e-249">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="4423e-250">在出现的“**操作**”页面上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="4423e-251">**邮件操作**：在此部分中配置以下操作：</span><span class="sxs-lookup"><span data-stu-id="4423e-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="4423e-252">**如果邮件被检测为模拟** 用户：只有在上一页上选择了"允许用户保护"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="4423e-253">对于发件人是上一页上指定的受保护用户之一的邮件，在下拉列表中选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423e-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="4423e-254">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="4423e-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="4423e-255">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="4423e-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="4423e-256">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4423e-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="4423e-257">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4423e-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="4423e-258">**传递邮件，将其他地址添加到"Bcc"行**</span><span class="sxs-lookup"><span data-stu-id="4423e-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="4423e-259">**在邮件传递之前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="4423e-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="4423e-260">**如果邮件被检测为** 模拟域：只有在上一页上选择了"启用要保护的域"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="4423e-261">对于发件人的电子邮件地址位于上一页上指定的某个受保护的域的邮件，请在下拉列表中选择以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423e-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="4423e-262">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="4423e-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="4423e-263">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="4423e-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="4423e-264">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4423e-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="4423e-265">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4423e-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="4423e-266">**传递邮件，将其他地址添加到"Bcc"行**</span><span class="sxs-lookup"><span data-stu-id="4423e-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="4423e-267">**在邮件传递之前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="4423e-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="4423e-268">**如果邮箱智能检测到模拟用户**：只有在上一页上选择了"启用智能 **以用于** 模拟保护"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="4423e-269">对于被邮箱智能标识为模拟尝试的邮件，请在下拉列表中选择以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423e-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="4423e-270">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="4423e-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="4423e-271">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="4423e-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="4423e-272">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4423e-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="4423e-273">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4423e-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="4423e-274">**传递邮件，将其他地址添加到"Bcc"行**</span><span class="sxs-lookup"><span data-stu-id="4423e-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="4423e-275">**在邮件传递之前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="4423e-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="4423e-276">**如果邮件被检测为欺骗邮件**：只有在上一页上选择了" **启用** 欺骗智能"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="4423e-277">在下拉列表中为来自阻止的欺骗性发件人的邮件选择以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4423e-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="4423e-278">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4423e-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="4423e-279">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4423e-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="4423e-280">**安全&：** 配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="4423e-281">**显示第一安全提示** 联系人：有关详细信息，请参阅第一个 [联系人安全提示。](set-up-anti-phishing-policies.md#first-contact-safety-tip)</span><span class="sxs-lookup"><span data-stu-id="4423e-281">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="4423e-282">**显示用户模拟安全提示：** 只有在上一页上选择了"**允许用户保护"** 时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-282">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="4423e-283">**显示域模拟安全提示：** 只有在上一页上选择了"启用要保护的域"时 **，此设置才** 可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-283">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="4423e-284">**显示用户模拟异常字符安全提示** 只有在上一页上选择了"允许用户保护域"或"启用要保护的域"时 **，此设置才** 可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-284">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="4423e-285">**显示 (？)** 欺骗的未经身份验证的发件人：仅在上一页上选择了"启用欺骗智能"时，此设置才可用。 </span><span class="sxs-lookup"><span data-stu-id="4423e-285">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="4423e-286">如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或复合身份验证，则向 Outlook的发件人照片添加问[号。](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="4423e-286">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="4423e-287">**显示"通过"标记**：只有当在上一页上选择了" **启用** 欺骗智能"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-287">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="4423e-288">如果 via 标记 (chris@contoso.com 通过 fabrikam.com) 添加到"收件人"地址（如果它不同于 DKIM 签名或 **MAIL FROM** 地址中的域）。</span><span class="sxs-lookup"><span data-stu-id="4423e-288">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="4423e-289">默认值在选定 (上) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-289">The default value is on (selected).</span></span> <span data-ttu-id="4423e-290">若要将其关闭，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="4423e-290">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="4423e-291">如果你没有"显示""通过"标记设置，则问号和通过标记都受组织中"显示 **(？)** 欺骗的未经身份验证的发件人"设置控制。</span><span class="sxs-lookup"><span data-stu-id="4423e-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="4423e-292">若要打开某个设置，请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="4423e-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="4423e-293">若要将其关闭，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="4423e-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="4423e-294">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="4423e-295">在出现的“**审阅**”页面上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="4423e-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="4423e-296">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="4423e-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="4423e-297">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="4423e-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="4423e-298">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="4423e-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="4423e-299">在出现的确认页面上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="4423e-300">使用Microsoft 365 Defender门户查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="4423e-301">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4423e-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="4423e-302">在 **"防钓鱼"** 页上，反网络钓鱼策略列表中将显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="4423e-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="4423e-303">**名称**</span><span class="sxs-lookup"><span data-stu-id="4423e-303">**Name**</span></span>
   - <span data-ttu-id="4423e-304">**状态**</span><span class="sxs-lookup"><span data-stu-id="4423e-304">**Status**</span></span>
   - <span data-ttu-id="4423e-305">**优先级**</span><span class="sxs-lookup"><span data-stu-id="4423e-305">**Priority**</span></span>
   - <span data-ttu-id="4423e-306">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="4423e-306">**Last modified**</span></span>

3. <span data-ttu-id="4423e-307">当您通过单击该名称选择策略时，策略设置将显示在一个飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="4423e-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="4423e-308">使用Microsoft 365 Defender门户修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="4423e-309">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4423e-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="4423e-310">在 **"防钓鱼"** 页上，通过单击名称从列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="4423e-311">在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="4423e-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="4423e-312">有关设置详细信息，请参阅本文前面使用 Microsoft 365 Defender 门户创建[防](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)钓鱼策略一节。</span><span class="sxs-lookup"><span data-stu-id="4423e-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="4423e-313">对于默认的防钓鱼策略，"用户、组和域"部分不可用 (该策略适用于所有用户) ，并且无法重命名该策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="4423e-314">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="4423e-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="4423e-315">启用或禁用自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="4423e-316">无法禁用默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="4423e-317">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4423e-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="4423e-318">在 **"防钓鱼"** 页上，通过单击名称从列表中选择自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="4423e-319">在出现的策略详细信息浮出控件顶部，你将看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="4423e-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="4423e-320">**策略关闭**：若要打开策略，请单击![“打开”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="4423e-321">**策略打开**：若要关闭策略，请单击![“关闭”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="4423e-322">在出现的确认对话框中，单击“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="4423e-323">单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="4423e-324">返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="4423e-325">设置自定义防钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="4423e-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="4423e-326">默认情况下，基于反网络钓鱼策略在 (较旧策略中创建的顺序，反网络钓鱼策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="4423e-327">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="4423e-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="4423e-328">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="4423e-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="4423e-329">若要更改策略的优先级，请单击策略属性中的“**提高优先级**”或“**降低优先级**”（不能直接修改 Microsoft 365 Defender 门户中的“**优先级**”数字）。</span><span class="sxs-lookup"><span data-stu-id="4423e-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="4423e-330">只有当你有多个策略时，更改策略的优先级才有意义。</span><span class="sxs-lookup"><span data-stu-id="4423e-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="4423e-331">**注意**：</span><span class="sxs-lookup"><span data-stu-id="4423e-331">**Notes**:</span></span>

- <span data-ttu-id="4423e-332">在Microsoft 365 Defender门户中，只能在创建反网络钓鱼策略后更改其优先级。</span><span class="sxs-lookup"><span data-stu-id="4423e-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="4423e-333">在 PowerShell 中，您可以在创建反网络钓鱼规则策略时替代默认优先级 (这可能会影响现有规则集的) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="4423e-334">反网络钓鱼策略按照其显示顺序进行处理， (策略的优先级值为 0 时) 。 </span><span class="sxs-lookup"><span data-stu-id="4423e-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="4423e-335">默认防钓鱼策略的优先级值为 **"** 最低"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="4423e-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="4423e-336">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4423e-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="4423e-337">在 **"防钓鱼"** 页上，通过单击名称从列表中选择自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="4423e-338">在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：</span><span class="sxs-lookup"><span data-stu-id="4423e-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="4423e-339">优先级值为 **0** **的策略** 只有"**减少优先级"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-339">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="4423e-340">优先级值最低的策略 (例如 **，3**) 只有"增加优先级 **"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-340">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="4423e-341">如果你有三个或多个策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 选项。</span><span class="sxs-lookup"><span data-stu-id="4423e-341">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="4423e-342">单击![“提高优先级”图标](../../media/m365-cc-sc-increase-icon.png)“**提高优先级**”或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png)“**降低优先级**”以更改“**优先级**”值。</span><span class="sxs-lookup"><span data-stu-id="4423e-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="4423e-343">完成后，单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="4423e-344">使用Microsoft 365 Defender门户删除自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="4423e-345">当你使用 Microsoft 365 Defender 门户删除自定义防钓鱼策略时，防钓鱼规则及相应的防钓鱼策略都将被删除。</span><span class="sxs-lookup"><span data-stu-id="4423e-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="4423e-346">无法删除默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="4423e-347">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4423e-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="4423e-348">在 **"防钓鱼"** 页上，通过单击策略的名称从列表中选择自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-348">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="4423e-349">在出现的策略详细信息浮出控件顶部，单击![“更多操作”图标](../../media/m365-cc-sc-more-actions-icon.png)“**更多操作**”\> ![“删除策略”图标](../../media/m365-cc-sc-delete-icon.png)“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="4423e-350">在出现的确认对话框中，单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="4423e-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="4423e-351">使用 Exchange Online PowerShell 配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="4423e-352">如前所述，反垃圾邮件策略由反网络钓鱼策略和反网络钓鱼规则组成。</span><span class="sxs-lookup"><span data-stu-id="4423e-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="4423e-353">在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="4423e-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="4423e-354">您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="4423e-355">在 PowerShell 中，首先创建防钓鱼策略，然后创建标识该规则所适用的策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="4423e-356">在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="4423e-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="4423e-357">从 PowerShell 删除防钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="4423e-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="4423e-358">使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="4423e-359">在 PowerShell 中创建防钓鱼策略的过程包括两个步骤：</span><span class="sxs-lookup"><span data-stu-id="4423e-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="4423e-360">创建防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="4423e-361">创建指定该规则所适用的防钓鱼策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="4423e-362">**注意**：</span><span class="sxs-lookup"><span data-stu-id="4423e-362">**Notes**:</span></span>

- <span data-ttu-id="4423e-363">你可以创建新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="4423e-364">反网络钓鱼规则不能与多个防钓鱼策略关联。</span><span class="sxs-lookup"><span data-stu-id="4423e-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="4423e-365">可以在 PowerShell 中对新的防钓鱼策略配置以下设置，这些设置在 Microsoft 365 Defender 门户中不可用，除非创建策略：</span><span class="sxs-lookup"><span data-stu-id="4423e-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="4423e-366">在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="4423e-367">在 _\<Number\>_ **New-AntiPhishRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="4423e-368">在 PowerShell 中新建的防钓鱼策略在 Microsoft 365 Defender门户中不可见，除非将策略分配给防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="4423e-369">步骤 1：使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="4423e-370">若要创建防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="4423e-371">本示例将创建名为"Research Quarantine"的防钓鱼策略，并具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="4423e-372">如果策略 (_Enabled_ 参数，则启用该策略，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="4423e-373">描述为：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="4423e-374">针对所有接受的域启用组织域保护，为组织域启用目标域 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="4423e-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="4423e-375">指定一 (mfujito@fabrikam.com) 用户的身份进行保护，防止模拟。</span><span class="sxs-lookup"><span data-stu-id="4423e-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="4423e-376">启用邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="4423e-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="4423e-377">启用邮箱智能保护，并指定隔离操作。</span><span class="sxs-lookup"><span data-stu-id="4423e-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="4423e-378">启用安全提示。</span><span class="sxs-lookup"><span data-stu-id="4423e-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="4423e-379">有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4423e-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="4423e-380">步骤 2：使用 PowerShell 创建防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4423e-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="4423e-381">若要创建防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="4423e-382">本示例创建一个名为"Research Department"的防钓鱼规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="4423e-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="4423e-383">该规则与名为"研究隔离"的防钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="4423e-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="4423e-384">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="4423e-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="4423e-385">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="4423e-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="4423e-386">有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="4423e-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="4423e-387">使用 PowerShell 查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="4423e-388">若要查看现有的防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="4423e-389">此示例返回所有防钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="4423e-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="4423e-390">此示例返回名为 Executives 的反网络钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="4423e-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="4423e-391">有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4423e-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="4423e-392">使用 PowerShell 查看防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4423e-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="4423e-393">若要查看现有的防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="4423e-394">此示例返回所有防钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="4423e-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="4423e-395">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4423e-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="4423e-396">此示例返回名为 Contoso Executives 的防钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="4423e-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="4423e-397">有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="4423e-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="4423e-398">使用 PowerShell 修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="4423e-399">除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建防钓鱼策略一节中所述。</span><span class="sxs-lookup"><span data-stu-id="4423e-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="4423e-400">_MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终最低，并且只有修改 PowerShell 中的防钓鱼策略时) 才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="4423e-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="4423e-401">如果 **Set-AntiPhishPolicy** cmdlet 没有 Name 参数 (，则不能重命名反网络钓鱼) 。 </span><span class="sxs-lookup"><span data-stu-id="4423e-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="4423e-402">在 Web 门户中重命名防钓鱼Microsoft 365 Defender，只需重命名防钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="4423e-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="4423e-403">要修改防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="4423e-404">有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4423e-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="4423e-405">使用 PowerShell 修改防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4423e-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="4423e-406">在 PowerShell 中修改反网络钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="4423e-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="4423e-407">若要启用或禁用现有防钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="4423e-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="4423e-408">否则，在 PowerShell 中修改防钓鱼规则时，其他设置将不可用。</span><span class="sxs-lookup"><span data-stu-id="4423e-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="4423e-409">创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则一节中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="4423e-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="4423e-410">要修改防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="4423e-411">有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="4423e-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="4423e-412">使用 PowerShell 启用或禁用防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4423e-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="4423e-413">在 PowerShell 中启用或禁用反网络钓鱼规则可启用或禁用整个防钓鱼策略 (以及分配的防钓鱼策略策略) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="4423e-414">无法启用或禁用默认反网络钓鱼策略 (该策略始终应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="4423e-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="4423e-415">若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="4423e-416">本示例禁用名为"Marketing Department"的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="4423e-417">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="4423e-418">有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="4423e-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="4423e-419">使用 PowerShell 设置防钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="4423e-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="4423e-p156">可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。</span><span class="sxs-lookup"><span data-stu-id="4423e-p156">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="4423e-425">若要在 PowerShell 中设置防钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="4423e-p157">此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。</span><span class="sxs-lookup"><span data-stu-id="4423e-p157">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="4423e-428">**注意**：</span><span class="sxs-lookup"><span data-stu-id="4423e-428">**Notes**:</span></span>

- <span data-ttu-id="4423e-429">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-AntiPhishRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="4423e-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="4423e-430">默认防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="4423e-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="4423e-431">使用 PowerShell 删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4423e-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="4423e-432">使用 PowerShell 删除防钓鱼策略时，不会删除相应的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="4423e-433">若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="4423e-434">此示例删除名为 Marketing Department 的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="4423e-435">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4423e-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="4423e-436">使用 PowerShell 删除防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4423e-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="4423e-437">使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4423e-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="4423e-438">若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4423e-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="4423e-439">此示例删除名为 Marketing Department 的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4423e-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="4423e-440">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="4423e-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4423e-441">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="4423e-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="4423e-442">若要验证是否成功配置了 Defender for Office 365 中的防钓鱼策略，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="4423e-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="4423e-443">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **policies** section \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4423e-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="4423e-444">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="4423e-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="4423e-445">若要查看更多详细信息，请从列表中选择策略，方法是单击名称并查看出现的飞出内容中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4423e-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="4423e-446">在 Exchange Online PowerShell 中，将 替换为策略或规则的名称，然后运行 \<Name\> 以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="4423e-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
