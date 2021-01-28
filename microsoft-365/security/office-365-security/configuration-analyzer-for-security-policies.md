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
description: 管理员可以了解如何使用配置分析器查找和修复低于标准保护和严格保护预设安全策略的安全策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04027e78a2683c6c33954bb548c502497c5e8323
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029474"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="b4d12-103">EOP 和 Microsoft Defender for Office 365 中保护策略的配置分析器</span><span class="sxs-lookup"><span data-stu-id="b4d12-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b4d12-104">安全与合规中心&配置分析器提供了一个中心位置，用于查找和修复安全策略，其中设置低于预设安全策略中的标准保护和严格保护 [配置文件设置](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-104">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="b4d12-105">配置分析器将分析以下类型的策略：</span><span class="sxs-lookup"><span data-stu-id="b4d12-105">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="b4d12-106">**Exchange Online Protection (EOP)** 策略：这包括具有 Exchange Online 邮箱的 Microsoft 365 组织和没有 Exchange Online 邮箱的独立 EOP 组织：</span><span class="sxs-lookup"><span data-stu-id="b4d12-106">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="b4d12-107">[反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-107">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="b4d12-108">[反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-108">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="b4d12-109">[EOP 防钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-109">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="b4d12-110">**Microsoft Defender for Office 365 策略**：这包括具有 Microsoft 365 E5 或适用于 Office 365 的 Defender 附加订阅的组织：</span><span class="sxs-lookup"><span data-stu-id="b4d12-110">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="b4d12-111">Microsoft Defender for Office 365 中的防钓鱼策略，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b4d12-111">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="b4d12-112">EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。</span><span class="sxs-lookup"><span data-stu-id="b4d12-112">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="b4d12-113">模拟设置</span><span class="sxs-lookup"><span data-stu-id="b4d12-113">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="b4d12-114">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="b4d12-114">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="b4d12-115">[安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-115">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="b4d12-116">[安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-116">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="b4d12-117">用作 **基线** 的标准 **和严格** 策略设置值在 EOP 和 [Microsoft Defender for Office 365 安全的建议设置中进行了介绍](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-117">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b4d12-118">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b4d12-118">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b4d12-119">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="b4d12-119">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b4d12-120">若要直接转到" **配置分析器"** 页，请使用 <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="b4d12-120">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="b4d12-121">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b4d12-122">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="b4d12-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b4d12-123">若要使用配置分析 **器** 并更新安全策略，你需要是组织管理或 **安全** 管理员角色组的成员。 </span><span class="sxs-lookup"><span data-stu-id="b4d12-123">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b4d12-124">若要对配置分析器进行只读访问，你需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="b4d12-124">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b4d12-125">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="b4d12-126">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="b4d12-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b4d12-127">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="b4d12-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  > 
  > - <span data-ttu-id="b4d12-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="b4d12-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="b4d12-129">使用安全与合规中心&分析器</span><span class="sxs-lookup"><span data-stu-id="b4d12-129">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="b4d12-130">在安全&，转到 **"威胁管理** \> **策略** \> **配置"分析器**。</span><span class="sxs-lookup"><span data-stu-id="b4d12-130">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

!["威胁管理策略"页上的配置分析 \> 器小组件](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="b4d12-132">配置分析器有两个主要选项卡：</span><span class="sxs-lookup"><span data-stu-id="b4d12-132">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="b4d12-133">**设置和建议**：选择"标准"或"严格"，并将这些设置与现有的安全策略进行比较。</span><span class="sxs-lookup"><span data-stu-id="b4d12-133">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="b4d12-134">在结果中，您可以调整设置的值，使它们达到与 Standard 或 Strict 相同的级别。</span><span class="sxs-lookup"><span data-stu-id="b4d12-134">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="b4d12-135">**配置偏移分析和历史记录**：此视图允许你跟踪一段时间的策略更改。</span><span class="sxs-lookup"><span data-stu-id="b4d12-135">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="b4d12-136">配置分析器中的"设置和建议"选项卡</span><span class="sxs-lookup"><span data-stu-id="b4d12-136">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="b4d12-137">默认情况下，选项卡将在与标准保护配置文件进行比较时打开。</span><span class="sxs-lookup"><span data-stu-id="b4d12-137">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="b4d12-138">可以通过单击"查看严格"建议切换到严格保护 **配置文件的比较**。</span><span class="sxs-lookup"><span data-stu-id="b4d12-138">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="b4d12-139">若要切换回，请选择 **"查看标准"建议**。</span><span class="sxs-lookup"><span data-stu-id="b4d12-139">To switch back, select **View Standard recommendations**.</span></span>

![配置分析器中的设置和建议视图](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="b4d12-141">默认情况下，策略 **组/设置名称** 列包含不同类型的安全策略的折叠视图以及需要改进的设置 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="b4d12-141">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="b4d12-142">策略类型为：</span><span class="sxs-lookup"><span data-stu-id="b4d12-142">The types of policies are:</span></span>

- <span data-ttu-id="b4d12-143">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b4d12-143">**Anti-spam**</span></span>
- <span data-ttu-id="b4d12-144">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="b4d12-144">**Anti-phishing**</span></span>
- <span data-ttu-id="b4d12-145">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b4d12-145">**Anti-malware**</span></span>
- <span data-ttu-id="b4d12-146">**如果订阅包含** Microsoft Defender for Office 365 (，ATP 安全附件) </span><span class="sxs-lookup"><span data-stu-id="b4d12-146">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="b4d12-147">**如果订阅包含** Microsoft Defender for Office 365 (，ATP 安全链接) </span><span class="sxs-lookup"><span data-stu-id="b4d12-147">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="b4d12-148">在默认视图中，所有内容都折叠。</span><span class="sxs-lookup"><span data-stu-id="b4d12-148">In the default view, everything is collapsed.</span></span> <span data-ttu-id="b4d12-149">每个策略旁边都有策略 (的比较结果摘要，您可以修改) 以及标准或严格保护配置文件的相应策略中的设置 (这些策略不能修改) 。</span><span class="sxs-lookup"><span data-stu-id="b4d12-149">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="b4d12-150">你将看到要比较的保护配置文件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="b4d12-150">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="b4d12-151">**绿色**：所有现有策略中所有设置都至少与保护配置文件一样安全。</span><span class="sxs-lookup"><span data-stu-id="b4d12-151">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="b4d12-152">**Amber：** 现有策略中的少量设置没有保护配置文件安全。</span><span class="sxs-lookup"><span data-stu-id="b4d12-152">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="b4d12-153">**红色**：现有策略中的大量设置没有保护配置文件安全。</span><span class="sxs-lookup"><span data-stu-id="b4d12-153">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="b4d12-154">这可能是许多策略中的一些设置或一个策略中的多个设置。</span><span class="sxs-lookup"><span data-stu-id="b4d12-154">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="b4d12-155">For favorable comparisons， you'll see the text： **All settings follow** \<**Standard** or **Strict**\> **recommendations.**</span><span class="sxs-lookup"><span data-stu-id="b4d12-155">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="b4d12-156">否则，你将看到要更改的建议设置的数量。</span><span class="sxs-lookup"><span data-stu-id="b4d12-156">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="b4d12-157">如果展开 **策略组/设置名称**，则显示每个特定策略中需要关注的所有策略和关联设置。</span><span class="sxs-lookup"><span data-stu-id="b4d12-157">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="b4d12-158">或者，您可以扩展特定类型的策略 (例如，反垃圾邮件) 查看那些需要您注意的策略类型的设置。</span><span class="sxs-lookup"><span data-stu-id="b4d12-158">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="b4d12-159">如果比较没有针对绿色策略 (建议) ，则扩展策略不会显示任何结果。</span><span class="sxs-lookup"><span data-stu-id="b4d12-159">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="b4d12-160">如果存在任何数量的改进建议， (或红色) ，则说明需要注意的设置，并且以下列中显示了相应的信息：</span><span class="sxs-lookup"><span data-stu-id="b4d12-160">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="b4d12-161">需要你注意的设置的名称。</span><span class="sxs-lookup"><span data-stu-id="b4d12-161">The name of the setting that requires your attention.</span></span> <span data-ttu-id="b4d12-162">例如，在上一张屏幕截图中，它是反垃圾邮件 **策略中的批量** 电子邮件阈值。</span><span class="sxs-lookup"><span data-stu-id="b4d12-162">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="b4d12-163">**策略**：包含设置的受影响策略的名称。</span><span class="sxs-lookup"><span data-stu-id="b4d12-163">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="b4d12-164">**应用于**：应用受影响的策略的用户数。</span><span class="sxs-lookup"><span data-stu-id="b4d12-164">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="b4d12-165">**当前配置**：设置的当前值。</span><span class="sxs-lookup"><span data-stu-id="b4d12-165">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="b4d12-166">**上次修改时间**：上次修改策略的日期。</span><span class="sxs-lookup"><span data-stu-id="b4d12-166">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="b4d12-167">**建议**：Standard 或 Strict 保护配置文件中设置的值。</span><span class="sxs-lookup"><span data-stu-id="b4d12-167">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="b4d12-168">若要更改策略中设置的值以匹配保护配置文件中的推荐值，请单击"**采用"。**</span><span class="sxs-lookup"><span data-stu-id="b4d12-168">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="b4d12-169">如果更改成功，你将看到消息： **建议已成功采用**。</span><span class="sxs-lookup"><span data-stu-id="b4d12-169">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="b4d12-170">单击 **"** 刷新"查看建议数量减少，以及从结果中删除特定设置/策略行。</span><span class="sxs-lookup"><span data-stu-id="b4d12-170">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="b4d12-171">配置分析器中的配置偏移分析和历史记录选项卡</span><span class="sxs-lookup"><span data-stu-id="b4d12-171">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="b4d12-172">此选项卡允许你跟踪对自定义安全策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b4d12-172">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="b4d12-173">默认情况下，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="b4d12-173">By default, the following information is displayed:</span></span>

- <span data-ttu-id="b4d12-174">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="b4d12-174">**Last modified**</span></span>
- <span data-ttu-id="b4d12-175">**修改者**</span><span class="sxs-lookup"><span data-stu-id="b4d12-175">**Modified by**</span></span>
- <span data-ttu-id="b4d12-176">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="b4d12-176">**Setting Name**</span></span>
- <span data-ttu-id="b4d12-177">**策略**</span><span class="sxs-lookup"><span data-stu-id="b4d12-177">**Policy**</span></span>
- <span data-ttu-id="b4d12-178">**类型**</span><span class="sxs-lookup"><span data-stu-id="b4d12-178">**Type**</span></span>

<span data-ttu-id="b4d12-179">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="b4d12-179">To filter the results, click **Filter**.</span></span> <span data-ttu-id="b4d12-180">在 **出现的** "筛选器"飞出中，可以从以下筛选器中选择：</span><span class="sxs-lookup"><span data-stu-id="b4d12-180">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="b4d12-181">**开始时间和\*\*\*\*结束时间 (** 日期) </span><span class="sxs-lookup"><span data-stu-id="b4d12-181">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="b4d12-182">**标准保护** 或 **严格保护**</span><span class="sxs-lookup"><span data-stu-id="b4d12-182">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="b4d12-183">若要将结果导出到 .csv 文件，请单击"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="b4d12-183">To export the results to a .csv file, click **Export**.</span></span>

![配置分析器中的配置偏移分析和历史记录视图](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
