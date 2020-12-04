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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 的保护功能中应用标准和严格的策略设置
ms.openlocfilehash: e968f7ea768ac8a0b402c28f3830a52b44afa342
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572773"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="bbad3-103">EOP 和 Microsoft Defender for Office 365 中的预设安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bbad3-104">预设安全策略提供了一个集中位置，用于一次性将所有建议的垃圾邮件、恶意软件和网络钓鱼策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="bbad3-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="bbad3-105">策略设置是不可配置的。</span><span class="sxs-lookup"><span data-stu-id="bbad3-105">The policy settings are not configurable.</span></span> <span data-ttu-id="bbad3-106">相反，它们由美国进行设置，并基于我们在数据中心中的观察和体验，以实现在不中断用户的情况下保持有害内容的平衡。</span><span class="sxs-lookup"><span data-stu-id="bbad3-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="bbad3-107">本主题的其余部分介绍了预设的安全策略以及如何对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="bbad3-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="bbad3-108">组成的预设安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-108">What preset security policies are made of</span></span>

<span data-ttu-id="bbad3-109">预设安全策略包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="bbad3-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="bbad3-110">配置文件</span><span class="sxs-lookup"><span data-stu-id="bbad3-110">Profiles</span></span>
- <span data-ttu-id="bbad3-111">策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-111">Policies</span></span>
- <span data-ttu-id="bbad3-112">策略设置</span><span class="sxs-lookup"><span data-stu-id="bbad3-112">Policy settings</span></span>

<span data-ttu-id="bbad3-113">此外，如果多个预设安全策略和其他策略适用于同一个人，则优先级顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="bbad3-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="bbad3-114">预设安全策略中的配置文件</span><span class="sxs-lookup"><span data-stu-id="bbad3-114">Profiles in preset security policies</span></span>

<span data-ttu-id="bbad3-115">配置文件确定保护级别。</span><span class="sxs-lookup"><span data-stu-id="bbad3-115">A profile determines the level of protection.</span></span> <span data-ttu-id="bbad3-116">以下配置文件可用：</span><span class="sxs-lookup"><span data-stu-id="bbad3-116">The following profiles are available:</span></span>

- <span data-ttu-id="bbad3-117">**标准保护**：适用于大多数用户的基准保护配置文件。</span><span class="sxs-lookup"><span data-stu-id="bbad3-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="bbad3-118">**严格保护**：针对所选用户的更为严格的保护配置文件 (高价值目标或优先级用户) 。</span><span class="sxs-lookup"><span data-stu-id="bbad3-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="bbad3-119">您将规则与条件和例外一起使用，以确定哪些配置文件是哪些或哪些不适用。</span><span class="sxs-lookup"><span data-stu-id="bbad3-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="bbad3-120">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="bbad3-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="bbad3-121">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="bbad3-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="bbad3-122">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="bbad3-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="bbad3-123">可用的条件和例外情况如下：</span><span class="sxs-lookup"><span data-stu-id="bbad3-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="bbad3-124">**收件人为**：组织中的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="bbad3-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="bbad3-125">**收件人是组织中的组的成员**。</span><span class="sxs-lookup"><span data-stu-id="bbad3-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="bbad3-126">**收件人域为**：在 Microsoft 365 中配置的接受域。</span><span class="sxs-lookup"><span data-stu-id="bbad3-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="bbad3-127">预设安全策略中的策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-127">Policies in preset security policies</span></span>

<span data-ttu-id="bbad3-128">预设安全策略使用 EOP 和 Microsoft Defender for Office 365 中的各种保护功能中对应的策略。</span><span class="sxs-lookup"><span data-stu-id="bbad3-128">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="bbad3-129">将 **标准保护** 或 **严格保护** 预设安全策略分配给用户 _后_，将创建这些策略。</span><span class="sxs-lookup"><span data-stu-id="bbad3-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="bbad3-130">您不能修改这些策略。</span><span class="sxs-lookup"><span data-stu-id="bbad3-130">You can't modify these policies.</span></span>

