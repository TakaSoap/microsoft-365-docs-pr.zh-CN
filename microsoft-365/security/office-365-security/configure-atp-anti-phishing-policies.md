---
title: 在 Microsoft Defender for Office 365 中配置反网络钓鱼策略
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
description: 管理员可以了解如何创建、修改和删除使用 Microsoft Defender for Office 365 的组织中提供的高级反网络钓鱼策略。
ms.openlocfilehash: ae8c87a0bfb7f975328d8283f0b62aa12c1d5e2b
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572401"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-103">在 Microsoft Defender for Office 365 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ed114-104">[Microsoft Defender For Office 365](office-365-atp.md)中的反网络钓鱼策略可帮助保护您的组织免受恶意的基于模拟的网络钓鱼攻击和其他类型的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="ed114-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="ed114-105">有关 Exchange Online Protection 中的反网络钓鱼策略之间的差异的详细信息 (EOP) 和 Microsoft Defender for Office 365 中的反网络钓鱼策略，请参阅 [反钓鱼防护](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="ed114-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="ed114-106">管理员可以查看、编辑和配置 (，但不能删除默认的反网络钓鱼策略) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="ed114-107">为了更细致，您还可以创建适用于组织中的特定用户、组或域的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ed114-108">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="ed114-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ed114-109">您可以在安全 & 合规中心 "或 Exchange Online PowerShell 中配置反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="ed114-110">有关在 Exchange Online Protection 组织中提供的更有限的防仿冒策略中的信息 (也就是说，没有 Microsoft Defender for Office 365) 的组织，请参阅 [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ed114-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="ed114-111">反网络钓鱼策略的基本元素为：</span><span class="sxs-lookup"><span data-stu-id="ed114-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="ed114-112">**反网络钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及要应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="ed114-112">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="ed114-113">**反网络钓鱼规则**：指定策略应用于) 反网络钓鱼策略的 (的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="ed114-113">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ed114-114">在安全 & 合规中心中管理反网络钓鱼策略时，这两个元素之间的差异并不明显：</span><span class="sxs-lookup"><span data-stu-id="ed114-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ed114-115">创建策略时，实际上是同时创建反网络钓鱼规则和关联的反网络钓鱼策略，同时为两者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="ed114-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ed114-116">修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ed114-117">所有其他设置将修改关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="ed114-118">删除策略时，将删除反网络钓鱼规则和关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ed114-119">在 Exchange Online PowerShell 中，可以单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ed114-120">有关详细信息，请参阅本主题后面的 [使用 Exchange Online PowerShell 配置 Microsoft Defender For Office 365 中的反网络钓鱼策略](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) 一节。</span><span class="sxs-lookup"><span data-stu-id="ed114-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="ed114-121">每个 Microsoft Defender for Office 365 组织都具有一个名为 Office365 AntiPhish 的内置反网络钓鱼策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="ed114-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ed114-122">该策略将应用于组织中的所有收件人，即使没有反网络钓鱼规则 (收件人筛选器与策略关联) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ed114-123">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="ed114-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ed114-124">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="ed114-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ed114-125">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ed114-126">若要提高 Microsoft Defender for Office 365 中防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置来创建自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ed114-127">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="ed114-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ed114-128">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="ed114-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ed114-129">若要直接转到 " **ATP 反钓鱼** " 页面，请使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="ed114-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ed114-130">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ed114-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ed114-131">您需要在安全 & 合规性中心中分配权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="ed114-131">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ed114-132">若要添加、修改和删除反网络钓鱼策略，您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="ed114-132">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ed114-133">若要对反网络钓鱼策略进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="ed114-133">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="ed114-134">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ed114-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ed114-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="ed114-135">**Notes**:</span></span>

  - <span data-ttu-id="ed114-136">将用户添加到 Microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心的必需权限 _以及_ Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="ed114-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ed114-137">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ed114-137">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="ed114-138">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**仅查看组织管理**" 角色组也提供了对功能的只读访问权限 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="ed114-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="ed114-139"><sup>\*</sup> 在安全 & 合规性中心中，只读访问允许用户查看自定义反网络钓鱼策略的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-139"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="ed114-140">只读用户无法查看默认反网络钓鱼策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-140">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="ed114-141">有关 Microsoft Defender for Office 365 中的反网络钓鱼策略的建议设置，请参阅 [Defender For office 365 设置中的反网络钓鱼策略](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="ed114-141">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="ed114-142">允许使用最长30分钟的时间来应用新的或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-142">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="ed114-143">有关在筛选管道中应用反网络钓鱼策略的位置的信息，请参阅 [电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="ed114-143">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-144">使用安全 & 合规性中心在 Microsoft Defender for Office 365 中创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-144">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ed114-145">在安全 & 合规性中心中创建自定义反网络钓鱼策略将同时使用相同的名称创建反钓鱼诈骗规则和关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-145">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="ed114-146">创建反网络钓鱼策略时，只能指定策略名称、说明和标识应用策略的收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="ed114-146">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="ed114-147">创建策略后，您可以修改策略以更改或查看默认的反网络钓鱼设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-147">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="ed114-148">在 "安全性 & 合规性中心中，转到" **威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ed114-149">在 " **反钓鱼网站** " 页上，单击 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-149">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="ed114-150">将打开 " **新建反网络钓鱼策略** " 向导。</span><span class="sxs-lookup"><span data-stu-id="ed114-150">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="ed114-151">在 " **命名策略** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ed114-152">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="ed114-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ed114-153">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="ed114-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ed114-154">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="ed114-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ed114-155">在显示的 " **应用于** " 页上，确定该策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="ed114-155">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ed114-156">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="ed114-156">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ed114-157">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="ed114-157">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ed114-158">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="ed114-158">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="ed114-159">单击 " **添加条件**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-159">Click **Add a condition**.</span></span> <span data-ttu-id="ed114-160">在出现的下拉列表中，选择 " **应用** 条件：</span><span class="sxs-lookup"><span data-stu-id="ed114-160">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="ed114-161">**收件人为**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="ed114-161">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ed114-162">**收件人是的成员**：指定组织中的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="ed114-162">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ed114-163">**收件人域为**：指定组织中已配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="ed114-163">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="ed114-164">选择条件后，将显示相应的下拉框，其中包含 **其中的任何** 框。</span><span class="sxs-lookup"><span data-stu-id="ed114-164">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ed114-165">在框中单击并滚动到要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="ed114-165">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ed114-166">在框中单击，然后开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="ed114-166">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ed114-167">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="ed114-167">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ed114-168">若要删除单个条目， **Remove** 请单击 ![ ](../../media/scc-remove-icon.png) 值上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="ed114-168">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ed114-169">若要删除整个条件，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="ed114-169">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ed114-170">若要添加其他条件，请单击 " **添加条件** "，然后选择 " **应用于**" 下的其他值。</span><span class="sxs-lookup"><span data-stu-id="ed114-170">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ed114-171">若要添加例外，请单击 " **添加条件** "，并在 " **除非**" 下选择例外。</span><span class="sxs-lookup"><span data-stu-id="ed114-171">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ed114-172">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="ed114-172">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ed114-173">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="ed114-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ed114-174">在显示的 " **查看您的设置** " 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-174">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ed114-175">您可以在每个设置上单击 " **编辑** " 以修改它。</span><span class="sxs-lookup"><span data-stu-id="ed114-175">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ed114-176">完成后，单击 " **创建此策略**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-176">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="ed114-177">在出现的确认对话框中，单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="ed114-177">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="ed114-178">在使用这些常规设置创建反网络钓鱼策略后，请按照下一节中的说明操作，在策略中配置保护设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-178">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-179">使用安全 & 合规性中心修改 Microsoft Defender for Office 365 中的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-179">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ed114-180">使用以下过程可修改反网络钓鱼策略：创建的新策略或已自定义的现有策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-180">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="ed114-181">如果尚不存在，请打开安全 & 合规中心，并转到 **威胁管理** \> **策略** \> **ATP 反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="ed114-181">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ed114-182">选择要修改的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-182">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="ed114-183">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ed114-183">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ed114-184">将出现 "**编辑 \<name\> 您的策略**" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="ed114-184">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="ed114-185">单击任意部分中的 " **编辑** " 可访问该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-185">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="ed114-186">以下步骤按节的显示顺序显示，但它们不是连续的 (您可以按任意顺序) 选择和修改各节。</span><span class="sxs-lookup"><span data-stu-id="ed114-186">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="ed114-187">在分区中单击 "**编辑**" 后，可用的设置将以向导格式显示，但您可以按任意顺序在页面中进行跳转，也可以单击任何页面上的 "**保存**" (或 "**取消**" 或 "**关闭** ![ 关闭 ](../../media/scc-remove-icon.png) " 图标，以返回到 " **\<name\> 编辑策略**" 页面 (您无需访问向导的最后一页以保存或离开) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-187">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="ed114-188">**策略设置**：单击 " **编辑** " 可修改在上一节中 [创建策略](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) 时可用的相同设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-188">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="ed114-189">**名称**</span><span class="sxs-lookup"><span data-stu-id="ed114-189">**Name**</span></span>
   - <span data-ttu-id="ed114-190">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed114-190">**Description**</span></span>
   - <span data-ttu-id="ed114-191">**应用于**</span><span class="sxs-lookup"><span data-stu-id="ed114-191">**Applied to**</span></span>
   - <span data-ttu-id="ed114-192">**查看设置**</span><span class="sxs-lookup"><span data-stu-id="ed114-192">**Review your settings**</span></span>

   <span data-ttu-id="ed114-193">完成后，请单击任意页面上的 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="ed114-193">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="ed114-194">**模拟**：单击 " **编辑** " 以修改策略中的受保护的发件人和受保护的域。</span><span class="sxs-lookup"><span data-stu-id="ed114-194">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="ed114-195">这些设置是策略的一个条件，用于标识欺骗性发件人，以在入站邮件的发件人地址中单独或按域) 查找 (。</span><span class="sxs-lookup"><span data-stu-id="ed114-195">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="ed114-196">有关详细信息，请参阅 [Microsoft Defender For Office 365 中的模拟设置中的反网络钓鱼策略](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="ed114-196">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="ed114-197">**添加要保护的用户**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="ed114-197">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="ed114-198">若要打开它，请将切换滑到 **"开**"，然后单击出现的 " **添加用户** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="ed114-198">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="ed114-199">在出现的 " **添加用户** 浮出控件" 中，配置以下值：</span><span class="sxs-lookup"><span data-stu-id="ed114-199">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="ed114-200">**电子邮件地址**：</span><span class="sxs-lookup"><span data-stu-id="ed114-200">**Email address**:</span></span>

       - <span data-ttu-id="ed114-201">在框中单击并滚动到要选择的用户列表。</span><span class="sxs-lookup"><span data-stu-id="ed114-201">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="ed114-202">在框中单击，然后开始键入以筛选列表并选择用户。</span><span class="sxs-lookup"><span data-stu-id="ed114-202">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="ed114-203">若要删除条目，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) "用户" 上的 "删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="ed114-203">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ed114-204">**名称**：根据您选择的电子邮件地址填充此值，但您可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="ed114-204">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="ed114-205">完成后，请单击任意页面上的 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="ed114-205">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="ed114-206">若要编辑现有条目，请在列表中选择受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="ed114-206">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="ed114-207">在每个反网络钓鱼策略中，您最多可以指定60个受保护的用户 (发件人的电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-207">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="ed114-208">您不能在多个策略中指定同一个受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="ed114-208">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="ed114-209">如果发件人和收件人之前通过电子邮件进行了通信，则用户模拟保护将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ed114-209">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="ed114-210">如果发件人和收件人从未通过电子邮件进行通信，则会将该邮件标识为模拟尝试。</span><span class="sxs-lookup"><span data-stu-id="ed114-210">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="ed114-211">**添加要保护的域**：配置以下一个或两个设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-211">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="ed114-212">**自动包括我拥有的域**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="ed114-212">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="ed114-213">若要打开它，请将开关滑到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-213">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ed114-214">**包含自定义域**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="ed114-214">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="ed114-215">若要打开它，请将开关滑到 **"打开**"，然后在 " **添加域** " 框中输入域名 (例如，CONTOSO.COM) ，按 enter，并在必要时重复此操作。</span><span class="sxs-lookup"><span data-stu-id="ed114-215">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ed114-216">在所有反网络钓鱼策略中，最多可以有50个域。</span><span class="sxs-lookup"><span data-stu-id="ed114-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="ed114-217">**操作**：单击 "**编辑**"</span><span class="sxs-lookup"><span data-stu-id="ed114-217">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="ed114-218">**如果由模拟用户发送电子邮件**：为欺骗性发件人是在 " **添加用户以保护**" 中指定的受保护用户之一的邮件配置下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ed114-218">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="ed114-219">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="ed114-219">**Don't apply any action**</span></span>
       - <span data-ttu-id="ed114-220">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="ed114-220">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ed114-221">**将邮件移动到 "垃圾邮件" 文件夹**</span><span class="sxs-lookup"><span data-stu-id="ed114-221">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ed114-222">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="ed114-222">**Quarantine the message**</span></span>
       - <span data-ttu-id="ed114-223">**传递邮件并向 "密件抄送" 行添加其他地址**</span><span class="sxs-lookup"><span data-stu-id="ed114-223">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ed114-224">**邮件传递前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="ed114-224">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="ed114-225">**如果由模拟域发送电子邮件**：为欺骗性发件人位于在 " **添加域以保护**" 中指定的受保护域之一的邮件配置下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ed114-225">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="ed114-226">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="ed114-226">**Don't apply any action**</span></span>
       - <span data-ttu-id="ed114-227">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="ed114-227">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ed114-228">**将邮件移动到 "垃圾邮件" 文件夹**</span><span class="sxs-lookup"><span data-stu-id="ed114-228">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ed114-229">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="ed114-229">**Quarantine the message**</span></span>
       - <span data-ttu-id="ed114-230">**传递邮件并向 "密件抄送" 行添加其他地址**</span><span class="sxs-lookup"><span data-stu-id="ed114-230">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ed114-231">**邮件传递前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="ed114-231">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ed114-232">单击 " **打开模拟安全提示** "，并配置以下任何设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-232">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="ed114-233">**为模拟用户显示提示**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="ed114-233">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="ed114-234">若要打开它，请将开关滑到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ed114-235">**显示模拟域的提示**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="ed114-235">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="ed114-236">若要打开它，请将开关滑到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-236">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ed114-237">**显示不正常字符的提示**：默认值为 **Off**。</span><span class="sxs-lookup"><span data-stu-id="ed114-237">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="ed114-238">若要打开它，请将开关滑到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-238">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="ed114-239">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="ed114-239">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="ed114-240">**邮箱智能**：</span><span class="sxs-lookup"><span data-stu-id="ed114-240">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="ed114-241">是否 **启用邮箱智能？**：默认值为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-241">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="ed114-242">若要将其关闭，请将开关滑动到 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-242">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="ed114-243">是否 **启用基于邮箱智能的模拟保护？**：此设置仅 **在**"**启用邮箱智能" 时可用？处于启用状态**。</span><span class="sxs-lookup"><span data-stu-id="ed114-243">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="ed114-244">在 **模拟用户发送电子邮件时**，您可以指定下列操作之一对邮箱智能失败 (的邮件执行与受保护的用户和受保护的域) 的相同操作的访问：</span><span class="sxs-lookup"><span data-stu-id="ed114-244">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="ed114-245">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="ed114-245">**Don't apply any action**</span></span>
       - <span data-ttu-id="ed114-246">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="ed114-246">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ed114-247">**将邮件移动到 "垃圾邮件" 文件夹**</span><span class="sxs-lookup"><span data-stu-id="ed114-247">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ed114-248">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="ed114-248">**Quarantine the message**</span></span>
       - <span data-ttu-id="ed114-249">**传递邮件并向 "密件抄送" 行添加其他地址**</span><span class="sxs-lookup"><span data-stu-id="ed114-249">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ed114-250">**邮件传递前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="ed114-250">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ed114-251">**添加受信任的发件人和域**：指定策略的例外项：</span><span class="sxs-lookup"><span data-stu-id="ed114-251">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="ed114-252">**受信任的发件人**：</span><span class="sxs-lookup"><span data-stu-id="ed114-252">**Trusted senders**:</span></span>

       - <span data-ttu-id="ed114-253">在框中单击并滚动到要选择的用户列表。</span><span class="sxs-lookup"><span data-stu-id="ed114-253">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="ed114-254">在框中单击，然后开始键入以筛选列表并选择用户。</span><span class="sxs-lookup"><span data-stu-id="ed114-254">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="ed114-255">若要删除条目，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) "用户" 上的 "删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="ed114-255">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ed114-256">**受信任域**：输入域名 (例如，contoso.com) ，按 enter，并根据需要重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="ed114-256">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="ed114-257">**查看设置**：不是单击每个单独的步骤，而是在摘要中显示设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-257">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ed114-258">您可以单击每个部分中的 " **编辑** " 以跳回到相关页面。</span><span class="sxs-lookup"><span data-stu-id="ed114-258">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ed114-259">您可以在此页面 **上\*\*\*\*直接切换** 以下设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-259">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ed114-260">**受保护的用户**</span><span class="sxs-lookup"><span data-stu-id="ed114-260">**Protected users**</span></span>
       - <span data-ttu-id="ed114-261">**受保护域** \>**包含我自己的域**</span><span class="sxs-lookup"><span data-stu-id="ed114-261">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="ed114-262">**受保护域** \>**受保护的域** (自定义域) </span><span class="sxs-lookup"><span data-stu-id="ed114-262">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="ed114-263">**邮箱智能**</span><span class="sxs-lookup"><span data-stu-id="ed114-263">**Mailbox intelligence**</span></span>

   <span data-ttu-id="ed114-264">完成后，请单击任意页面上的 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="ed114-264">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="ed114-265">**哄骗**：单击 " **编辑** " 以打开或关闭欺骗情报，在 Outlook 中打开或关闭未经身份验证的发件人标识，并将操作配置为应用于阻止的欺骗性发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed114-265">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="ed114-266">有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="ed114-266">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="ed114-267">请注意，EOP 中的反网络钓鱼策略中也提供了这些相同的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-267">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="ed114-268">**哄骗筛选器设置**：默认值为 **"开**"，我们建议您将其保留在中。</span><span class="sxs-lookup"><span data-stu-id="ed114-268">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="ed114-269">若要将其关闭，请将开关滑动到 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-269">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="ed114-270">有关详细信息，请参阅 [在 EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="ed114-270">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="ed114-271">如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。</span><span class="sxs-lookup"><span data-stu-id="ed114-271">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ed114-272">有关说明，请参阅 [增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="ed114-272">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="ed114-273">**启用未经身份验证的发件人功能**：默认值为 **打开**。</span><span class="sxs-lookup"><span data-stu-id="ed114-273">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="ed114-274">若要将其关闭，请将开关滑动到 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-274">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="ed114-275">**操作**：指定对欺骗性智能邮件失败的邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="ed114-275">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="ed114-276">**如果电子邮件由不允许欺骗您的域的人发送**：</span><span class="sxs-lookup"><span data-stu-id="ed114-276">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="ed114-277">**将邮件移到收件人的 "垃圾邮件" 文件夹**</span><span class="sxs-lookup"><span data-stu-id="ed114-277">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="ed114-278">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="ed114-278">**Quarantine the message**</span></span>

   - <span data-ttu-id="ed114-279">**查看设置**：不是单击每个单独的步骤，而是在摘要中显示设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-279">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ed114-280">您可以单击每个部分中的 " **编辑** " 以跳回到相关页面。</span><span class="sxs-lookup"><span data-stu-id="ed114-280">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ed114-281">您可以在此页面 **上\*\*\*\*直接切换** 以下设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-281">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="ed114-282">**启用 antispoofing 保护**</span><span class="sxs-lookup"><span data-stu-id="ed114-282">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="ed114-283">**启用未经身份验证的发件人功能**</span><span class="sxs-lookup"><span data-stu-id="ed114-283">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="ed114-284">完成后，请单击任意页面上的 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="ed114-284">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="ed114-285">**高级设置**：单击 " **编辑** " 以配置高级网络钓鱼阈值。</span><span class="sxs-lookup"><span data-stu-id="ed114-285">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="ed114-286">有关详细信息，请参阅 [Microsoft Defender For Office 365 中的反网络钓鱼策略中的高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="ed114-286">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="ed114-287">**高级网络钓鱼阈值**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="ed114-287">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="ed114-288">**1-标准** (这是默认值。 ) </span><span class="sxs-lookup"><span data-stu-id="ed114-288">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="ed114-289">**2-主动**</span><span class="sxs-lookup"><span data-stu-id="ed114-289">**2 - Aggressive**</span></span>
   - <span data-ttu-id="ed114-290">**3-更主动**</span><span class="sxs-lookup"><span data-stu-id="ed114-290">**3 - More aggressive**</span></span>
   - <span data-ttu-id="ed114-291">**4-最主动**</span><span class="sxs-lookup"><span data-stu-id="ed114-291">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="ed114-292">**查看设置**：单击 " **编辑** " 以跳回到 " **高级网络钓鱼阈值** " 页面。</span><span class="sxs-lookup"><span data-stu-id="ed114-292">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="ed114-293">完成后，单击任意页面上的 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="ed114-293">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="ed114-294">返回到 "**编辑你的 \<Name\> 策略**" 页，查看你的设置，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-294">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-295">使用安全 & 合规性中心修改 Microsoft Defender for Office 365 中的默认反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-295">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ed114-296">Microsoft Defender for Office 365 中的默认反网络钓鱼策略名为 Office365 AntiPhish Default，并且不会出现在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="ed114-296">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="ed114-297">若要修改默认的反网络钓鱼策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ed114-297">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="ed114-298">在 "安全性 & 合规性中心中，转到" **威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-298">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ed114-299">在 " **反钓鱼网站** " 页上，单击 " **默认策略**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-299">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="ed114-300">将显示 " **编辑您的策略 Office365 AntiPhish 默认** 页"。</span><span class="sxs-lookup"><span data-stu-id="ed114-300">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="ed114-301">以下各节均可用，其中包含 [修改自定义策略](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)时的相同设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-301">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="ed114-302">**模拟**</span><span class="sxs-lookup"><span data-stu-id="ed114-302">**Impersonation**</span></span>
   - <span data-ttu-id="ed114-303">**哄骗**</span><span class="sxs-lookup"><span data-stu-id="ed114-303">**Spoof**</span></span>
   - <span data-ttu-id="ed114-304">**高级设置**</span><span class="sxs-lookup"><span data-stu-id="ed114-304">**Advanced settings**</span></span>

   <span data-ttu-id="ed114-305">修改默认策略时，以下设置不可用：</span><span class="sxs-lookup"><span data-stu-id="ed114-305">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="ed114-306">您可以看到 " **策略设置** " 部分和值，但没有 " **编辑** " 链接，因此不能修改 (策略名称、说明和策略应用于的用户 (它适用于所有收件人) # A3。</span><span class="sxs-lookup"><span data-stu-id="ed114-306">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="ed114-307">您不能删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-307">You can't delete the default policy.</span></span>
   - <span data-ttu-id="ed114-308">您不能更改默认策略的优先级 (它始终应用于最后) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-308">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="ed114-309">在 " **编辑策略 Office365 AntiPhish 默认** 页面上，查看您的设置，然后单击" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-309">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-310">在 Microsoft Defender for Office 365 中启用或禁用自定义反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-310">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ed114-311">在 "安全性 & 合规性中心中，转到" **威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-311">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ed114-312">请注意 " **状态** " 列中的值：</span><span class="sxs-lookup"><span data-stu-id="ed114-312">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ed114-313">将开关滑到 " **关闭** " 以禁用该策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-313">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="ed114-314">将切换滑到 **打开** 以启用该策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-314">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="ed114-315">您不能禁用默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-315">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-316">在 Microsoft Defender for Office 365 中设置自定义反网络钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="ed114-316">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ed114-317">默认情况下，会为反网络钓鱼策略指定一个优先级，这取决于它们的创建顺序 (较旧策略的优先级低于旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-317">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ed114-318">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="ed114-318">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ed114-319">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="ed114-319">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ed114-320">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="ed114-320">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ed114-321">自定义反网络钓鱼策略按其处理顺序显示， (第一个策略的 **优先级** 值为 0) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-321">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ed114-322">名为 Office365 AntiPhish 的默认反网络钓鱼策略默认的自定义优先级值为 **最低**，无法更改。</span><span class="sxs-lookup"><span data-stu-id="ed114-322">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="ed114-323">**注意**：在安全 & 合规性中心中，您只能在创建后更改反网络钓鱼策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="ed114-323">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="ed114-324">在 PowerShell 中，您可以在创建反网络钓鱼规则时替代默认优先级 (这可能会影响现有规则) 的优先级。</span><span class="sxs-lookup"><span data-stu-id="ed114-324">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ed114-325">若要更改策略的优先级，请在策略的属性中单击 " **提高优先级** " 或 " **降低优先级** " (您不能直接修改安全 & 合规性中心) 中的 **优先级** 号码。</span><span class="sxs-lookup"><span data-stu-id="ed114-325">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="ed114-326">如果有多个策略，则更改策略的优先级仅是有意义的。</span><span class="sxs-lookup"><span data-stu-id="ed114-326">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ed114-327">在 "安全性 & 合规性中心中，转到" **威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ed114-328">选择要修改的策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-328">Select the policy that you want to modify.</span></span> <span data-ttu-id="ed114-329">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ed114-329">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ed114-330">将出现 "**编辑 \<name\> 您的策略**" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="ed114-330">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="ed114-331">**优先级** 值为 **0** 的自定义反网络钓鱼策略只有 "**降低优先级**" 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="ed114-331">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ed114-332">具有最低 **优先级** 值的自定义反网络钓鱼策略 (例如， **3**) 仅有 " **提高优先级** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="ed114-332">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ed114-333">如果您具有三个或更多自定义的反网络钓鱼策略，则在最高和最低优先级值之间的策略将具有 " **增加优先级** " 和 " **降低优先级** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="ed114-333">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ed114-334">单击 " **提高优先级** " 或 " **降低优先级** " 以更改 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="ed114-334">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ed114-335">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="ed114-335">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-336">使用安全 & 合规中心在 Microsoft Defender for Office 365 中查看反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-336">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ed114-337">在安全 & 合规性中心，并转到 **威胁管理** \> **策略** \> **ATP 反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="ed114-337">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ed114-338">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="ed114-338">Do one of the following steps:</span></span>

   - <span data-ttu-id="ed114-339">选择要查看的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-339">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="ed114-340">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ed114-340">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="ed114-341">单击 " **默认策略** " 以查看默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-341">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="ed114-342">将出现 "**编辑 \<name\> 策略**" 浮出控件，您可以在其中查看设置和值。</span><span class="sxs-lookup"><span data-stu-id="ed114-342">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-343">使用安全 & 合规性中心删除 Microsoft Defender for Office 365 中的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-343">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ed114-344">在 "安全性 & 合规性中心中，转到" **威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-344">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ed114-345">选择要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-345">Select the policy that you want to remove.</span></span> <span data-ttu-id="ed114-346">如果已被选中，请取消选择并再次选择它。</span><span class="sxs-lookup"><span data-stu-id="ed114-346">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ed114-347">在出现的 "**编辑 \<name\> 策略**" 浮出控件中，单击 "**删除策略**"，然后在出现的警告对话框中单击 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="ed114-347">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ed114-348">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-348">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ed114-349">使用 Exchange Online PowerShell 在 Microsoft Defender for Office 365 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-349">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ed114-350">如前面所述，反垃圾邮件策略由反网络钓鱼策略和反网络钓鱼规则组成。</span><span class="sxs-lookup"><span data-stu-id="ed114-350">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="ed114-351">在 Exchange Online PowerShell 中，反网络钓鱼策略和反网络钓鱼规则之间的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="ed114-351">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ed114-352">您可以使用 **\* -AntiPhishPolicy** cmdlet 管理反网络钓鱼策略，并使用 **\* -AntiPhishRule** cmdlet 管理反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-352">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ed114-353">在 PowerShell 中，首先创建反网络钓鱼策略，然后创建反网络钓鱼规则来标识应用该规则的策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-353">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ed114-354">在 PowerShell 中，可以单独修改反网络钓鱼策略和反钓鱼诈骗规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-354">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="ed114-355">从 PowerShell 中删除反网络钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ed114-355">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ed114-356">使用 PowerShell 创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-356">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ed114-357">在 PowerShell 中创建反网络钓鱼策略的过程分为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="ed114-357">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ed114-358">创建反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-358">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="ed114-359">创建反网络钓鱼规则，该规则指定应用该规则的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-359">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ed114-360">**注意**：</span><span class="sxs-lookup"><span data-stu-id="ed114-360">**Notes**:</span></span>

- <span data-ttu-id="ed114-361">您可以创建新的反网络钓鱼规则并向其分配现有的未关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-361">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ed114-362">反网络钓鱼规则不能与多个反网络钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="ed114-362">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="ed114-363">您可以在 PowerShell 中的新反网络钓鱼策略中配置以下设置，这些设置在安全 & 合规性中心中不可用，直到您创建了策略：</span><span class="sxs-lookup"><span data-stu-id="ed114-363">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ed114-364">将新策略创建为 _Enabled_ `$false` **AntiPhishRule** cmdlet) 上启用的禁用 (。</span><span class="sxs-lookup"><span data-stu-id="ed114-364">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="ed114-365">在 _Priority_ _\<Number\>_ **AntiPhishRule** Cmdlet) 上创建 (优先级) 时设置策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="ed114-365">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="ed114-366">在 PowerShell 中创建的新反网络钓鱼策略在安全 & 合规性中心中不可见，除非您将策略分配给反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-366">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ed114-367">步骤1：使用 PowerShell 创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-367">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ed114-368">若要创建反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-368">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ed114-369">本示例使用以下设置创建名为 "调研隔离" 的反网络钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="ed114-369">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ed114-370">启用此策略 (我们不使用 _enabled_ 参数，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-370">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="ed114-371">说明是：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-371">The description is: Research department policy.</span></span>
- <span data-ttu-id="ed114-372">为所有接受域启用组织域保护，并对 fabrikam.com 的目标域提供保护。</span><span class="sxs-lookup"><span data-stu-id="ed114-372">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="ed114-373">指定 Mai Fujito (mfujito@fabrikam.com) 为要从模拟中进行保护的用户。</span><span class="sxs-lookup"><span data-stu-id="ed114-373">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="ed114-374">启用邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="ed114-374">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="ed114-375">启用邮箱智能保护，并指定隔离操作。</span><span class="sxs-lookup"><span data-stu-id="ed114-375">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="ed114-376">启用安全提示。</span><span class="sxs-lookup"><span data-stu-id="ed114-376">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="ed114-377">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ed114-377">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ed114-378">步骤2：使用 PowerShell 创建反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ed114-378">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ed114-379">若要创建反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-379">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ed114-380">本示例将创建一个名为 "研究部门" 的反网络钓鱼规则，条件如下：</span><span class="sxs-lookup"><span data-stu-id="ed114-380">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ed114-381">该规则与名为 "研究隔离" 的反网络钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="ed114-381">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ed114-382">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="ed114-382">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ed114-383">由于我们不使用 _Priority_ 参数，因此使用默认的优先级。</span><span class="sxs-lookup"><span data-stu-id="ed114-383">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ed114-384">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="ed114-384">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ed114-385">使用 PowerShell 查看反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-385">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ed114-386">若要查看现有的反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-386">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ed114-387">本示例返回所有反网络钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="ed114-387">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ed114-388">本示例将返回名为 "主管" 的反网络钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="ed114-388">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ed114-389">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ed114-389">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ed114-390">使用 PowerShell 查看反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ed114-390">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ed114-391">若要查看现有的反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-391">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ed114-392">本示例返回所有反网络钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="ed114-392">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ed114-393">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ed114-393">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ed114-394">本示例将返回名为 "Contoso 行政主管" 的反网络钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="ed114-394">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ed114-395">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="ed114-395">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ed114-396">使用 PowerShell 修改反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-396">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ed114-397">除了以下项目之外，当您在 PowerShell 中按照 " [步骤1：使用 PowerShell 创建反网络钓鱼策略](#step-1-use-powershell-to-create-an-anti-phish-policy) " 一节中所述，在 PowerShell 中修改反网络钓鱼策略时，可以使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-397">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="ed114-398">将指定策略打开 (应用于每个人的 _MakeDefault_ 开关，始终为 **最低** 优先级，并且您无法删除它) 仅当您在 PowerShell 中修改反网络钓鱼策略时才可用。</span><span class="sxs-lookup"><span data-stu-id="ed114-398">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ed114-399">无法重命名反网络钓鱼策略 (**AntiPhishPolicy** Cmdlet 没有 _名称_ 参数) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-399">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ed114-400">重命名安全 & 合规中心中的反网络钓鱼策略时，只是重命名反网络钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="ed114-400">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ed114-401">若要修改反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-401">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ed114-402">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ed114-402">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ed114-403">使用 PowerShell 修改反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ed114-403">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ed114-404">在 PowerShell 中修改反网络钓鱼规则时，唯一不可用的设置是允许您创建禁用规则的 _启用_ 参数。</span><span class="sxs-lookup"><span data-stu-id="ed114-404">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ed114-405">若要启用或禁用现有的反网络钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="ed114-405">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ed114-406">否则，在 PowerShell 中修改反网络钓鱼规则时，不提供其他任何设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-406">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="ed114-407">按照本主题前面的 " [步骤2：使用 PowerShell 创建反钓鱼诈骗规则](#step-2-use-powershell-to-create-an-anti-phish-rule) " 一节中所述，创建规则时，可以使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="ed114-407">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="ed114-408">若要修改反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-408">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ed114-409">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="ed114-409">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ed114-410">使用 PowerShell 启用或禁用反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ed114-410">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ed114-411">若要启用或禁用 PowerShell 中的反网络钓鱼规则，可以启用或禁用反钓鱼诈骗规则和分配的反网络钓鱼策略) 的整个反网络钓鱼策略 (。</span><span class="sxs-lookup"><span data-stu-id="ed114-411">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ed114-412">您不能启用或禁用默认的反网络钓鱼策略 (始终将其应用于所有收件人) 。</span><span class="sxs-lookup"><span data-stu-id="ed114-412">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ed114-413">若要在 PowerShell 中启用或禁用反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-413">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ed114-414">本示例禁用名为 "Marketing 部门" 的反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-414">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ed114-415">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-415">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ed114-416">有关语法和参数的详细信息，请参阅 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="ed114-416">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ed114-417">使用 PowerShell 设置反网络钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="ed114-417">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ed114-418">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="ed114-418">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ed114-419">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="ed114-419">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ed114-420">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="ed114-420">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ed114-421">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="ed114-421">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ed114-422">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="ed114-422">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ed114-423">若要在 PowerShell 中设置反网络钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-423">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ed114-424">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="ed114-424">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ed114-425">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="ed114-425">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ed114-426">**注意**：</span><span class="sxs-lookup"><span data-stu-id="ed114-426">**Notes**:</span></span>

- <span data-ttu-id="ed114-427">若要在创建时设置新规则的优先级，请改用 **AntiPhishRule** cmdlet 上的 _priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="ed114-427">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ed114-428">默认反网络钓鱼策略不具有相应的反网络钓鱼规则，并且它始终具有 "不可修改的优先级" 值（ **最低**）。</span><span class="sxs-lookup"><span data-stu-id="ed114-428">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ed114-429">使用 PowerShell 删除反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ed114-429">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ed114-430">当您使用 PowerShell 删除反网络钓鱼策略时，不会删除相应的反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-430">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ed114-431">若要删除 PowerShell 中的反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-431">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ed114-432">本示例将删除名为 "Marketing 部门" 的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-432">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ed114-433">有关语法和参数的详细信息，请参阅 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ed114-433">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ed114-434">使用 PowerShell 删除反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="ed114-434">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ed114-435">当您使用 PowerShell 删除反网络钓鱼规则时，不会删除相应的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ed114-435">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ed114-436">若要删除 PowerShell 中的反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed114-436">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ed114-437">本示例将删除名为 "Marketing 部门" 的反钓鱼诈骗规则。</span><span class="sxs-lookup"><span data-stu-id="ed114-437">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ed114-438">有关语法和参数的详细信息，请参阅 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="ed114-438">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ed114-439">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="ed114-439">How do you know these procedures worked?</span></span>

<span data-ttu-id="ed114-440">若要验证是否已在 Microsoft Defender for Office 365 中成功配置了反网络钓鱼策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="ed114-440">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="ed114-441">在 "安全性 & 合规性中心中，转到" **威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="ed114-441">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="ed114-442">验证策略列表、策略的 **状态** 值及其 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="ed114-442">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ed114-443">若要查看更多详细信息，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="ed114-443">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="ed114-444">从列表中选择策略，并在浮出控件中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed114-444">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="ed114-445">单击 " **默认策略** " 并在浮出控件中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed114-445">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="ed114-446">在 Exchange Online PowerShell 中，将替换 \<Name\> 为策略或规则的名称，然后运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="ed114-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
