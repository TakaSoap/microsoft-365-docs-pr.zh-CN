---
title: 在 Microsoft Defender 保险箱设置链接策略Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for 保险箱 中查看、创建、修改和删除保险箱链接策略和全局 保险箱 链接Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 61cb4746289a8acbdd9af7f668010604de511902
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694493"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95484-103">在 Microsoft Defender 保险箱设置链接策略Office 365</span><span class="sxs-lookup"><span data-stu-id="95484-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95484-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="95484-104">**Applies to**</span></span>
- [<span data-ttu-id="95484-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="95484-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="95484-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95484-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="95484-107">本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="95484-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="95484-108">如果你是一位家庭用户，正在查找有关 Outlook 中的安全链接的信息，请参阅 Advanced [Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="95484-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="95484-109">保险箱链接是 Microsoft [Defender for Office 365](defender-for-office-365.md)中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。</span><span class="sxs-lookup"><span data-stu-id="95484-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="95484-110">有关详细信息，请参阅 microsoft Defender 保险箱[中的链接Office 365。](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="95484-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="95484-111">链接策略没有内置或默认保险箱。</span><span class="sxs-lookup"><span data-stu-id="95484-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="95484-112">若要保险箱 URL 的链接扫描，需要创建一个或多个保险箱链接策略，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="95484-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="95484-113">在"链接"策略保险箱 **配置链接保护保险箱** 全局设置。</span><span class="sxs-lookup"><span data-stu-id="95484-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="95484-114">有关说明，请参阅[在 Microsoft Defender 中配置保险箱链接的全局Office 365。](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="95484-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="95484-115">您可以在安全保险箱 &合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置链接Exchange Online;独立 EOP PowerShell，适用于Exchange Online邮箱，但使用 Microsoft Defender for Office 365 加载项订阅的组织) 。</span><span class="sxs-lookup"><span data-stu-id="95484-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="95484-116">链接策略的基本保险箱包括：</span><span class="sxs-lookup"><span data-stu-id="95484-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="95484-117">安全链接策略：打开 保险箱 链接保护，启用实时 URL 扫描，指定是否在传递邮件之前等待实时扫描完成，启用内部邮件扫描，指定是否跟踪用户单击 URL，并指定是否允许用户单击原始 URL。</span><span class="sxs-lookup"><span data-stu-id="95484-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="95484-118">**安全链接规则**：指定策略应用于 (的优先级和收件人) 。</span><span class="sxs-lookup"><span data-stu-id="95484-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95484-119">管理员应考虑 SafeLinks 的不同配置设置。</span><span class="sxs-lookup"><span data-stu-id="95484-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="95484-120">可用选项之一是在 SafeLinks 中包括用户可识别信息。</span><span class="sxs-lookup"><span data-stu-id="95484-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="95484-121">此功能使 *安全运营团队* 能够调查潜在用户泄露、采取纠正措施并限制代价高昂的泄露。</span><span class="sxs-lookup"><span data-stu-id="95484-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="95484-122">在安全与合规中心内管理链接保险箱，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="95484-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="95484-123">创建链接保险箱策略时，实际上是同时对两者使用相同的名称创建安全链接规则和相关安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="95484-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="95484-124">修改邮件保险箱策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="95484-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="95484-125">所有其他设置修改关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="95484-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="95484-126">删除链接保险箱时，安全链接规则和相关的安全链接策略将被删除。</span><span class="sxs-lookup"><span data-stu-id="95484-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="95484-127">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="95484-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="95484-128">有关详细信息，请参阅本文稍后的使用[Exchange Online PowerShell 或独立 EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)配置 保险箱 链接策略部分。</span><span class="sxs-lookup"><span data-stu-id="95484-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95484-129">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="95484-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95484-130">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="95484-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="95484-131">若要直接转到"链接 **保险箱，** 请使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="95484-131">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="95484-132">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="95484-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="95484-133">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="95484-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="95484-134">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="95484-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="95484-135">若要创建、修改和删除 保险箱 链接策略，您需要是安全 &与合规中心内组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。 </span><span class="sxs-lookup"><span data-stu-id="95484-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="95484-136">若要对链接策略保险箱只读访问权限，您需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="95484-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="95484-137">有关详细信息，请参阅安全与[合规&中的权限](permissions-in-the-security-and-compliance-center.md)和[Exchange Online。](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="95484-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="95484-138">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="95484-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="95484-139">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="95484-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="95484-140">.</span><span class="sxs-lookup"><span data-stu-id="95484-140">.</span></span> <span data-ttu-id="95484-141">- **Exchange Online** 中的"仅查看组织管理"[](/Exchange/permissions-exo/permissions-exo#role-groups)角色组还授予对该功能的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="95484-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="95484-142">有关推荐的链接策略保险箱，请参阅保险箱[链接策略设置。](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="95484-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="95484-143">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="95484-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="95484-144">[新功能不断添加到 Microsoft Defender for Office 365。](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="95484-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="95484-145">添加新功能时，可能需要对现有"链接"策略保险箱调整。</span><span class="sxs-lookup"><span data-stu-id="95484-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="95484-146">使用安全&合规中心创建保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-146">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="95484-147">在安全保险箱安全中心创建自定义链接&将同时创建安全链接规则和相关的安全链接策略，对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="95484-147">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="95484-148">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 保险箱链接。**</span><span class="sxs-lookup"><span data-stu-id="95484-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="95484-149">在 **"保险箱"页上**，单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="95484-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="95484-150">"**新建保险箱链接"策略** 向导将打开。</span><span class="sxs-lookup"><span data-stu-id="95484-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="95484-151">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="95484-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="95484-152">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="95484-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="95484-153">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="95484-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="95484-154">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="95484-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="95484-155">在 **设置** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="95484-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="95484-156">**选择邮件中未知潜在** 恶意 URL 的操作：选择"打开"以保险箱电子邮件中的链接的链接保护。</span><span class="sxs-lookup"><span data-stu-id="95484-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="95484-157">**Select the action for unknown or potentially malicious URLS within Microsoft Teams**： Select **On** to enable 保险箱 Links protection for links in Teams.</span><span class="sxs-lookup"><span data-stu-id="95484-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="95484-158">**对指向文件的可疑链接应用实时 URL** 扫描：选择此设置可启用电子邮件中链接的实时扫描。</span><span class="sxs-lookup"><span data-stu-id="95484-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="95484-159">**等待 URL 扫描完成，然后再传递邮件**：选择此设置以等待实时 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="95484-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="95484-160">**Apply 保险箱 Links to email messages sent within the organization**： Select this setting to apply the 保险箱 Links policy to messages between internal senders and internal recipients.</span><span class="sxs-lookup"><span data-stu-id="95484-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="95484-161">**Do not track user clicks**： Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span><span class="sxs-lookup"><span data-stu-id="95484-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="95484-162">**不允许用户单击到原始 URL：** 选择此设置可阻止用户单击到警告页面中 [的原始](safe-links.md#warning-pages-from-safe-links)URL。</span><span class="sxs-lookup"><span data-stu-id="95484-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="95484-163">**不要重写以下 URL：** 允许访问指定 URL，否则，链接保险箱阻止。</span><span class="sxs-lookup"><span data-stu-id="95484-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="95484-164">在框中，键入您想要的 URL 或值，然后单击</span><span class="sxs-lookup"><span data-stu-id="95484-164">In the box, type the URL or value that you want, and then click</span></span> ![添加按钮图标](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="95484-166">.</span><span class="sxs-lookup"><span data-stu-id="95484-166">.</span></span>

     <span data-ttu-id="95484-167">若要删除现有条目，请选择它，然后单击</span><span class="sxs-lookup"><span data-stu-id="95484-167">To remove an existing entry, select it and then click</span></span> ![删除按钮图标](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="95484-169">.</span><span class="sxs-lookup"><span data-stu-id="95484-169">.</span></span>

     <span data-ttu-id="95484-170">有关条目语法，请参阅 ["不重写以下 URL"列表的条目语法](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="95484-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="95484-171">有关这些设置的详细信息，请参阅保险箱[电子邮件](safe-links.md#safe-links-settings-for-email-messages)的链接设置和保险箱[的链接Microsoft Teams。](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="95484-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="95484-172">有关"标准"和"严格"策略设置的建议值，请参阅保险箱[链接策略设置"](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="95484-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="95484-173">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="95484-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="95484-174">在 **出现的"应用于** "页上，标识策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="95484-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="95484-175">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="95484-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="95484-176">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="95484-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="95484-177">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="95484-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="95484-178">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="95484-178">Click **Add a condition**.</span></span> <span data-ttu-id="95484-179">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="95484-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="95484-180">**收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="95484-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="95484-181">**收件人是 ：指定** 组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="95484-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="95484-182">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="95484-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="95484-183">选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。</span><span class="sxs-lookup"><span data-stu-id="95484-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="95484-184">在框中单击并滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="95484-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="95484-185">在框中单击并开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="95484-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="95484-186">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="95484-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="95484-187">若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="95484-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="95484-188">若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="95484-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="95484-189">若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。</span><span class="sxs-lookup"><span data-stu-id="95484-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="95484-190">若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。</span><span class="sxs-lookup"><span data-stu-id="95484-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="95484-191">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="95484-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="95484-192">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="95484-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="95484-193">在出现的 **"查看设置** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="95484-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="95484-194">可以单击每个 **设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="95484-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="95484-195">完成后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="95484-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="95484-196">使用安全与&中心查看保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-196">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="95484-197">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 保险箱链接。**</span><span class="sxs-lookup"><span data-stu-id="95484-197">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="95484-198">On the **保险箱 Links** page， select a policy from the list and click on it (don't select the check box) .</span><span class="sxs-lookup"><span data-stu-id="95484-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="95484-199">策略详细信息以飞出方式显示</span><span class="sxs-lookup"><span data-stu-id="95484-199">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="95484-200">使用安全与&中心修改保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-200">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="95484-201">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 保险箱链接。**</span><span class="sxs-lookup"><span data-stu-id="95484-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="95484-202">On the **保险箱 Links** page， select a policy from the list and click on it (don't select the check box) .</span><span class="sxs-lookup"><span data-stu-id="95484-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="95484-203">在出现的策略详细信息飞出中，单击"编辑 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="95484-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="95484-204">在飞出中显示可用的设置与使用安全与合规中心创建链接&[中所述的设置保险箱相同](#use-the-security--compliance-center-to-create-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="95484-204">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="95484-205">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="95484-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="95484-206">启用或禁用保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="95484-207">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 保险箱链接。**</span><span class="sxs-lookup"><span data-stu-id="95484-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="95484-208">请注意"状态" **列中** 的值：</span><span class="sxs-lookup"><span data-stu-id="95484-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="95484-209">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="95484-209">Move the toggle to the left to disable the policy:</span></span> ![关闭策略](../../media/scc-toggle-off.png)<span data-ttu-id="95484-211">.</span><span class="sxs-lookup"><span data-stu-id="95484-211">.</span></span>

   - <span data-ttu-id="95484-212">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="95484-212">Move the toggle to the right to enable the policy:</span></span> ![打开策略](../../media/scc-toggle-on.png)<span data-ttu-id="95484-214">.</span><span class="sxs-lookup"><span data-stu-id="95484-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="95484-215">设置链接保险箱的优先级</span><span class="sxs-lookup"><span data-stu-id="95484-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="95484-216">默认情况下，保险箱链接策略的优先级基于它们在新策略中创建的顺序 (策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="95484-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="95484-217">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="95484-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="95484-218">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="95484-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="95484-219">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="95484-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="95484-220">保险箱链接策略按其处理顺序显示 (策略的优先级值为 0) 。 </span><span class="sxs-lookup"><span data-stu-id="95484-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="95484-221">在安全&合规中心，只能在创建"链接保险箱策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="95484-221">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="95484-222">在 PowerShell 中，您可以在创建安全链接规则集时替代默认优先级 (这可能会影响现有规则或规则) 。</span><span class="sxs-lookup"><span data-stu-id="95484-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="95484-223">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="95484-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="95484-224">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 保险箱链接。**</span><span class="sxs-lookup"><span data-stu-id="95484-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="95484-225">On the **保险箱 Links** page， select a policy from the list and click on it (don't select the check box) .</span><span class="sxs-lookup"><span data-stu-id="95484-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="95484-226">在出现的策略详细信息飞出中，单击可用的优先级按钮：</span><span class="sxs-lookup"><span data-stu-id="95484-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="95484-227">优先级保险箱 **0** 的"链接"策略仅具有"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="95484-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="95484-228">优先级保险箱最低的"链接"策略 (例如 **，3**) 只有"增加 **优先级"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="95484-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="95484-229">如果你有三个或多个"链接保险箱，则最高优先级和最低优先级值之间的策略将同时具有"增加优先级"和"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="95484-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="95484-230">单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。</span><span class="sxs-lookup"><span data-stu-id="95484-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="95484-231">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="95484-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="95484-232">使用安全与&中心删除保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-232">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="95484-233">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 保险箱链接。**</span><span class="sxs-lookup"><span data-stu-id="95484-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="95484-234">On the **保险箱 Links** page， select a policy from the list and click on it (don't select the check box) .</span><span class="sxs-lookup"><span data-stu-id="95484-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="95484-235">在随即出现的策略详细信息飞出中，单击"删除 **策略**"，然后在出现的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="95484-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="95484-236">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="95484-237">如前所述，链接保险箱由安全链接策略和安全链接规则组成。</span><span class="sxs-lookup"><span data-stu-id="95484-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="95484-238">在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="95484-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="95484-239">您可以使用 **\* -SafeLinksPolicy** cmdlet 管理安全链接策略，使用 **\* -SafeLinksRule** cmdlet 管理安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="95484-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="95484-240">在 PowerShell 中，首先创建安全链接策略，然后创建安全链接规则，以标识该规则应用于的策略。</span><span class="sxs-lookup"><span data-stu-id="95484-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="95484-241">在 PowerShell 中，分别修改安全链接策略和安全链接规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="95484-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="95484-242">从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="95484-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="95484-243">使用 PowerShell 创建链接保险箱策略</span><span class="sxs-lookup"><span data-stu-id="95484-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="95484-244">在 PowerShell 保险箱链接策略的过程包含两个步骤：</span><span class="sxs-lookup"><span data-stu-id="95484-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="95484-245">创建安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="95484-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="95484-246">创建安全链接规则，该规则指定应用该规则的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="95484-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="95484-247">你可以创建新的安全链接规则，并为其分配现有的未关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="95484-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="95484-248">安全链接规则不能与多个安全链接策略关联。</span><span class="sxs-lookup"><span data-stu-id="95484-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="95484-249">可以在 PowerShell 中的新安全链接策略上配置以下设置，这些设置在创建策略之前&安全与合规中心不可用：</span><span class="sxs-lookup"><span data-stu-id="95484-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="95484-250">在 `$false` **New-SafeLinksRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="95484-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="95484-251">在 _\<Number\>_ **New-SafeLinksRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="95484-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="95484-252">在 PowerShell 中新建的安全链接策略在安全与合规&，除非将策略分配给安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="95484-252">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="95484-253">步骤 1：使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="95484-254">若要创建安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="95484-255">有关要用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅"不要重写以下 [URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)列表的条目语法。</span><span class="sxs-lookup"><span data-stu-id="95484-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="95484-256">有关在使用 **Set-SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于 _DoNotRewriteUrls_ 参数的其他语法，请参阅本文稍后的使用 [PowerShell](#use-powershell-to-modify-safe-links-policies)修改安全链接策略一节。</span><span class="sxs-lookup"><span data-stu-id="95484-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="95484-257">此示例创建一个名为 Contoso All 的安全链接策略，并具有以下值：</span><span class="sxs-lookup"><span data-stu-id="95484-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="95484-258">在电子邮件中打开 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="95484-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="95484-259">在"点击点击预览Teams (启用 URL) 。</span><span class="sxs-lookup"><span data-stu-id="95484-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="95484-260">打开单击的 URL（包括指向文件的单击链接）实时扫描。</span><span class="sxs-lookup"><span data-stu-id="95484-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="95484-261">等待 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="95484-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="95484-262">打开内部邮件的 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="95484-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="95484-263">跟踪与 保险箱 链接保护相关的用户单击 (我们使用的不是 _DoNotTrackUserClicks_ 参数，默认值是 $false，这意味着用户单击会) 。</span><span class="sxs-lookup"><span data-stu-id="95484-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="95484-264">不允许用户单击访问原始 URL。</span><span class="sxs-lookup"><span data-stu-id="95484-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="95484-265">有关语法和参数的详细信息，请参阅[New-SafeLinksPolicy。](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="95484-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="95484-266">步骤 2：使用 PowerShell 创建安全链接规则</span><span class="sxs-lookup"><span data-stu-id="95484-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="95484-267">若要创建安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="95484-268">本示例创建一个名为"Contoso All"的安全链接规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="95484-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="95484-269">该规则与名为 Contoso All 的安全链接策略相关联。</span><span class="sxs-lookup"><span data-stu-id="95484-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="95484-270">该规则适用于域中的所有 contoso.com 收件人。</span><span class="sxs-lookup"><span data-stu-id="95484-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="95484-271">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="95484-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="95484-272">如果规则 (_Enabled_ 参数，则启用该规则，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="95484-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="95484-273">有关语法和参数的详细信息，请参阅[New-SafeLinksRule。](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="95484-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="95484-274">使用 PowerShell 查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="95484-275">若要查看现有安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95484-276">本示例返回所有安全链接策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="95484-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="95484-277">此示例返回名为 Contoso Executives 的安全链接策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95484-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="95484-278">有关语法和参数的详细信息，请参阅 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="95484-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="95484-279">使用 PowerShell 查看安全链接规则</span><span class="sxs-lookup"><span data-stu-id="95484-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="95484-280">若要查看现有安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95484-281">本示例返回所有安全链接规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="95484-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="95484-282">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="95484-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="95484-283">本示例返回名为 Contoso Executives 的安全链接规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95484-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="95484-284">有关语法和参数的详细信息，请参阅 [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="95484-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="95484-285">使用 PowerShell 修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="95484-286">如果 **Set-SafeLinksPolicy** cmdlet 没有 Name 参数，则 (在 PowerShell 中重命名安全链接) 。</span><span class="sxs-lookup"><span data-stu-id="95484-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="95484-287">在安全与保险箱重命名"链接"策略&，只需重命名安全链接 _规则_。</span><span class="sxs-lookup"><span data-stu-id="95484-287">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="95484-288">在 PowerShell 中修改安全链接策略的唯一额外注意事项是 _DoNotRewriteUrls_ 参数的可用语法 ("不重写以下 [URL"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 列表) ：</span><span class="sxs-lookup"><span data-stu-id="95484-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="95484-289">若要添加将替换任何现有条目的值，请使用以下语法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="95484-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="95484-290">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="95484-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="95484-291">否则，创建安全链接策略时可用的设置与本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) 创建安全链接策略部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="95484-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="95484-292">若要修改安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="95484-293">有关语法和参数的详细信息，请参阅 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="95484-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="95484-294">使用 PowerShell 修改安全链接规则</span><span class="sxs-lookup"><span data-stu-id="95484-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="95484-295">在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="95484-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="95484-296">若要启用或禁用现有安全链接规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="95484-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="95484-297">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) 创建安全链接规则一节中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="95484-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="95484-298">若要修改安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="95484-299">有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="95484-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="95484-300">使用 PowerShell 启用或禁用安全链接规则</span><span class="sxs-lookup"><span data-stu-id="95484-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="95484-301">在 PowerShell 中启用或禁用安全链接规则可启用或禁用整个 保险箱 链接策略 (安全链接规则以及分配的安全链接策略) 。</span><span class="sxs-lookup"><span data-stu-id="95484-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="95484-302">若要在 PowerShell 中启用或禁用安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="95484-303">本示例禁用名为"Marketing Department"的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="95484-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="95484-304">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="95484-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="95484-305">有关语法和参数的详细信息，请参阅[Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule)和[Disable-SafeLinksRule。](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="95484-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="95484-306">使用 PowerShell 设置安全链接规则的优先级</span><span class="sxs-lookup"><span data-stu-id="95484-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="95484-p123">可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。</span><span class="sxs-lookup"><span data-stu-id="95484-p123">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="95484-312">若要在 PowerShell 中设置安全链接规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="95484-p124">此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。</span><span class="sxs-lookup"><span data-stu-id="95484-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="95484-315">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-SafeLinksRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="95484-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="95484-316">有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="95484-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="95484-317">使用 PowerShell 删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="95484-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="95484-318">使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="95484-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="95484-319">若要在 PowerShell 中删除安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="95484-320">此示例删除名为 Marketing Department 的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="95484-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="95484-321">有关语法和参数的详细信息，请参阅[Remove-SafeLinksPolicy。](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="95484-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="95484-322">使用 PowerShell 删除安全链接规则</span><span class="sxs-lookup"><span data-stu-id="95484-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="95484-323">使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="95484-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="95484-324">若要在 PowerShell 中删除安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="95484-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="95484-325">本示例删除名为"Marketing Department"的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="95484-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="95484-326">有关语法和参数的详细信息，请参阅 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="95484-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="95484-327">若要验证保险箱是否正在扫描邮件，请查看可用的 Microsoft Defender Office 365报告。</span><span class="sxs-lookup"><span data-stu-id="95484-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="95484-328">有关详细信息，请参阅查看[Defender for Office 365](view-reports-for-mdo.md)报告和在安全与合规&[使用资源管理器](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="95484-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="95484-329">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="95484-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="95484-330">若要验证是否成功创建、修改或删除了链接保险箱，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="95484-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="95484-331">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 保险箱链接。**</span><span class="sxs-lookup"><span data-stu-id="95484-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="95484-332">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="95484-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="95484-333">若要查看更多详细信息，请从列表中选择策略，然后查看飞出中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95484-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="95484-334">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：</span><span class="sxs-lookup"><span data-stu-id="95484-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```