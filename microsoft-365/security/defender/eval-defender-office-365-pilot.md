---
title: 试用 Microsoft Defender for Office 365，在生产环境中使用评估，提升评估以在生产中运行，了解如何评估 Defender
description: 针对活动用户和现有用户组试点评估的步骤，以便正确测试 Microsoft Defender for Office 365。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 86f8dcc7b5e06605042f609ede4027510663cc65
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457668"
---
# <a name="pilot-microsoft-defender-for-office-365"></a><span data-ttu-id="72edf-103">试用 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="72edf-103">Pilot Microsoft Defender for Office 365</span></span>
<span data-ttu-id="72edf-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="72edf-104">**Applies to:**</span></span>
- <span data-ttu-id="72edf-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72edf-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="72edf-106">本文是设置 Microsoft Defender for Office 365 评估环境过程中的第 3 步（第[3](eval-defender-office-365-overview.md) Office 365）。</span><span class="sxs-lookup"><span data-stu-id="72edf-106">This article is [Step 3 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="72edf-107">有关此过程详细信息，请参阅 [概述文章](eval-defender-office-365-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="72edf-107">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="72edf-108">使用以下步骤设置和配置 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="72edf-108">Use the following steps to setup and configure the pilot for Microsoft Defender for Office 365.</span></span>

![为 Microsoft Defender for Office 365](../../media/defender/m365-defender-office-pilot.png)