- <span data-ttu-id="bbad3-131">**Exchange Online Protection (EOP) 策略**：这包括具有 exchange online 邮箱和独立 EOP 组织的 Microsoft 365 组织，而无需使用 exchange online 邮箱：</span><span class="sxs-lookup"><span data-stu-id="bbad3-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="bbad3-132">名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bbad3-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="bbad3-133">名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bbad3-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="bbad3-134">EOP 欺骗设置 (的名为 **标准预设安全策略** 和 **严格预设安全策略**[的反网络钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)) 。</span><span class="sxs-lookup"><span data-stu-id="bbad3-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="bbad3-135">**Microsoft Defender For office 365 策略**：这包括具有 Microsoft 365 E5 或 Defender for office 365 附加订阅的组织：</span><span class="sxs-lookup"><span data-stu-id="bbad3-135">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="bbad3-136">Microsoft Defender for Office 365 中名为 **标准预设安全策略** 和 **严格预设安全策略** 的反网络钓鱼策略，其中包括：</span><span class="sxs-lookup"><span data-stu-id="bbad3-136">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="bbad3-137">EOP 反网络钓鱼策略中提供的相同 [欺骗设置](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="bbad3-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="bbad3-138">模拟设置</span><span class="sxs-lookup"><span data-stu-id="bbad3-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="bbad3-139">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="bbad3-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="bbad3-140">名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bbad3-140">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="bbad3-141">名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bbad3-141">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="bbad3-142">请注意，您可以将 EOP 保护应用于与 Microsoft Defender for Office 365 保护不同的用户。</span><span class="sxs-lookup"><span data-stu-id="bbad3-142">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="bbad3-143">预设安全策略中的策略设置</span><span class="sxs-lookup"><span data-stu-id="bbad3-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="bbad3-144">不能在保护配置文件中修改策略设置。</span><span class="sxs-lookup"><span data-stu-id="bbad3-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="bbad3-145">[EOP 和 Microsoft Defender For Office 365 security 中的建议设置](recommended-settings-for-eop-and-office365-atp.md)中介绍了 **标准** 和 **严格** 的策略设置值。</span><span class="sxs-lookup"><span data-stu-id="bbad3-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="bbad3-146">预设安全策略和其他策略的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="bbad3-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="bbad3-147">向用户应用多个策略时，将从最高优先级到最低优先级应用以下顺序：</span><span class="sxs-lookup"><span data-stu-id="bbad3-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="bbad3-148">**严格保护** 预设安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="bbad3-149">**标准保护** 预设安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="bbad3-150">自定义安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-150">Custom security policies</span></span>
4. <span data-ttu-id="bbad3-151">默认安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-151">Default security policies</span></span>

<span data-ttu-id="bbad3-152">换言之， **严格保护** 策略的设置会覆盖 **标准保护** 策略的设置，这将覆盖自定义策略中的设置，这将覆盖默认策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="bbad3-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="bbad3-153">为用户分配预设的安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bbad3-154">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="bbad3-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bbad3-155">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="bbad3-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bbad3-156">若要直接转到 " **预设安全策略** " 页，请使用 <https://protection.office.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="bbad3-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="bbad3-157">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bbad3-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bbad3-158">您需要先分配权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="bbad3-158">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="bbad3-159">若要配置预设安全策略，您需要是 [安全 & 合规性中心](permissions-in-the-security-and-compliance-center.md)中的 "**组织管理**" 或 "**安全管理员**" 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="bbad3-159">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="bbad3-160">若要对预设安全策略进行只读访问，您需要是 [安全 & 合规性中心](permissions-in-the-security-and-compliance-center.md)中 **全局读取器** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="bbad3-160">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="bbad3-161">使用安全 & 合规性中心向用户分配预设的安全策略</span><span class="sxs-lookup"><span data-stu-id="bbad3-161">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="bbad3-162">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **预设安全策略**"。</span><span class="sxs-lookup"><span data-stu-id="bbad3-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="bbad3-163">在 " **标准保护** 或 **严格保护**" 下，单击 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bbad3-163">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="bbad3-164">将启动 " **应用标准保护** " 或 " **应用严格保护** " 向导。</span><span class="sxs-lookup"><span data-stu-id="bbad3-164">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="bbad3-165">在 **EOP 保护应用** 于步骤中，确定 [EOP 防护](#policies-in-preset-security-policies) 适用于的内部收件人：</span><span class="sxs-lookup"><span data-stu-id="bbad3-165">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="bbad3-166">单击 " **添加条件**"。</span><span class="sxs-lookup"><span data-stu-id="bbad3-166">Click **Add a condition**.</span></span> <span data-ttu-id="bbad3-167">在出现的下拉列表中，选择 " **应用** 条件：</span><span class="sxs-lookup"><span data-stu-id="bbad3-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="bbad3-168">**收件人是**</span><span class="sxs-lookup"><span data-stu-id="bbad3-168">**The recipients are**</span></span>
      - <span data-ttu-id="bbad3-169">**收件人是的成员**</span><span class="sxs-lookup"><span data-stu-id="bbad3-169">**The recipients are members of**</span></span>
      - <span data-ttu-id="bbad3-170">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="bbad3-170">**The recipient domains are**</span></span>

      <span data-ttu-id="bbad3-171">仅可以使用一次条件，但可以为条件指定多个值。</span><span class="sxs-lookup"><span data-stu-id="bbad3-171">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="bbad3-172">同一条件的多个值使用或逻辑 (例如 _\<recipient1\>_ 或 _\<recipient2\>_) 。</span><span class="sxs-lookup"><span data-stu-id="bbad3-172">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="bbad3-173">选定的条件将显示在着色部分中。</span><span class="sxs-lookup"><span data-stu-id="bbad3-173">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="bbad3-174">在该部分中，单击 **任一** 框中的 ""。</span><span class="sxs-lookup"><span data-stu-id="bbad3-174">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="bbad3-175">如果你等待一段时间，将显示一个列表，以便你可以选择一个值。</span><span class="sxs-lookup"><span data-stu-id="bbad3-175">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="bbad3-176">或者，可以开始键入值来筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="bbad3-176">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="bbad3-177">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="bbad3-177">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="bbad3-178">若要删除单个值，请单击值上的 " **删除** ![ 删除 ](../../media/scc-remove-icon.png) " 图标。</span><span class="sxs-lookup"><span data-stu-id="bbad3-178">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="bbad3-179">若要删除整个条件，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="bbad3-179">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="bbad3-180">若要添加其他条件，请单击 " **添加条件** "，然后从其余条件中进行选择。</span><span class="sxs-lookup"><span data-stu-id="bbad3-180">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="bbad3-181">不同的条件使用和逻辑 (例如， _\<recipient1\>_ 和 _\<member of group 1\>_) 。</span><span class="sxs-lookup"><span data-stu-id="bbad3-181">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="bbad3-182">重复上一步以向条件中添加值，并根据需要多次重复此步骤，或在条件不足之前重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="bbad3-182">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="bbad3-183">若要添加例外，请单击 " **添加条件**"。</span><span class="sxs-lookup"><span data-stu-id="bbad3-183">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="bbad3-184">在出现的下拉列表中，选择 " **如果条件除外**" 下的条件。</span><span class="sxs-lookup"><span data-stu-id="bbad3-184">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="bbad3-185">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="bbad3-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="bbad3-186">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bbad3-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bbad3-187">如果你的组织具有 Microsoft Defender for Office 365，则将转到 **ATP 防护适用** 于步骤，以确定 [Microsoft defender for Office 365 防护](#policies-in-preset-security-policies) 适用的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="bbad3-187">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="bbad3-188">设置和行为与 **EOP 保护应用** 于步骤完全一样。</span><span class="sxs-lookup"><span data-stu-id="bbad3-188">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="bbad3-189">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bbad3-189">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bbad3-190">在 " **确认** 步骤" 中，验证您的选择，然后单击 " **确认**"。</span><span class="sxs-lookup"><span data-stu-id="bbad3-190">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="bbad3-191">使用安全 & 合规性中心修改预设安全策略的分配</span><span class="sxs-lookup"><span data-stu-id="bbad3-191">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="bbad3-192">修改 **标准保护** 或 **严格保护** 安全策略分配的步骤与最初 [向用户分配预设安全策略](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)的步骤相同。</span><span class="sxs-lookup"><span data-stu-id="bbad3-192">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="bbad3-193">若要禁用 **标准保护** 或 **严格保护** 安全策略，同时仍保留现有条件和例外，请将开关滑动到 " **已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="bbad3-193">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="bbad3-194">若要启用这些策略，请将开关滑动到 " **已启用**"。</span><span class="sxs-lookup"><span data-stu-id="bbad3-194">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bbad3-195">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="bbad3-195">How do you know these procedures worked?</span></span>

<span data-ttu-id="bbad3-196">若要验证是否已成功将 **标准保护** 或 **严格保护** 安全策略分配给用户，请使用默认值不同于 **标准保护** 设置的保护设置，该设置不同于 **严格的保护** 设置。</span><span class="sxs-lookup"><span data-stu-id="bbad3-196">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="bbad3-197">例如，对于检测为垃圾邮件的电子邮件 (不高可信度垃圾邮件) 验证是否将邮件传递到 **标准保护** 用户的 "垃圾邮件" 文件夹，并为 **严格的保护** 用户隔离。</span><span class="sxs-lookup"><span data-stu-id="bbad3-197">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="bbad3-198">或者，对于 [批量电子邮件](bulk-complaint-level-values.md)，请验证 BCL 值6或更高将邮件传递到 **标准保护** 用户的 "垃圾邮件" 文件夹，bcl 值4或更高版本将隔离邮件的 **严格保护** 用户。</span><span class="sxs-lookup"><span data-stu-id="bbad3-198">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
