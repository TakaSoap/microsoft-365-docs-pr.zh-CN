---
title: 在 EOP 中配置防钓鱼策略
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
description: 管理员可以了解如何创建、修改和删除在具有或不使用 Exchange Online 邮箱的情况下，在运行 EOP 和 () 组织的 Exchange Online Protection) 策略中使用的反网络钓鱼策略。
ms.openlocfilehash: af6577d32d43300867d29a365baaa4e1e7e1b5e3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825745"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="84976-103">在 EOP 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="84976-104">在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，默认提供默认的反网络钓鱼策略包含默认情况下启用的有限数量的反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="84976-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="84976-105">有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="84976-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="84976-106">管理员可以查看、编辑和配置 (但不能) 删除默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="84976-107">更精细地进行管理，还可以创建自定义防钓鱼策略，这些策略适用于组织中的特定用户、组或域。</span><span class="sxs-lookup"><span data-stu-id="84976-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="84976-108">自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="84976-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="84976-109">具有 Exchange Online 邮箱的组织可以在安全 & 合规中心或 Exchange Online PowerShell 中配置反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="84976-110">独立 EOP 组织只能使用安全与&合规中心。</span><span class="sxs-lookup"><span data-stu-id="84976-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="84976-111">有关创建和修改更高级的 ATP 反网络钓鱼策略在 Office 365 高级威胁防护 (Office 365 ATP) 中可用的信息，请参阅"[配置 ATP 防钓鱼策略"。](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="84976-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="84976-112">防钓鱼策略的基本要点包括：</span><span class="sxs-lookup"><span data-stu-id="84976-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="84976-113">**反钓鱼策略**：指定要启用或禁用的网络钓鱼防护以及应用选项的操作。</span><span class="sxs-lookup"><span data-stu-id="84976-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="84976-114">**反网络钓鱼规则：** 指定 (策略应用于反钓鱼策略) 的优先级和收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="84976-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="84976-115">在安全与合规中心管理反网络钓鱼策略时，这两&意不显而是：</span><span class="sxs-lookup"><span data-stu-id="84976-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="84976-116">创建反网络钓鱼策略时，实际上是在同时创建反钓鱼规则和关联的反钓鱼策略：对这两者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="84976-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="84976-117">修改反网络钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置可以修改反网络钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="84976-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="84976-118">所有其他设置都将修改关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="84976-119">删除反网络钓鱼策略时，将删除反网络钓鱼规则和关联的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="84976-120">在 Exchange Online PowerShell 中，您可以单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="84976-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="84976-121">有关详细信息，请参阅本主题 [后面的"使用 Exchange Online PowerShell 配置反网络钓鱼](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 策略"一节。</span><span class="sxs-lookup"><span data-stu-id="84976-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="84976-122">每个组织都有一个名为 Office365 AntiPhish Default 的内置反网络钓鱼策略，该策略具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="84976-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="84976-123">策略会应用于组织中的所有收件人，即使没有任何反网络 (网络钓鱼规则) 自定义收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="84976-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="84976-124">该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。</span><span class="sxs-lookup"><span data-stu-id="84976-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="84976-125">你创建的任何自定义策略始终具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="84976-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="84976-126">该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="84976-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="84976-127">若要提高防钓鱼防钓鱼保护的有效性，可以创建自定义反网络钓鱼策略，将这些设置应用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="84976-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="84976-128">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="84976-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="84976-129">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="84976-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="84976-130">若要直接转到 **"反网络钓鱼"页面，** 请使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="84976-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="84976-131">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="84976-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="84976-132">您不能在独立 EOP PowerShell 中管理反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="84976-133">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="84976-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="84976-134">若要添加、修改和删除反网络钓鱼策略，你需要是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="84976-134">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="84976-135">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="84976-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="84976-136">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="84976-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="84976-137">必须是以下角色组的成员之一，才能以只读方式访问反网络钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="84976-137">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="84976-138">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="84976-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="84976-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="84976-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="84976-140">为了能够在独立 EOP 中创建和修改反垃圾邮件策略，您需要执行一些需要 _对租户执行_ 代理的操作。</span><span class="sxs-lookup"><span data-stu-id="84976-140">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="84976-141">例如，在 Exchange 管理中心 (EAC) 中，您可以转到" **权限"** 选项卡，选择现有角色组，单击" **编辑** ![ " ](../../media/ITPro-EAC-EditIcon.png) 图标，然后 (删除最终将添加回的) 。</span><span class="sxs-lookup"><span data-stu-id="84976-141">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="84976-142">如果租户从未延迟，则会出现一个名为" **更新组织设置"的** 对话框，并显示应成功完成的进度栏。</span><span class="sxs-lookup"><span data-stu-id="84976-142">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="84976-143">有关 hydration 的详细信息，请参阅独立 EOP PowerShell 或安全与合规中心仪表板 &中不可用的 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet () 。</span><span class="sxs-lookup"><span data-stu-id="84976-143">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="84976-144">有关我们推荐的反网络钓鱼策略设置， [请参阅 EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="84976-144">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="84976-145">最多允许应用更新的策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="84976-145">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="84976-146">有关在筛选管道中应用防钓鱼策略的位置的信息，请参阅 [电子邮件保护的订单和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="84976-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="84976-147">使用安全与&合规中心来创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-147">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="84976-148">在安全 & 合规中心内创建自定义的反网络钓鱼策略将同时创建反钓鱼规则和关联的反钓鱼策略：将二者的同一名称用于两者。</span><span class="sxs-lookup"><span data-stu-id="84976-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="84976-149">在创建反网络钓鱼策略时，只能指定策略名称、描述和用于标识向其应用策略的收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="84976-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="84976-150">创建此策略后，可以修改该策略以更改或查看默认的防钓鱼设置。</span><span class="sxs-lookup"><span data-stu-id="84976-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="84976-151">在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="84976-152">在"**反网络钓鱼"页上，** 单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="84976-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="84976-153">将 **打开"创建新的反网络钓鱼** 策略向导"。</span><span class="sxs-lookup"><span data-stu-id="84976-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="84976-154">在" **命名策略"** 页面上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="84976-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="84976-155">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="84976-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="84976-156">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="84976-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="84976-157">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84976-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="84976-158">在 **显示的"** 已应用到"页上，确定向其应用策略的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="84976-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="84976-159">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="84976-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="84976-160">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="84976-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="84976-161">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="84976-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="84976-162">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="84976-162">Click **Add a condition**.</span></span> <span data-ttu-id="84976-163">在出现的下拉列表中，选择"已应用"下面的条件 **（如果出现该条件：）**</span><span class="sxs-lookup"><span data-stu-id="84976-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="84976-164">**收件人是**：指定您所在组织的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="84976-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="84976-165">**收件人为以下组的成员**：指定您所在组织的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="84976-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="84976-166">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="84976-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="84976-167">选择条件后，将出现相应的下拉列表，其中有一个 **其中任何一个** 框。</span><span class="sxs-lookup"><span data-stu-id="84976-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="84976-168">在框中单击，然后滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="84976-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="84976-169">单击此框，然后开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="84976-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="84976-170">若要添加其他值，请在框中的空白区域单击。</span><span class="sxs-lookup"><span data-stu-id="84976-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="84976-171">若要删除各个条目，请单击该值 **上的** ![ " ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="84976-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="84976-172">若要删除整个条件，请单击条件 **上的** ![ " ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="84976-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="84976-173">要添加其他条件，请单击" **添加一个条件"，** 并在"应用时"下选择其 **余值**。</span><span class="sxs-lookup"><span data-stu-id="84976-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="84976-174">要添加例外，请单击" **添加一个条件"，** 并在"除非"时 **选择例外情况**。</span><span class="sxs-lookup"><span data-stu-id="84976-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="84976-175">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="84976-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="84976-176">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84976-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="84976-177">在" **查看显示的** 设置"页上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="84976-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="84976-178">可以单击每个 **设置** 上的"编辑"以修改每个设置。</span><span class="sxs-lookup"><span data-stu-id="84976-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="84976-179">完成后，请单击"创建**此策略"。**</span><span class="sxs-lookup"><span data-stu-id="84976-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="84976-180">在 **出现** 的确认对话框中，单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="84976-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="84976-181">在使用这些常规策略设置创建反网络钓鱼策略之后，请使用下一节中的说明来配置策略中的保护设置。</span><span class="sxs-lookup"><span data-stu-id="84976-181">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="84976-182">使用安全&与网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-182">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="84976-183">使用以下过程修改反网络钓鱼策略：已创建的新策略或已自定义的现有策略。</span><span class="sxs-lookup"><span data-stu-id="84976-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="84976-184">如果你尚不在该位置，请打开安全与&合规中心，并转到 **威** \> **胁** \> **管理策略防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="84976-185">选择要修改的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="84976-186">如果已经选中，请取消选中它，然后重新选择它。</span><span class="sxs-lookup"><span data-stu-id="84976-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="84976-187">此\*\*时将显示" \<name\> \*\*编辑策略"浮出控件。</span><span class="sxs-lookup"><span data-stu-id="84976-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="84976-188">单击任何 **部分** 中的"编辑"可访问该节中的设置。</span><span class="sxs-lookup"><span data-stu-id="84976-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="84976-189">以下步骤按节显示的顺序显示，但它们不是一次性步骤 (您可以选择和修改这些部分，而无需按顺序) 。</span><span class="sxs-lookup"><span data-stu-id="84976-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="84976-190">单击部分**中的"编辑**"后，可用设置将以向导格式显示，但可以按任意顺序跳转到页面内，并且你可以在任一页面上单击"**保存**"或" (取消"**或"** 关闭"图标**Close** ![ ](../../media/scc-remove-icon.png) \*\* \<name\> \*\*以返回到"编辑策略"页面 (而无需访问向导的最后一页来保存或离开) 。</span><span class="sxs-lookup"><span data-stu-id="84976-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="84976-191">**策略设置**：单击 **"** 编辑"可修改与您在上一 [部分创建策略时](#use-the-security--compliance-center-to-create-anti-phishing-policies) 可用的设置相同的设置：</span><span class="sxs-lookup"><span data-stu-id="84976-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="84976-192">**名称**</span><span class="sxs-lookup"><span data-stu-id="84976-192">**Name**</span></span>
   - <span data-ttu-id="84976-193">**说明**</span><span class="sxs-lookup"><span data-stu-id="84976-193">**Description**</span></span>
   - <span data-ttu-id="84976-194">**应用于**</span><span class="sxs-lookup"><span data-stu-id="84976-194">**Applied to**</span></span>
   - <span data-ttu-id="84976-195">**查看你的设置**</span><span class="sxs-lookup"><span data-stu-id="84976-195">**Review your settings**</span></span>

   <span data-ttu-id="84976-196">完成后，在任何页面上单击" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="84976-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="84976-197">**欺骗**： **单击"编辑** "可打开或关闭欺骗智能，打开或关闭 Outlook 中的未经身份验证的发件人标识，以及将操作配置为应用于来自受阻止的欺骗性发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="84976-197">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="84976-198">有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="84976-198">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="84976-199">请注意，ATP 防钓鱼策略中也提供这些相同的设置。</span><span class="sxs-lookup"><span data-stu-id="84976-199">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="84976-200">**欺骗性筛选设置**：默认值是 **"打开"，** 建议将其保持为开。</span><span class="sxs-lookup"><span data-stu-id="84976-200">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="84976-201">若要将其关闭，请将切换开关滑动到 **"关闭"。**</span><span class="sxs-lookup"><span data-stu-id="84976-201">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="84976-202">有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="84976-202">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="84976-203">如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;改为启用连接器的增强筛选功能。</span><span class="sxs-lookup"><span data-stu-id="84976-203">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="84976-204">有关说明，请参阅["增强的 Exchange Online 中的连接器筛选"。](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="84976-204">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="84976-205">**启用未经身份验证的**发件人功能：默认值是**On。**</span><span class="sxs-lookup"><span data-stu-id="84976-205">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="84976-206">若要将其关闭，请将切换开关滑动到 **"关闭"。**</span><span class="sxs-lookup"><span data-stu-id="84976-206">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="84976-207">**操作**： 指定要对未通过欺骗智能的邮件采取的操作：</span><span class="sxs-lookup"><span data-stu-id="84976-207">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="84976-208">**如果电子邮件是由不允许欺骗你的域的人发送的**：</span><span class="sxs-lookup"><span data-stu-id="84976-208">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="84976-209">**将邮件移动到收件人的垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="84976-209">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="84976-210">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="84976-210">**Quarantine the message**</span></span>

   - <span data-ttu-id="84976-211">**查看你的设置**：设置显示在摘要中，而不是单击每个单独的步骤。</span><span class="sxs-lookup"><span data-stu-id="84976-211">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="84976-212">您可以单击 **每个** 部分中的"编辑"以跳转到相关页面。</span><span class="sxs-lookup"><span data-stu-id="84976-212">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="84976-213">可以直接在此页上**打开\*\*\*\*或关闭**以下设置：</span><span class="sxs-lookup"><span data-stu-id="84976-213">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="84976-214">**启用防欺骗保护**</span><span class="sxs-lookup"><span data-stu-id="84976-214">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="84976-215">**启用未经身份验证的发件人功能**</span><span class="sxs-lookup"><span data-stu-id="84976-215">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="84976-216">完成后，在任何页面上单击" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="84976-216">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="84976-217">返回到"编辑**策略" \<Name\> 页面**，查看设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="84976-217">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="84976-218">使用安全与&网络中心修改默认防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-218">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="84976-219">默认的反网络钓鱼策略名为"Office365 AntiPhish Default"，但不显示在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="84976-219">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="84976-220">若要修改默认防钓鱼策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="84976-220">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="84976-221">在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="84976-222">在"**防网络钓鱼"页上，** 单击"默认**策略"。**</span><span class="sxs-lookup"><span data-stu-id="84976-222">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="84976-223">此 **时将显示"编辑 Office365 防钓鱼 Default"** 页面。</span><span class="sxs-lookup"><span data-stu-id="84976-223">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="84976-224">以下部分均可用，它包含修改自定义策略时 [的相同设置](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="84976-224">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="84976-225">**模拟**</span><span class="sxs-lookup"><span data-stu-id="84976-225">**Impersonation**</span></span>
   - <span data-ttu-id="84976-226">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="84976-226">**Spoof**</span></span>
   - <span data-ttu-id="84976-227">**高级设置**</span><span class="sxs-lookup"><span data-stu-id="84976-227">**Advanced settings**</span></span>

   <span data-ttu-id="84976-228">修改默认策略时，以下设置不可用：</span><span class="sxs-lookup"><span data-stu-id="84976-228">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="84976-229">您可以看到" **策略设置"** 部分和值，但是没有 **编辑链接** ，因此不能修改设置 (策略名称、描述以及该策略适用于 (的人员（) 例如) ）。</span><span class="sxs-lookup"><span data-stu-id="84976-229">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="84976-230">不能删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="84976-230">You can't delete the default policy.</span></span>
   - <span data-ttu-id="84976-231">不能更改默认策略的优先级， (始终在上次应用的) 。</span><span class="sxs-lookup"><span data-stu-id="84976-231">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="84976-232">在"**编辑策略 Office365 防钓鱼默认'** 页面上，查看你的设置，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="84976-232">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="84976-233">启用或禁用自定义防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-233">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="84976-234">在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-234">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="84976-235">请注意"状态" **列中的** 值：</span><span class="sxs-lookup"><span data-stu-id="84976-235">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="84976-236">将切换开关滑 **动到** "关闭"可禁用此策略。</span><span class="sxs-lookup"><span data-stu-id="84976-236">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="84976-237">将切换按钮滑 **动到"** 启用"以启用策略。</span><span class="sxs-lookup"><span data-stu-id="84976-237">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="84976-238">无法禁用默认防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-238">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="84976-239">设置自定义反网络钓鱼策略的优先级</span><span class="sxs-lookup"><span data-stu-id="84976-239">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="84976-240">默认情况下，反网络钓鱼策略根据在策略创建顺序来获得 (新策略的优先级低于旧策略创建) 。</span><span class="sxs-lookup"><span data-stu-id="84976-240">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="84976-241">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="84976-241">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="84976-242">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="84976-242">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="84976-243">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="84976-243">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="84976-244">自定义的反网络钓鱼策略按处理它们时 (第一个策略的优先级值为 0 **) 。**</span><span class="sxs-lookup"><span data-stu-id="84976-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="84976-245">名为"Office365 AntiPhish Default"的默认反网络钓鱼策略的自定义优先级值 **"最低**"，你无法更改它。</span><span class="sxs-lookup"><span data-stu-id="84976-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="84976-246">**注意**：在&合规性中心内，只能在创建后更改防钓鱼策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="84976-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="84976-247">在 PowerShell 中，可在创建反网络钓鱼规则时 (它会影响现有规则的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="84976-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="84976-248">要更改策略的优先级，请单击**策略**属性中的"提高优先级"或**Decrease priority**"减少优先级 (无法直接修改安全 & 合规中心) 中的优先级) 。 **Priority**</span><span class="sxs-lookup"><span data-stu-id="84976-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="84976-249">仅当你有多个策略时，更改策略的优先级也有任何作用。</span><span class="sxs-lookup"><span data-stu-id="84976-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="84976-250">在安全与&中心内，转到 **威** \> **胁管理** \> **策略 ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="84976-251">选择要修改的策略。</span><span class="sxs-lookup"><span data-stu-id="84976-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="84976-252">如果已经选中，请取消选中它，然后重新选择它。</span><span class="sxs-lookup"><span data-stu-id="84976-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="84976-253">此\*\*时将显示" \<name\> \*\*编辑策略"浮出控件。</span><span class="sxs-lookup"><span data-stu-id="84976-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="84976-254">优先级值为 0 的自定义反网络**钓鱼\*\*\*\*策略**只有 **"减少优先级"按钮**可用。</span><span class="sxs-lookup"><span data-stu-id="84976-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="84976-255">优先级值较低的自定义反网络钓鱼 (例如 **，3** **Priority**) 保留策略只有"增加**优先级"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="84976-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="84976-256">如果你有三个或更多个自定义防钓鱼策略，则最高优先级和最低优先级值之间的策略会具有"增加优先级"**和\*\*\*\*"减少优先级**"按钮。</span><span class="sxs-lookup"><span data-stu-id="84976-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="84976-257">单击 **"提高优先级\*\*\*\*"或"减少优先级"以**更改**优先级**值。</span><span class="sxs-lookup"><span data-stu-id="84976-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="84976-258">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84976-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="84976-259">使用安全与&策略查看反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="84976-260">在安全与&中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="84976-261">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="84976-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="84976-262">选择要查看的自定义反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="84976-263">如果已经选中，请取消选中它，然后重新选择它。</span><span class="sxs-lookup"><span data-stu-id="84976-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="84976-264">单击 **"** 默认策略"以查看默认的预钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="84976-265">"\*\*编辑策略 \<name\> \*\*"浮出控件，可在其中查看设置和值。</span><span class="sxs-lookup"><span data-stu-id="84976-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="84976-266">使用安全与&中心可以删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="84976-267">在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="84976-268">选择要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="84976-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="84976-269">如果已经选中，请取消选中它，然后重新选择它。</span><span class="sxs-lookup"><span data-stu-id="84976-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="84976-270">在随**即显示 \<name\> **的策略浮出控件中，单击 **"删除策略**"，然后在**出现**的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="84976-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="84976-271">无法删除默认策略。</span><span class="sxs-lookup"><span data-stu-id="84976-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="84976-272">使用 Exchange Online PowerShell 配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="84976-273">如前所述，反垃圾邮件策略由一个反网络钓鱼策略和一个反网络钓鱼规则提供。</span><span class="sxs-lookup"><span data-stu-id="84976-273">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="84976-274">在 Exchange Online PowerShell 中，防钓鱼策略和反网络钓鱼规则之间的区别明显。</span><span class="sxs-lookup"><span data-stu-id="84976-274">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="84976-275">您可以使用\*\* \* -AntiPhishPolicy\*\* cmdlet 管理反钓鱼策略，并且可以通过\*\* \* 使用 -AntiPhishRule\*\* cmdlet 管理反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="84976-275">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="84976-276">在 PowerShell 中，先创建反钓鱼策略，然后再创建反网络钓鱼规则，以标识将向其应用的策略。</span><span class="sxs-lookup"><span data-stu-id="84976-276">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="84976-277">在 PowerShell 中，分别修改防钓鱼策略和防钓鱼规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="84976-277">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="84976-278">从 PowerShell 删除反网络钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦而是。</span><span class="sxs-lookup"><span data-stu-id="84976-278">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="84976-279">使用 Exchange Online Protection PowerShell 无法在独立 EOP 组织中执行下列 PowerShell 过程。</span><span class="sxs-lookup"><span data-stu-id="84976-279">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="84976-280">使用 PowerShell 创建反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-280">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="84976-281">在 PowerShell 中创建防钓鱼策略的过程分为两步：</span><span class="sxs-lookup"><span data-stu-id="84976-281">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="84976-282">创建反钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-282">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="84976-283">创建反网络钓鱼规则，以指定该规则将应用于的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-283">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="84976-284">**注意**：</span><span class="sxs-lookup"><span data-stu-id="84976-284">**Notes**:</span></span>

- <span data-ttu-id="84976-285">可以创建新的反钓鱼规则并向它分配现有的未关联的反钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-285">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="84976-286">一个反网络钓鱼规则不能与多个反网络钓鱼策略关联。</span><span class="sxs-lookup"><span data-stu-id="84976-286">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="84976-287">在创建策略之前，可以在 PowerShell 中配置新反钓鱼策略的以下设置，以防安全 & 合规中心内未提供：</span><span class="sxs-lookup"><span data-stu-id="84976-287">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="84976-288">为禁用状态中心 (对_Enabled_ `$false` **New-AntiPhishRule cmdlet 策略列表启用) 。**</span><span class="sxs-lookup"><span data-stu-id="84976-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="84976-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="84976-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="84976-290">在 PowerShell 中创建的新反网络钓鱼策略在安全 & 合规中心内不可见，除非你将策略分配到反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="84976-290">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="84976-291">步骤 1：使用 PowerShell 创建反钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-291">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="84976-292">若要创建反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-292">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="84976-293">本示例使用以下设置创建名为"研究隔离"的防钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="84976-293">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="84976-294">启用策略时 (没有使用 _Enabled 参数_ ，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="84976-294">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="84976-295">该说明是：研究部门策略。</span><span class="sxs-lookup"><span data-stu-id="84976-295">The description is: Research department policy.</span></span>
- <span data-ttu-id="84976-296">将欺骗的默认操作更改为隔离。</span><span class="sxs-lookup"><span data-stu-id="84976-296">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="84976-297">有关语法和参数的详细信息，请参阅[New-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="84976-297">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="84976-298">步骤 2：使用 PowerShell 创建反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="84976-298">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="84976-299">若要创建反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-299">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="84976-300">本示例创建名为"研究部门"的反网络钓鱼规则，规则为以下条件：</span><span class="sxs-lookup"><span data-stu-id="84976-300">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="84976-301">此规则与名为"研究隔离"的反网络钓鱼策略相关联。</span><span class="sxs-lookup"><span data-stu-id="84976-301">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="84976-302">此规则应用于“研究部门”组中的成员。</span><span class="sxs-lookup"><span data-stu-id="84976-302">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="84976-303">因为我们没有使用 _Priority 参数_ ，因此使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="84976-303">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="84976-304">有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="84976-304">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="84976-305">使用 PowerShell 查看反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-305">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="84976-306">若要查看现有的反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-306">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="84976-307">此示例返回所有反钓鱼策略的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="84976-307">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="84976-308">此示例返回名为"Executives"的防钓鱼策略的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="84976-308">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="84976-309">有关语法和参数的详细信息，请参阅[Get-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="84976-309">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="84976-310">使用 PowerShell 查看反网络钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="84976-310">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="84976-311">若要查看现有的反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-311">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="84976-312">本示例返回所有防钓鱼规则的摘要列表以及指定的属性。</span><span class="sxs-lookup"><span data-stu-id="84976-312">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="84976-313">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="84976-313">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="84976-314">本示例返回名为"Contoso Executives"的防钓鱼规则的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="84976-314">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="84976-315">有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="84976-315">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="84976-316">使用 PowerShell 修改防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-316">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="84976-317">除了以下项目之外，在 PowerShell 中修改反钓鱼策略时可用的设置，与在步骤 1 中创建策略时可用的设置相同，如本主题前面的步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建反网络钓鱼策略部分。</span><span class="sxs-lookup"><span data-stu-id="84976-317">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="84976-318">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone， **alwaysest** priority， and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84976-318">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="84976-319">无法在 **Set-AntiPhishPolicy** cmdlet 没有 _name_ 参数 (重命名反网络钓鱼策略) 。</span><span class="sxs-lookup"><span data-stu-id="84976-319">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="84976-320">在安全中心中重命名防钓 &鱼策略时，你仅将重命名反网络钓鱼 _规则_。</span><span class="sxs-lookup"><span data-stu-id="84976-320">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="84976-321">若要修改反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-321">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="84976-322">有关语法和参数的详细信息，请参阅[Set-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="84976-322">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="84976-323">使用 PowerShell 修改防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="84976-323">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="84976-324">在 PowerShell 中修改反钓鱼规则时，唯一不可用的设置 _是可以_ 创建已禁用规则的 Enabled 参数。</span><span class="sxs-lookup"><span data-stu-id="84976-324">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="84976-325">若要启用或禁用现有的反网络钓鱼规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="84976-325">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="84976-326">否则，在 PowerShell 中修改反钓鱼规则时，将无法使用其他设置。</span><span class="sxs-lookup"><span data-stu-id="84976-326">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="84976-327">创建规则时可用的设置，与 [步骤 2：使用 PowerShell 创建本主题](#step-2-use-powershell-to-create-an-anti-phish-rule) 前面介绍的反网络钓鱼规则部分时可用的设置相同。</span><span class="sxs-lookup"><span data-stu-id="84976-327">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="84976-328">若要修改反网络钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-328">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="84976-329">有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="84976-329">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="84976-330">使用 PowerShell 启用或禁用防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="84976-330">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="84976-331">在 PowerShell 中启用或禁用防钓鱼规则会启用或禁用整个防钓鱼策略 (以及分配的反网络钓鱼策略) 。</span><span class="sxs-lookup"><span data-stu-id="84976-331">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="84976-332">您无法启用或禁用默认的反网络钓鱼策略 (所有收件人都将始终应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="84976-332">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="84976-333">若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-333">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="84976-334">本示例禁用名为"Marketing Department"的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="84976-334">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="84976-335">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="84976-335">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="84976-336">有关语法和参数的详细信息，请参阅 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) 和 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="84976-336">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="84976-337">使用 PowerShell 设置防钓鱼规则的优先级</span><span class="sxs-lookup"><span data-stu-id="84976-337">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="84976-338">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="84976-338">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="84976-339">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="84976-339">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="84976-340">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="84976-340">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="84976-341">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="84976-341">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="84976-342">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="84976-342">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="84976-343">若要在 PowerShell 中设置反钓鱼规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-343">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="84976-344">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="84976-344">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="84976-345">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="84976-345">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="84976-346">**注意**：</span><span class="sxs-lookup"><span data-stu-id="84976-346">**Notes**:</span></span>

- <span data-ttu-id="84976-347">若要在创建新规则时设置它的优先级，请对**New-AntiPhishRule** cmdlet 使用_Priority_参数。</span><span class="sxs-lookup"><span data-stu-id="84976-347">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="84976-348">默认的防钓鱼策略没有相应的防钓鱼规则，且始终具有不可修改的优先级值 **"最低"。**</span><span class="sxs-lookup"><span data-stu-id="84976-348">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="84976-349">使用 PowerShell 删除防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="84976-349">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="84976-350">使用 PowerShell 删除反网络钓鱼策略时，不会删除相应的反钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="84976-350">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="84976-351">若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-351">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="84976-352">本示例将删除名为 Marketing Department 的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-352">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="84976-353">有关语法和参数的详细信息，请参阅[Remove-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="84976-353">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="84976-354">使用 PowerShell 删除防钓鱼规则</span><span class="sxs-lookup"><span data-stu-id="84976-354">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="84976-355">使用 PowerShell 删除防钓鱼规则时，不会删除相应的反钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="84976-355">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="84976-356">若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="84976-356">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="84976-357">本示例删除名为"Marketing Department"的防钓鱼规则。</span><span class="sxs-lookup"><span data-stu-id="84976-357">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="84976-358">有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="84976-358">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="84976-359">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="84976-359">How do you know these procedures worked?</span></span>

<span data-ttu-id="84976-360">若要验证是否已成功配置 ATP 防钓鱼策略，请执行以下任意步骤：</span><span class="sxs-lookup"><span data-stu-id="84976-360">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="84976-361">在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="84976-361">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="84976-362">验证策略列表、其 **状态** 值及其 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="84976-362">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="84976-363">若要查看更多详细信息，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="84976-363">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="84976-364">从列表中选择该策略，并在浮出控件中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="84976-364">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="84976-365">单击 **"默认** 策略"并在浮出控件中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="84976-365">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="84976-366">在 Exchange Online PowerShell 中 \<Name\> ，将策略或规则的名称替换为策略或规则，并运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="84976-366">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
