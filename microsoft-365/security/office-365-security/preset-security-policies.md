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
description: '管理员可以了解如何在 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护策略 ATP 策略的保护功能上应用 (条) '
ms.openlocfilehash: a2f0472d8dd44c90fd5db14e71d2db0d5d323b50
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825253"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="6415a-103">EOP 和 Office 365 ATP 中的预设安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-103">Preset security policies in EOP and Office 365 ATP</span></span>

<span data-ttu-id="6415a-104">预设安全策略提供了一个集中位置，用于一次性向用户应用所有推荐的垃圾邮件、恶意软件和网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="6415a-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="6415a-105">策略设置不可配置。</span><span class="sxs-lookup"><span data-stu-id="6415a-105">The policy settings are not configurable.</span></span> <span data-ttu-id="6415a-106">而是由我们设置这些功能，它们基于我们在数据中心中的观察和体验，在保持无害内容从用户中断而不会中断其工作之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="6415a-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="6415a-107">本主题的其余部分介绍预设的安全策略以及如何配置它们。</span><span class="sxs-lookup"><span data-stu-id="6415a-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="6415a-108">制作哪些预设安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-108">What preset security policies are made of</span></span>

<span data-ttu-id="6415a-109">预设安全策略由以下元素组成：</span><span class="sxs-lookup"><span data-stu-id="6415a-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="6415a-110">配置文件</span><span class="sxs-lookup"><span data-stu-id="6415a-110">Profiles</span></span>
- <span data-ttu-id="6415a-111">策略</span><span class="sxs-lookup"><span data-stu-id="6415a-111">Policies</span></span>
- <span data-ttu-id="6415a-112">策略设置</span><span class="sxs-lookup"><span data-stu-id="6415a-112">Policy settings</span></span>

<span data-ttu-id="6415a-113">此外，如果有多个预设安全策略和其他策略适用于同一个人，则优先级的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="6415a-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="6415a-114">预设安全策略中的配置文件</span><span class="sxs-lookup"><span data-stu-id="6415a-114">Profiles in preset security policies</span></span>

<span data-ttu-id="6415a-115">配置文件确定保护级别。</span><span class="sxs-lookup"><span data-stu-id="6415a-115">A profile determines the level of protection.</span></span> <span data-ttu-id="6415a-116">提供了以下配置文件：</span><span class="sxs-lookup"><span data-stu-id="6415a-116">The following profiles are available:</span></span>

- <span data-ttu-id="6415a-117">**标准保护**： 适合大多数用户的基础保护配置文件。</span><span class="sxs-lookup"><span data-stu-id="6415a-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="6415a-118">**严格的保护**：适用于选定用户的更级 (目标或优先级的用户的更严格的) 。</span><span class="sxs-lookup"><span data-stu-id="6415a-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="6415a-119">您使用具有条件和例外的规则，这些规则可确定配置文件是或不适用于哪些人。</span><span class="sxs-lookup"><span data-stu-id="6415a-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="6415a-120">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="6415a-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="6415a-121">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="6415a-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6415a-122">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="6415a-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="6415a-123">可用的条件和例外如下所示：</span><span class="sxs-lookup"><span data-stu-id="6415a-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="6415a-124">**收件人是**：组织中的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="6415a-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="6415a-125">**收件人为以下组的成员**：您组织中的组。</span><span class="sxs-lookup"><span data-stu-id="6415a-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="6415a-126">**收件人域是：** 在 Microsoft 365 中配置的接受域。</span><span class="sxs-lookup"><span data-stu-id="6415a-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="6415a-127">预设安全策略中的策略</span><span class="sxs-lookup"><span data-stu-id="6415a-127">Policies in preset security policies</span></span>

<span data-ttu-id="6415a-128">预设安全策略使用 EOP 和 Office 365 ATP 中各种保护功能的相应策略。</span><span class="sxs-lookup"><span data-stu-id="6415a-128">Preset security policies use the corresponding policies from the various protection features in EOP and Office 365 ATP.</span></span> <span data-ttu-id="6415a-129">在向用户 _分配标准_ 保护 **或** 严格 **保护预设** 安全策略后，将创建这些策略。</span><span class="sxs-lookup"><span data-stu-id="6415a-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="6415a-130">您无法修改这些策略。</span><span class="sxs-lookup"><span data-stu-id="6415a-130">You can't modify these policies.</span></span>

