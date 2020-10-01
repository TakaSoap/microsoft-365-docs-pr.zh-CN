---
title: 安全策略的配置分析器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用配置分析器来查找和修复低于标准保护和严格保护预设安全策略的安全策略。
ms.openlocfilehash: ac70b7fa2b2d0ecc65cf81ea4e5e5f2e807f2467
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326575"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="f5218-103">EOP 和 Office 365 ATP 中的保护策略的配置分析器</span><span class="sxs-lookup"><span data-stu-id="f5218-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f5218-104">本主题中所述的功能在预览中，在所有组织中均不可用，可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="f5218-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="f5218-105">有关发布计划的信息，请参阅 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer)。</span><span class="sxs-lookup"><span data-stu-id="f5218-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="f5218-106">Security & 合规中心中的配置分析器提供了一个中心位置，用于查找和修复安全策略，其中的设置位于 [预设安全策略](preset-security-policies.md)中的标准保护和严格保护配置文件设置之下。</span><span class="sxs-lookup"><span data-stu-id="f5218-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="f5218-107">配置分析器将对以下策略类型进行分析：</span><span class="sxs-lookup"><span data-stu-id="f5218-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="f5218-108">**Exchange Online Protection (EOP) 策略**：这包括具有 exchange online 邮箱和独立 EOP 组织的 Microsoft 365 组织，而无需使用 exchange online 邮箱：</span><span class="sxs-lookup"><span data-stu-id="f5218-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="f5218-109">[反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5218-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="f5218-110">[反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5218-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="f5218-111">[EOP 反网络钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="f5218-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="f5218-112">**Office 365 高级威胁防护 (ATP) 策略**：这包括具有 Microsoft 365 E5 或 OFFICE 365 ATP 附加产品订阅的组织：</span><span class="sxs-lookup"><span data-stu-id="f5218-112">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="f5218-113">ATP 反网络钓鱼策略，其中包括：</span><span class="sxs-lookup"><span data-stu-id="f5218-113">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="f5218-114">EOP 反网络钓鱼策略中提供的相同 [欺骗设置](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="f5218-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="f5218-115">模拟设置</span><span class="sxs-lookup"><span data-stu-id="f5218-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="f5218-116">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="f5218-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="f5218-117">[安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5218-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="f5218-118">[安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5218-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="f5218-119">[EOP 和 Office 365 ATP security 的建议设置](recommended-settings-for-eop-and-office365-atp.md)中介绍了用作基准的**标准**策略设置值和**严格**策略设置值。</span><span class="sxs-lookup"><span data-stu-id="f5218-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f5218-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="f5218-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f5218-121">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="f5218-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f5218-122">若要直接转到 " **配置分析器** " 页，请使用 <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="f5218-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="f5218-123">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f5218-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f5218-124">您需要先分配权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="f5218-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="f5218-125">若要使用配置分析器 **并** 对安全策略进行更新，您需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="f5218-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f5218-126">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="f5218-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f5218-127">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="f5218-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f5218-128">若要对配置分析器进行只读访问，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="f5218-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f5218-129">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="f5218-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f5218-130">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="f5218-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="f5218-131">在安全 & 合规中心中使用配置分析器</span><span class="sxs-lookup"><span data-stu-id="f5218-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="f5218-132">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **配置分析器**"。</span><span class="sxs-lookup"><span data-stu-id="f5218-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

!["威胁管理策略" 页上的 "配置分析器" 小部件 \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="f5218-134">配置分析器有两个主要选项卡：</span><span class="sxs-lookup"><span data-stu-id="f5218-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="f5218-135">**设置和建议**：选择 "标准" 或 "严格"，并将这些设置与现有的安全策略进行比较。</span><span class="sxs-lookup"><span data-stu-id="f5218-135">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="f5218-136">在结果中，您可以调整设置的值，使其与标准或严格的级别相同。</span><span class="sxs-lookup"><span data-stu-id="f5218-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="f5218-137">**配置偏移分析和历史记录**：此视图允许您跟踪一段时间内的策略更改。</span><span class="sxs-lookup"><span data-stu-id="f5218-137">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="f5218-138">配置分析器中的 "设置和建议" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f5218-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="f5218-139">默认情况下，该选项卡将在与标准保护配置文件的比较中打开。</span><span class="sxs-lookup"><span data-stu-id="f5218-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="f5218-140">您可以通过单击 " **查看严格建议**" 切换到严格保护配置文件的比较。</span><span class="sxs-lookup"><span data-stu-id="f5218-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="f5218-141">若要切换回，请选择 " **查看标准建议**"。</span><span class="sxs-lookup"><span data-stu-id="f5218-141">To switch back, select **View Standard recommendations**.</span></span>

![配置分析器中的 "设置和建议" 视图](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="f5218-143">默认情况下，" **策略组/设置名称** " 列包含不同类型的安全策略和需要改进 (如果有任何) 的设置数量的折叠视图。</span><span class="sxs-lookup"><span data-stu-id="f5218-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="f5218-144">策略类型为：</span><span class="sxs-lookup"><span data-stu-id="f5218-144">The types of policies are:</span></span>

- <span data-ttu-id="f5218-145">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="f5218-145">**Anti-spam**</span></span>
- <span data-ttu-id="f5218-146">**反网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="f5218-146">**Anti-phishing**</span></span>
- <span data-ttu-id="f5218-147">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="f5218-147">**Anti-malware**</span></span>
- <span data-ttu-id="f5218-148">如果您的订阅包括 ATP) ， **Atp 安全附件** (</span><span class="sxs-lookup"><span data-stu-id="f5218-148">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="f5218-149">如果您的订阅包括 ATP) ， **Atp 安全链接** (</span><span class="sxs-lookup"><span data-stu-id="f5218-149">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="f5218-150">在默认视图中，所有内容都处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="f5218-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="f5218-151">在每个策略旁边有一个有关策略的比较结果的摘要 (可以在这些策略中修改) 以及在不能修改) 的标准或严格保护配置文件 (相应策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="f5218-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="f5218-152">你将看到您要与之进行比较的保护配置文件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="f5218-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="f5218-153">**绿色**：所有现有策略中的所有设置都至少与保护配置文件一样安全。</span><span class="sxs-lookup"><span data-stu-id="f5218-153">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="f5218-154">**琥珀色**：现有策略中的小一些设置与保护配置文件的安全性不一样。</span><span class="sxs-lookup"><span data-stu-id="f5218-154">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="f5218-155">**红色**：现有策略中的大量设置与保护配置文件的安全性不一样。</span><span class="sxs-lookup"><span data-stu-id="f5218-155">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="f5218-156">这可能是一种策略中的许多策略或许多设置中的几个设置。</span><span class="sxs-lookup"><span data-stu-id="f5218-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="f5218-157">对于有利的比较，你将看到以下文本： **所有设置都遵循** \<**Standard** or **Strict**\> **建议**。</span><span class="sxs-lookup"><span data-stu-id="f5218-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="f5218-158">否则，你将看到建议的设置要更改的数量。</span><span class="sxs-lookup"><span data-stu-id="f5218-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="f5218-159">如果展开 " **策略" 组/设置名称**，则会显示每个需要注意的特定策略中的所有策略和关联设置。</span><span class="sxs-lookup"><span data-stu-id="f5218-159">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="f5218-160">或者，您可以展开特定类型的策略 (例如， **反垃圾邮件**) 仅查看那些需要注意的策略类型中的设置。</span><span class="sxs-lookup"><span data-stu-id="f5218-160">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="f5218-161">如果比较没有改进建议 (绿色) ，则展开该策略将不会显示任何内容。</span><span class="sxs-lookup"><span data-stu-id="f5218-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="f5218-162">如果有任意数量的改进建议 (琥珀色或红色) ，则会显示需要注意的设置，并在以下各列中显示相应的信息：</span><span class="sxs-lookup"><span data-stu-id="f5218-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="f5218-163">需要您注意的设置的名称。</span><span class="sxs-lookup"><span data-stu-id="f5218-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="f5218-164">例如，在前面的屏幕截图中，它是反垃圾邮件策略中的 **批量电子邮件阈值** 。</span><span class="sxs-lookup"><span data-stu-id="f5218-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="f5218-165">**Policy**：包含该设置的受影响策略的名称。</span><span class="sxs-lookup"><span data-stu-id="f5218-165">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="f5218-166">**应用**于：受影响的策略应用于的用户数量。</span><span class="sxs-lookup"><span data-stu-id="f5218-166">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="f5218-167">**当前配置**：设置的当前值。</span><span class="sxs-lookup"><span data-stu-id="f5218-167">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="f5218-168">**上次修改**时间：策略的上次修改日期。</span><span class="sxs-lookup"><span data-stu-id="f5218-168">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="f5218-169">**建议**：标准或严格保护配置文件中的设置的值。</span><span class="sxs-lookup"><span data-stu-id="f5218-169">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="f5218-170">若要将策略中设置的值更改为与保护配置文件中的推荐值相匹配，请单击 " **采用**"。</span><span class="sxs-lookup"><span data-stu-id="f5218-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="f5218-171">如果更改成功，您将看到以下消息： " **已成功采用" 建议**。</span><span class="sxs-lookup"><span data-stu-id="f5218-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="f5218-172">单击 " **刷新** " 以查看减少的建议数，以及从结果中删除特定设置/策略行。</span><span class="sxs-lookup"><span data-stu-id="f5218-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="f5218-173">配置分析器中的 "配置偏移分析和历史记录" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f5218-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="f5218-174">此选项卡允许你跟踪你对自定义安全策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f5218-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="f5218-175">默认情况下，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="f5218-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="f5218-176">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="f5218-176">**Last modified**</span></span>
- <span data-ttu-id="f5218-177">**修改者**</span><span class="sxs-lookup"><span data-stu-id="f5218-177">**Modified by**</span></span>
- <span data-ttu-id="f5218-178">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="f5218-178">**Setting Name**</span></span>
- <span data-ttu-id="f5218-179">**策略**</span><span class="sxs-lookup"><span data-stu-id="f5218-179">**Policy**</span></span>
- <span data-ttu-id="f5218-180">**Type**</span><span class="sxs-lookup"><span data-stu-id="f5218-180">**Type**</span></span>

<span data-ttu-id="f5218-181">若要筛选结果，请单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5218-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="f5218-182">在显示的 " **筛选器** " 浮出控件中，可以从以下筛选器中进行选择：</span><span class="sxs-lookup"><span data-stu-id="f5218-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="f5218-183">**开始时间** 和 **结束时间** (日期) </span><span class="sxs-lookup"><span data-stu-id="f5218-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="f5218-184">**标准保护** 或 **严格保护**</span><span class="sxs-lookup"><span data-stu-id="f5218-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="f5218-185">若要将结果导出到 .csv 文件，请单击 " **导出**"。</span><span class="sxs-lookup"><span data-stu-id="f5218-185">To export the results to a .csv file, click **Export**.</span></span>

![配置分析器中的配置偏移分析和历史记录视图](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
