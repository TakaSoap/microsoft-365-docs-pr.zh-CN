---
title: 在 EOP 中配置反垃圾邮件策略
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
ms.openlocfilehash: bc3c15d2a652e9acd3407ecb91fc99b7ef295c7e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537915"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="79d36-103">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="79d36-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="79d36-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="79d36-104">**Applies to**</span></span>
- [<span data-ttu-id="79d36-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="79d36-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="79d36-106">在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，则有一个默认的反网络钓鱼策略，其中包含有限数量的默认情况下启用的反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="79d36-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="79d36-107">有关详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="79d36-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="79d36-108">管理员可以查看、编辑和配置 (，但不能) 默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="79d36-109">更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="79d36-110">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="79d36-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="79d36-111">具有Exchange Online的组织可以在安全与合规中心或 & PowerShell 中配置Exchange Online防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="79d36-112">独立 EOP 组织只能使用安全&中心。</span><span class="sxs-lookup"><span data-stu-id="79d36-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="79d36-113">有关在 Microsoft Defender for Office 365 中创建和修改适用于 Office 365 的更高级反网络钓鱼策略的信息，请参阅在 Microsoft Defender 中为 Office 365 配置[防钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="79d36-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="79d36-114">防钓鱼策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="79d36-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="79d36-115">**防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="79d36-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="79d36-116">**防钓鱼** 规则 ：指定策略应用于 (策略的收件人筛选器) 策略的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="79d36-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="79d36-117">在安全与合规中心内管理防钓鱼策略时，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="79d36-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="79d36-118">创建防钓鱼策略时，实际上是同时使用同一名称创建反网络钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="79d36-119">修改防钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="79d36-120">所有其他设置修改关联的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="79d36-121">删除防钓鱼策略时，会删除防钓鱼规则及相关的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="79d36-122">在 Exchange Online PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="79d36-123">有关详细信息，请参阅本文Exchange Online[使用 PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)配置防钓鱼策略一节。</span><span class="sxs-lookup"><span data-stu-id="79d36-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="79d36-124">每个组织都有一个名为 Office365 AntiPhish Default 的内置防钓鱼策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="79d36-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="79d36-125">即使与策略关联的收件人筛选器没有反网络钓鱼规则， (应用于组织) 所有收件人。</span><span class="sxs-lookup"><span data-stu-id="79d36-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="79d36-126">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="79d36-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="79d36-127">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="79d36-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="79d36-128">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="79d36-129">若要提高防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="79d36-130">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="79d36-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="79d36-131">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="79d36-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="79d36-132">若要直接转到" **防钓鱼"页面** ，请使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="79d36-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="79d36-133">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="79d36-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="79d36-134">你无法管理独立 EOP PowerShell 中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="79d36-135">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="79d36-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="79d36-136">若要添加、修改和删除防钓鱼策略，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="79d36-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="79d36-137">若要对防钓鱼策略进行只读访问，你需要是全局读者或 **安全读者角色\*\*\*\*组的成员** <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="79d36-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="79d36-138">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="79d36-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="79d36-139">**注意**：</span><span class="sxs-lookup"><span data-stu-id="79d36-139">**Notes**:</span></span>

  - <span data-ttu-id="79d36-140">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="79d36-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="79d36-141">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="79d36-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="79d36-142">此 **策略中的**"仅查看组织管理"角色 [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)还授予对该功能的只读访问权限 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="79d36-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="79d36-143"><sup>\*</sup> 在安全&合规中心，只读访问允许用户查看自定义防钓鱼策略的设置。</span><span class="sxs-lookup"><span data-stu-id="79d36-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="79d36-144">只读用户看不到默认防钓鱼策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="79d36-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="79d36-145">若要在独立 EOP 中创建和修改防钓鱼策略，需要执行一些需要租户 _冻结操作_ 。</span><span class="sxs-lookup"><span data-stu-id="79d36-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="79d36-146">例如，在 Exchange 管理中心 (EAC) 中，可以转到"权限"选项卡，选择现有角色组，单击"编辑编辑"图标，然后删除角色 (最终将添加回 ![ ](../../media/ITPro-EAC-EditIcon.png)) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="79d36-147">如果租户从未被冻结，则会显示一个名为"更新组织"设置 **一个** 应成功完成的进度栏。</span><span class="sxs-lookup"><span data-stu-id="79d36-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="79d36-148">有关冻结详细信息，请参阅 [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (该 cmdlet 在独立 EOP PowerShell 或安全与合规中心 & 中) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="79d36-149">有关建议的反网络钓鱼策略设置，请参阅 [EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="79d36-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="79d36-150">最多允许应用更新的策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="79d36-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="79d36-151">有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="79d36-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="79d36-152">使用安全&中心创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="79d36-153">在安全与合规中心内创建自定义防钓鱼策略&使用相同的名称同时创建防钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="79d36-154">创建防钓鱼策略时，只能指定策略名称、说明和收件人筛选器，以标识策略的适用者。</span><span class="sxs-lookup"><span data-stu-id="79d36-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="79d36-155">创建策略后，可以修改该策略以更改或查看默认的防钓鱼设置。</span><span class="sxs-lookup"><span data-stu-id="79d36-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="79d36-156">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="79d36-157">在"**防钓鱼"页上，** 单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="79d36-158">将 **打开"创建新的防钓鱼策略"** 向导。</span><span class="sxs-lookup"><span data-stu-id="79d36-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="79d36-159">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="79d36-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="79d36-160">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="79d36-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="79d36-161">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="79d36-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="79d36-162">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="79d36-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="79d36-163">在 **出现的"应用于** "页上，标识策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="79d36-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="79d36-164">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="79d36-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="79d36-165">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="79d36-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="79d36-166">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="79d36-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="79d36-167">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-167">Click **Add a condition**.</span></span> <span data-ttu-id="79d36-168">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="79d36-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="79d36-169">**收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="79d36-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="79d36-170">**收件人是 ：指定** 组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="79d36-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="79d36-171">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="79d36-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="79d36-172">选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。</span><span class="sxs-lookup"><span data-stu-id="79d36-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="79d36-173">在框中单击并滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="79d36-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="79d36-174">在框中单击并开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="79d36-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="79d36-175">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="79d36-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="79d36-176">若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="79d36-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="79d36-177">若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="79d36-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="79d36-178">若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。</span><span class="sxs-lookup"><span data-stu-id="79d36-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="79d36-179">若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。</span><span class="sxs-lookup"><span data-stu-id="79d36-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="79d36-180">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="79d36-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="79d36-181">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="79d36-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="79d36-182">在出现的 **"查看设置** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="79d36-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="79d36-183">可以单击每个 **设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="79d36-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="79d36-184">完成后，单击"创建 **此策略"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="79d36-185">在 **出现的** 确认对话框中单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="79d36-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="79d36-186">使用这些常规策略设置创建防钓鱼策略后，请使用下一节中的说明配置策略中的保护设置。</span><span class="sxs-lookup"><span data-stu-id="79d36-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="79d36-187">使用安全&合规中心修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="79d36-188">使用以下过程可修改防钓鱼策略：您创建的新策略或已自定义的现有策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="79d36-189">如果尚未开始，请打开安全与合规&，然后转到威胁管理 \> **策略** \> **防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="79d36-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="79d36-190">选择要修改的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="79d36-191">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="79d36-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="79d36-192">将显示 **"编辑策略 \<name\>**"飞出控件。</span><span class="sxs-lookup"><span data-stu-id="79d36-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="79d36-193">单击 **任何** 部分中的"编辑"，即可访问该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="79d36-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="79d36-194">以下步骤按各节的显示顺序显示，但它们不是按顺序 (您可以按任意顺序选择和修改) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="79d36-195">在部分中单击"编辑"后，可用设置以向导格式显示，但您可以按任意顺序跳转到页面内，并且您可以单击任何页面的"保存" (或 ![ ](../../media/scc-remove-icon.png) **\<name\>**"取消"或"关闭"图标返回到"编辑策略"页面 (无需访问向导的最后一页即可保存或离开) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="79d36-196">**策略设置\*\*\*\*：单击**"编辑"修改在上一部分中创建 [策略时可用的](#use-the-security--compliance-center-to-create-anti-phishing-policies)相同设置：</span><span class="sxs-lookup"><span data-stu-id="79d36-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="79d36-197">**名称**</span><span class="sxs-lookup"><span data-stu-id="79d36-197">**Name**</span></span>
   - <span data-ttu-id="79d36-198">**说明**</span><span class="sxs-lookup"><span data-stu-id="79d36-198">**Description**</span></span>
   - <span data-ttu-id="79d36-199">**应用于**</span><span class="sxs-lookup"><span data-stu-id="79d36-199">**Applied to**</span></span>
   - <span data-ttu-id="79d36-200">**查看设置**</span><span class="sxs-lookup"><span data-stu-id="79d36-200">**Review your settings**</span></span>

   <span data-ttu-id="79d36-201">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="79d36-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="79d36-202">**欺骗**：单击"编辑"打开或关闭欺骗智能，在 Outlook 中打开或关闭未经身份验证的发件人标识，并配置操作以应用于来自被阻止的欺骗发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="79d36-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="79d36-203">有关这些设置详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="79d36-203">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="79d36-204">请注意，Defender for Office 365 中的防钓鱼策略中也提供了这些相同的Office 365。</span><span class="sxs-lookup"><span data-stu-id="79d36-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="79d36-205">**欺骗筛选器设置**：使用启用 **欺骗智能？** 设置打开或关闭欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="79d36-205">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="79d36-206">默认值为 **On，** 建议保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="79d36-206">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="79d36-207">若要将其关闭，将切换开关滑动到 **关闭** ![ 切换关闭 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-207">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="79d36-208">如果你的 MX 记录没有指向反欺骗保护，则无需关闭Microsoft 365;改为启用连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="79d36-208">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="79d36-209">有关说明，请参阅[增强的连接器筛选Exchange Online。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="79d36-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="79d36-210">**未经身份验证的发件人设置**：可以配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="79d36-210">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="79d36-211">启用未经身份验证的发件人问号 **(？) 符号？：** 如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或复合身份验证，则这些设置会将问号添加到 Outlook的发件人框中的发件人照片。 [](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="79d36-211">**Enable unauthenticated sender question mark (?) symbol?**: This settings adds question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="79d36-212">默认值为“打开”。</span><span class="sxs-lookup"><span data-stu-id="79d36-212">The default value is **On**.</span></span> <span data-ttu-id="79d36-213">若要将其关闭，将切换开关滑动到 **关闭** ![ 切换关闭 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-213">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="79d36-214">**启用"via"标记？：** 此设置通过 (chris@contoso.com 添加 fabrikam.com) 不同于 DKIM 签名或 **MAIL FROM** 地址中的域。</span><span class="sxs-lookup"><span data-stu-id="79d36-214">**Enable "via" tag?**: This setting adds a via tag (chris@contoso.com via fabrikam.com) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="79d36-215">默认值为“打开”。</span><span class="sxs-lookup"><span data-stu-id="79d36-215">The default value is **On**.</span></span> <span data-ttu-id="79d36-216">若要将其关闭，将切换开关滑动到 **关闭** ![ 切换关闭 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-216">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="79d36-217">**操作**：指定对来自被阻止的欺骗发件人的邮件采取的操作：</span><span class="sxs-lookup"><span data-stu-id="79d36-217">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="79d36-218">**如果电子邮件是由不允许欺骗你的域的人发送的**：</span><span class="sxs-lookup"><span data-stu-id="79d36-218">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="79d36-219">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="79d36-219">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="79d36-220">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="79d36-220">**Quarantine the message**</span></span>

   - <span data-ttu-id="79d36-221">**查看设置**：设置会显示在摘要中，而不是单击每个单独的步骤。</span><span class="sxs-lookup"><span data-stu-id="79d36-221">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="79d36-222">可以单击每个 **部分** 中的"编辑"跳转回相关页面。</span><span class="sxs-lookup"><span data-stu-id="79d36-222">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="79d36-223">您可以直接在此页面上切换以下设置 **：打开\*\*\*\*或关闭**：</span><span class="sxs-lookup"><span data-stu-id="79d36-223">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="79d36-224">**欺骗筛选器设置**</span><span class="sxs-lookup"><span data-stu-id="79d36-224">**Spoof filter settings**</span></span>
       - <span data-ttu-id="79d36-225">**未经身份验证的发件人设置**</span><span class="sxs-lookup"><span data-stu-id="79d36-225">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="79d36-226">**Actions**</span><span class="sxs-lookup"><span data-stu-id="79d36-226">**Actions**</span></span>

   <span data-ttu-id="79d36-227">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="79d36-227">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="79d36-228">返回到"**编辑策略"页面 \<Name\>**，查看设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-228">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="79d36-229">使用安全&合规中心修改默认的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-229">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="79d36-230">默认的防钓鱼策略名为"Office365 反钓鱼默认策略"，它不会显示在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="79d36-230">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="79d36-231">若要修改默认的防钓鱼策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="79d36-231">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="79d36-232">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="79d36-233">在"**反网络钓鱼"页上**，单击"**默认策略"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-233">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="79d36-234">将显示 **"编辑你的策略 Office365 反语言默认"** 页。</span><span class="sxs-lookup"><span data-stu-id="79d36-234">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="79d36-235">只有 **"欺骗** "部分可用，其中包含修改自定义策略 [时相同的设置](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="79d36-235">Only the **Spoof** section is available, which contains identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   <span data-ttu-id="79d36-236">修改默认策略时，以下设置不可用：</span><span class="sxs-lookup"><span data-stu-id="79d36-236">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="79d36-237">You can see the **Policy setting section** and values， but there's no **Edit** link， so you can't modify the settings (policy name， description， and who the policy applies to (it applies to all recipients) ) .</span><span class="sxs-lookup"><span data-stu-id="79d36-237">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="79d36-238">不能删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-238">You can't delete the default policy.</span></span>
   - <span data-ttu-id="79d36-239">你无法更改默认策略的优先级 (它始终在上次应用) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-239">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="79d36-240">在"**编辑策略 Office365 反默认** 策略"页上，查看设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-240">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="79d36-241">启用或禁用自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-241">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="79d36-242">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-242">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="79d36-243">请注意"状态" **列中** 的值：</span><span class="sxs-lookup"><span data-stu-id="79d36-243">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="79d36-244">将切换开关滑动 **到"关闭** ![ ""关闭 ](../../media/scc-toggle-off.png) "以禁用该策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-244">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="79d36-245">将切换开关滑动 **到"打开** ![ "" ](../../media/scc-toggle-on.png) 打开"以启用策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-245">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="79d36-246">无法禁用默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-246">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="79d36-247">设置自定义防钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="79d36-247">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="79d36-248">默认情况下，基于反网络钓鱼策略在 (较旧策略中创建的顺序，反网络钓鱼策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-248">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="79d36-249">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="79d36-249">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="79d36-250">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="79d36-250">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="79d36-251">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="79d36-251">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="79d36-252">自定义防钓鱼策略按照其处理顺序显示， (策略的优先级值为 0) 。 </span><span class="sxs-lookup"><span data-stu-id="79d36-252">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="79d36-253">名为"Office365 反钓鱼默认"的默认防钓鱼策略具有自定义优先级值 **"** 最低"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="79d36-253">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="79d36-254">**注意**：在安全&合规中心，只能在创建后更改反网络钓鱼策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="79d36-254">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="79d36-255">在 PowerShell 中，您可以在创建反网络钓鱼规则策略时替代默认优先级 (这可能会影响现有规则集的) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-255">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="79d36-256">若要更改策略的优先级，请单击策略属性中的"增加优先级"或"减少优先级 (你无法直接修改安全与合规中心&优先级) 。 </span><span class="sxs-lookup"><span data-stu-id="79d36-256">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="79d36-257">更改策略的优先级仅在有多个策略时有意义。</span><span class="sxs-lookup"><span data-stu-id="79d36-257">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="79d36-258">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="79d36-259">选择要修改的策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-259">Select the policy that you want to modify.</span></span> <span data-ttu-id="79d36-260">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="79d36-260">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="79d36-261">将显示 **"编辑策略 \<name\>**"飞出控件。</span><span class="sxs-lookup"><span data-stu-id="79d36-261">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="79d36-262">优先级值为 **0** 的自定义防钓鱼策略仅具有"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="79d36-262">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="79d36-263">优先级值最低的自定义防钓鱼策略 (例如 **，3**) 只有"增加优先级 **"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="79d36-263">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="79d36-264">如果你有三个或多个自定义防钓鱼策略，则优先级最高的值和最低优先级值之间的策略同时具有"增加优先级"和"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="79d36-264">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="79d36-265">单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。</span><span class="sxs-lookup"><span data-stu-id="79d36-265">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="79d36-266">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="79d36-266">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="79d36-267">使用安全&中心查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-267">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="79d36-268">在安全&中心，转到"**威胁** 管理策略 \>  \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-268">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="79d36-269">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="79d36-269">Do one of the following steps:</span></span>

   - <span data-ttu-id="79d36-270">选择要查看的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-270">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="79d36-271">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="79d36-271">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="79d36-272">单击 **"默认** 策略"以查看默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-272">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="79d36-273">将出现 **"编辑策略 \<name\>**"飞出控件，可在其中查看设置和值。</span><span class="sxs-lookup"><span data-stu-id="79d36-273">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="79d36-274">使用安全&合规中心删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-274">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="79d36-275">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="79d36-276">选择要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-276">Select the policy that you want to remove.</span></span> <span data-ttu-id="79d36-277">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="79d36-277">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="79d36-278">在出现的 **"编辑策略 \<name\>**"飞出控件中，单击"删除策略"，然后在出现的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="79d36-278">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="79d36-279">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="79d36-280">使用 Exchange Online PowerShell 配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-280">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="79d36-281">如前所述，防钓鱼策略由防钓鱼策略和防钓鱼规则组成。</span><span class="sxs-lookup"><span data-stu-id="79d36-281">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="79d36-282">在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="79d36-282">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="79d36-283">您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-283">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="79d36-284">在 PowerShell 中，首先创建防钓鱼策略，然后创建标识该规则所适用的策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-284">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="79d36-285">在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="79d36-285">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="79d36-286">从 PowerShell 删除防钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="79d36-286">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="79d36-287">以下 PowerShell 过程不适用于使用 PowerShell 的独立 EOP Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="79d36-287">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="79d36-288">使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-288">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="79d36-289">在 PowerShell 中创建防钓鱼策略的过程包括两个步骤：</span><span class="sxs-lookup"><span data-stu-id="79d36-289">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="79d36-290">创建防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-290">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="79d36-291">创建指定该规则所适用的防钓鱼策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-291">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="79d36-292">**注意**：</span><span class="sxs-lookup"><span data-stu-id="79d36-292">**Notes**:</span></span>

- <span data-ttu-id="79d36-293">你可以创建新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-293">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="79d36-294">反网络钓鱼规则不能与多个防钓鱼策略关联。</span><span class="sxs-lookup"><span data-stu-id="79d36-294">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="79d36-295">可以在 PowerShell 中的新防钓鱼策略上配置以下设置，这些设置在创建策略之前&安全与合规中心内不可用：</span><span class="sxs-lookup"><span data-stu-id="79d36-295">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="79d36-296">在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-296">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="79d36-297">在 _\<Number\>_ **New-AntiPhishRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-297">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="79d36-298">在安全与合规中心内看不到在 PowerShell 中创建的新防钓鱼策略&策略分配给防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-298">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="79d36-299">步骤 1：使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-299">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="79d36-300">若要创建防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-300">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="79d36-301">本示例将创建一个名为"Research Quarantine"的防钓鱼策略，并具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="79d36-301">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="79d36-302">描述为：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-302">The description is: Research department policy.</span></span>
- <span data-ttu-id="79d36-303">将欺骗的默认操作更改为隔离。</span><span class="sxs-lookup"><span data-stu-id="79d36-303">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="79d36-304">有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="79d36-304">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="79d36-305">步骤 2：使用 PowerShell 创建防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="79d36-305">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="79d36-306">若要创建防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-306">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="79d36-307">本示例创建一个名为"Research Department"的防钓鱼规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="79d36-307">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="79d36-308">该规则与名为"研究隔离"的防钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="79d36-308">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="79d36-309">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="79d36-309">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="79d36-310">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="79d36-310">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="79d36-311">有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="79d36-311">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="79d36-312">使用 PowerShell 查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-312">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="79d36-313">若要查看现有的防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-313">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="79d36-314">此示例返回所有防钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="79d36-314">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="79d36-315">此示例返回名为 Executives 的反网络钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="79d36-315">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="79d36-316">有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="79d36-316">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="79d36-317">使用 PowerShell 查看防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="79d36-317">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="79d36-318">若要查看现有的防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-318">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="79d36-319">此示例返回所有防钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="79d36-319">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="79d36-320">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="79d36-320">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="79d36-321">此示例返回名为 Contoso Executives 的防钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="79d36-321">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="79d36-322">有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="79d36-322">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="79d36-323">使用 PowerShell 修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-323">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="79d36-324">除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建防钓鱼策略中所述。</span><span class="sxs-lookup"><span data-stu-id="79d36-324">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="79d36-325">_MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终最低，并且只有修改 PowerShell 中的防钓鱼策略时) 才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="79d36-325">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="79d36-326">如果 **Set-AntiPhishPolicy** cmdlet 没有 Name 参数 (，则不能重命名反网络钓鱼) 。 </span><span class="sxs-lookup"><span data-stu-id="79d36-326">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="79d36-327">在安全与合规中心内重命名防钓鱼&，只需重命名防钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="79d36-327">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="79d36-328">要修改防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-328">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="79d36-329">有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="79d36-329">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="79d36-330">使用 PowerShell 修改防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="79d36-330">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="79d36-331">在 PowerShell 中修改防钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="79d36-331">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="79d36-332">若要启用或禁用现有防钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="79d36-332">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="79d36-333">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="79d36-333">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="79d36-334">要修改防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-334">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="79d36-335">有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="79d36-335">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="79d36-336">使用 PowerShell 启用或禁用防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="79d36-336">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="79d36-337">在 PowerShell 中启用或禁用反网络钓鱼规则可启用或禁用整个防钓鱼策略 (以及分配的防钓鱼策略策略) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-337">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="79d36-338">无法启用或禁用默认反网络钓鱼策略 (该策略始终应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="79d36-338">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="79d36-339">若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-339">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="79d36-340">本示例禁用名为"Marketing Department"的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-340">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="79d36-341">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-341">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="79d36-342">有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="79d36-342">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="79d36-343">使用 PowerShell 设置防钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="79d36-343">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="79d36-344">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="79d36-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="79d36-345">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="79d36-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="79d36-346">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="79d36-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="79d36-347">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="79d36-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="79d36-348">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="79d36-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="79d36-349">若要在 PowerShell 中设置防钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-349">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="79d36-350">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="79d36-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="79d36-351">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="79d36-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="79d36-352">**注意**：</span><span class="sxs-lookup"><span data-stu-id="79d36-352">**Notes**:</span></span>

- <span data-ttu-id="79d36-353">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-AntiPhishRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="79d36-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="79d36-354">默认防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="79d36-354">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="79d36-355">使用 PowerShell 删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="79d36-355">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="79d36-356">使用 PowerShell 删除防钓鱼策略时，不会删除相应的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-356">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="79d36-357">若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-357">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="79d36-358">此示例删除名为 Marketing Department 的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-358">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="79d36-359">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="79d36-359">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="79d36-360">使用 PowerShell 删除防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="79d36-360">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="79d36-361">使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="79d36-361">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="79d36-362">若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="79d36-362">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="79d36-363">此示例删除名为 Marketing Department 的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="79d36-363">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="79d36-364">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="79d36-364">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="79d36-365">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="79d36-365">How do you know these procedures worked?</span></span>

<span data-ttu-id="79d36-366">若要验证您是否已成功在 Microsoft Defender for Office 365配置防钓鱼策略，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="79d36-366">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="79d36-367">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="79d36-367">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="79d36-368">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="79d36-368">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="79d36-369">若要查看更多详细信息，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="79d36-369">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="79d36-370">从列表中选择策略，并查看该飞出内容中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="79d36-370">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="79d36-371">单击 **"默认** 策略"，在飞出视图中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="79d36-371">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="79d36-372">在 Exchange Online PowerShell 中，将 替换为策略或规则的名称，运行 \<Name\> 以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="79d36-372">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```