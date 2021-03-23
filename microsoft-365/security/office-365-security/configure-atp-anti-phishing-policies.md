---
title: 在 Microsoft Defender for Office 365 中配置防钓鱼策略
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
description: 管理员可以了解如何创建、修改和删除 Microsoft Defender for Office 365 组织中可用的高级防钓鱼策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9f9fe04b2c3b6db3681212d678c8e827f6a83f41
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994566"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-103">在 Microsoft Defender for Office 365 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4846f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4846f-104">**Applies to**</span></span>
- [<span data-ttu-id="4846f-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4846f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4846f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4846f-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4846f-107">Microsoft Defender for [Office 365](office-365-atp.md) 中的防钓鱼策略可帮助保护组织免受基于恶意模拟的网络钓鱼攻击和其他类型的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="4846f-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="4846f-108">有关 Exchange Online Protection (EOP) 中的反网络钓鱼策略与 Microsoft Defender for Office 365 中的防钓鱼策略之间的差异详细信息，请参阅反钓鱼 [保护](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4846f-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="4846f-109">管理员可以查看、编辑和配置 (，但不能) 默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="4846f-110">更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="4846f-111">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="4846f-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="4846f-112">您可以在安全与合规中心或 Exchange Online PowerShell &反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="4846f-113">有关在 Exchange Online Protection 组织 (（即没有 Microsoft Defender for Office 365) 的组织）中可用的反网络钓鱼策略中配置更加有限的信息，请参阅在 [EOP](configure-anti-phishing-policies-eop.md)中配置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="4846f-114">防钓鱼策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="4846f-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="4846f-115">**防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="4846f-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="4846f-116">**防钓鱼** 规则 ：指定策略应用于 (策略的收件人筛选器) 策略的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="4846f-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="4846f-117">在安全与合规中心内管理防钓鱼策略时，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="4846f-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="4846f-118">创建策略时，实际上是同时使用同一名称创建防钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="4846f-119">修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="4846f-120">所有其他设置修改关联的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="4846f-121">删除策略时，将删除防钓鱼规则和相关反钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="4846f-122">在 Exchange Online PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="4846f-123">有关详细信息，请参阅本文稍后介绍的使用 Exchange Online PowerShell 在 [Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) 中配置防钓鱼策略一节。</span><span class="sxs-lookup"><span data-stu-id="4846f-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="4846f-124">每个 Microsoft Defender for Office 365 组织都有一个名为 Office365 AntiPhish Default 的内置防钓鱼策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="4846f-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="4846f-125">即使与策略关联的收件人筛选器没有反网络钓鱼规则， (应用于组织) 所有收件人。</span><span class="sxs-lookup"><span data-stu-id="4846f-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="4846f-126">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="4846f-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="4846f-127">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="4846f-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="4846f-128">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="4846f-129">若要提高 Microsoft Defender for Office 365 中的防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4846f-130">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="4846f-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4846f-131">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="4846f-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4846f-132">若要直接转到 **ATP 防钓鱼页面** ，请使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="4846f-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="4846f-133">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4846f-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4846f-134">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="4846f-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4846f-135">若要添加、修改和删除防钓鱼策略，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="4846f-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4846f-136">若要对防钓鱼策略进行只读访问，你需要是全局读者或 **安全读者角色\*\*\*\*组的成员** <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="4846f-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="4846f-137">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="4846f-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="4846f-138">**注意**：</span><span class="sxs-lookup"><span data-stu-id="4846f-138">**Notes**:</span></span>

  - <span data-ttu-id="4846f-139">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="4846f-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4846f-140">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4846f-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="4846f-141">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) **中的"** 仅查看组织管理"角色组还授予对该功能的只读访问权限 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="4846f-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="4846f-142"><sup>\*</sup> 在安全&合规中心，只读访问允许用户查看自定义防钓鱼策略的设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="4846f-143">只读用户看不到默认防钓鱼策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="4846f-144">有关在 Microsoft Defender for Office 365 中建议的反网络钓鱼策略设置，请参阅 [Defender for Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)设置中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="4846f-145">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="4846f-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="4846f-146">有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="4846f-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-147">使用安全&合规中心在 Microsoft Defender for Office 365 中创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4846f-148">在安全与合规中心内创建自定义防钓鱼策略&使用相同的名称同时创建防钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="4846f-149">创建防钓鱼策略时，只能指定策略名称、说明和收件人筛选器，以标识策略的适用者。</span><span class="sxs-lookup"><span data-stu-id="4846f-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="4846f-150">创建策略后，可以修改该策略以更改或查看默认的防钓鱼设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="4846f-151">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4846f-152">在"**防钓鱼"页上，** 单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="4846f-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="4846f-153">将 **打开"创建新的防钓鱼策略"** 向导。</span><span class="sxs-lookup"><span data-stu-id="4846f-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="4846f-154">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="4846f-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="4846f-155">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4846f-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="4846f-156">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="4846f-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="4846f-157">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="4846f-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4846f-158">在 **出现的"应用于** "页上，标识策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="4846f-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="4846f-159">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="4846f-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="4846f-160">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="4846f-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="4846f-161">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="4846f-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="4846f-162">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="4846f-162">Click **Add a condition**.</span></span> <span data-ttu-id="4846f-163">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="4846f-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="4846f-164">**收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="4846f-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="4846f-165">**收件人是 ：指定** 组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="4846f-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="4846f-166">**收件人域为**：指定组织中一个或多个已配置的接受域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="4846f-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="4846f-167">选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。</span><span class="sxs-lookup"><span data-stu-id="4846f-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="4846f-168">在框中单击并滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="4846f-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="4846f-169">在框中单击并开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="4846f-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="4846f-170">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="4846f-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="4846f-171">若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="4846f-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="4846f-172">若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="4846f-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="4846f-173">若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。</span><span class="sxs-lookup"><span data-stu-id="4846f-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="4846f-174">若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。</span><span class="sxs-lookup"><span data-stu-id="4846f-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="4846f-175">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="4846f-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="4846f-176">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="4846f-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4846f-177">在出现的 **"查看设置** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="4846f-178">可以单击每个 **设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="4846f-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="4846f-179">完成后，单击"创建 **此策略"。**</span><span class="sxs-lookup"><span data-stu-id="4846f-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="4846f-180">在 **出现的** 确认对话框中单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="4846f-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="4846f-181">使用这些常规设置创建防钓鱼策略后，请使用下一节中的说明配置策略中的保护设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-182">使用安全&合规中心修改 Microsoft Defender for Office 365 中的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4846f-183">使用以下过程可修改防钓鱼策略：您创建的新策略或已自定义的现有策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="4846f-184">如果尚未开始，请打开安全与合规&， **然后转到威胁** 管理 \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4846f-185">选择要修改的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="4846f-186">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="4846f-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="4846f-187">将显示 **"编辑策略 \<name\>**"飞出控件。</span><span class="sxs-lookup"><span data-stu-id="4846f-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="4846f-188">单击 **任何** 部分中的"编辑"，即可访问该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="4846f-189">以下步骤按各节的显示顺序显示，但它们不是按顺序 (您可以按任意顺序选择和修改) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="4846f-190">在部分中单击"编辑"后，可用设置以向导格式显示，但您可以按任意顺序跳转到页面内，并且您可以单击任何页面的"保存" (或 ![ ](../../media/scc-remove-icon.png) **\<name\>**"取消"或"关闭"图标返回到"编辑策略"页面 (无需访问向导的最后一页即可保存或离开) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="4846f-191">**策略设置\*\*\*\*：单击**"编辑"修改在上一部分中创建 [策略时可用的](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365)相同设置：</span><span class="sxs-lookup"><span data-stu-id="4846f-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="4846f-192">**名称**</span><span class="sxs-lookup"><span data-stu-id="4846f-192">**Name**</span></span>
   - <span data-ttu-id="4846f-193">**说明**</span><span class="sxs-lookup"><span data-stu-id="4846f-193">**Description**</span></span>
   - <span data-ttu-id="4846f-194">**应用于**</span><span class="sxs-lookup"><span data-stu-id="4846f-194">**Applied to**</span></span>
   - <span data-ttu-id="4846f-195">**查看您的设置**</span><span class="sxs-lookup"><span data-stu-id="4846f-195">**Review your settings**</span></span>

   <span data-ttu-id="4846f-196">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="4846f-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="4846f-197">**模拟**：单击 **"** 编辑"修改策略中的受保护的发件人和受保护的域。</span><span class="sxs-lookup"><span data-stu-id="4846f-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="4846f-198">这些设置是策略的一个条件，用于标识欺骗性发件人，以单独 (或按域) 入站邮件的发件人地址查找邮件。</span><span class="sxs-lookup"><span data-stu-id="4846f-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="4846f-199">有关详细信息，请参阅 [Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)中的防钓鱼策略中的模拟设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="4846f-200">**添加要保护的用户**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="4846f-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="4846f-201">若要将其打开，将切换开关滑动到 **"开**"，然后单击出现的 **"添加用户** "按钮。</span><span class="sxs-lookup"><span data-stu-id="4846f-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="4846f-202">在出现的 **"添加** 用户"飞出中，配置以下值：</span><span class="sxs-lookup"><span data-stu-id="4846f-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="4846f-203">**电子邮件地址**：</span><span class="sxs-lookup"><span data-stu-id="4846f-203">**Email address**:</span></span>

       - <span data-ttu-id="4846f-204">在框中单击并滚动浏览要选择的用户列表。</span><span class="sxs-lookup"><span data-stu-id="4846f-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="4846f-205">在框中单击并开始键入以筛选列表并选择用户。</span><span class="sxs-lookup"><span data-stu-id="4846f-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="4846f-206">若要删除条目，请单击 **用户上的"** ![ ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="4846f-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="4846f-207">**名称**：此值将基于你选择的电子邮件地址进行填充，但你可以更改它。</span><span class="sxs-lookup"><span data-stu-id="4846f-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="4846f-208">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="4846f-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="4846f-209">若要编辑现有条目，请在列表中选择受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="4846f-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="4846f-210">在每个防钓鱼策略中，最多可指定 60 个受保护 (发件人电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="4846f-211">不能在多个策略中指定同一受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="4846f-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="4846f-212">如果发件人和收件人之前通过电子邮件进行通信，则用户模拟保护不起作用。</span><span class="sxs-lookup"><span data-stu-id="4846f-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="4846f-213">如果发件人和收件人从未通过电子邮件进行通信，则邮件将被标识为模拟尝试。</span><span class="sxs-lookup"><span data-stu-id="4846f-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="4846f-214">**添加要保护的域**：配置以下一个或两个设置：</span><span class="sxs-lookup"><span data-stu-id="4846f-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="4846f-215">**自动包含我拥有的域**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="4846f-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="4846f-216">若要将其打开，将切换开关滑动到 **开**。</span><span class="sxs-lookup"><span data-stu-id="4846f-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="4846f-217">**包含自定义域**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="4846f-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="4846f-218">若要将其打开，将开关滑动到 **"** 开"，在"添加域"框中，输入域名 (例如 contoso.com) ，按 Enter，然后根据需要重复。</span><span class="sxs-lookup"><span data-stu-id="4846f-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4846f-219">在所有防钓鱼策略中最多可以有 50 个域。</span><span class="sxs-lookup"><span data-stu-id="4846f-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="4846f-220">**操作**：单击 **"编辑"**</span><span class="sxs-lookup"><span data-stu-id="4846f-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="4846f-221">**如果电子邮件由** 模拟用户发送：为欺骗性发件人是添加要保护的用户中指定的受保护用户之一的邮件配置以下操作 **之一**：</span><span class="sxs-lookup"><span data-stu-id="4846f-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="4846f-222">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="4846f-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="4846f-223">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="4846f-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="4846f-224">**将邮件移动到"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4846f-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="4846f-225">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4846f-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="4846f-226">**传递邮件，将其他地址添加到"Bcc"行**</span><span class="sxs-lookup"><span data-stu-id="4846f-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="4846f-227">**在邮件传递之前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="4846f-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="4846f-228">**如果电子邮件是由** 模拟域发送的：为欺骗性发件人位于你在添加要保护的域中指定的其中一个受保护的域的邮件配置以下操作 **之一**：</span><span class="sxs-lookup"><span data-stu-id="4846f-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="4846f-229">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="4846f-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="4846f-230">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="4846f-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="4846f-231">**将邮件移动到"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4846f-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="4846f-232">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4846f-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="4846f-233">**传递邮件，将其他地址添加到"Bcc"行**</span><span class="sxs-lookup"><span data-stu-id="4846f-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="4846f-234">**在邮件传递之前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="4846f-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="4846f-235">单击 **"打开模拟安全提示"** 并配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="4846f-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="4846f-236">**显示模拟用户的提示**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="4846f-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="4846f-237">若要将其打开，将切换开关滑动到 **开**。</span><span class="sxs-lookup"><span data-stu-id="4846f-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="4846f-238">**显示模拟域的提示**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="4846f-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="4846f-239">若要将其打开，将切换开关滑动到 **开**。</span><span class="sxs-lookup"><span data-stu-id="4846f-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="4846f-240">**显示异常字符的提示**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="4846f-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="4846f-241">若要将其打开，将切换开关滑动到 **开**。</span><span class="sxs-lookup"><span data-stu-id="4846f-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="4846f-242">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4846f-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="4846f-243">**邮箱智能**：</span><span class="sxs-lookup"><span data-stu-id="4846f-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="4846f-244">**启用邮箱智能？：** 默认值为 **On。**</span><span class="sxs-lookup"><span data-stu-id="4846f-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="4846f-245">若要关闭它，将切换开关滑动到 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="4846f-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="4846f-246">**启用基于邮箱智能的模拟保护？：** 此设置仅在启用 **邮箱智能时可用？** 为 **On**。</span><span class="sxs-lookup"><span data-stu-id="4846f-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="4846f-247">打开此设置可指定对邮件执行的操作，以从邮箱智能结果进行模拟检测。</span><span class="sxs-lookup"><span data-stu-id="4846f-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="4846f-248">在 **"** 如果电子邮件由模拟用户发送"中，可以指定以下操作之一 (保护用户和受保护的域可执行) ：</span><span class="sxs-lookup"><span data-stu-id="4846f-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="4846f-249">**不要应用任何操作**：请注意，此值与启用邮箱智能具有相同的结果 **？但关闭** 启用基于邮箱 **智能的模拟保护？。**</span><span class="sxs-lookup"><span data-stu-id="4846f-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="4846f-250">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="4846f-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="4846f-251">**将邮件移动到"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4846f-251">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="4846f-252">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4846f-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="4846f-253">**传递邮件，将其他地址添加到"Bcc"行**</span><span class="sxs-lookup"><span data-stu-id="4846f-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="4846f-254">**在邮件传递之前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="4846f-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="4846f-255">**添加受信任的发件人和域**：指定策略的例外：</span><span class="sxs-lookup"><span data-stu-id="4846f-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="4846f-256">**受信任的发件人**：</span><span class="sxs-lookup"><span data-stu-id="4846f-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="4846f-257">在框中单击并滚动浏览要选择的用户列表。</span><span class="sxs-lookup"><span data-stu-id="4846f-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="4846f-258">在框中单击并开始键入以筛选列表并选择用户。</span><span class="sxs-lookup"><span data-stu-id="4846f-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="4846f-259">若要删除条目，请单击 **用户上的"** ![ ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="4846f-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="4846f-260">**受信任的域**：输入域名 (例如，contoso.com) 按 Enter，然后根据需要重复。</span><span class="sxs-lookup"><span data-stu-id="4846f-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="4846f-261">**查看设置**：设置会显示在摘要中，而不是单击每个单独的步骤。</span><span class="sxs-lookup"><span data-stu-id="4846f-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="4846f-262">可以单击每个 **部分** 中的"编辑"跳转回相关页面。</span><span class="sxs-lookup"><span data-stu-id="4846f-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="4846f-263">您可以直接在此页面上切换以下设置 **：打开\*\*\*\*或关闭**：</span><span class="sxs-lookup"><span data-stu-id="4846f-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="4846f-264">**受保护的用户**</span><span class="sxs-lookup"><span data-stu-id="4846f-264">**Protected users**</span></span>
       - <span data-ttu-id="4846f-265">**受保护的域** \>**包含我拥有域**</span><span class="sxs-lookup"><span data-stu-id="4846f-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="4846f-266">**受保护的域** \>**受保护的域 (** 自定义域) </span><span class="sxs-lookup"><span data-stu-id="4846f-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="4846f-267">**邮箱智能**</span><span class="sxs-lookup"><span data-stu-id="4846f-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="4846f-268">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="4846f-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="4846f-269">**欺骗**：单击"编辑"打开或关闭欺骗智能，打开或关闭 Outlook 中的未经身份验证的发件人标识，并配置操作以应用于来自被阻止的欺骗发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="4846f-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="4846f-270">有关详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="4846f-270">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="4846f-271">请注意，EOP 中的防钓鱼策略中也提供了这些相同的设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="4846f-272">**欺骗筛选器设置**：默认值为 **"开**"，建议保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="4846f-272">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="4846f-273">若要关闭它，将切换开关滑动到 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="4846f-273">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="4846f-274">有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="4846f-274">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="4846f-275">如果你的 MX 记录不指向 Microsoft 365，你无需禁用反欺骗保护;改为启用连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="4846f-275">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="4846f-276">有关说明，请参阅 [增强的 Exchange Online 中的连接器筛选](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="4846f-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="4846f-277">**启用未经身份验证的发件人功能**：默认值为 **On**。</span><span class="sxs-lookup"><span data-stu-id="4846f-277">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="4846f-278">若要关闭它，将切换开关滑动到 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="4846f-278">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="4846f-279">**操作**：指定对未通过欺骗智能的邮件采取的操作：</span><span class="sxs-lookup"><span data-stu-id="4846f-279">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="4846f-280">**如果电子邮件是由不允许欺骗你的域的人发送的**：</span><span class="sxs-lookup"><span data-stu-id="4846f-280">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="4846f-281">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="4846f-281">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="4846f-282">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="4846f-282">**Quarantine the message**</span></span>

   - <span data-ttu-id="4846f-283">**查看设置**：设置会显示在摘要中，而不是单击每个单独的步骤。</span><span class="sxs-lookup"><span data-stu-id="4846f-283">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="4846f-284">可以单击每个 **部分** 中的"编辑"跳转回相关页面。</span><span class="sxs-lookup"><span data-stu-id="4846f-284">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="4846f-285">您可以直接在此页面上切换以下设置 **：打开\*\*\*\*或关闭**：</span><span class="sxs-lookup"><span data-stu-id="4846f-285">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="4846f-286">**启用反应答保护**</span><span class="sxs-lookup"><span data-stu-id="4846f-286">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="4846f-287">**启用未经身份验证的发件人功能**</span><span class="sxs-lookup"><span data-stu-id="4846f-287">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="4846f-288">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="4846f-288">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="4846f-289">**高级设置**：单击 **"** 编辑"以配置高级网络钓鱼阈值。</span><span class="sxs-lookup"><span data-stu-id="4846f-289">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="4846f-290">有关详细信息，请参阅 [Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)中的反网络钓鱼策略中的高级网络钓鱼阈值。</span><span class="sxs-lookup"><span data-stu-id="4846f-290">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="4846f-291">**高级网络钓鱼阈值**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4846f-291">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="4846f-292">**1 - 标准** (此值为默认值。) </span><span class="sxs-lookup"><span data-stu-id="4846f-292">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="4846f-293">**2 - 主动**</span><span class="sxs-lookup"><span data-stu-id="4846f-293">**2 - Aggressive**</span></span>
   - <span data-ttu-id="4846f-294">**3 - 更主动**</span><span class="sxs-lookup"><span data-stu-id="4846f-294">**3 - More aggressive**</span></span>
   - <span data-ttu-id="4846f-295">**4 - 最积极**</span><span class="sxs-lookup"><span data-stu-id="4846f-295">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="4846f-296">**查看设置：** 单击 **"编辑** "跳转回 **"高级网络钓鱼阈值"** 页面。</span><span class="sxs-lookup"><span data-stu-id="4846f-296">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="4846f-297">完成后，单击任一 **页面上的"** 保存"。</span><span class="sxs-lookup"><span data-stu-id="4846f-297">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="4846f-298">返回到"**编辑策略"页面 \<Name\>**，查看设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="4846f-298">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-299">使用安全&合规中心修改 Microsoft Defender for Office 365 中的默认防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-299">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4846f-300">Microsoft Defender for Office 365 中的默认防钓鱼策略名为"Office365 反钓鱼默认策略"，它不会显示在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="4846f-300">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="4846f-301">若要修改默认的防钓鱼策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4846f-301">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="4846f-302">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-302">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4846f-303">在"**反网络钓鱼"页上**，单击"**默认策略"。**</span><span class="sxs-lookup"><span data-stu-id="4846f-303">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="4846f-304">将显示 **"编辑你的策略 Office365 反语言默认"** 页。</span><span class="sxs-lookup"><span data-stu-id="4846f-304">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="4846f-305">以下部分可用，其中包含修改自定义策略 [时相同的设置](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)：</span><span class="sxs-lookup"><span data-stu-id="4846f-305">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="4846f-306">**模拟**</span><span class="sxs-lookup"><span data-stu-id="4846f-306">**Impersonation**</span></span>
   - <span data-ttu-id="4846f-307">**欺骗**</span><span class="sxs-lookup"><span data-stu-id="4846f-307">**Spoof**</span></span>
   - <span data-ttu-id="4846f-308">**高级设置**</span><span class="sxs-lookup"><span data-stu-id="4846f-308">**Advanced settings**</span></span>

   <span data-ttu-id="4846f-309">修改默认策略时，以下设置不可用：</span><span class="sxs-lookup"><span data-stu-id="4846f-309">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="4846f-310">You can see the **Policy setting section** and values， but there's no **Edit** link， so you can't modify the settings (policy name， description， and who the policy applies to (it applies to all recipients) ) .</span><span class="sxs-lookup"><span data-stu-id="4846f-310">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="4846f-311">不能删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-311">You can't delete the default policy.</span></span>
   - <span data-ttu-id="4846f-312">你无法更改默认策略的优先级 (它始终在上次应用) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-312">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="4846f-313">在"**编辑策略 Office365 反默认** 策略"页上，查看设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="4846f-313">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-314">在 Microsoft Defender for Office 365 中启用或禁用自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-314">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="4846f-315">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-315">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4846f-316">请注意"状态" **列中** 的值：</span><span class="sxs-lookup"><span data-stu-id="4846f-316">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="4846f-317">将开关滑动到 **"关闭"** 以禁用该策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-317">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="4846f-318">将切换开关滑动 **到"打开** "以启用策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-318">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="4846f-319">无法禁用默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-319">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-320">在 Microsoft Defender for Office 365 中设置自定义防钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="4846f-320">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4846f-321">默认情况下，基于反网络钓鱼策略在 (较旧策略中创建的顺序，反网络钓鱼策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-321">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="4846f-322">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="4846f-322">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="4846f-323">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="4846f-323">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="4846f-324">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="4846f-324">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="4846f-325">自定义防钓鱼策略按照其处理顺序显示， (策略的优先级值为 0) 。 </span><span class="sxs-lookup"><span data-stu-id="4846f-325">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="4846f-326">名为"Office365 反钓鱼默认"的默认防钓鱼策略具有自定义优先级值 **"** 最低"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="4846f-326">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="4846f-327">**注意**：在安全&合规中心，只能在创建后更改反网络钓鱼策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="4846f-327">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="4846f-328">在 PowerShell 中，您可以在创建反网络钓鱼规则策略时替代默认优先级 (这可能会影响现有规则集的) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-328">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="4846f-329">若要更改策略的优先级，请单击策略属性中的"增加优先级"或"减少优先级 (你无法直接修改安全与合规中心&优先级) 。 </span><span class="sxs-lookup"><span data-stu-id="4846f-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="4846f-330">更改策略的优先级仅在有多个策略时有意义。</span><span class="sxs-lookup"><span data-stu-id="4846f-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="4846f-331">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4846f-332">选择要修改的策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-332">Select the policy that you want to modify.</span></span> <span data-ttu-id="4846f-333">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="4846f-333">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="4846f-334">将显示 **"编辑策略 \<name\>**"飞出控件。</span><span class="sxs-lookup"><span data-stu-id="4846f-334">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="4846f-335">优先级值为 **0** 的自定义防钓鱼策略仅具有"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="4846f-335">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="4846f-336">优先级值最低的自定义防钓鱼策略 (例如 **，3**) 只有"增加优先级 **"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="4846f-336">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="4846f-337">如果你有三个或多个自定义防钓鱼策略，则优先级最高的值和最低优先级值之间的策略同时具有"增加优先级"和"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="4846f-337">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="4846f-338">单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。</span><span class="sxs-lookup"><span data-stu-id="4846f-338">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="4846f-339">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="4846f-339">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-340">使用安全&中心查看 Microsoft Defender for Office 365 中的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-340">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="4846f-341">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-341">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4846f-342">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="4846f-342">Do one of the following steps:</span></span>

   - <span data-ttu-id="4846f-343">选择要查看的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-343">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="4846f-344">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="4846f-344">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="4846f-345">单击 **"默认** 策略"以查看默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-345">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="4846f-346">将出现 **"编辑策略 \<name\>**"飞出控件，可在其中查看设置和值。</span><span class="sxs-lookup"><span data-stu-id="4846f-346">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-347">使用安全&合规中心删除 Microsoft Defender for Office 365 中的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-347">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="4846f-348">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-348">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4846f-349">选择要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-349">Select the policy that you want to remove.</span></span> <span data-ttu-id="4846f-350">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="4846f-350">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="4846f-351">在出现的 **"编辑策略 \<name\>**"飞出控件中，单击"删除策略"，然后在出现的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="4846f-351">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="4846f-352">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-352">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4846f-353">使用 Exchange Online PowerShell 在 Microsoft Defender for Office 365 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-353">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4846f-354">如前所述，反垃圾邮件策略由反网络钓鱼策略和反网络钓鱼规则组成。</span><span class="sxs-lookup"><span data-stu-id="4846f-354">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="4846f-355">在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="4846f-355">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="4846f-356">您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-356">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="4846f-357">在 PowerShell 中，首先创建防钓鱼策略，然后创建标识该规则所适用的策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-357">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="4846f-358">在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="4846f-358">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="4846f-359">从 PowerShell 删除防钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="4846f-359">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="4846f-360">使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-360">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="4846f-361">在 PowerShell 中创建防钓鱼策略的过程包括两个步骤：</span><span class="sxs-lookup"><span data-stu-id="4846f-361">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="4846f-362">创建防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-362">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="4846f-363">创建指定该规则所适用的防钓鱼策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-363">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="4846f-364">**注意**：</span><span class="sxs-lookup"><span data-stu-id="4846f-364">**Notes**:</span></span>

- <span data-ttu-id="4846f-365">你可以创建新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-365">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="4846f-366">反网络钓鱼规则不能与多个防钓鱼策略关联。</span><span class="sxs-lookup"><span data-stu-id="4846f-366">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="4846f-367">可以在 PowerShell 中的新防钓鱼策略上配置以下设置，这些设置在创建策略之前&安全与合规中心内不可用：</span><span class="sxs-lookup"><span data-stu-id="4846f-367">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="4846f-368">在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-368">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="4846f-369">在 _\<Number\>_ **New-AntiPhishRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-369">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="4846f-370">在安全与合规中心内看不到在 PowerShell 中创建的新防钓鱼策略&策略分配给防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-370">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="4846f-371">步骤 1：使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-371">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="4846f-372">若要创建防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-372">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="4846f-373">本示例将创建名为"Research Quarantine"的防钓鱼策略，并具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="4846f-373">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="4846f-374">如果策略 (_Enabled_ 参数，则启用该策略，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-374">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="4846f-375">描述为：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-375">The description is: Research department policy.</span></span>
- <span data-ttu-id="4846f-376">针对所有接受的域启用组织域保护，为组织域启用目标域 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="4846f-376">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="4846f-377">指定一 (mfujito@fabrikam.com) 用户的身份进行保护，防止模拟。</span><span class="sxs-lookup"><span data-stu-id="4846f-377">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="4846f-378">启用邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="4846f-378">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="4846f-379">启用邮箱智能保护，并指定隔离操作。</span><span class="sxs-lookup"><span data-stu-id="4846f-379">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="4846f-380">启用安全提示。</span><span class="sxs-lookup"><span data-stu-id="4846f-380">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="4846f-381">有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4846f-381">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="4846f-382">步骤 2：使用 PowerShell 创建防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4846f-382">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="4846f-383">若要创建防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-383">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="4846f-384">本示例创建一个名为"Research Department"的防钓鱼规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="4846f-384">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="4846f-385">该规则与名为"研究隔离"的防钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="4846f-385">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="4846f-386">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="4846f-386">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="4846f-387">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="4846f-387">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="4846f-388">有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="4846f-388">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="4846f-389">使用 PowerShell 查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-389">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="4846f-390">若要查看现有的防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-390">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="4846f-391">此示例返回所有防钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="4846f-391">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="4846f-392">此示例返回名为 Executives 的反网络钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="4846f-392">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="4846f-393">有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4846f-393">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="4846f-394">使用 PowerShell 查看防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4846f-394">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="4846f-395">若要查看现有的防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-395">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="4846f-396">此示例返回所有防钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="4846f-396">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="4846f-397">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4846f-397">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="4846f-398">此示例返回名为 Contoso Executives 的防钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="4846f-398">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="4846f-399">有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="4846f-399">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="4846f-400">使用 PowerShell 修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-400">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="4846f-401">除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建防钓鱼策略一节中所述。</span><span class="sxs-lookup"><span data-stu-id="4846f-401">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="4846f-402">_MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终最低，并且只有修改 PowerShell 中的防钓鱼策略时) 才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="4846f-402">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="4846f-403">如果 **Set-AntiPhishPolicy** cmdlet 没有 Name 参数 (，则不能重命名反网络钓鱼) 。 </span><span class="sxs-lookup"><span data-stu-id="4846f-403">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="4846f-404">在安全与合规中心内重命名防钓鱼&，只需重命名防钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="4846f-404">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="4846f-405">要修改防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-405">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="4846f-406">有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4846f-406">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="4846f-407">使用 PowerShell 修改防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4846f-407">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="4846f-408">在 PowerShell 中修改反网络钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="4846f-408">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="4846f-409">若要启用或禁用现有防钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="4846f-409">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="4846f-410">否则，在 PowerShell 中修改防钓鱼规则时，其他设置将不可用。</span><span class="sxs-lookup"><span data-stu-id="4846f-410">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="4846f-411">创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则一节中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="4846f-411">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="4846f-412">要修改防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-412">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="4846f-413">有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="4846f-413">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="4846f-414">使用 PowerShell 启用或禁用防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4846f-414">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="4846f-415">在 PowerShell 中启用或禁用反网络钓鱼规则可启用或禁用整个防钓鱼策略 (以及分配的防钓鱼策略策略) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-415">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="4846f-416">无法启用或禁用默认反网络钓鱼策略 (该策略始终应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="4846f-416">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="4846f-417">若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-417">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="4846f-418">本示例禁用名为"Marketing Department"的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-418">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="4846f-419">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-419">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="4846f-420">有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="4846f-420">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="4846f-421">使用 PowerShell 设置防钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="4846f-421">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="4846f-422">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="4846f-422">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="4846f-423">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="4846f-423">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="4846f-424">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="4846f-424">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="4846f-425">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="4846f-425">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="4846f-426">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="4846f-426">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="4846f-427">若要在 PowerShell 中设置防钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-427">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="4846f-428">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="4846f-428">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="4846f-429">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="4846f-429">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="4846f-430">**注意**：</span><span class="sxs-lookup"><span data-stu-id="4846f-430">**Notes**:</span></span>

- <span data-ttu-id="4846f-431">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-AntiPhishRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="4846f-431">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="4846f-432">默认防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="4846f-432">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="4846f-433">使用 PowerShell 删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="4846f-433">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="4846f-434">使用 PowerShell 删除防钓鱼策略时，不会删除相应的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-434">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="4846f-435">若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-435">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="4846f-436">此示例删除名为 Marketing Department 的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-436">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="4846f-437">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="4846f-437">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="4846f-438">使用 PowerShell 删除防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="4846f-438">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="4846f-439">使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="4846f-439">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="4846f-440">若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4846f-440">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="4846f-441">此示例删除名为 Marketing Department 的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="4846f-441">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="4846f-442">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="4846f-442">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4846f-443">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="4846f-443">How do you know these procedures worked?</span></span>

<span data-ttu-id="4846f-444">若要验证您是否已成功在 Microsoft Defender for Office 365 中配置防钓鱼策略，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="4846f-444">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="4846f-445">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="4846f-445">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="4846f-446">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="4846f-446">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="4846f-447">若要查看更多详细信息，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="4846f-447">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="4846f-448">从列表中选择策略，并查看该飞出内容中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4846f-448">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="4846f-449">单击 **"默认** 策略"，在飞出视图中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="4846f-449">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="4846f-450">在 Exchange Online PowerShell 中，将 替换为策略或规则的名称，然后运行 \<Name\> 以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="4846f-450">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```