- <span data-ttu-id="6415a-131">**Exchange Online Protection (EOP) 策略**：包括具有 Exchange Online 邮箱的 Microsoft 365 组织和独立的 EOP 组织，无需 Exchange Online 邮箱：</span><span class="sxs-lookup"><span data-stu-id="6415a-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="6415a-132">[名为"标准预](configure-your-spam-filter-policies.md)**设安全策略"和"严\*\*\*\*格预设安全策略"的反垃圾邮件策略**。</span><span class="sxs-lookup"><span data-stu-id="6415a-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="6415a-133">[名为"标准预](configure-anti-malware-policies.md)**设安全策略"和"严\*\*\*\*格预设安全策略"的反恶意软件策略**。</span><span class="sxs-lookup"><span data-stu-id="6415a-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="6415a-134">[EOP 反网络钓鱼策略（名为](set-up-anti-phishing-policies.md#spoof-settings)**"标准预设安全策略"\*\*\*\*和"严格预设安全** (策略）防欺骗) 。</span><span class="sxs-lookup"><span data-stu-id="6415a-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="6415a-135">**Office 365 高级威胁防 (ATP) 策略**：其中包括订阅有 Microsoft 365 E5 或 Office 365 ATP 的组织：</span><span class="sxs-lookup"><span data-stu-id="6415a-135">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="6415a-136">名为"标准预设安全策略"和"严格预 **设安全** 策略"的 ATP **防钓鱼策略**，包括：</span><span class="sxs-lookup"><span data-stu-id="6415a-136">ATP anti-phishing policies named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="6415a-137">EOP [反网络](set-up-anti-phishing-policies.md#spoof-settings) 钓鱼策略中提供的相同欺骗设置。</span><span class="sxs-lookup"><span data-stu-id="6415a-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="6415a-138">模拟设置</span><span class="sxs-lookup"><span data-stu-id="6415a-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="6415a-139">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="6415a-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="6415a-140">[名为标准预设](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)**安全策略和严格\*\*\*\*预设安全策略的安全链接策略**。</span><span class="sxs-lookup"><span data-stu-id="6415a-140">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="6415a-141">[名为"标准预](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)**设安全策略"和"严\*\*\*\*格预设安全策略"的安全附件策略**。</span><span class="sxs-lookup"><span data-stu-id="6415a-141">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="6415a-142">请注意，EOP 保护可以对不同于 ATP 保护的用户应用 EOP 保护。</span><span class="sxs-lookup"><span data-stu-id="6415a-142">Note that you can apply EOP protections to different users than ATP protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="6415a-143">预设安全策略中的策略设置</span><span class="sxs-lookup"><span data-stu-id="6415a-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="6415a-144">您无法修改保护配置文件中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="6415a-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="6415a-145">**"EOP"\*\*\*\*和"Office** 365 ATP 安全"推荐[设置中描述了标准和严格策略设置值](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="6415a-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="6415a-146">预设的安全策略和其他策略的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="6415a-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="6415a-147">如果向用户应用多个策略，将按以下顺序应用到最低优先级：</span><span class="sxs-lookup"><span data-stu-id="6415a-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="6415a-148">**严格保护预** 设安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="6415a-149">**标准保护** 预设安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="6415a-150">自定义安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-150">Custom security policies</span></span>
4. <span data-ttu-id="6415a-151">默认安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-151">Default security policies</span></span>

<span data-ttu-id="6415a-152">换言之，严格 **保护策略的** 设置会覆盖标准保护策略 **的** 设置，它会覆盖自定义策略的设置，该策略会覆盖默认策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="6415a-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="6415a-153">向用户分配预设安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6415a-154">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="6415a-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6415a-155">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="6415a-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6415a-156">若要直接转到"预设 **安全策略"** 页，请使用 <https://protection.office.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="6415a-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="6415a-157">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6415a-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6415a-158">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="6415a-158">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="6415a-159">若要配置预设安全策略，您必须是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="6415a-159">To configure preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="6415a-160">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="6415a-160">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="6415a-161">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="6415a-161">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="6415a-162">若要对预设安全策略进行只读访问，您需要是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="6415a-162">For read-only access to preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="6415a-163">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="6415a-163">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="6415a-164">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="6415a-164">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="6415a-165">使用安全与&中心向用户分配预设安全策略</span><span class="sxs-lookup"><span data-stu-id="6415a-165">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="6415a-166">在安全与合规&中心内，转到 **威胁** \> **管理** \> **策略预设安全策略**。</span><span class="sxs-lookup"><span data-stu-id="6415a-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="6415a-167">在 **"标准保护**或**严格保护"下，单击**"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="6415a-167">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="6415a-168">此**时将启动\*\*\*\*"应用标准保护"或"应用严**格保护"向导。</span><span class="sxs-lookup"><span data-stu-id="6415a-168">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="6415a-169">在 **EOP 保护应用于步骤** 时，确定将应用 EOP 保护 [的内部](#policies-in-preset-security-policies) 收件人：</span><span class="sxs-lookup"><span data-stu-id="6415a-169">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="6415a-170">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="6415a-170">Click **Add a condition**.</span></span> <span data-ttu-id="6415a-171">在出现的下拉列表中，选择"已应用"下面的条件 **（如果出现该条件：）**</span><span class="sxs-lookup"><span data-stu-id="6415a-171">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="6415a-172">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="6415a-172">**The recipients are**</span></span>
      - <span data-ttu-id="6415a-173">**收件人为以下项的成员**</span><span class="sxs-lookup"><span data-stu-id="6415a-173">**The recipients are members of**</span></span>
      - <span data-ttu-id="6415a-174">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="6415a-174">**The recipient domains are**</span></span>

      <span data-ttu-id="6415a-175">您只能使用一次条件，但可为该条件指定多个值。</span><span class="sxs-lookup"><span data-stu-id="6415a-175">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="6415a-176">同一条件的多个值使用 OR (例如 _\<recipient1\>_ _\<recipient2\>_ ，) 。</span><span class="sxs-lookup"><span data-stu-id="6415a-176">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="6415a-177">您选择的条件将显示在具有底纹的部分中。</span><span class="sxs-lookup"><span data-stu-id="6415a-177">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="6415a-178">在该部分，单击" **任意内容"** 框。</span><span class="sxs-lookup"><span data-stu-id="6415a-178">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="6415a-179">如果等待等待，将显示一个列表，以便您可以选择一个值。</span><span class="sxs-lookup"><span data-stu-id="6415a-179">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="6415a-180">或者，可以开始键入一个值来筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="6415a-180">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="6415a-181">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="6415a-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="6415a-182">若要删除单个值，请单击该值 **上的"** ![ ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="6415a-182">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="6415a-183">要删除整个条件，请单击条件 **上的** ![ " ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="6415a-183">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="6415a-184">要添加其他条件，请单击 **"添加一个条件** ，并从其余条件中进行选择"。</span><span class="sxs-lookup"><span data-stu-id="6415a-184">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="6415a-185">例如，不同的条件使用 AND (逻辑 _\<recipient1\>_ ， _\<member of group 1\>_ 以及) 。</span><span class="sxs-lookup"><span data-stu-id="6415a-185">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="6415a-186">重复上一步向条件中添加值，并根据需要多次重复此步骤，直到您不在条件运行状态。</span><span class="sxs-lookup"><span data-stu-id="6415a-186">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="6415a-187">若要添加例外，请单击"**添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="6415a-187">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="6415a-188">在出现的下拉列表中，选择"除非"时 **的条件**。</span><span class="sxs-lookup"><span data-stu-id="6415a-188">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="6415a-189">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="6415a-189">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6415a-190">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6415a-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6415a-191">如果你的组织拥有 Office 365 ATP，则 **你将转到 ATP** 保护来识别要应用 [Office 365 ATP 保护](#policies-in-preset-security-policies) 的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="6415a-191">If your organization has Office 365 ATP, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Office 365 ATP protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="6415a-192">设置和行为与 EOP 保护完全 **一样，步骤要应用到** EOP 保护。</span><span class="sxs-lookup"><span data-stu-id="6415a-192">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="6415a-193">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6415a-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6415a-194">在 **"确认**步骤"上，验证您的选择，然后单击"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="6415a-194">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="6415a-195">使用安全与&合规中心修改预设安全策略的分配</span><span class="sxs-lookup"><span data-stu-id="6415a-195">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="6415a-196">修改标准保护或严格 **保护** 安全策略分配 **的** 步骤与初始向用户分配 [预设的安全策略时的相同](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。</span><span class="sxs-lookup"><span data-stu-id="6415a-196">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="6415a-197">当仍**保留现有条件**和**例外的同时，若要**禁用标准保护或严格保护安全策略，请将切换滑动到 **"已禁用"。**</span><span class="sxs-lookup"><span data-stu-id="6415a-197">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="6415a-198">若要启用策略，请将切换滑动 **到启用**。</span><span class="sxs-lookup"><span data-stu-id="6415a-198">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6415a-199">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="6415a-199">How do you know these procedures worked?</span></span>

<span data-ttu-id="6415a-200">若要验证是否向用户成功分配了标准保护**Standard protection**或严**格**保护安全策略，请使用保护设置，其中默认值与标准保护设置不同，此设置与**严格保护设置不同**。 **Standard protection**</span><span class="sxs-lookup"><span data-stu-id="6415a-200">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="6415a-201">例如，对于检测为垃圾邮件的电子邮件 (非高可信度垃圾邮件) 验证此邮件是否是标准保护用户的"垃圾邮件 **"文件夹**，并已隔离为 **"严格保护用户"。**</span><span class="sxs-lookup"><span data-stu-id="6415a-201">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="6415a-202">或者，对于 [批量电子邮件，](bulk-complaint-level-values.md)请验证 BCL 值 6 或更高版本是否将邮件传递到标准保护用户的 **垃圾邮件文件夹，** 而 BCL 值 4 或更高则隔离此邮件以 **供严格保护** 用户使用。</span><span class="sxs-lookup"><span data-stu-id="6415a-202">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