- [<span data-ttu-id="72edf-110">步骤 1：创建试点组</span><span class="sxs-lookup"><span data-stu-id="72edf-110">Step 1: Create pilot groups</span></span>](#step-1-create-pilot-groups)
- [<span data-ttu-id="72edf-111">步骤 2：配置保护</span><span class="sxs-lookup"><span data-stu-id="72edf-111">Step 2: Configure protection</span></span>](#step-2-configure-protection)
- [<span data-ttu-id="72edf-112">步骤 3：试用功能 - 熟悉模拟、监视和指标</span><span class="sxs-lookup"><span data-stu-id="72edf-112">Step 3: Try out capabilities — Get familiar with simulation, monitoring, and metrics</span></span>](#step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics)

<span data-ttu-id="72edf-113">评估 Microsoft Defender Office 365时，你可以选择先试点特定用户，然后再为整个组织启用和实施策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-113">When you evaluate Microsoft Defender for Office 365, you may choose to pilot specific users before enabling and enforcing policies for your entire organization.</span></span> <span data-ttu-id="72edf-114">创建通讯组可帮助管理部署过程。</span><span class="sxs-lookup"><span data-stu-id="72edf-114">Creating distribution groups can help manage the deployment processes.</span></span> <span data-ttu-id="72edf-115">例如，创建 Defender *for Office 365 Users - Standard Protection、Defender* for Office 365 Users - Strict *Protection、Defender* *for Office 365 Users - Custom Protection* 或 Defender for Office 365 Users *- Exceptions 等* 组。</span><span class="sxs-lookup"><span data-stu-id="72edf-115">For example, create groups such as *Defender for Office 365 Users - Standard Protection*, *Defender for Office 365 Users - Strict Protection*, *Defender for Office 365 Users - Custom Protection*, or *Defender for Office 365 Users - Exceptions*.</span></span>

<span data-ttu-id="72edf-116">为何"标准"和"严格"是用于此术语的术语可能并不明显，但在你浏览更多有关 Defender for Office 365安全预设时，这一点将变得清晰。</span><span class="sxs-lookup"><span data-stu-id="72edf-116">It may not be evident why 'Standard' and 'Strict' are the terms used for this, but that will become clear when you explore more about Defender for Office 365 security presets.</span></span> <span data-ttu-id="72edf-117">命名组"自定义"和"例外"代表自己，尽管大多数用户都应在标准和严格下，但自定义和例外组将收集关于管理风险的有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="72edf-117">Naming groups 'custom' and 'exceptions' speak for themselves, and though most of your users should fall under *standard* and *strict*, custom and exception groups will collect valuable data for you regarding managing risk.</span></span>

## <a name="step-1-create-pilot-groups"></a><span data-ttu-id="72edf-118">步骤 1：创建试点组</span><span class="sxs-lookup"><span data-stu-id="72edf-118">Step 1: Create pilot groups</span></span>

<span data-ttu-id="72edf-119">通讯组可以直接在本地 Active Directory 中创建和Exchange Online或同步。</span><span class="sxs-lookup"><span data-stu-id="72edf-119">Distribution groups can be created and defined directly in Exchange Online or synchronized from on-premises Active Directory.</span></span>

1. <span data-ttu-id="72edf-120">使用已Exchange或 (组管理权限) 帐户登录到 EAC 管理中心。</span><span class="sxs-lookup"><span data-stu-id="72edf-120">Logon to Exchange Admin Center (EAC) using an account that has been granted Recipient Administrator role or been delegated group management permissions.</span></span>
2. <span data-ttu-id="72edf-121">从导航菜单中，展开 *"收件人"，* 然后选择"组 *"。*</span><span class="sxs-lookup"><span data-stu-id="72edf-121">From the navigation menu, expand *Recipients* and select *Groups*.</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text="Exchange导航菜单上的&quot;管理中心 (&quot;) &quot;组&quot;箭头单击&quot;快速启动&quot;菜单。单击&quot;组&quot;。":::

3. <span data-ttu-id="72edf-123">从组仪表板中，选择"添加组"。</span><span class="sxs-lookup"><span data-stu-id="72edf-123">From the Groups dashboard, select "Add a group".</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="在&quot;组&quot;面板上添加组。":::

4. <span data-ttu-id="72edf-125">对于组类型，选择" *分发"，* 然后单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="72edf-125">For group type, select *Distribution* and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text="在此处选择通讯组类型。":::

5. <span data-ttu-id="72edf-127">为组指定名称和说明，然后单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="72edf-127">Give the group a name and description and then click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="命名并描述组。":::

## <a name="step-2-configure-protection"></a><span data-ttu-id="72edf-129">步骤 2：配置保护</span><span class="sxs-lookup"><span data-stu-id="72edf-129">Step 2: Configure protection</span></span>

<span data-ttu-id="72edf-130">默认情况下，Defender for Office 365中的某些功能已配置并打开，但安全操作可能需要从默认级别提升保护级别。</span><span class="sxs-lookup"><span data-stu-id="72edf-130">Some capabilities in Defender for Office 365 are configured and turned on by default, but security operations may want to raise the level of protection from the default.</span></span>

<span data-ttu-id="72edf-131">某些功能 *尚未* 配置。</span><span class="sxs-lookup"><span data-stu-id="72edf-131">Some capabilities are *not yet* configured.</span></span> <span data-ttu-id="72edf-132">有三个选项用于配置保护：</span><span class="sxs-lookup"><span data-stu-id="72edf-132">You have three options for configuring protection:</span></span>

- <span data-ttu-id="72edf-133">**自动分配预设安全策略**[—](../office-365-security/preset-security-policies.md)预设安全策略作为一种方法提供，可快速在所有功能之间分配统一的保护级别。</span><span class="sxs-lookup"><span data-stu-id="72edf-133">**Assign preset security policies automatically** — [Preset security policies](../office-365-security/preset-security-policies.md) are provided as a method to quickly assign a uniform level of protection across all of the capabilities.</span></span> <span data-ttu-id="72edf-134">可以从标准 _ \**_或_ _ _strict_*中选择\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="72edf-134">You can choose from **_standard_*_ or _*_strict_**.</span></span> <span data-ttu-id="72edf-135">一个好方法是从预设安全策略开始，然后在你了解有关功能和你自己的独特威胁环境更多信息时微调策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-135">A good approach is to start with preset security policies and then fine-tune the policies as you learn more about the capabilities and your own unique threat environment.</span></span> <span data-ttu-id="72edf-136">此处的优势在于，您可以尽快保护用户组，并随后调整保护。</span><span class="sxs-lookup"><span data-stu-id="72edf-136">The advantage here is that you protect groups of users as quickly as possible, with the ability to tweak protection afterward.</span></span> <span data-ttu-id="72edf-137"> (建议使用此方法。) </span><span class="sxs-lookup"><span data-stu-id="72edf-137">(This method is recommended.)</span></span>
- <span data-ttu-id="72edf-138">**手动配置基线保护**- 如果你更喜欢自己配置环境，可以按照防止威胁中的指南快速 [实现保护基线](../office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="72edf-138">**Configure baseline protection manually** — If you prefer to configure the environment yourself, you can quickly achieve a *baseline* of protection by following the guidance in [Protect against threats](../office-365-security/protect-against-threats.md).</span></span> <span data-ttu-id="72edf-139">通过此方法，您可以了解有关可配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="72edf-139">With this approach you get to learn more about the settings that are configurable.</span></span> <span data-ttu-id="72edf-140">当然，您稍后可以微调策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-140">And, of course, you can fine-tune the policies later.</span></span>
- <span data-ttu-id="72edf-141">**配置 *自定义* 保护策略** — 还可以生成和分配自定义保护策略作为评估的一部分。</span><span class="sxs-lookup"><span data-stu-id="72edf-141">**Configure *custom* protection policies** — You can also build and assign custom protection policies as part of your evaluation.</span></span> <span data-ttu-id="72edf-142">在开始自定义策略之前，必须了解应用和强制执行这些保护策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="72edf-142">Before you start customizing policies, it's important to understand the precedence in which these protection policies are applied and enforced.</span></span> <span data-ttu-id="72edf-143">即使应用了预设，安全操作也需要创建一些策略，以便为"链接"和"附件"保险箱安全策略保险箱策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-143">Security ops will need to create some policies even if when the preset is applied, in specific in order to define security policies for Safe Links and Safe Attachments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72edf-144">**如果需要配置** 自定义保护策略，应检查此处标准安全定义和严格安全定义的值 *[：EOP](../office-365-security/recommended-settings-for-eop-and-office365.md)* 和 Microsoft Defender 的推荐设置Office 365安全。  </span><span class="sxs-lookup"><span data-stu-id="72edf-144">**If you need to configure custom protection policies**, you should examine the values that make up the **Standard** and **Strict** security definitions here: *[Recommended settings for EOP and Microsoft Defender for Office 365 security](../office-365-security/recommended-settings-for-eop-and-office365.md)*.</span></span> <span data-ttu-id="72edf-145">还会列出默认值，如发生任何配置之前所见。</span><span class="sxs-lookup"><span data-stu-id="72edf-145">Default values, as seen before  any configuration takes place are also listed.</span></span> <span data-ttu-id="72edf-146">保留自定义内部版本偏离位置的电子表格。</span><span class="sxs-lookup"><span data-stu-id="72edf-146">Keep a spreadsheet of where your custom build deviates.</span></span>

### <a name="assign-preset-security-policies"></a><span data-ttu-id="72edf-147">分配预设安全策略</span><span class="sxs-lookup"><span data-stu-id="72edf-147">Assign preset security policies</span></span>

<span data-ttu-id="72edf-148">建议在评估 MDO 时先从推荐的基准策略开始，然后在评估期间根据需要细化这些策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-148">It's encouraged to begin with the *recommended baseline policies* when evaluating MDO and then refine them as needed over the course of your evaluation period.</span></span>

<span data-ttu-id="72edf-149">你可以快速启用推荐的 EOP 和 Defender Office 365保护策略，并将其分配给特定试点用户或定义的组作为评估的一部分。</span><span class="sxs-lookup"><span data-stu-id="72edf-149">You can enable recommended EOP and Defender for Office 365 protection policies fast, and assign them to specific pilot users or defined groups as part of your evaluation.</span></span> <span data-ttu-id="72edf-150">预设策略提供基线 **标准** 保护模板或 **更主动的** 严格保护模板，可单独分配或组合使用。</span><span class="sxs-lookup"><span data-stu-id="72edf-150">Preset policies offer a baseline **Standard** protection template or a more aggressive **Strict** protection template which can be assigned independently, or combined.</span></span>

<span data-ttu-id="72edf-151">下面是概述[步骤的 Preset security policies in EOP and Microsoft Defender for Office 365](../office-365-security/preset-security-policies.md)一文。</span><span class="sxs-lookup"><span data-stu-id="72edf-151">Here is the [Preset security policies in EOP and Microsoft Defender for Office 365](../office-365-security/preset-security-policies.md) article outlining the steps.</span></span>

1. <span data-ttu-id="72edf-152">登录到你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="72edf-152">Log on to your Microsoft 365 tenant.</span></span> <span data-ttu-id="72edf-153">使用有权访问 Microsoft 365 Defender 门户的帐户、添加到 Office 365 中的组织管理角色或 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="72edf-153">Use an account with access to the Microsoft 365 Defender portal, added to Organization Management role in Office 365, or Security Administrator role in Microsoft 365.</span></span>
2. <span data-ttu-id="72edf-154">从导航菜单中，选择"电子邮件 *&协作"* 下的"&规则"。</span><span class="sxs-lookup"><span data-stu-id="72edf-154">From the navigation menu, select *Polices & Rules* under Email & Collaboration.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text="在导航&&quot;电子邮件和协作&quot;下，单击&quot;策略&规则&quot;。":::

3. <span data-ttu-id="72edf-156">在策略策略&仪表板上，单击威胁 *策略*。</span><span class="sxs-lookup"><span data-stu-id="72edf-156">On the Policy & Rules dashboard, click *Threat Policies*.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text="a":::

4. <span data-ttu-id="72edf-158">从Microsoft 365 Defender门户中，从导航菜单中展开"威胁管理"，然后从子菜单中选择"策略"。</span><span class="sxs-lookup"><span data-stu-id="72edf-158">From the Microsoft 365 Defender portal, expand Threat Management from the navigation menu and then select Policy from the submenu.</span></span>
5. <span data-ttu-id="72edf-159">在策略仪表板上，单击 *预设安全策略*。</span><span class="sxs-lookup"><span data-stu-id="72edf-159">On the Policy dashboard, click *Preset security policies*.</span></span>

:::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="单击&quot;预设安全策略&quot;磁贴。":::

6. <span data-ttu-id="72edf-161">单击 *"编辑* "以配置和分配标准策略和/或严格策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-161">Click *Edit* to configure and assign the Standard policy and/or Strict policy.</span></span> :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="在&quot;预设安全策略&quot;面板上，单击&quot;编辑&quot;。":::
7. <span data-ttu-id="72edf-163">根据需要添加条件以将基线 ***EOP** _ 保护应用于特定试点用户或用户组，然后选择"_Next*"继续。</span><span class="sxs-lookup"><span data-stu-id="72edf-163">Add conditions to apply baseline ***EOP** _ protections to specific pilot users, or groups of users, as needed, and select _Next* to continue.</span></span>
    - <span data-ttu-id="72edf-164">例如，如果收件人是 Office 365 Standard Protection 组的已定义 Defender 的成员，然后只需向该组添加帐户或删除帐户，就可以管理试点评估的 Defender for *Office 365* 条件。</span><span class="sxs-lookup"><span data-stu-id="72edf-164">Example, a Defender for Office 365 condition for pilot evaluations could be applied if the recipients are *members* of a defined *Defender for Office 365 Standard Protection* group, and then managed by simply adding accounts to, or removing account from, the group.</span></span>
 :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="向试点组添加将 EOP 安全级别应用所需的条件。":::

8. <span data-ttu-id="72edf-166">根据需要添加条件以将基线 \***MDO** _ 保护应用于特定试点用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="72edf-166">Add conditions to apply baseline \***MDO** _ protections to specific pilot users, or groups of users, as needed.</span></span> <span data-ttu-id="72edf-167">单击_Next\*继续。</span><span class="sxs-lookup"><span data-stu-id="72edf-167">Click _Next\* to continue.</span></span>
    - <span data-ttu-id="72edf-168">例如，如果收件人是 Office 365 Standard Protection 定义的 Defender 组的成员，然后只需通过组添加/删除帐户进行管理，就可以应用适用于试点评估的 Defender for *Office 365* 条件。</span><span class="sxs-lookup"><span data-stu-id="72edf-168">For example, a Defender for Office 365 condition for pilot evaluations could be applied if the recipients are *members* of a defined *Defender for Office 365 Standard Protection* group and then managed by simply adding / removing accounts via the group.</span></span>
  :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="将应用 Defender for Office 365安全级别所需的条件添加到试点组。":::

9. <span data-ttu-id="72edf-170">查看并确认更改以分配预设安全策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-170">Review and confirm your changes for assigning preset security policies.</span></span>
10. <span data-ttu-id="72edf-171">通过返回到 Microsoft 365 Defender 门户 > 策略 & 规则 > 威胁策略 > 并单击"预设安全策略"磁贴，可以管理预设保护策略 (重新配置、重新应用、禁用等 ) 。 </span><span class="sxs-lookup"><span data-stu-id="72edf-171">Preset protection policies can be managed (re-configured, re-applied, disabled, etc.) by returning to the Microsoft 365 Defender portal > Policies & rules > Threat Policies > and clicking the *Preset security policies* tile.</span></span>

### <a name="configure-custom-protection-policies"></a><span data-ttu-id="72edf-172">配置自定义保护策略</span><span class="sxs-lookup"><span data-stu-id="72edf-172">Configure custom protection policies</span></span>

<span data-ttu-id="72edf-173">预定义的 *Standard* 或 *Strict* Defender for Office 365模板为试点用户提供推荐的基线保护。</span><span class="sxs-lookup"><span data-stu-id="72edf-173">The pre-defined *Standard* or *Strict* Defender for Office 365 policy templates give your pilot users the recommended baseline protection.</span></span> <span data-ttu-id="72edf-174">但是，作为评估的一部分，还可以生成和分配自定义保护策略。</span><span class="sxs-lookup"><span data-stu-id="72edf-174">However, you can also build and assign custom protection policies as part of your evaluation.</span></span>

<span data-ttu-id="72edf-175">必须 *了解这些* 保护策略在应用和强制执行时所采用优先级，如电子邮件保护的顺序和优先级 - [Office 365说明。](../office-365-security/how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="72edf-175">It's *important* to be aware of the precedence these protection policies take when applied and enforced, as [Order and precedence of email protection - Office 365](../office-365-security/how-policies-and-protections-are-combined.md) explains.</span></span>

<span data-ttu-id="72edf-176">下表提供了有关配置和分配自定义保护策略的参考和其他指南：</span><span class="sxs-lookup"><span data-stu-id="72edf-176">The table below provides references and additional guidance for configuring and assigning custom protection policies:</span></span>

|<span data-ttu-id="72edf-177">策略</span><span class="sxs-lookup"><span data-stu-id="72edf-177">Policy</span></span>   |<span data-ttu-id="72edf-178">说明</span><span class="sxs-lookup"><span data-stu-id="72edf-178">Description</span></span>  |<span data-ttu-id="72edf-179">参考</span><span class="sxs-lookup"><span data-stu-id="72edf-179">Reference</span></span>  |
|:---------:|---------|---------|
|<span data-ttu-id="72edf-180">连接筛选</span><span class="sxs-lookup"><span data-stu-id="72edf-180">Connection Filtering</span></span>     |    <span data-ttu-id="72edf-181">按 IP 地址标识好或坏的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="72edf-181">Identify good or bad source email servers by their IP addresses.</span></span>     |     [<span data-ttu-id="72edf-182">在 EOP 中配置默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="72edf-182">Configure the default connection filter policy in EOP</span></span>](../office-365-security/configure-the-connection-filter-policy.md)    |
|<span data-ttu-id="72edf-183">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="72edf-183">Anti-Malware</span></span>    |    <span data-ttu-id="72edf-184">保护用户免受电子邮件恶意软件的攻击，包括要采取的操作以及检测到恶意软件时要通知的用户。</span><span class="sxs-lookup"><span data-stu-id="72edf-184">Protect users from email malware including what actions to take and who to notify if malware is detected.</span></span>     |    [<span data-ttu-id="72edf-185">在 EOP 中配置反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="72edf-185">Configure anti-malware policies in EOP</span></span>](../office-365-security/configure-anti-malware-policies.md)     |
|<span data-ttu-id="72edf-186">反欺骗</span><span class="sxs-lookup"><span data-stu-id="72edf-186">Anti-Spoofing</span></span>     |  <span data-ttu-id="72edf-187">使用欺骗智能和欺骗智能见解保护用户免受欺骗尝试。</span><span class="sxs-lookup"><span data-stu-id="72edf-187">Protect users from spoofing attempts using spoof intelligence and spoof intelligence insights.</span></span>   |     [<span data-ttu-id="72edf-188">在 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="72edf-188">Configure spoof intelligence in Defender for Office 365</span></span>](../office-365-security/learn-about-spoof-intelligence.md)    |
|<span data-ttu-id="72edf-189">反垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="72edf-189">Anti-Spam</span></span>     |    <span data-ttu-id="72edf-190">防止用户收到垃圾电子邮件，包括检测到垃圾邮件时要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="72edf-190">Protect users from email spam including what actions to take if spam is detected.</span></span>     |    [<span data-ttu-id="72edf-191">在 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="72edf-191">Configure anti-spam policies in Defender for Office 365</span></span>](../office-365-security/configure-your-spam-filter-policies.md)     |
|<span data-ttu-id="72edf-192">防钓鱼</span><span class="sxs-lookup"><span data-stu-id="72edf-192">Anti-Phishing</span></span>     |   <span data-ttu-id="72edf-193">保护用户免受网络钓鱼攻击，并配置可疑邮件的安全提示</span><span class="sxs-lookup"><span data-stu-id="72edf-193">Protect users from phishing attacks and configure safety tips on suspicious messages</span></span>      |     [<span data-ttu-id="72edf-194">在 Defender for Office 365 中配置反钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="72edf-194">Configure anti-phishing policies in Defender for Office 365</span></span>](../office-365-security/configure-mdo-anti-phishing-policies.md)    |
|<span data-ttu-id="72edf-195">安全附件</span><span class="sxs-lookup"><span data-stu-id="72edf-195">Safe Attachments</span></span>     |    <span data-ttu-id="72edf-196">保护用户免受电子邮件附件中的恶意内容以及电子邮件SharePoint、OneDrive和Teams。</span><span class="sxs-lookup"><span data-stu-id="72edf-196">Protect users from malicious content in email attachments and files in SharePoint, OneDrive, and Teams.</span></span>     |    [<span data-ttu-id="72edf-197">在 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="72edf-197">Set up safe attachment policies in Defender for Office 365</span></span>](../office-365-security/set-up-safe-attachments-policies.md)     |
|<span data-ttu-id="72edf-198">安全链接</span><span class="sxs-lookup"><span data-stu-id="72edf-198">Safe Links</span></span>     |     <span data-ttu-id="72edf-199">防止用户在电子邮件或桌面应用中打开和共享Office链接。</span><span class="sxs-lookup"><span data-stu-id="72edf-199">Protect users from opening and sharing malicious links in email messages or Office desktop apps.</span></span>    |    [<span data-ttu-id="72edf-200">在 Defender for Office 365 中设置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="72edf-200">Set up safe links policies in Defender for Office 365</span></span>](../office-365-security/set-up-safe-links-policies.md)     |

## <a name="step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics"></a><span data-ttu-id="72edf-201">步骤 3：试用功能 - 熟悉模拟、监视和指标</span><span class="sxs-lookup"><span data-stu-id="72edf-201">Step 3: Try out capabilities — Get familiar with simulation, monitoring, and metrics</span></span>

<span data-ttu-id="72edf-202">现在，你的试点已设置和配置，熟悉 Microsoft Defender for Microsoft 365 独有的报告、监视和攻击模拟工具Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="72edf-202">Now that your pilot is set up and configured, it's helpful to become familiar with the reporting, monitoring, and attack simulation tools that are unique to Microsoft Defender for Microsoft 365.</span></span>

|<span data-ttu-id="72edf-203">功能</span><span class="sxs-lookup"><span data-stu-id="72edf-203">Capability</span></span>  |<span data-ttu-id="72edf-204">说明</span><span class="sxs-lookup"><span data-stu-id="72edf-204">Description</span></span>  |<span data-ttu-id="72edf-205">详细信息</span><span class="sxs-lookup"><span data-stu-id="72edf-205">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="72edf-206">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="72edf-206">Threat Explorer</span></span>     | <span data-ttu-id="72edf-207">威胁资源管理器是一个强大的近实时工具，可帮助安全运营团队调查和响应威胁，并显示有关 Office 365 中电子邮件和文件中可疑恶意软件和网络钓鱼的信息，以及组织面临的其他安全威胁和风险。</span><span class="sxs-lookup"><span data-stu-id="72edf-207">Threat Explorer is a powerful near real-time tool to help Security Operations teams investigate and respond to threats and displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>        | [<span data-ttu-id="72edf-208">威胁资源管理器中的视图和实时检测 </span><span class="sxs-lookup"><span data-stu-id="72edf-208">Views in Threat Explorer and real-time detections </span></span>](../office-365-security/threat-explorer-views.md)       | 
|<span data-ttu-id="72edf-209">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="72edf-209">Attack Simulator</span></span>     | <span data-ttu-id="72edf-210">可以使用 Microsoft Defender 365 门户中的攻击模拟培训在组织中运行真实的攻击方案，这有助于你在真正的攻击影响你的环境之前识别和查找易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="72edf-210">You can use Attack Simulation Training in the Microsoft Defender 365 portal to run realistic attack scenarios in your organization which help you identify and find vulnerable users before a real attack impacts your environment.</span></span>        |  [<span data-ttu-id="72edf-211">Microsoft Defender for Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="72edf-211">Attack Simulator in Microsoft Defender for Office 365</span></span>](../office-365-security/attack-simulator.md)       |
|<span data-ttu-id="72edf-212">报表仪表板</span><span class="sxs-lookup"><span data-stu-id="72edf-212">Reports dashboard</span></span>     | <span data-ttu-id="72edf-213">在左侧导航菜单上，单击"报告"，然后展开"电子邮件&协作"标题。</span><span class="sxs-lookup"><span data-stu-id="72edf-213">On the left navigation menu, click Reports and expand the Email & collaboration heading.</span></span> <span data-ttu-id="72edf-214">Email & collaboration reports are about detectioning security trends some of which will allow you to take action (through buttons like 'Go to submissions') ， and others that will show trends， like Mailflow status summary， Top Malware， Spoof detections， Compromised users， Mail latency， 保险箱 Links and 保险箱 attachments reports.</span><span class="sxs-lookup"><span data-stu-id="72edf-214">The Email & collaboration reports are about spotting security trends some of which will allow you to take action (through buttons like 'Go to submissions'), and others that will show trends, like Mailflow status summary, Top Malware, Spoof detections, Compromised users, Mail latency, Safe Links and Safe attachments reports.</span></span> <span data-ttu-id="72edf-215">这些指标是自动生成的。</span><span class="sxs-lookup"><span data-stu-id="72edf-215">These metrics are generated automatically.</span></span>  |    [<span data-ttu-id="72edf-216">查看报告</span><span class="sxs-lookup"><span data-stu-id="72edf-216">View Reports</span></span>](../office-365-security/view-email-security-reports.md)     |

## <a name="next-steps"></a><span data-ttu-id="72edf-217">后续步骤</span><span class="sxs-lookup"><span data-stu-id="72edf-217">Next steps</span></span>


[<span data-ttu-id="72edf-218">评估 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72edf-218">Evaluate Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-overview.md)

<span data-ttu-id="72edf-219">返回到评估 Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365</span><span class="sxs-lookup"><span data-stu-id="72edf-219">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="72edf-220">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="72edf-220">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>