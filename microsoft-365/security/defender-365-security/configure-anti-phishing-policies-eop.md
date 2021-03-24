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
description: 管理员可以了解如何创建、修改和删除 Exchange Online Protection (EOP) （具有或没有 Exchange Online 邮箱）中提供的防钓鱼策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c277558bad32e1926030483d202b70ae3c910315
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055741"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="2f120-103">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="2f120-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2f120-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2f120-104">**Applies to**</span></span>
- [<span data-ttu-id="2f120-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2f120-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="2f120-106">在具有 Exchange Online 邮箱或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，有一个默认的反网络钓鱼策略，其中包含有限数量的默认情况下启用的反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="2f120-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="2f120-107">有关详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="2f120-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="2f120-108">管理员可以查看、编辑和配置 (，但不能) 默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="2f120-109">更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="2f120-110">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="2f120-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="2f120-111">具有 Exchange Online 邮箱的组织可以在安全与合规中心或 Exchange Online &配置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="2f120-112">独立 EOP 组织只能使用安全&中心。</span><span class="sxs-lookup"><span data-stu-id="2f120-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="2f120-113">有关在适用于 Office 365 的 Defender 中可用的 Microsoft Defender for Office 365 创建和修改更高级反网络钓鱼策略的信息，请参阅在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="2f120-114">防钓鱼策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="2f120-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="2f120-115">**防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="2f120-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="2f120-116">**防钓鱼** 规则 ：指定策略应用于 (策略的收件人筛选器) 策略的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="2f120-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="2f120-117">在安全与合规中心内管理防钓鱼策略时，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="2f120-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2f120-118">创建防钓鱼策略时，实际上是同时使用同一名称创建反网络钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="2f120-119">修改防钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="2f120-120">所有其他设置修改关联的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="2f120-121">删除防钓鱼策略时，会删除防钓鱼规则及相关的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="2f120-122">在 Exchange Online PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="2f120-123">有关详细信息，请参阅本文稍后介绍的使用 [Exchange Online PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 配置防钓鱼策略一节。</span><span class="sxs-lookup"><span data-stu-id="2f120-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="2f120-124">每个组织都有一个名为 Office365 AntiPhish Default 的内置防钓鱼策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="2f120-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="2f120-125">即使与策略关联的收件人筛选器没有反网络钓鱼规则， (应用于组织) 所有收件人。</span><span class="sxs-lookup"><span data-stu-id="2f120-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="2f120-126">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="2f120-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="2f120-127">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="2f120-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="2f120-128">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="2f120-129">若要提高防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f120-130">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2f120-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f120-131">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="2f120-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2f120-132">若要直接转到" **防钓鱼"页面** ，请使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="2f120-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="2f120-133">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2f120-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="2f120-134">你无法管理独立 EOP PowerShell 中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="2f120-135">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="2f120-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2f120-136">若要添加、修改和删除防钓鱼策略，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="2f120-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2f120-137">若要对防钓鱼策略进行只读访问，你需要是全局读者或 **安全读者角色\*\*\*\*组的成员** <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="2f120-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="2f120-138">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="2f120-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="2f120-139">**注意**：</span><span class="sxs-lookup"><span data-stu-id="2f120-139">**Notes**:</span></span>

  - <span data-ttu-id="2f120-140">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="2f120-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2f120-141">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="2f120-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="2f120-142">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) **中的"** 仅查看组织管理"角色组还授予对该功能的只读访问权限 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="2f120-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="2f120-143"><sup>\*</sup> 在安全&合规中心，只读访问允许用户查看自定义防钓鱼策略的设置。</span><span class="sxs-lookup"><span data-stu-id="2f120-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="2f120-144">只读用户看不到默认防钓鱼策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="2f120-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="2f120-145">若要在独立 EOP 中创建和修改防钓鱼策略，需要执行一些需要租户 _冻结操作_ 。</span><span class="sxs-lookup"><span data-stu-id="2f120-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="2f120-146">例如，在 Exchange 管理中心 (EAC) 中，可以转到"权限"选项卡，选择现有角色组，单击"编辑编辑"图标，然后删除角色 (你最终将添加回 ![ ](../../media/ITPro-EAC-EditIcon.png)) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="2f120-147">如果你的租户从未被冻结，你将看到一个名为"更新组织设置"的对话框，其进度栏应该成功完成。</span><span class="sxs-lookup"><span data-stu-id="2f120-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="2f120-148">有关冻结详细信息，请参阅 [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (该 cmdlet 在独立 EOP PowerShell 或安全与合规中心 & 中) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="2f120-149">有关建议的反网络钓鱼策略设置，请参阅 [EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="2f120-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="2f120-150">最多允许应用更新的策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="2f120-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="2f120-151">有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="2f120-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="2f120-152">使用安全&中心创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="2f120-153">在安全与合规中心内创建自定义防钓鱼策略&使用相同的名称同时创建防钓鱼规则和相关防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="2f120-154">创建防钓鱼策略时，只能指定策略名称、说明和收件人筛选器，以标识策略的适用者。</span><span class="sxs-lookup"><span data-stu-id="2f120-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="2f120-155">创建策略后，可以修改该策略以更改或查看默认的防钓鱼设置。</span><span class="sxs-lookup"><span data-stu-id="2f120-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="2f120-156">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2f120-157">在"**防钓鱼"页上，** 单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="2f120-158">将 **打开"创建新的防钓鱼策略"** 向导。</span><span class="sxs-lookup"><span data-stu-id="2f120-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="2f120-159">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2f120-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="2f120-160">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="2f120-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="2f120-161">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="2f120-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="2f120-162">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="2f120-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2f120-163">在 **出现的"应用于** "页上，标识策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="2f120-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="2f120-164">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="2f120-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="2f120-165">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="2f120-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="2f120-166">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="2f120-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="2f120-167">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-167">Click **Add a condition**.</span></span> <span data-ttu-id="2f120-168">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="2f120-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="2f120-169">**收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="2f120-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="2f120-170">**收件人是 ：指定** 组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="2f120-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="2f120-171">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="2f120-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="2f120-172">选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。</span><span class="sxs-lookup"><span data-stu-id="2f120-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="2f120-173">在框中单击并滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="2f120-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="2f120-174">在框中单击并开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="2f120-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="2f120-175">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="2f120-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="2f120-176">若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="2f120-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="2f120-177">若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="2f120-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="2f120-178">若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。</span><span class="sxs-lookup"><span data-stu-id="2f120-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="2f120-179">若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。</span><span class="sxs-lookup"><span data-stu-id="2f120-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="2f120-180">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="2f120-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="2f120-181">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="2f120-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2f120-182">在出现的 **"查看设置** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="2f120-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="2f120-183">可以单击每个 **设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="2f120-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="2f120-184">完成后，单击"创建 **此策略"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="2f120-185">在 **出现的** 确认对话框中单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="2f120-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="2f120-186">使用这些常规策略设置创建防钓鱼策略后，请使用下一节中的说明配置策略中的保护设置。</span><span class="sxs-lookup"><span data-stu-id="2f120-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="2f120-187">使用安全&合规中心修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="2f120-188">使用以下过程可修改防钓鱼策略：您创建的新策略或已自定义的现有策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="2f120-189">如果尚未开始，请打开安全与合规&，然后转到威胁管理 \> **策略** \> **防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="2f120-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2f120-190">选择要修改的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="2f120-191">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="2f120-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2f120-192">将显示 **"编辑策略 \<name\>**"飞出控件。</span><span class="sxs-lookup"><span data-stu-id="2f120-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="2f120-193">单击 **任何** 部分中的"编辑"，即可访问该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="2f120-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="2f120-194">以下步骤按各节的显示顺序显示，但它们不是按顺序 (您可以按任意顺序选择和修改) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="2f120-195">在部分中单击"编辑"后，可用设置以向导格式显示，但您可以按任意顺序跳转到页面内，并且您可以单击任何页面的"保存" (或 ![ ](../../media/scc-remove-icon.png) **\<name\>**"取消"或"关闭"图标返回到"编辑策略"页面 (无需访问向导的最后一页即可保存或离开) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="2f120-196">**策略设置\*\*\*\*：单击**"编辑"修改在上一部分中创建 [策略时可用的](#use-the-security--compliance-center-to-create-anti-phishing-policies)相同设置：</span><span class="sxs-lookup"><span data-stu-id="2f120-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="2f120-197">**名称**</span><span class="sxs-lookup"><span data-stu-id="2f120-197">**Name**</span></span>
   - <span data-ttu-id="2f120-198">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f120-198">**Description**</span></span>
   - <span data-ttu-id="2f120-199">**应用于**</span><span class="sxs-lookup"><span data-stu-id="2f120-199">**Applied to**</span></span>
   - <span data-ttu-id="2f120-200">**查看设置**</span><span class="sxs-lookup"><span data-stu-id="2f120-200">**Review your settings**</span></span>

   <span data-ttu-id="2f120-201">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="2f120-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="2f120-202">**欺骗**：单击"编辑"打开或关闭欺骗智能，打开或关闭 Outlook 中的未经身份验证的发件人标识，并配置操作以应用于来自被阻止的欺骗发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="2f120-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="2f120-203">有关详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="2f120-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="2f120-204">请注意，这些相同的设置也可在 Defender for Office 365 中的防钓鱼策略中提供。</span><span class="sxs-lookup"><span data-stu-id="2f120-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="2f120-205">**欺骗筛选器设置**：默认值为 **"开**"，建议保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="2f120-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="2f120-206">若要关闭它，将切换开关滑动到 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="2f120-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="2f120-207">有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="2f120-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="2f120-208">如果你的 MX 记录不指向 Microsoft 365，你无需禁用反欺骗保护;改为启用连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="2f120-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="2f120-209">有关说明，请参阅 [增强的 Exchange Online 中的连接器筛选](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="2f120-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="2f120-210">**启用未经身份验证的发件人功能**：默认值为 **On**。</span><span class="sxs-lookup"><span data-stu-id="2f120-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="2f120-211">若要关闭它，将切换开关滑动到 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="2f120-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="2f120-212">**操作**：指定对未通过欺骗智能的邮件采取的操作：</span><span class="sxs-lookup"><span data-stu-id="2f120-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="2f120-213">**如果电子邮件是由不允许欺骗你的域的人发送的**：</span><span class="sxs-lookup"><span data-stu-id="2f120-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="2f120-214">**将邮件移动到收件人的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="2f120-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="2f120-215">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="2f120-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="2f120-216">**查看设置**：设置会显示在摘要中，而不是单击每个单独的步骤。</span><span class="sxs-lookup"><span data-stu-id="2f120-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="2f120-217">可以单击每个 **部分** 中的"编辑"跳转回相关页面。</span><span class="sxs-lookup"><span data-stu-id="2f120-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="2f120-218">您可以直接在此页面上切换以下设置 **：打开\*\*\*\*或关闭**：</span><span class="sxs-lookup"><span data-stu-id="2f120-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="2f120-219">**启用反应答保护**</span><span class="sxs-lookup"><span data-stu-id="2f120-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="2f120-220">**启用未经身份验证的发件人功能**</span><span class="sxs-lookup"><span data-stu-id="2f120-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="2f120-221">完成后，单击任意 **页面上** 的"保存"。</span><span class="sxs-lookup"><span data-stu-id="2f120-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="2f120-222">返回到"**编辑策略"页面 \<Name\>**，查看设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="2f120-223">使用安全&合规中心修改默认的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="2f120-224">默认的防钓鱼策略名为"Office365 反钓鱼默认策略"，它不会显示在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="2f120-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="2f120-225">若要修改默认的防钓鱼策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2f120-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="2f120-226">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2f120-227">在"**反网络钓鱼"页上**，单击"**默认策略"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="2f120-228">将显示 **"编辑你的策略 Office365 反语言默认"** 页。</span><span class="sxs-lookup"><span data-stu-id="2f120-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="2f120-229">以下各节可用，其中包含修改自定义策略 [时相同的设置](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="2f120-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="2f120-230">**模拟**</span><span class="sxs-lookup"><span data-stu-id="2f120-230">**Impersonation**</span></span>
   - <span data-ttu-id="2f120-231">**欺骗**</span><span class="sxs-lookup"><span data-stu-id="2f120-231">**Spoof**</span></span>
   - <span data-ttu-id="2f120-232">**高级设置**</span><span class="sxs-lookup"><span data-stu-id="2f120-232">**Advanced settings**</span></span>

   <span data-ttu-id="2f120-233">修改默认策略时，以下设置不可用：</span><span class="sxs-lookup"><span data-stu-id="2f120-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="2f120-234">You can see the **Policy setting section** and values， but there's no **Edit** link， so you can't modify the settings (policy name， description， and who the policy applies to (it applies to all recipients) ) .</span><span class="sxs-lookup"><span data-stu-id="2f120-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="2f120-235">不能删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="2f120-236">你无法更改默认策略的优先级 (它始终在上次应用) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="2f120-237">在"**编辑策略 Office365 反默认** 策略"页上，查看设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="2f120-238">启用或禁用自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="2f120-239">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2f120-240">请注意"状态" **列中** 的值：</span><span class="sxs-lookup"><span data-stu-id="2f120-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="2f120-241">将开关滑动到 **"关闭"** 以禁用该策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="2f120-242">将切换开关滑动 **到"打开** "以启用策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="2f120-243">无法禁用默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="2f120-244">设置自定义防钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="2f120-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="2f120-245">默认情况下，基于反网络钓鱼策略在 (较旧策略中创建的顺序，反网络钓鱼策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="2f120-246">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="2f120-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="2f120-247">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="2f120-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="2f120-248">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="2f120-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="2f120-249">自定义防钓鱼策略按照其处理顺序显示， (策略的优先级值为 0) 。 </span><span class="sxs-lookup"><span data-stu-id="2f120-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="2f120-250">名为"Office365 反钓鱼默认"的默认防钓鱼策略具有自定义优先级值 **"** 最低"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="2f120-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="2f120-251">**注意**：在安全&合规中心，只能在创建后更改反网络钓鱼策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="2f120-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="2f120-252">在 PowerShell 中，您可以在创建反网络钓鱼规则策略时替代默认优先级 (这可能会影响现有规则集的) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="2f120-253">若要更改策略的优先级，请单击策略属性中的"增加优先级"或"减少优先级 (你无法直接修改安全与合规中心&优先级) 。 </span><span class="sxs-lookup"><span data-stu-id="2f120-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="2f120-254">更改策略的优先级仅在有多个策略时有意义。</span><span class="sxs-lookup"><span data-stu-id="2f120-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="2f120-255">在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="2f120-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="2f120-256">选择要修改的策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="2f120-257">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="2f120-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2f120-258">将显示 **"编辑策略 \<name\>**"飞出控件。</span><span class="sxs-lookup"><span data-stu-id="2f120-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="2f120-259">优先级值为 **0** 的自定义防钓鱼策略仅具有"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2f120-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="2f120-260">优先级值最低的自定义防钓鱼策略 (例如 **，3**) 只有"增加优先级 **"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="2f120-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="2f120-261">如果你有三个或多个自定义防钓鱼策略，则优先级最高的值和最低优先级值之间的策略同时具有"增加优先级"和"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2f120-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="2f120-262">单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。</span><span class="sxs-lookup"><span data-stu-id="2f120-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="2f120-263">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="2f120-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="2f120-264">使用安全&中心查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="2f120-265">在安全&中心，转到"**威胁** 管理策略 \>  \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2f120-266">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="2f120-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="2f120-267">选择要查看的自定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="2f120-268">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="2f120-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="2f120-269">单击 **"默认** 策略"以查看默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="2f120-270">将出现 **"编辑策略 \<name\>**"飞出控件，可在其中查看设置和值。</span><span class="sxs-lookup"><span data-stu-id="2f120-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="2f120-271">使用安全&合规中心删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="2f120-272">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2f120-273">选择要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="2f120-274">如果已选择，请取消选择它，然后再次选择它。</span><span class="sxs-lookup"><span data-stu-id="2f120-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2f120-275">在出现的 **"编辑策略 \<name\>**"飞出控件中，单击"删除策略"，然后在出现的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="2f120-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="2f120-276">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="2f120-277">使用 Exchange Online PowerShell 配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="2f120-278">如前所述，防钓鱼策略由防钓鱼策略和防钓鱼规则组成。</span><span class="sxs-lookup"><span data-stu-id="2f120-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="2f120-279">在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="2f120-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="2f120-280">您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="2f120-281">在 PowerShell 中，首先创建防钓鱼策略，然后创建标识该规则所适用的策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="2f120-282">在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="2f120-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="2f120-283">从 PowerShell 删除防钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="2f120-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="2f120-284">以下 PowerShell 过程不适用于使用 Exchange Online Protection PowerShell 的独立 EOP 组织。</span><span class="sxs-lookup"><span data-stu-id="2f120-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="2f120-285">使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="2f120-286">在 PowerShell 中创建防钓鱼策略的过程包括两个步骤：</span><span class="sxs-lookup"><span data-stu-id="2f120-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="2f120-287">创建防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="2f120-288">创建指定该规则所适用的防钓鱼策略的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="2f120-289">**注意**：</span><span class="sxs-lookup"><span data-stu-id="2f120-289">**Notes**:</span></span>

- <span data-ttu-id="2f120-290">你可以创建新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="2f120-291">反网络钓鱼规则不能与多个防钓鱼策略关联。</span><span class="sxs-lookup"><span data-stu-id="2f120-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="2f120-292">可以在 PowerShell 中的新防钓鱼策略上配置以下设置，这些设置在创建策略之前&安全与合规中心内不可用：</span><span class="sxs-lookup"><span data-stu-id="2f120-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="2f120-293">在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="2f120-294">在 _\<Number\>_ **New-AntiPhishRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="2f120-295">在安全与合规中心内看不到在 PowerShell 中创建的新防钓鱼策略&策略分配给防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="2f120-296">步骤 1：使用 PowerShell 创建防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="2f120-297">若要创建防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="2f120-298">本示例将创建一个名为"Research Quarantine"的防钓鱼策略，并具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="2f120-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="2f120-299">描述为：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="2f120-300">将欺骗的默认操作更改为隔离。</span><span class="sxs-lookup"><span data-stu-id="2f120-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="2f120-301">有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="2f120-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="2f120-302">步骤 2：使用 PowerShell 创建防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="2f120-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="2f120-303">若要创建防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="2f120-304">本示例创建一个名为"Research Department"的防钓鱼规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="2f120-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="2f120-305">该规则与名为"研究隔离"的防钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="2f120-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="2f120-306">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="2f120-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="2f120-307">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="2f120-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="2f120-308">有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="2f120-308">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="2f120-309">使用 PowerShell 查看防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="2f120-310">若要查看现有的防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2f120-311">此示例返回所有防钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="2f120-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="2f120-312">此示例返回名为 Executives 的反网络钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="2f120-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="2f120-313">有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="2f120-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="2f120-314">使用 PowerShell 查看防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="2f120-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="2f120-315">若要查看现有的防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2f120-316">此示例返回所有防钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="2f120-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="2f120-317">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2f120-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="2f120-318">此示例返回名为 Contoso Executives 的防钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="2f120-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="2f120-319">有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="2f120-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="2f120-320">使用 PowerShell 修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="2f120-321">除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建防钓鱼策略中所述。</span><span class="sxs-lookup"><span data-stu-id="2f120-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="2f120-322">_MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终最低，并且只有修改 PowerShell 中的防钓鱼策略时) 才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="2f120-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="2f120-323">如果 **Set-AntiPhishPolicy** cmdlet 没有 Name 参数 (，则不能重命名反网络钓鱼) 。 </span><span class="sxs-lookup"><span data-stu-id="2f120-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="2f120-324">在安全与合规中心内重命名防钓鱼&，只需重命名防钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="2f120-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="2f120-325">要修改防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="2f120-326">有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="2f120-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="2f120-327">使用 PowerShell 修改防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="2f120-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="2f120-328">在 PowerShell 中修改防钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="2f120-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="2f120-329">若要启用或禁用现有防钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="2f120-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="2f120-330">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="2f120-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="2f120-331">要修改防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="2f120-332">有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="2f120-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="2f120-333">使用 PowerShell 启用或禁用防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="2f120-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="2f120-334">在 PowerShell 中启用或禁用反网络钓鱼规则可启用或禁用整个防钓鱼策略 (以及分配的防钓鱼策略策略) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="2f120-335">无法启用或禁用默认反网络钓鱼策略 (该策略始终应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="2f120-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="2f120-336">若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="2f120-337">本示例禁用名为"Marketing Department"的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2f120-338">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2f120-339">有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="2f120-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="2f120-340">使用 PowerShell 设置防钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="2f120-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="2f120-341">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="2f120-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="2f120-342">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="2f120-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="2f120-343">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="2f120-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="2f120-344">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="2f120-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="2f120-345">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="2f120-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="2f120-346">若要在 PowerShell 中设置防钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="2f120-347">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="2f120-347">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="2f120-348">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="2f120-348">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="2f120-349">**注意**：</span><span class="sxs-lookup"><span data-stu-id="2f120-349">**Notes**:</span></span>

- <span data-ttu-id="2f120-350">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-AntiPhishRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="2f120-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="2f120-351">默认防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="2f120-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="2f120-352">使用 PowerShell 删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2f120-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="2f120-353">使用 PowerShell 删除防钓鱼策略时，不会删除相应的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="2f120-354">若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="2f120-355">此示例删除名为 Marketing Department 的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="2f120-356">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="2f120-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="2f120-357">使用 PowerShell 删除防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="2f120-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="2f120-358">使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2f120-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="2f120-359">若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f120-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="2f120-360">此示例删除名为 Marketing Department 的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="2f120-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2f120-361">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="2f120-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2f120-362">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="2f120-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="2f120-363">若要验证您是否已成功在 Microsoft Defender for Office 365 中配置防钓鱼策略，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="2f120-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="2f120-364">在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f120-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="2f120-365">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="2f120-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="2f120-366">若要查看更多详细信息，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="2f120-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="2f120-367">从列表中选择策略，并查看该飞出内容中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f120-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="2f120-368">单击 **"默认** 策略"，在飞出视图中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f120-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="2f120-369">在 Exchange Online PowerShell 中，将 替换为策略或规则的名称，运行 \<Name\> 以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="2f120-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```