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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建、修改和删除 Exchange Online Protection (EOP 中提供的反网络钓鱼策略，以及具有或不包含 Exchange Online 邮箱的组织) 组织。
ms.openlocfilehash: 69ab17263ab8c0cc03d3bc4aed6bdf39b251b9fb
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572521"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="ad8dd-103">在 EOP 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ad8dd-104">在 Exchange Online 中有邮箱或独立 Exchange Online 保护的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，有一个默认的反网络钓鱼策略，其中包含默认情况下启用的有限数量的反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="ad8dd-105">有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="ad8dd-106">管理员可以查看、编辑和配置 (，但不能删除默认的反网络钓鱼策略) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="ad8dd-107">为了更细致，您还可以创建适用于组织中的特定用户、组或域的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ad8dd-108">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ad8dd-109">具有 Exchange Online 邮箱的组织可以在安全 & 合规中心或 Exchange Online PowerShell 中配置反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="ad8dd-110">独立 EOP 组织只能使用安全 & 合规中心。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="ad8dd-111">有关在 Microsoft Defender for office 365 中创建和修改更高级的反网络钓鱼策略的信息，可在适用于 office 的 Defender for office 365 中进行配置，请参阅 [在 Microsoft defender For office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-111">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="ad8dd-112">反网络钓鱼策略的基本元素为：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="ad8dd-113">**反网络钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及要应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="ad8dd-114">**反网络钓鱼规则**：指定策略应用于) 反网络钓鱼策略的 (的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ad8dd-115">在安全 & 合规中心中管理反网络钓鱼策略时，这两个元素之间的差异并不明显：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ad8dd-116">创建反网络钓鱼策略时，实际上是使用相同的名称同时创建反网络钓鱼规则和关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ad8dd-117">修改反网络钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ad8dd-118">所有其他设置将修改关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="ad8dd-119">删除反网络钓鱼策略时，将删除反网络钓鱼规则和关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ad8dd-120">在 Exchange Online PowerShell 中，可以单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ad8dd-121">有关详细信息，请参阅本文后面的 [使用 Exchange Online PowerShell 配置反网络钓鱼策略](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 一节。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="ad8dd-122">每个组织都有一个名为 Office365 AntiPhish 的内置反网络钓鱼策略，默认情况下具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ad8dd-123">该策略将应用于组织中的所有收件人，即使没有反网络钓鱼规则 (收件人筛选器与策略关联) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ad8dd-124">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ad8dd-125">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ad8dd-126">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ad8dd-127">若要提高反网络钓鱼保护的有效性，可以创建具有应用于特定用户或用户组的更严格设置的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad8dd-128">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="ad8dd-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad8dd-129">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ad8dd-130">若要直接转到 " **反钓鱼** " 页面，请使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ad8dd-131">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="ad8dd-132">您无法在独立 EOP PowerShell 中管理反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="ad8dd-133">您需要在安全 & 合规性中心中分配权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-133">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ad8dd-134">若要添加、修改和删除反网络钓鱼策略，您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-134">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ad8dd-135">若要对反网络钓鱼策略进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-135">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="ad8dd-136">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ad8dd-137">**注意**：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-137">**Notes**:</span></span>

  - <span data-ttu-id="ad8dd-138">将用户添加到 Microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心的必需权限 _以及_ Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ad8dd-139">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-139">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="ad8dd-140">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**仅查看组织管理**" 角色组也提供了对功能的只读访问权限 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-140">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="ad8dd-141"><sup>\*</sup> 在安全 & 合规性中心中，只读访问允许用户查看自定义反网络钓鱼策略的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-141"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="ad8dd-142">只读用户无法查看默认反网络钓鱼策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-142">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="ad8dd-143">若要在独立 EOP 中创建和修改反网络钓鱼策略，您需要为租户执行需要 _水合_ 的操作。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-143">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="ad8dd-144">例如，在 Exchange 管理中心 (EAC) 中，可以转到 " **权限** " 选项卡，选择现有角色组，单击 " **编辑**" "编辑 ![ ](../../media/ITPro-EAC-EditIcon.png) " 图标，然后删除最终将) 添加到其中的角色 (。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-144">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="ad8dd-145">如果您的租户从未 hydrated 过，您将看到一个名为 " **更新组织设置** " 的对话框，其中包含应成功完成的进度栏。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-145">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="ad8dd-146">有关水合的详细信息，请参阅 [OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (，该 cmdlet 在独立 EOP PowerShell 中或安全 & 合规中心) 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-146">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="ad8dd-147">有关反网络钓鱼策略的推荐设置，请参阅 [EOP 默认反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-147">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="ad8dd-148">允许应用更新后的策略最长为30分钟。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-148">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="ad8dd-149">有关在筛选管道中应用反网络钓鱼策略的位置的信息，请参阅 [电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-149">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="ad8dd-150">使用安全 & 合规性中心创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-150">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="ad8dd-151">在安全 & 合规性中心中创建自定义反网络钓鱼策略将同时使用相同的名称创建反钓鱼诈骗规则和关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-151">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="ad8dd-152">创建反网络钓鱼策略时，只能指定策略名称、说明和标识应用策略的收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-152">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="ad8dd-153">创建策略后，您可以修改策略以更改或查看默认的反网络钓鱼设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-153">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="ad8dd-154">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ad8dd-155">在 " **反钓鱼网站** " 页上，单击 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-155">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="ad8dd-156">将打开 " **新建反网络钓鱼策略** " 向导。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-156">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="ad8dd-157">在 " **命名策略** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-157">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ad8dd-158">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-158">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ad8dd-159">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-159">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ad8dd-160">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-160">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ad8dd-161">在显示的 " **应用于** " 页上，确定该策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-161">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ad8dd-162">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-162">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ad8dd-163">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-163">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ad8dd-164">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-164">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="ad8dd-165">单击 " **添加条件**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-165">Click **Add a condition**.</span></span> <span data-ttu-id="ad8dd-166">在出现的下拉列表中，选择 " **应用** 条件：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-166">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="ad8dd-167">**收件人为**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-167">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ad8dd-168">**收件人是的成员**：指定组织中的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-168">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ad8dd-169">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-169">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="ad8dd-170">选择条件后，将显示相应的下拉框，其中包含 **其中的任何** 框。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-170">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ad8dd-171">在框中单击并滚动到要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-171">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ad8dd-172">在框中单击，然后开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-172">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ad8dd-173">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-173">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ad8dd-174">若要删除单个条目， **Remove** 请单击 ![ ](../../media/scc-remove-icon.png) 值上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-174">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ad8dd-175">若要删除整个条件，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-175">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ad8dd-176">若要添加其他条件，请单击 " **添加条件** "，然后选择 " **应用于**" 下的其他值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-176">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ad8dd-177">若要添加例外，请单击 " **添加条件** "，并在 " **除非**" 下选择例外。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-177">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ad8dd-178">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-178">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ad8dd-179">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-179">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ad8dd-180">在显示的 " **查看您的设置** " 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-180">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ad8dd-181">您可以在每个设置上单击 " **编辑** " 以修改它。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-181">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ad8dd-182">完成后，单击 " **创建此策略**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-182">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="ad8dd-183">在出现的确认对话框中，单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-183">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="ad8dd-184">在使用这些常规策略设置创建反网络钓鱼策略后，请按照下一节中的说明操作，在策略中配置保护设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-184">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="ad8dd-185">使用安全 & 合规性中心修改反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-185">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="ad8dd-186">使用以下过程可修改反网络钓鱼策略：创建的新策略或已自定义的现有策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-186">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="ad8dd-187">如果尚不存在，请打开安全 & 合规中心，并转到 **威胁管理** \> **策略** \> **反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-187">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ad8dd-188">选择要修改的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-188">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="ad8dd-189">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-189">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ad8dd-190">将出现 "**编辑 \<name\> 您的策略**" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-190">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="ad8dd-191">单击任意部分中的 " **编辑** " 可访问该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-191">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="ad8dd-192">以下步骤按节的显示顺序显示，但它们不是连续的 (您可以按任意顺序) 选择和修改各节。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-192">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="ad8dd-193">在分区中单击 "**编辑**" 后，可用的设置将以向导格式显示，但您可以按任意顺序在页面中进行跳转，也可以单击任何页面上的 "**保存**" (或 "**取消**" 或 "**关闭** ![ 关闭 ](../../media/scc-remove-icon.png) " 图标，以返回到 " **\<name\> 编辑策略**" 页面 (您无需访问向导的最后一页以保存或离开) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-193">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="ad8dd-194">**策略设置**：单击 " **编辑** " 可修改在上一节中 [创建策略](#use-the-security--compliance-center-to-create-anti-phishing-policies) 时可用的相同设置：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-194">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="ad8dd-195">**名称**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-195">**Name**</span></span>
   - <span data-ttu-id="ad8dd-196">**说明**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-196">**Description**</span></span>
   - <span data-ttu-id="ad8dd-197">**应用于**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-197">**Applied to**</span></span>
   - <span data-ttu-id="ad8dd-198">**查看设置**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-198">**Review your settings**</span></span>

   <span data-ttu-id="ad8dd-199">完成后，请单击任意页面上的 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-199">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="ad8dd-200">**哄骗**：单击 " **编辑** " 以打开或关闭欺骗情报，在 Outlook 中打开或关闭未经身份验证的发件人标识，并将操作配置为应用于阻止的欺骗性发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-200">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="ad8dd-201">有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-201">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="ad8dd-202">请注意，Office 365 的 Defender 中的反网络钓鱼策略中也提供了这些相同的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-202">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="ad8dd-203">**哄骗筛选器设置**：默认值为 **"开**"，我们建议您将其保留在中。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-203">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="ad8dd-204">若要将其关闭，请将开关滑动到 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-204">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="ad8dd-205">有关详细信息，请参阅 [在 EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-205">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="ad8dd-206">如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-206">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ad8dd-207">有关说明，请参阅 [增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-207">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="ad8dd-208">**启用未经身份验证的发件人功能**：默认值为 **打开**。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-208">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="ad8dd-209">若要将其关闭，请将开关滑动到 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-209">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="ad8dd-210">**操作**：指定对欺骗性智能邮件失败的邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-210">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="ad8dd-211">**如果电子邮件由不允许欺骗您的域的人发送**：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-211">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="ad8dd-212">**将邮件移到收件人的 "垃圾邮件" 文件夹**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-212">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="ad8dd-213">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-213">**Quarantine the message**</span></span>

   - <span data-ttu-id="ad8dd-214">**查看设置**：不是单击每个单独的步骤，而是在摘要中显示设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-214">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ad8dd-215">您可以单击每个部分中的 " **编辑** " 以跳回到相关页面。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-215">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ad8dd-216">您可以在此页面 **上\*\*\*\*直接切换** 以下设置：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-216">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ad8dd-217">**启用 antispoofing 保护**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-217">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="ad8dd-218">**启用未经身份验证的发件人功能**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-218">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="ad8dd-219">完成后，请单击任意页面上的 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-219">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="ad8dd-220">返回到 "**编辑你的 \<Name\> 策略**" 页，查看你的设置，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-220">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="ad8dd-221">使用安全 & 合规性中心修改默认的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-221">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="ad8dd-222">默认的反网络钓鱼策略名为 Office365 AntiPhish Default，且不会出现在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-222">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="ad8dd-223">若要修改默认的反网络钓鱼策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-223">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="ad8dd-224">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ad8dd-225">在 " **反钓鱼网站** " 页上，单击 " **默认策略**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-225">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="ad8dd-226">将显示 " **编辑您的策略 Office365 AntiPhish 默认** 页"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-226">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="ad8dd-227">以下各节均可用，其中包含 [修改自定义策略](#use-the-security--compliance-center-to-modify-anti-phishing-policies)时的相同设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-227">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="ad8dd-228">**模拟**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-228">**Impersonation**</span></span>
   - <span data-ttu-id="ad8dd-229">**哄骗**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-229">**Spoof**</span></span>
   - <span data-ttu-id="ad8dd-230">**高级设置**</span><span class="sxs-lookup"><span data-stu-id="ad8dd-230">**Advanced settings**</span></span>

   <span data-ttu-id="ad8dd-231">修改默认策略时，以下设置不可用：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-231">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="ad8dd-232">您可以看到 " **策略设置** " 部分和值，但没有 " **编辑** " 链接，因此不能修改 (策略名称、说明和策略应用于的用户 (它适用于所有收件人) # A3。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-232">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="ad8dd-233">您不能删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-233">You can't delete the default policy.</span></span>
   - <span data-ttu-id="ad8dd-234">您不能更改默认策略的优先级 (它始终应用于最后) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-234">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="ad8dd-235">在 " **编辑策略 Office365 AntiPhish 默认** 页面上，查看您的设置，然后单击" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-235">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="ad8dd-236">启用或禁用自定义反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-236">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="ad8dd-237">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-237">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ad8dd-238">请注意 " **状态** " 列中的值：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-238">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ad8dd-239">将开关滑到 " **关闭** " 以禁用该策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-239">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="ad8dd-240">将切换滑到 **打开** 以启用该策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-240">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="ad8dd-241">您不能禁用默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-241">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="ad8dd-242">设置自定义反网络钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="ad8dd-242">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="ad8dd-243">默认情况下，会为反网络钓鱼策略指定一个优先级，这取决于它们的创建顺序 (较旧策略的优先级低于旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-243">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ad8dd-244">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-244">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ad8dd-245">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-245">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ad8dd-246">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-246">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ad8dd-247">自定义反网络钓鱼策略按其处理顺序显示， (第一个策略的 **优先级** 值为 0) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ad8dd-248">名为 Office365 AntiPhish 的默认反网络钓鱼策略默认的自定义优先级值为 **最低**，无法更改。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="ad8dd-249">**注意**：在安全 & 合规性中心中，您只能在创建后更改反网络钓鱼策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="ad8dd-250">在 PowerShell 中，您可以在创建反网络钓鱼规则时替代默认优先级 (这可能会影响现有规则) 的优先级。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ad8dd-251">若要更改策略的优先级，请在策略的属性中单击 " **提高优先级** " 或 " **降低优先级** " (您不能直接修改安全 & 合规性中心) 中的 **优先级** 号码。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="ad8dd-252">如果有多个策略，则更改策略的优先级仅是有意义的。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ad8dd-253">在 "安全性 & 合规性中心中，转到" **威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ad8dd-254">选择要修改的策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="ad8dd-255">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ad8dd-256">将出现 "**编辑 \<name\> 您的策略**" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="ad8dd-257">**优先级** 值为 **0** 的自定义反网络钓鱼策略只有 "**降低优先级**" 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ad8dd-258">具有最低 **优先级** 值的自定义反网络钓鱼策略 (例如， **3**) 仅有 " **提高优先级** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ad8dd-259">如果您具有三个或更多自定义的反网络钓鱼策略，则在最高和最低优先级值之间的策略将具有 " **增加优先级** " 和 " **降低优先级** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ad8dd-260">单击 " **提高优先级** " 或 " **降低优先级** " 以更改 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ad8dd-261">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="ad8dd-262">使用安全 & 合规性中心查看反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="ad8dd-263">在安全 & 合规性中心，并转到 **威胁管理** \> **策略** \> **反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ad8dd-264">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="ad8dd-265">选择要查看的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="ad8dd-266">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="ad8dd-267">单击 " **默认策略** " 以查看默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="ad8dd-268">将出现 "**编辑 \<name\> 策略**" 浮出控件，您可以在其中查看设置和值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="ad8dd-269">使用安全 & 合规性中心删除反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="ad8dd-270">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ad8dd-271">选择要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="ad8dd-272">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ad8dd-273">在出现的 "**编辑 \<name\> 策略**" 浮出控件中，单击 "**删除策略**"，然后在出现的警告对话框中单击 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ad8dd-274">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="ad8dd-275">使用 Exchange Online PowerShell 配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="ad8dd-276">如前面所述，反网络钓鱼策略由反网络钓鱼策略和反网络钓鱼规则组成。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-276">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="ad8dd-277">在 Exchange Online PowerShell 中，反网络钓鱼策略和反网络钓鱼规则之间的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-277">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ad8dd-278">您可以使用 **\* -AntiPhishPolicy** cmdlet 管理反网络钓鱼策略，并使用 **\* -AntiPhishRule** cmdlet 管理反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-278">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ad8dd-279">在 PowerShell 中，首先创建反网络钓鱼策略，然后创建反网络钓鱼规则来标识应用该规则的策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-279">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ad8dd-280">在 PowerShell 中，可以单独修改反网络钓鱼策略和反钓鱼诈骗规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-280">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="ad8dd-281">从 PowerShell 中删除反网络钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-281">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="ad8dd-282">使用 Exchange Online Protection PowerShell 的独立 EOP 组织中不提供以下 PowerShell 过程。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-282">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ad8dd-283">使用 PowerShell 创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-283">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ad8dd-284">在 PowerShell 中创建反网络钓鱼策略的过程分为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-284">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ad8dd-285">创建反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-285">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="ad8dd-286">创建反网络钓鱼规则，该规则指定应用该规则的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-286">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ad8dd-287">**注意**：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-287">**Notes**:</span></span>

- <span data-ttu-id="ad8dd-288">您可以创建新的反网络钓鱼规则并向其分配现有的未关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-288">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ad8dd-289">反网络钓鱼规则不能与多个反网络钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-289">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="ad8dd-290">您可以在 PowerShell 中的新反网络钓鱼策略中配置以下设置，这些设置在安全 & 合规性中心中不可用，直到您创建了策略：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-290">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ad8dd-291">将新策略创建为 _Enabled_ `$false` **AntiPhishRule** cmdlet) 上启用的禁用 (。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-291">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="ad8dd-292">在 _Priority_ _\<Number\>_ **AntiPhishRule** Cmdlet) 上创建 (优先级) 时设置策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-292">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="ad8dd-293">在 PowerShell 中创建的新反网络钓鱼策略在安全 & 合规性中心中不可见，除非您将策略分配给反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-293">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ad8dd-294">步骤1：使用 PowerShell 创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-294">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ad8dd-295">若要创建反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-295">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="ad8dd-296">本示例将使用以下设置创建名为 "调研隔离" 的反网络钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-296">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ad8dd-297">说明是：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-297">The description is: Research department policy.</span></span>
- <span data-ttu-id="ad8dd-298">将哄骗的默认操作更改为 "隔离"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-298">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="ad8dd-299">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-299">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ad8dd-300">步骤2：使用 PowerShell 创建反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ad8dd-300">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ad8dd-301">若要创建反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-301">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ad8dd-302">本示例将创建一个名为 "研究部门" 的反网络钓鱼规则，条件如下：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-302">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ad8dd-303">该规则与名为 "研究隔离" 的反网络钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-303">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ad8dd-304">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-304">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ad8dd-305">由于我们不使用 _Priority_ 参数，因此使用默认的优先级。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-305">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ad8dd-306">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-306">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ad8dd-307">使用 PowerShell 查看反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-307">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ad8dd-308">若要查看现有的反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-308">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ad8dd-309">本示例返回所有反网络钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-309">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ad8dd-310">本示例将返回名为 "主管" 的反网络钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-310">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ad8dd-311">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-311">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ad8dd-312">使用 PowerShell 查看反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ad8dd-312">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ad8dd-313">若要查看现有的反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-313">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ad8dd-314">本示例返回所有反网络钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-314">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ad8dd-315">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-315">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ad8dd-316">本示例将返回名为 "Contoso 行政主管" 的反网络钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-316">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ad8dd-317">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-317">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ad8dd-318">使用 PowerShell 修改反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-318">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ad8dd-319">除了以下项目之外，当您在 PowerShell 中按照 [步骤1：使用 PowerShell 创建反网络钓鱼策略](#step-1-use-powershell-to-create-an-anti-phish-policy) 中所述，在创建策略时，您在 PowerShell 中修改反网络钓鱼策略时，就可以使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-319">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="ad8dd-320">将指定策略打开 (应用于每个人的 _MakeDefault_ 开关，始终为 **最低** 优先级，并且您无法删除它) 仅当您在 PowerShell 中修改反网络钓鱼策略时才可用。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-320">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ad8dd-321">无法重命名反网络钓鱼策略 (**AntiPhishPolicy** Cmdlet 没有 _名称_ 参数) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-321">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ad8dd-322">重命名安全 & 合规中心中的反网络钓鱼策略时，只是重命名反网络钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-322">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ad8dd-323">若要修改反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-323">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ad8dd-324">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-324">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ad8dd-325">使用 PowerShell 修改反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ad8dd-325">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ad8dd-326">在 PowerShell 中修改反网络钓鱼规则时，唯一不可用的设置是允许您创建禁用规则的 _启用_ 参数。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-326">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ad8dd-327">若要启用或禁用现有的反网络钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-327">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ad8dd-328">否则，在创建规则时，在本文前面的 " [步骤2：使用 PowerShell 创建反钓鱼规则](#step-2-use-powershell-to-create-an-anti-phish-rule) " 一节中所述，可以使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-328">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="ad8dd-329">若要修改反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-329">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ad8dd-330">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-330">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ad8dd-331">使用 PowerShell 启用或禁用反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ad8dd-331">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ad8dd-332">若要启用或禁用 PowerShell 中的反网络钓鱼规则，可以启用或禁用反钓鱼诈骗规则和分配的反网络钓鱼策略) 的整个反网络钓鱼策略 (。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-332">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ad8dd-333">您不能启用或禁用默认的反网络钓鱼策略 (始终将其应用于所有收件人) 。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-333">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ad8dd-334">若要在 PowerShell 中启用或禁用反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-334">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ad8dd-335">本示例禁用名为 "Marketing 部门" 的反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-335">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ad8dd-336">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-336">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ad8dd-337">有关语法和参数的详细信息，请参阅 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-337">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ad8dd-338">使用 PowerShell 设置反网络钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="ad8dd-338">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ad8dd-339">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ad8dd-340">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ad8dd-341">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ad8dd-342">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ad8dd-343">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ad8dd-344">若要在 PowerShell 中设置反网络钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-344">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ad8dd-345">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-345">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ad8dd-346">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-346">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ad8dd-347">**注意**：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-347">**Notes**:</span></span>

- <span data-ttu-id="ad8dd-348">若要在创建时设置新规则的优先级，请改用 **AntiPhishRule** cmdlet 上的 _priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-348">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ad8dd-349">默认反网络钓鱼策略不具有相应的反网络钓鱼规则，并且它始终具有 "不可修改的优先级" 值（ **最低**）。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-349">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ad8dd-350">使用 PowerShell 删除反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ad8dd-350">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ad8dd-351">当您使用 PowerShell 删除反网络钓鱼策略时，不会删除相应的反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-351">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ad8dd-352">若要删除 PowerShell 中的反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-352">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ad8dd-353">本示例将删除名为 "Marketing 部门" 的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-353">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ad8dd-354">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-354">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ad8dd-355">使用 PowerShell 删除反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ad8dd-355">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ad8dd-356">当您使用 PowerShell 删除反网络钓鱼规则时，不会删除相应的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-356">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ad8dd-357">若要删除 PowerShell 中的反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-357">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ad8dd-358">本示例将删除名为 "Marketing 部门" 的反钓鱼诈骗规则。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-358">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ad8dd-359">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-359">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ad8dd-360">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="ad8dd-360">How do you know these procedures worked?</span></span>

<span data-ttu-id="ad8dd-361">若要验证是否已在 Microsoft Defender for Office 365 中成功配置了反网络钓鱼策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-361">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="ad8dd-362">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-362">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="ad8dd-363">验证策略列表、策略的 **状态** 值及其 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-363">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ad8dd-364">若要查看更多详细信息，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-364">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="ad8dd-365">从列表中选择策略，并在浮出控件中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-365">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="ad8dd-366">单击 " **默认策略** " 并在浮出控件中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="ad8dd-366">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="ad8dd-367">在 Exchange Online PowerShell 中，将替换 \<Name\> 为策略或规则的名称，运行以下命令，并验证设置：</span><span class="sxs-lookup"><span data-stu-id="ad8dd-367">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
