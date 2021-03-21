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
description: 管理员可以了解如何跨 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 的保护功能应用标准和严格策略设置
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b57c13517d9fd41bcafea5c9d672da0e6b581ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926756"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="12236-103">在 EOP 和 Microsoft Defender for Office 365 中预设安全策略</span><span class="sxs-lookup"><span data-stu-id="12236-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="12236-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="12236-104">**Applies to**</span></span>
- [<span data-ttu-id="12236-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="12236-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="12236-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="12236-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="12236-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12236-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="12236-108">预设安全策略提供了一个集中位置，用于一次将建议的所有垃圾邮件、恶意软件和网络钓鱼策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="12236-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="12236-109">策略设置不可配置。</span><span class="sxs-lookup"><span data-stu-id="12236-109">The policy settings are not configurable.</span></span> <span data-ttu-id="12236-110">相反，它们是由我们设置的，它们基于我们在数据中心中的观察和体验，以在将有害的内容远离用户而不中断他们的工作之间取得平衡。</span><span class="sxs-lookup"><span data-stu-id="12236-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="12236-111">本主题的其余部分介绍了预设安全策略以及如何配置它们。</span><span class="sxs-lookup"><span data-stu-id="12236-111">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="12236-112">预设安全策略由什么决定</span><span class="sxs-lookup"><span data-stu-id="12236-112">What preset security policies are made of</span></span>

<span data-ttu-id="12236-113">预设安全策略包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="12236-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="12236-114">配置文件</span><span class="sxs-lookup"><span data-stu-id="12236-114">Profiles</span></span>
- <span data-ttu-id="12236-115">策略</span><span class="sxs-lookup"><span data-stu-id="12236-115">Policies</span></span>
- <span data-ttu-id="12236-116">策略设置</span><span class="sxs-lookup"><span data-stu-id="12236-116">Policy settings</span></span>

<span data-ttu-id="12236-117">此外，如果多个预设安全策略和其他策略适用于同一个人，则优先顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="12236-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="12236-118">预设安全策略中的配置文件</span><span class="sxs-lookup"><span data-stu-id="12236-118">Profiles in preset security policies</span></span>

<span data-ttu-id="12236-119">配置文件确定保护级别。</span><span class="sxs-lookup"><span data-stu-id="12236-119">A profile determines the level of protection.</span></span> <span data-ttu-id="12236-120">以下配置文件可用：</span><span class="sxs-lookup"><span data-stu-id="12236-120">The following profiles are available:</span></span>

- <span data-ttu-id="12236-121">**标准保护**：适用于大多数用户的基线保护配置文件。</span><span class="sxs-lookup"><span data-stu-id="12236-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="12236-122">**严格保护**：针对所选用户的更主动 (高值目标或优先用户) 。</span><span class="sxs-lookup"><span data-stu-id="12236-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="12236-123">使用具有条件和例外的规则，这些规则可确定配置文件的适用或不应用于哪些用户。</span><span class="sxs-lookup"><span data-stu-id="12236-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="12236-124">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="12236-124">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="12236-125">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="12236-125">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="12236-126">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="12236-126">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="12236-127">可用的条件和例外包括：</span><span class="sxs-lookup"><span data-stu-id="12236-127">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="12236-128">**收件人为**：组织中邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="12236-128">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="12236-129">**收件人是组织中**： 组的成员。</span><span class="sxs-lookup"><span data-stu-id="12236-129">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="12236-130">**收件人域为**：在 Microsoft 365 中配置的接受域。</span><span class="sxs-lookup"><span data-stu-id="12236-130">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="12236-131">预设安全策略中的策略</span><span class="sxs-lookup"><span data-stu-id="12236-131">Policies in preset security policies</span></span>

<span data-ttu-id="12236-132">预设安全策略使用来自 EOP 和 Microsoft Defender for Office 365 中各种保护功能的相应策略。</span><span class="sxs-lookup"><span data-stu-id="12236-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="12236-133">这些策略是在 _将"标准保护"_ 或"严格 **保护**"预设安全策略分配给用户后创建的。 </span><span class="sxs-lookup"><span data-stu-id="12236-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="12236-134">不能修改这些策略。</span><span class="sxs-lookup"><span data-stu-id="12236-134">You can't modify these policies.</span></span>

- <span data-ttu-id="12236-135">**Exchange Online Protection (EOP)** 策略：这包括具有 Exchange Online 邮箱的 Microsoft 365 组织和没有 Exchange Online 邮箱的独立 EOP 组织：</span><span class="sxs-lookup"><span data-stu-id="12236-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="12236-136">[名为"标准预设安全策略](configure-your-spam-filter-policies.md)"**和"\*\*\*\*严格预设安全策略"的反垃圾邮件策略**。</span><span class="sxs-lookup"><span data-stu-id="12236-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="12236-137">[名为"标准预设安全策略](configure-anti-malware-policies.md)"**和"\*\*\*\*严格预设安全策略"的反恶意软件策略**。</span><span class="sxs-lookup"><span data-stu-id="12236-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="12236-138">[名为"标准预设安全策略"](set-up-anti-phishing-policies.md#spoof-settings)和"严格预设安全策略"的EOP 防钓鱼策略 (欺骗) 。</span><span class="sxs-lookup"><span data-stu-id="12236-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="12236-139">**Microsoft Defender for Office 365 策略**：这包括具有 Microsoft 365 E5 或适用于 Office 365 的 Defender 附加订阅的组织：</span><span class="sxs-lookup"><span data-stu-id="12236-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="12236-140">Microsoft Defender for Office 365 中的防钓鱼策略，名为 **"标准** 预设安全策略"和" **严格预设** 安全策略"，其中包括：</span><span class="sxs-lookup"><span data-stu-id="12236-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="12236-141">EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。</span><span class="sxs-lookup"><span data-stu-id="12236-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="12236-142">模拟设置</span><span class="sxs-lookup"><span data-stu-id="12236-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="12236-143">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="12236-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="12236-144">[名为"标准预设](set-up-atp-safe-links-policies.md)**安全策略**"和"**严格预设安全策略"的安全链接策略**。</span><span class="sxs-lookup"><span data-stu-id="12236-144">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="12236-145">[名为"标准预设](set-up-atp-safe-attachments-policies.md)**安全策略**"和"**严格预设安全策略"的安全附件策略**。</span><span class="sxs-lookup"><span data-stu-id="12236-145">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="12236-146">请注意，你可以将 EOP 保护应用于与 Microsoft Defender for Office 365 保护不同的用户。</span><span class="sxs-lookup"><span data-stu-id="12236-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="12236-147">预设安全策略中的策略设置</span><span class="sxs-lookup"><span data-stu-id="12236-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="12236-148">你无法修改保护配置文件中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="12236-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="12236-149">The **Standard** and **Strict** policy setting values are described in Recommended settings [for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="12236-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="12236-150">预设安全策略和其他策略的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="12236-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="12236-151">向用户应用多个策略时，将按从最高优先级到最低优先级的顺序应用以下顺序：</span><span class="sxs-lookup"><span data-stu-id="12236-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="12236-152">**严格保护** 预设安全策略</span><span class="sxs-lookup"><span data-stu-id="12236-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="12236-153">**标准保护** 预设安全策略</span><span class="sxs-lookup"><span data-stu-id="12236-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="12236-154">自定义安全策略</span><span class="sxs-lookup"><span data-stu-id="12236-154">Custom security policies</span></span>
4. <span data-ttu-id="12236-155">默认安全策略</span><span class="sxs-lookup"><span data-stu-id="12236-155">Default security policies</span></span>

<span data-ttu-id="12236-156">换句话说，严格保护策略的设置会覆盖 **标准** 保护策略的设置，这将覆盖自定义策略中的设置，这将覆盖默认策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="12236-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="12236-157">向用户分配预设安全策略</span><span class="sxs-lookup"><span data-stu-id="12236-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="12236-158">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="12236-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="12236-159">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="12236-159">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="12236-160">若要直接转到 **预设安全策略页面** ，请使用 <https://protection.office.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="12236-160">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="12236-161">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="12236-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="12236-162">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="12236-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="12236-163">若要配置预设安全策略，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="12236-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="12236-164">若要对预设安全策略进行只读访问，你需要是全局读者角色 **组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="12236-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="12236-165">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="12236-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="12236-166">**注意**：将用户添加到 Microsoft 365 管理中心的相应 Azure Active Directory 角色会为用户提供Microsoft 365 中其他功能所需的权限。</span><span class="sxs-lookup"><span data-stu-id="12236-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="12236-167">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="12236-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="12236-168">使用安全&中心向用户分配预设安全策略</span><span class="sxs-lookup"><span data-stu-id="12236-168">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="12236-169">在安全与&中心，转到威胁 **管理** \> **策略** \> **预设安全策略**。</span><span class="sxs-lookup"><span data-stu-id="12236-169">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="12236-170">在 **"标准保护"** 或 **"严格保护"下，** 单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="12236-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="12236-171">将 **启动"应用标准保护** " **或"应用严格保护** "向导。</span><span class="sxs-lookup"><span data-stu-id="12236-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="12236-172">在 **"适用于步骤的 EOP** 保护"上，标识 [EOP 保护应用于](#policies-in-preset-security-policies) 的内部收件人：</span><span class="sxs-lookup"><span data-stu-id="12236-172">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="12236-173">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="12236-173">Click **Add a condition**.</span></span> <span data-ttu-id="12236-174">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="12236-174">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="12236-175">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="12236-175">**The recipients are**</span></span>
      - <span data-ttu-id="12236-176">**收件人是以下组的成员**</span><span class="sxs-lookup"><span data-stu-id="12236-176">**The recipients are members of**</span></span>
      - <span data-ttu-id="12236-177">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="12236-177">**The recipient domains are**</span></span>

      <span data-ttu-id="12236-178">一个条件只能使用一次，但可以为此条件指定多个值。</span><span class="sxs-lookup"><span data-stu-id="12236-178">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="12236-179">同一条件的多个值使用 OR 逻辑 (例如 _\<recipient1\>_ ，或 _\<recipient2\>_) 。</span><span class="sxs-lookup"><span data-stu-id="12236-179">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="12236-180">所选条件将显示在阴影部分。</span><span class="sxs-lookup"><span data-stu-id="12236-180">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="12236-181">In that section， click in the **Any of these** box.</span><span class="sxs-lookup"><span data-stu-id="12236-181">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="12236-182">如果您等待片刻，将显示一个列表，以便您可以选择一个值。</span><span class="sxs-lookup"><span data-stu-id="12236-182">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="12236-183">或者，您可以开始键入值以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="12236-183">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="12236-184">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="12236-184">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="12236-185">若要删除单个值，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="12236-185">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="12236-186">若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="12236-186">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="12236-187">若要添加另一个条件，请单击" **添加** 条件"，然后从其余条件中选择。</span><span class="sxs-lookup"><span data-stu-id="12236-187">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="12236-188">不同的条件使用 AND 逻辑 (例如 _\<recipient1\>_ ，和 _\<member of group 1\>_) 。</span><span class="sxs-lookup"><span data-stu-id="12236-188">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="12236-189">重复上一步以向条件添加值，并根据需要多次重复此步骤或直到条件用完。</span><span class="sxs-lookup"><span data-stu-id="12236-189">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="12236-190">若要添加例外，请单击"**添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="12236-190">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="12236-191">In the dropdown that appears， select a condition under **Except when**.</span><span class="sxs-lookup"><span data-stu-id="12236-191">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="12236-192">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="12236-192">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="12236-193">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="12236-193">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="12236-194">如果你的组织具有适用于 Office 365 的 Microsoft Defender，你将采用 **ATP** 保护应用步骤，以标识 [Microsoft Defender for Office 365](#policies-in-preset-security-policies) 保护适用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="12236-194">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="12236-195">设置和行为与适用于步骤 **的 EOP 保护完全相同** 。</span><span class="sxs-lookup"><span data-stu-id="12236-195">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="12236-196">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="12236-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="12236-197">在"**确认"** 步骤中，验证您的选择，然后单击"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="12236-197">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="12236-198">使用安全&合规中心修改预设安全策略的分配</span><span class="sxs-lookup"><span data-stu-id="12236-198">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="12236-199">修改标准保护或严格保护安全策略分配的步骤与最初向用户分配预设安全策略[时的步骤相同](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。</span><span class="sxs-lookup"><span data-stu-id="12236-199">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="12236-200">若要禁用 **标准保护** 或 **严格保护** 安全策略，同时仍保留现有条件和例外，将开关滑动到 **禁用**。</span><span class="sxs-lookup"><span data-stu-id="12236-200">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="12236-201">若要启用策略，将切换开关滑动到 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="12236-201">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="12236-202">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="12236-202">How do you know these procedures worked?</span></span>

<span data-ttu-id="12236-203">若要验证是否成功向用户分配了标准保护或严格保护安全策略，请使用默认值不同于"标准"保护设置（不同于"严格保护"设置）的保护设置。 </span><span class="sxs-lookup"><span data-stu-id="12236-203">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="12236-204">例如，对于被检测为垃圾邮件 (高可信度垃圾邮件) 验证邮件是否传递到 **标准** 保护用户的"垃圾邮件"文件夹，并隔离" **严格** 保护"用户。</span><span class="sxs-lookup"><span data-stu-id="12236-204">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="12236-205">或者，对于 [](bulk-complaint-level-values.md)批量电子邮件，验证 BCL 值 6 或更高版本是否将邮件发送到 **标准** 保护用户的垃圾邮件文件夹，BCL 值 4 或更高值会隔离严格保护用户的邮件。</span><span class="sxs-lookup"><span data-stu-id="12236-205">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>