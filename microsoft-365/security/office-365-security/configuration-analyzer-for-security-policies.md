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
description: 管理员可以了解如何使用配置分析器，查找并修复安全策略，其中包含标准保护和严格保护预设安全策略下的设置。
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825769"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="2e7cd-103">EOP 和 Office 365 ATP 中保护策略的配置分析器</span><span class="sxs-lookup"><span data-stu-id="2e7cd-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="2e7cd-104">本主题中所述的功能在预览中，并不是在所有组织中可用，可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="2e7cd-105">安全 & 合规中心中的配置分析器提供了一个中央位置，用于查找并修复任何安全策略，这些策略包含预设安全策略中标准保护和严格保护 [配置文件设置下方的设置](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="2e7cd-106">配置分析器分析了以下类型的策略：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="2e7cd-107">**Exchange Online Protection (EOP) 策略**：包括具有 Exchange Online 邮箱的 Microsoft 365 组织和独立的 EOP 组织，无需 Exchange Online 邮箱：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="2e7cd-108">[反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="2e7cd-109">[反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="2e7cd-110">[EOP 反网络钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="2e7cd-111">**Office 365 高级威胁防 (ATP) 策略**：其中包括订阅有 Microsoft 365 E5 或 Office 365 ATP 的组织：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="2e7cd-112">ATP 防钓鱼策略，包括：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="2e7cd-113">EOP [反网络](set-up-anti-phishing-policies.md#spoof-settings) 钓鱼策略中提供的相同欺骗设置。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="2e7cd-114">模拟设置</span><span class="sxs-lookup"><span data-stu-id="2e7cd-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="2e7cd-115">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="2e7cd-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="2e7cd-116">[安全链接策略](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="2e7cd-117">[安全附件策略](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="2e7cd-118">EOP **和** **Office** 365 ATP 安全的推荐设置中介绍了用作基线的标准和 [严格策略设置值](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2e7cd-119">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2e7cd-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2e7cd-120">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2e7cd-121">要直接转到"配置 **分析器"** 页面，请使用 <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="2e7cd-122">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2e7cd-123">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="2e7cd-124">若要使用配置分析 **器** 并对安全策略进行更新，您需要是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="2e7cd-125">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="2e7cd-126">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="2e7cd-127">对于对配置分析器的只读访问权限，您需要是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="2e7cd-128">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="2e7cd-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="2e7cd-130">使用安全与合规中心中的&器</span><span class="sxs-lookup"><span data-stu-id="2e7cd-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="2e7cd-131">在安全与 &合规中心内，转到 **威胁** \> **管理** \> **策略配置分析器**。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

!["威胁管理策略"页上的"配置分析器 \> "小组件](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="2e7cd-133">配置分析器有两个主要选项卡：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="2e7cd-134">**设置和建议**：你可以选取"标准"或"严格"，并将这些设置与现有安全策略进行比较。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="2e7cd-135">在结果中，你可以调整设置的值以使其与标准或严格级别相同。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="2e7cd-136">**配置摘要分析和历史记录**：此视图允许根据配置分析器在一段时间内所做的更改，跟踪您已对策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="2e7cd-137">配置分析器中的设置和建议选项卡</span><span class="sxs-lookup"><span data-stu-id="2e7cd-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="2e7cd-138">默认情况下，此选项卡将打开与标准保护配置文件的比较。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="2e7cd-139">单击"视图严格"建议可切换到严 **格保护配置文件比较**。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="2e7cd-140">要切换回来，**请选择"查看标准建议"。**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-140">To switch back, select **View Standard recommendations**.</span></span>

![配置分析器中的设置和建议视图](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="2e7cd-142">默认情况下，" **策略组/设置名称** "列包含不同类型的安全策略以及需要改善 (（如果有）的策略中的设置数量的折叠) 。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="2e7cd-143">策略类型为：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-143">The types of policies are:</span></span>

- <span data-ttu-id="2e7cd-144">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-144">**Anti-spam**</span></span>
- <span data-ttu-id="2e7cd-145">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-145">**Anti-phishing**</span></span>
- <span data-ttu-id="2e7cd-146">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-146">**Anti-malware**</span></span>
- <span data-ttu-id="2e7cd-147">**如果你的订阅包括 ATP** (管理者，则 ATP 安全) </span><span class="sxs-lookup"><span data-stu-id="2e7cd-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="2e7cd-148">**如果订阅包括 ATP** (，则 ATP 安全链接) </span><span class="sxs-lookup"><span data-stu-id="2e7cd-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="2e7cd-149">在默认视图中，所有内容都已折叠。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="2e7cd-150">在每个策略旁边，会显示来自策略 (的比较结果摘要，可以修改) 以及无法修改严格的标准或严格保护配置文件 (的相应) 策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="2e7cd-151">你将看到以下信息：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-151">You'll see the following information:</span></span>

- <span data-ttu-id="2e7cd-152">**绿色**：所有现有策略中的全部设置至少与要比较的保护配置文件一安全。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="2e7cd-153">**Amber：** 现有策略中的一少设置不如你正在比较的保护配置文件一捷。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="2e7cd-154">**红**色：现有策略中的大量设置不如你正比较的保护配置文件一安全。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="2e7cd-155">在许多策略中，这可能是许多策略中的几个设置，也可以是一个策略中的许多设置。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="2e7cd-156">对于可采用的比较，你将看到文本：遵 **循建议的所有** \<**Standard** or **Strict**\> **设置**。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="2e7cd-157">否则，你将看到建议更改的设置的数量。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="2e7cd-158">如果展开 **策略组/设置名称**，则会显示需要注意的每个特定策略中的所有策略和关联设置。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="2e7cd-159">或者，你可以展开特定类型的策略 (例如， **反垃圾邮件** 垃圾邮件) ，查看那些需要你关注的策略类型中的设置。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="2e7cd-160">如果比较针对的改进未提供 (建议，) ，则展开策略会显示"nothing"。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="2e7cd-161">如果以下各列中显示任意 (改善建议) ，则显示需要注意的设置，且以下列中显示相应的信息：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="2e7cd-162">需要关注你的设置的名称。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="2e7cd-163">例如，在上面的屏幕截图中，它是 **反垃圾邮件策略中的** 批量电子邮件阈值。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="2e7cd-164">**Policy：** 包含设置的受影响策略的名称。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="2e7cd-165">**应用于**：受影响的策略应用到的用户数量。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="2e7cd-166">**当前配置**：设置的当前值。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="2e7cd-167">**上次**修改时间：上次修改策略的日期。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="2e7cd-168">**建议：** 标准保护配置文件或严格保护配置文件中设置的值。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="2e7cd-169">要更改策略中设置的值，以与保护配置文件中的建议值匹配，请单击"**采用"。**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="2e7cd-170">如果更改成功，你将看到以下消息 **：建议已成功采用**。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="2e7cd-171">单击 **"** 刷新"可查看建议数量减少，并从结果中删除特定设置/策略行。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="2e7cd-172">配置分析器中的配置详细分析和历史记录选项卡</span><span class="sxs-lookup"><span data-stu-id="2e7cd-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="2e7cd-173">此选项卡允许您根据安全分析器中的信息跟踪已对自定义安全策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="2e7cd-174">默认情况下，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="2e7cd-175">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-175">**Last modified**</span></span>
- <span data-ttu-id="2e7cd-176">**修改者**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-176">**Modified by**</span></span>
- <span data-ttu-id="2e7cd-177">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-177">**Setting Name**</span></span>
- <span data-ttu-id="2e7cd-178">**策略**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-178">**Policy**</span></span>
- <span data-ttu-id="2e7cd-179">**类型**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-179">**Type**</span></span>

<span data-ttu-id="2e7cd-180">若要筛选结果，请单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2e7cd-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="2e7cd-181">在 **显示的** 筛选器浮出控件中，可以选择以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="2e7cd-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="2e7cd-182">**开始时间** 和 **结束时间** (日期) </span><span class="sxs-lookup"><span data-stu-id="2e7cd-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="2e7cd-183">**标准保护\*\*\*\*或严格保护**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="2e7cd-184">要将结果导出到 .csv 文件，请单击"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="2e7cd-184">To export the results to a .csv file, click **Export**.</span></span>

![配置分析器中的配置详细分析和历史记录视图](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
