---
title: 预设安全策略
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
description: 管理员可以了解如何跨 EOP Exchange Online Protection (和 Microsoft Defender for) 保护功能应用标准策略和严格Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24fe67a7465ec71451b649dbc5963c28e0dc7cf3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879008"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="a0ca6-103">在 EOP 和 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a0ca6-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a0ca6-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="a0ca6-104">**Applies to**</span></span>
- [<span data-ttu-id="a0ca6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a0ca6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a0ca6-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="a0ca6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a0ca6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0ca6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a0ca6-108">预设安全策略提供了一个集中位置，用于一次将建议的所有垃圾邮件、恶意软件和网络钓鱼策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="a0ca6-109">策略设置不可配置。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-109">The policy settings are not configurable.</span></span> <span data-ttu-id="a0ca6-110">相反，它们是由我们设置的，它们基于我们在数据中心中的观察和体验，以平衡将有害的内容远离用户和避免不必要的中断。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users and avoiding unnecessary disruptions.</span></span>

<span data-ttu-id="a0ca6-111">本文的其余部分介绍了预设安全策略以及如何配置它们。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-111">The rest of this article describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="a0ca6-112">预设安全策略由什么决定</span><span class="sxs-lookup"><span data-stu-id="a0ca6-112">What preset security policies are made of</span></span>

<span data-ttu-id="a0ca6-113">预设安全策略包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="a0ca6-114">配置文件</span><span class="sxs-lookup"><span data-stu-id="a0ca6-114">Profiles</span></span>
- <span data-ttu-id="a0ca6-115">策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-115">Policies</span></span>
- <span data-ttu-id="a0ca6-116">策略设置</span><span class="sxs-lookup"><span data-stu-id="a0ca6-116">Policy settings</span></span>

<span data-ttu-id="a0ca6-117">此外，如果多个预设安全策略和其他策略适用于同一个人，则优先顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="a0ca6-118">预设安全策略中的配置文件</span><span class="sxs-lookup"><span data-stu-id="a0ca6-118">Profiles in preset security policies</span></span>

<span data-ttu-id="a0ca6-119">配置文件确定保护级别。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-119">A profile determines the level of protection.</span></span> <span data-ttu-id="a0ca6-120">以下配置文件可用：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-120">The following profiles are available:</span></span>

- <span data-ttu-id="a0ca6-121">**标准保护**：适用于大多数用户的基线保护配置文件。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="a0ca6-122">**严格保护**：针对所选用户的更主动 (高值目标或优先用户) 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="a0ca6-123">使用具有条件和例外的规则，这些规则可确定配置文件的适用或不应用于哪些用户。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="a0ca6-124">可用的条件和例外包括：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-124">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="a0ca6-125">**用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-125">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="a0ca6-126">**组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-126">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
- <span data-ttu-id="a0ca6-127">**域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-127">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

<span data-ttu-id="a0ca6-128">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-128">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a0ca6-129">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-129">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a0ca6-130">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-130">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="a0ca6-131">预设安全策略中的策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-131">Policies in preset security policies</span></span>

<span data-ttu-id="a0ca6-132">预设安全策略使用来自 EOP 和 Microsoft Defender for Office 365 中各种保护功能的相应策略。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a0ca6-133">这些策略是在 _将"标准保护"_ 或"严格 **保护**"预设安全策略分配给用户后创建的。 </span><span class="sxs-lookup"><span data-stu-id="a0ca6-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="a0ca6-134">不能修改这些策略。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-134">You can't modify these policies.</span></span>

- <span data-ttu-id="a0ca6-135">**Exchange Online Protection (EOP)** 策略：这包括Microsoft 365邮箱的 Exchange Online 组织，以及没有邮箱Exchange Online独立 EOP 组织：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="a0ca6-136">[名为"标准预设安全策略](configure-your-spam-filter-policies.md)"**和"\*\*\*\*严格预设安全策略"的反垃圾邮件策略**。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="a0ca6-137">[名为"标准预设安全策略](configure-anti-malware-policies.md)"**和"\*\*\*\*严格预设安全策略"的反恶意软件策略**。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="a0ca6-138">[名为"标准预设安全策略"](set-up-anti-phishing-policies.md#spoof-settings)和"严格预设安全策略"的EOP 防钓鱼策略 (欺骗) 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="a0ca6-139">**Microsoft Defender for Office 365** 策略：这包括具有 Microsoft 365 E5 或 Defender for Office 365 加载项订阅的组织：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="a0ca6-140">Microsoft Defender 中的反网络钓鱼策略Office 365 **标准** 预设安全策略和 **严格预设** 安全策略，其中包括：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="a0ca6-141">EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="a0ca6-142">模拟设置</span><span class="sxs-lookup"><span data-stu-id="a0ca6-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="a0ca6-143">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="a0ca6-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="a0ca6-144">[保险箱"标准预设](set-up-safe-links-policies.md)安全策略"和"**严格预设安全策略"的链接策略**。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="a0ca6-145">[保险箱"](set-up-safe-attachments-policies.md)**标准** 预设安全策略"和"**严格预设安全策略"的附件策略**。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="a0ca6-146">请注意，你可以将 EOP 保护应用于与 Microsoft Defender 不同的用户，Office 365保护。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="a0ca6-147">预设安全策略中的策略设置</span><span class="sxs-lookup"><span data-stu-id="a0ca6-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="a0ca6-148">你无法修改保护配置文件中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="a0ca6-149">The **Standard** and **Strict** policy setting values are described in Recommended settings [for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span><span class="sxs-lookup"><span data-stu-id="a0ca6-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="a0ca6-150">预设安全策略和其他策略的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="a0ca6-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="a0ca6-151">向用户应用多个策略时，将按从最高优先级到最低优先级的顺序应用以下顺序：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="a0ca6-152">**严格保护** 预设安全策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="a0ca6-153">**标准保护** 预设安全策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="a0ca6-154">自定义安全策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-154">Custom security policies</span></span>
4. <span data-ttu-id="a0ca6-155">默认安全策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-155">Default security policies</span></span>

<span data-ttu-id="a0ca6-156">换句话说，严格保护策略的设置会覆盖 **标准** 保护策略的设置，这将覆盖自定义策略中的设置，这将覆盖默认策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="a0ca6-157">向用户分配预设安全策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a0ca6-158">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="a0ca6-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a0ca6-159">在 打开Microsoft 365 Defender 门户 <https://security.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-159">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="a0ca6-160">若要直接转到 **预设安全策略页面** ，请使用 <https://security.microsoft.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-160">To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="a0ca6-161">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a0ca6-162">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a0ca6-163">若要配置预设安全策略，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a0ca6-164">若要对预设安全策略进行只读访问，你需要是全局读者角色 **组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="a0ca6-165">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a0ca6-166">**注意**：将用户添加到 Azure Active Directory 管理中心中的相应 Microsoft 365 角色会为用户提供对 Microsoft 365 中其他功能所需的权限。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a0ca6-167">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="a0ca6-168">使用 Microsoft 365 Defender 门户向用户分配预设安全策略</span><span class="sxs-lookup"><span data-stu-id="a0ca6-168">Use the Microsoft 365 Defender portal to assign preset security policies to users</span></span>

1. <span data-ttu-id="a0ca6-169">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **Rules** \> **Threat Policies** \> **Templated policies** section Preset Security \> **Policies**.</span><span class="sxs-lookup"><span data-stu-id="a0ca6-169">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & Rules** \> **Threat Policies** \> **Templated policies** section \> **Preset Security Policies**.</span></span>

2. <span data-ttu-id="a0ca6-170">在 **"标准保护"** 或 **"严格保护"下，** 单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="a0ca6-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="a0ca6-171">将 **启动"应用标准保护** " **或"应用严格保护** "向导。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="a0ca6-172">在 **"适用于 EOP** 保护"页上，标识 [EOP](#policies-in-preset-security-policies) 保护应用于以下收件人 (内部) ：</span><span class="sxs-lookup"><span data-stu-id="a0ca6-172">On the **EOP protections apply to** page, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to (recipient conditions):</span></span>
   - <span data-ttu-id="a0ca6-173">**用户**</span><span class="sxs-lookup"><span data-stu-id="a0ca6-173">**Users**</span></span>
   - <span data-ttu-id="a0ca6-174">**组**</span><span class="sxs-lookup"><span data-stu-id="a0ca6-174">**Groups**</span></span>
   - <span data-ttu-id="a0ca6-175">**域**</span><span class="sxs-lookup"><span data-stu-id="a0ca6-175">**Domains**</span></span>

   <span data-ttu-id="a0ca6-176">单击相应的框，开始键入值，然后从结果中选择所需的值。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-176">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="a0ca6-177">根据需要多次重复此过程。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-177">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="a0ca6-178">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="a0ca6-178">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a0ca6-180">“删除”。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-180">next to the value.</span></span>

   <span data-ttu-id="a0ca6-181">对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-181">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="a0ca6-182">对于用户，请自行输入星号 (\*) 以查看所有可用值。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-182">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   - <span data-ttu-id="a0ca6-183">**排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-183">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="a0ca6-184">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-184">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a0ca6-185">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a0ca6-186">在适用于 Office 365 组织的 Microsoft Defender 中，你将访问适用于 Office 365 保护的 **Defender** 页面，以标识 Microsoft Defender 针对 [Office 365](#policies-in-preset-security-policies)保护应用于 (收件人条件) 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-186">In Microsoft Defender for Office 365 organizations, you're taken to the **Defender for Office 365 protections apply to** page to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to (recipient conditions).</span></span>

   <span data-ttu-id="a0ca6-187">设置和行为与适用于页面 **的 EOP 保护完全相同** 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-187">The settings and behavior are exactly like the **EOP protections apply to** page.</span></span>

   <span data-ttu-id="a0ca6-188">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-188">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a0ca6-189">在"**查看并确认更改"** 页上，验证您的选择，然后单击"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0ca6-189">On the **Review and confirm your changes** page, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="a0ca6-190">使用 Microsoft 365 Defender 门户修改预设安全策略的分配</span><span class="sxs-lookup"><span data-stu-id="a0ca6-190">Use the Microsoft 365 Defender portal to modify the assignments of preset security policies</span></span>

<span data-ttu-id="a0ca6-191">修改标准保护或严格保护安全策略分配的步骤与最初向用户分配预设安全策略[时的步骤相同](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-191">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="a0ca6-192">若要禁用 **标准保护** 或 **严格** 保护安全策略，同时仍保留现有条件和例外，将开关滑动到 **禁用切换** ![ 关闭 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-192">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="a0ca6-193">若要启用策略，将切换开关滑动到 **启用切换** ![ 打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-193">To enable the policies, slide the toggle to **Enabled** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a0ca6-194">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="a0ca6-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="a0ca6-195">若要验证是否成功向用户分配了标准保护或严格保护安全策略，请使用默认值不同于"标准"保护设置（不同于"严格保护"设置）的保护设置。 </span><span class="sxs-lookup"><span data-stu-id="a0ca6-195">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="a0ca6-196">例如，对于被检测为垃圾邮件 (高可信度垃圾邮件) 验证邮件是否传递到 **标准** 保护用户的"垃圾邮件"文件夹，并隔离" **严格** 保护"用户。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-196">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="a0ca6-197">或者，对于 [](bulk-complaint-level-values.md)批量邮件，请验证 BCL 值 6 或更高版本是否将邮件发送到 **标准** 保护用户的"垃圾邮件"文件夹，BCL 值 4 或更高值会隔离"严格保护"用户的邮件。</span><span class="sxs-lookup"><span data-stu-id="a0ca6-197">Or, for [bulk mail](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
