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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用配置分析器查找和修复低于"标准保护"和"严格保护"预设安全策略的安全策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fd67c93711dc847a25be485b4b016af55e4a31
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203184"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="77587-103">EOP 和 Microsoft Defender for Office 365 中的保护策略的配置分析器</span><span class="sxs-lookup"><span data-stu-id="77587-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="77587-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="77587-104">**Applies to**</span></span>
- [<span data-ttu-id="77587-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="77587-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="77587-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="77587-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="77587-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77587-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="77587-108">安全与&中心中的配置分析器提供了一个中心位置，用于查找和修复安全策略，其中设置位于预设安全策略中的"标准保护"和"严格保护配置文件" [设置下方](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77587-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="77587-109">配置分析器分析以下类型的策略：</span><span class="sxs-lookup"><span data-stu-id="77587-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="77587-110">**Exchange Online Protection (EOP)** 策略：这包括具有 Exchange Online 邮箱的 Microsoft 365 组织和没有 Exchange Online 邮箱的独立 EOP 组织：</span><span class="sxs-lookup"><span data-stu-id="77587-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="77587-111">[反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77587-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="77587-112">[反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77587-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="77587-113">[EOP 防钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="77587-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="77587-114">**Microsoft Defender for Office 365 策略**：这包括具有 Microsoft 365 E5 或适用于 Office 365 的 Defender 附加订阅的组织：</span><span class="sxs-lookup"><span data-stu-id="77587-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="77587-115">Microsoft Defender for Office 365 中的防钓鱼策略，其中包括：</span><span class="sxs-lookup"><span data-stu-id="77587-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="77587-116">EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。</span><span class="sxs-lookup"><span data-stu-id="77587-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="77587-117">模拟设置</span><span class="sxs-lookup"><span data-stu-id="77587-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="77587-118">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="77587-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="77587-119">[安全链接策略](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77587-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>

  - <span data-ttu-id="77587-120">[安全附件策略](set-up-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77587-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="77587-121">用作 **基线\*\*\*\*的标准** 和严格策略设置值在 EOP 和 [Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md)安全推荐设置中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="77587-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="77587-122">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="77587-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="77587-123">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="77587-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="77587-124">若要直接转到配置 **分析器页面** ，请使用 <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="77587-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="77587-125">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="77587-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="77587-126">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="77587-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="77587-127">若要使用 **配置分析器** 并更新安全策略，您必须是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="77587-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="77587-128">若要对配置分析器进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。</span><span class="sxs-lookup"><span data-stu-id="77587-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="77587-129">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="77587-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="77587-130">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="77587-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="77587-131">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="77587-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="77587-132">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="77587-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="77587-133">使用安全与合规中心&分析器</span><span class="sxs-lookup"><span data-stu-id="77587-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="77587-134">在安全与&中心，转到"**威胁管理** \> **策略** \> **配置分析器"。**</span><span class="sxs-lookup"><span data-stu-id="77587-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

!["威胁管理策略"页上的配置分析 \> 器小组件](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="77587-136">配置分析器有两个主要选项卡：</span><span class="sxs-lookup"><span data-stu-id="77587-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="77587-137">**设置和建议**：选择"标准"或"严格"，并将这些设置与现有的安全策略进行比较。</span><span class="sxs-lookup"><span data-stu-id="77587-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="77587-138">在结果中，可以调整设置的值，使它们达到与 Standard 或 Strict 相同的级别。</span><span class="sxs-lookup"><span data-stu-id="77587-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="77587-139">**配置偏移分析和历史记录**：此视图允许你随着时间的推移跟踪策略更改。</span><span class="sxs-lookup"><span data-stu-id="77587-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="77587-140">配置分析器中的"设置和建议"选项卡</span><span class="sxs-lookup"><span data-stu-id="77587-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="77587-141">默认情况下，选项卡在与标准保护配置文件的比较中打开。</span><span class="sxs-lookup"><span data-stu-id="77587-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="77587-142">可以通过单击查看严格建议切换到严格保护 **配置文件的比较**。</span><span class="sxs-lookup"><span data-stu-id="77587-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="77587-143">若要切换回，请选择 **"查看标准建议"。**</span><span class="sxs-lookup"><span data-stu-id="77587-143">To switch back, select **View Standard recommendations**.</span></span>

![配置分析器中的设置和建议视图](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="77587-145">默认情况下，" **策略组/** 设置名称"列包含不同类型的安全策略的折叠视图以及需要改进的设置 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="77587-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="77587-146">策略类型为：</span><span class="sxs-lookup"><span data-stu-id="77587-146">The types of policies are:</span></span>

- <span data-ttu-id="77587-147">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="77587-147">**Anti-spam**</span></span>
- <span data-ttu-id="77587-148">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="77587-148">**Anti-phishing**</span></span>
- <span data-ttu-id="77587-149">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="77587-149">**Anti-malware**</span></span>
- <span data-ttu-id="77587-150">**如果订阅包含** Microsoft Defender for Office 365 (，ATP 安全附件) </span><span class="sxs-lookup"><span data-stu-id="77587-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="77587-151">**如果你的订阅** 包含 Microsoft Defender for Office 365 (，ATP 安全链接) </span><span class="sxs-lookup"><span data-stu-id="77587-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="77587-152">在默认视图中，所有内容都折叠。</span><span class="sxs-lookup"><span data-stu-id="77587-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="77587-153">在每个策略旁边，有一个策略 (的比较结果摘要，您可以修改) 以及标准或严格保护配置文件 (其中不能修改) 的相应策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="77587-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="77587-154">你将看到要进行比较的保护配置文件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="77587-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="77587-155">**绿色**：所有现有策略的所有设置都至少与保护配置文件一样安全。</span><span class="sxs-lookup"><span data-stu-id="77587-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="77587-156">**Amber：** 现有策略中的少量设置没有保护配置文件安全。</span><span class="sxs-lookup"><span data-stu-id="77587-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="77587-157">**红色**：现有策略中的大量设置没有保护配置文件安全。</span><span class="sxs-lookup"><span data-stu-id="77587-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="77587-158">这可能是许多策略中的一些设置或一个策略中的许多设置。</span><span class="sxs-lookup"><span data-stu-id="77587-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="77587-159">For favorable comparisons， you'll see the text： **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span><span class="sxs-lookup"><span data-stu-id="77587-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="77587-160">否则，你将看到要更改的建议设置数。</span><span class="sxs-lookup"><span data-stu-id="77587-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="77587-161">如果展开" **策略组/设置** 名称"，将显示每个需要关注的特定策略中所有策略和相关设置。</span><span class="sxs-lookup"><span data-stu-id="77587-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="77587-162">或者，您可以扩展特定类型的策略 (例如，"反垃圾邮件) 查看那些需要您注意的策略类型中的设置。</span><span class="sxs-lookup"><span data-stu-id="77587-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="77587-163">如果比较没有针对绿色策略 (建议) ，则扩展策略不会显示任何结果。</span><span class="sxs-lookup"><span data-stu-id="77587-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="77587-164">如果存在任何数量的有关改进建议 (或红色) ，则说明需要注意的设置，并且以下列中显示了相应的信息：</span><span class="sxs-lookup"><span data-stu-id="77587-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="77587-165">需要你注意的设置的名称。</span><span class="sxs-lookup"><span data-stu-id="77587-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="77587-166">例如，在上一个屏幕截图中，它是反垃圾邮件策略中的批量电子邮件阈值。</span><span class="sxs-lookup"><span data-stu-id="77587-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="77587-167">**策略**：包含设置的受影响策略的名称。</span><span class="sxs-lookup"><span data-stu-id="77587-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="77587-168">**应用于**：应用了受影响策略的用户数。</span><span class="sxs-lookup"><span data-stu-id="77587-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="77587-169">**当前配置**：设置的当前值。</span><span class="sxs-lookup"><span data-stu-id="77587-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="77587-170">**上次修改** 时间：上次修改策略的日期。</span><span class="sxs-lookup"><span data-stu-id="77587-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="77587-171">**建议**：Standard 或 Strict 保护配置文件中的设置的值。</span><span class="sxs-lookup"><span data-stu-id="77587-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="77587-172">若要更改策略中的设置值以匹配保护配置文件中的推荐值，请单击"采用 **"。**</span><span class="sxs-lookup"><span data-stu-id="77587-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="77587-173">如果更改成功，你将看到消息："**建议已成功采用"。**</span><span class="sxs-lookup"><span data-stu-id="77587-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="77587-174">单击 **"** 刷新"查看建议数量减少以及从结果删除特定设置/策略行。</span><span class="sxs-lookup"><span data-stu-id="77587-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="77587-175">配置分析器中的"配置偏移分析和历史记录"选项卡</span><span class="sxs-lookup"><span data-stu-id="77587-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="77587-176">此选项卡允许你跟踪对自定义安全策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="77587-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="77587-177">默认情况下，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="77587-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="77587-178">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="77587-178">**Last modified**</span></span>
- <span data-ttu-id="77587-179">**修改者**</span><span class="sxs-lookup"><span data-stu-id="77587-179">**Modified by**</span></span>
- <span data-ttu-id="77587-180">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="77587-180">**Setting Name**</span></span>
- <span data-ttu-id="77587-181">**策略**</span><span class="sxs-lookup"><span data-stu-id="77587-181">**Policy**</span></span>
- <span data-ttu-id="77587-182">**类型**</span><span class="sxs-lookup"><span data-stu-id="77587-182">**Type**</span></span>

<span data-ttu-id="77587-183">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="77587-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="77587-184">在出现的 **"** 筛选器"飞出中，可以从以下筛选器中选择：</span><span class="sxs-lookup"><span data-stu-id="77587-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="77587-185">**开始时间和\*\*\*\*结束 (** 日期) </span><span class="sxs-lookup"><span data-stu-id="77587-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="77587-186">**标准保护** 或 **严格保护**</span><span class="sxs-lookup"><span data-stu-id="77587-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="77587-187">若要将结果导出到 .csv 文件，请单击"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="77587-187">To export the results to a .csv file, click **Export**.</span></span>

![配置分析器中的配置偏移分析和历史记录视图](../../media/configuration-analyzer-configuration-drift-analysis-view.png)