---
title: 在 Microsoft Defender for Office 365 中设置安全链接策略
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
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中查看、创建、修改和删除安全链接策略和全局安全链接设置。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203554"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c9ea7-103">在 Microsoft Defender for Office 365 中设置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c9ea7-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="c9ea7-104">**Applies to**</span></span>
- [<span data-ttu-id="c9ea7-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="c9ea7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c9ea7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9ea7-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="c9ea7-107">本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="c9ea7-108">如果您是一位家庭用户，正在查找有关 Outlook 中安全链接的信息，请参阅高级安全 Outlook.com [信息](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c9ea7-109">安全链接是 Microsoft [Defender for Office 365](defender-for-office-365.md) 中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="c9ea7-110">有关详细信息，请参阅 [Microsoft Defender for Office 365 中的安全链接](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="c9ea7-111">没有内置或默认安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="c9ea7-112">若要获取 URL 的安全链接扫描，需要创建一个或多个安全链接策略，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="c9ea7-113">在安全链接策略之外配置安全 **链接保护的** 全局设置。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="c9ea7-114">有关说明，请参阅 [在 Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md)中配置安全链接的全局设置。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="c9ea7-115">您可以在安全与合规中心或 PowerShell (& Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置安全链接策略;适用于没有 Exchange Online 邮箱，但具有 Microsoft Defender for Office 365 附加订阅的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="c9ea7-116">安全链接策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="c9ea7-117">安全链接策略：打开安全链接保护，启用实时 URL 扫描，指定是否在传递邮件之前等待实时扫描完成，启用内部邮件扫描，指定是否跟踪用户单击 URL，并指定是否允许用户单击原始 URL。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="c9ea7-118">**安全链接规则**：指定策略应用于 (的优先级和收件人) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="c9ea7-119">在安全与合规中心内管理安全链接策略时，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c9ea7-120">创建安全链接策略时，实际上是同时使用同一名称创建安全链接规则和相关安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="c9ea7-121">修改安全链接策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="c9ea7-122">所有其他设置修改关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="c9ea7-123">删除安全链接策略时，安全链接规则和相关的安全链接策略将被删除。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="c9ea7-124">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="c9ea7-125">有关详细信息，请参阅本文稍后介绍的使用 Exchange Online PowerShell 或独立 [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 配置安全链接策略部分。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c9ea7-126">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="c9ea7-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c9ea7-127">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c9ea7-128">若要直接转到安全 **链接页面** ，请使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="c9ea7-129">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c9ea7-130">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c9ea7-131">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c9ea7-132">若要创建、修改和删除安全链接策略，您需要是安全 & 合规中心内组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。 </span><span class="sxs-lookup"><span data-stu-id="c9ea7-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="c9ea7-133">若要对安全链接策略进行只读访问，你需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="c9ea7-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c9ea7-134">有关详细信息，请参阅安全 [与合规](permissions-in-the-security-and-compliance-center.md) 中心&和 [Exchange Online 中的权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="c9ea7-135">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c9ea7-136">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="c9ea7-137">.</span><span class="sxs-lookup"><span data-stu-id="c9ea7-137">.</span></span> <span data-ttu-id="c9ea7-138">- [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) **中的"** 仅查看组织管理"角色组还授予对该功能的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-138">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="c9ea7-139">有关安全链接策略的建议设置，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="c9ea7-140">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c9ea7-141">[新功能不断添加到 Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)中。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-141">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="c9ea7-142">添加新功能时，可能需要对现有安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="c9ea7-143">使用安全&中心创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="c9ea7-144">在安全与合规中心内&安全链接策略会同时创建安全链接规则和相关安全链接策略，对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="c9ea7-145">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全链接**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c9ea7-146">在"安全 **链接"** 页上，单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="c9ea7-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="c9ea7-147">将 **打开"新建安全链接"策略** 向导。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="c9ea7-148">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="c9ea7-149">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="c9ea7-150">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="c9ea7-151">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c9ea7-152">在出现的 **"** 设置"页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c9ea7-153">**选择邮件中未知潜在** 恶意 URL 的操作：选择 **"** 打开"为电子邮件中的链接启用安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="c9ea7-154">**选择 Microsoft Teams 中未知** 或潜在恶意 URL 的操作：选择"打开"为 Teams 中的链接启用安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="c9ea7-155">**对指向文件的可疑链接应用实时 URL** 扫描：选择此设置可启用电子邮件中链接的实时扫描。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="c9ea7-156">**等待 URL 扫描完成，然后再传递邮件**：选择此设置以等待实时 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="c9ea7-157">**将安全链接应用于组织** 内部发送的电子邮件：选择此设置将安全链接策略应用于内部发件人和内部收件人之间的邮件。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="c9ea7-158">**Do not track user clicks**： Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span><span class="sxs-lookup"><span data-stu-id="c9ea7-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="c9ea7-159">**不允许用户单击到原始 URL：** 选择此设置可阻止用户单击到警告页面中 [的原始](safe-links.md#warning-pages-from-safe-links)URL。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="c9ea7-160">**不要重写以下 URL：** 允许访问指定 URL，否则安全链接会阻止这些 URL。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="c9ea7-161">在框中，键入您想要的 URL 或值，然后单击</span><span class="sxs-lookup"><span data-stu-id="c9ea7-161">In the box, type the URL or value that you want, and then click</span></span> ![添加按钮图标](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="c9ea7-163">.</span><span class="sxs-lookup"><span data-stu-id="c9ea7-163">.</span></span>

     <span data-ttu-id="c9ea7-164">若要删除现有条目，请选择它，然后单击</span><span class="sxs-lookup"><span data-stu-id="c9ea7-164">To remove an existing entry, select it and then click</span></span> ![删除按钮图标](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="c9ea7-166">.</span><span class="sxs-lookup"><span data-stu-id="c9ea7-166">.</span></span>

     <span data-ttu-id="c9ea7-167">有关条目语法，请参阅 ["不重写以下 URL"列表的条目语法](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="c9ea7-168">有关这些设置的详细信息，请参阅 [电子邮件的安全链接设置](safe-links.md#safe-links-settings-for-email-messages) 和 Microsoft Teams [的安全链接设置](safe-links.md#safe-links-settings-for-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-168">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="c9ea7-169">有关"标准"和"严格"策略设置的建议值，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="c9ea7-170">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c9ea7-171">在 **出现的"应用于** "页上，标识策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="c9ea7-172">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="c9ea7-173">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="c9ea7-174">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="c9ea7-175">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="c9ea7-175">Click **Add a condition**.</span></span> <span data-ttu-id="c9ea7-176">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="c9ea7-177">**收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="c9ea7-178">**收件人是 ：指定** 组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="c9ea7-179">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="c9ea7-180">选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="c9ea7-181">在框中单击并滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="c9ea7-182">在框中单击并开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="c9ea7-183">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="c9ea7-184">若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="c9ea7-185">若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="c9ea7-186">若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="c9ea7-187">若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="c9ea7-188">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="c9ea7-189">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c9ea7-190">在出现的 **"查看设置** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="c9ea7-191">可以单击每个 **设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="c9ea7-192">完成后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="c9ea7-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="c9ea7-193">使用安全&中心查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="c9ea7-194">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全链接**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c9ea7-195">在" **安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="c9ea7-196">策略详细信息以飞出方式显示</span><span class="sxs-lookup"><span data-stu-id="c9ea7-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="c9ea7-197">使用安全&中心修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="c9ea7-198">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全链接**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c9ea7-199">在" **安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c9ea7-200">在出现的策略详细信息飞出中，单击"编辑 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="c9ea7-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="c9ea7-201">飞出中的可用设置与使用安全与合规中心创建安全链接策略& [中所述的设置相同](#use-the-security--compliance-center-to-create-safe-links-policies) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="c9ea7-202">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="c9ea7-203">启用或禁用安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="c9ea7-204">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全链接**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c9ea7-205">请注意"状态" **列中** 的值：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="c9ea7-206">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-206">Move the toggle to the left to disable the policy:</span></span> ![关闭策略](../../media/scc-toggle-off.png)<span data-ttu-id="c9ea7-208">.</span><span class="sxs-lookup"><span data-stu-id="c9ea7-208">.</span></span>

   - <span data-ttu-id="c9ea7-209">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-209">Move the toggle to the right to enable the policy:</span></span> ![打开策略](../../media/scc-toggle-on.png)<span data-ttu-id="c9ea7-211">.</span><span class="sxs-lookup"><span data-stu-id="c9ea7-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="c9ea7-212">设置安全链接策略的优先级</span><span class="sxs-lookup"><span data-stu-id="c9ea7-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="c9ea7-213">默认情况下，安全链接策略的优先级基于它们在新策略中创建的顺序 (策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="c9ea7-214">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c9ea7-215">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="c9ea7-216">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="c9ea7-217">安全链接策略按其处理顺序显示， (优先级值为 0 时) 。 </span><span class="sxs-lookup"><span data-stu-id="c9ea7-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="c9ea7-218">在安全&合规中心，只能在创建安全链接策略后更改策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="c9ea7-219">在 PowerShell 中，您可以在创建安全链接规则集时替代默认优先级 (这可能会影响现有规则或规则) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="c9ea7-220">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="c9ea7-221">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全链接**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c9ea7-222">在" **安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c9ea7-223">在出现的策略详细信息飞出中，单击可用的优先级按钮：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="c9ea7-224">优先级值为 **0** **的安全** 链接策略只有"**减少优先级"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="c9ea7-225">优先级值最低的安全链接策略 (例如 **，3**) 只有"增加 **优先级"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="c9ea7-226">如果你有三个或多个安全链接策略，则优先级最高和最低值之间的策略同时具有"增加优先级"和"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="c9ea7-227">单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="c9ea7-228">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="c9ea7-229">使用安全&中心删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="c9ea7-230">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全链接**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c9ea7-231">在" **安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c9ea7-232">在随即出现的策略详细信息飞出中，单击"删除 **策略**"，然后在出现的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="c9ea7-233">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="c9ea7-234">如前所述，安全链接策略由安全链接策略和安全链接规则组成。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="c9ea7-235">在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="c9ea7-236">您可以使用 **\* -SafeLinksPolicy** cmdlet 管理安全链接策略，使用 **\* -SafeLinksRule** cmdlet 管理安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="c9ea7-237">在 PowerShell 中，首先创建安全链接策略，然后创建安全链接规则，以标识该规则应用于的策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="c9ea7-238">在 PowerShell 中，分别修改安全链接策略和安全链接规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="c9ea7-239">从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="c9ea7-240">使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="c9ea7-241">在 PowerShell 中创建安全链接策略的过程包含两个步骤：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c9ea7-242">创建安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="c9ea7-243">创建安全链接规则，该规则指定应用该规则的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="c9ea7-244">你可以创建新的安全链接规则，并为其分配现有的未关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="c9ea7-245">安全链接规则不能与多个安全链接策略关联。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="c9ea7-246">可以在 PowerShell 中的新安全链接策略上配置以下设置，这些设置在创建策略之前&安全与合规中心不可用：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="c9ea7-247">在 `$false` **New-SafeLinksRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="c9ea7-248">在 _\<Number\>_ **New-SafeLinksRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="c9ea7-249">在 PowerShell 中新建的安全链接策略在安全与合规&，除非将策略分配给安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="c9ea7-250">步骤 1：使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="c9ea7-251">若要创建安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="c9ea7-252">有关要用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅"不要重写以下 [URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)列表的条目语法。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="c9ea7-253">有关在使用 **Set-SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于 _DoNotRewriteUrls_ 参数的其他语法，请参阅本文稍后的使用 [PowerShell](#use-powershell-to-modify-safe-links-policies)修改安全链接策略一节。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="c9ea7-254">此示例创建一个名为 Contoso All 的安全链接策略，并具有以下值：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="c9ea7-255">在电子邮件中打开 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="c9ea7-256">在 Teams 中打开 URL 扫描 (点击预览) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="c9ea7-257">打开单击的 URL（包括指向文件的单击链接）实时扫描。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="c9ea7-258">等待 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="c9ea7-259">打开内部邮件的 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="c9ea7-260">跟踪与安全链接保护相关的用户单击 (我们未使用 _DoNotTrackUserClicks_ 参数，默认值为 $false，这意味着将跟踪用户单击) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="c9ea7-261">不允许用户单击访问原始 URL。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="c9ea7-262">有关语法和参数的详细信息，请参阅[New-SafeLinksPolicy。](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="c9ea7-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="c9ea7-263">步骤 2：使用 PowerShell 创建安全链接规则</span><span class="sxs-lookup"><span data-stu-id="c9ea7-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="c9ea7-264">若要创建安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="c9ea7-265">本示例创建一个名为"Contoso All"的安全链接规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="c9ea7-266">该规则与名为 Contoso All 的安全链接策略相关联。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="c9ea7-267">该规则适用于域中的所有 contoso.com 收件人。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="c9ea7-268">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="c9ea7-269">如果规则 (_Enabled_ 参数，则启用该规则，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="c9ea7-270">有关语法和参数的详细信息，请参阅[New-SafeLinksRule。](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="c9ea7-270">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="c9ea7-271">使用 PowerShell 查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="c9ea7-272">若要查看现有安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c9ea7-273">本示例返回所有安全链接策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="c9ea7-274">此示例返回名为 Contoso Executives 的安全链接策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="c9ea7-275">有关语法和参数的详细信息，请参阅 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="c9ea7-276">使用 PowerShell 查看安全链接规则</span><span class="sxs-lookup"><span data-stu-id="c9ea7-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="c9ea7-277">若要查看现有安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c9ea7-278">本示例返回所有安全链接规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="c9ea7-279">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="c9ea7-280">本示例返回名为 Contoso Executives 的安全链接规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="c9ea7-281">有关语法和参数的详细信息，请参阅 [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="c9ea7-282">使用 PowerShell 修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="c9ea7-283">如果 **Set-SafeLinksPolicy** cmdlet 没有 Name 参数，则 (在 PowerShell 中重命名安全链接) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c9ea7-284">在安全与合规中心内重命名安全链接&，只需重命名安全链接 _规则_。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="c9ea7-285">在 PowerShell 中修改安全链接策略的唯一额外注意事项是 _DoNotRewriteUrls_ 参数的可用语法 ("不重写以下 [URL"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 列表) ：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="c9ea7-286">若要添加将替换任何现有条目的值，请使用以下语法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="c9ea7-287">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="c9ea7-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="c9ea7-288">否则，创建安全链接策略时可用的设置与本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) 创建安全链接策略部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="c9ea7-289">若要修改安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c9ea7-290">有关语法和参数的详细信息，请参阅 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="c9ea7-291">使用 PowerShell 修改安全链接规则</span><span class="sxs-lookup"><span data-stu-id="c9ea7-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="c9ea7-292">在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c9ea7-293">若要启用或禁用现有安全链接规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="c9ea7-294">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) 创建安全链接规则一节中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="c9ea7-295">若要修改安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c9ea7-296">有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="c9ea7-297">使用 PowerShell 启用或禁用安全链接规则</span><span class="sxs-lookup"><span data-stu-id="c9ea7-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="c9ea7-298">在 PowerShell 中启用或禁用安全链接规则可启用或禁用整个安全链接策略 (安全链接规则以及分配的安全链接策略) 。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="c9ea7-299">若要在 PowerShell 中启用或禁用安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="c9ea7-300">本示例禁用名为"Marketing Department"的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c9ea7-301">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c9ea7-302">有关语法和参数的详细信息，请参阅[Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule)和[Disable-SafeLinksRule。](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="c9ea7-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="c9ea7-303">使用 PowerShell 设置安全链接规则的优先级</span><span class="sxs-lookup"><span data-stu-id="c9ea7-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="c9ea7-304">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="c9ea7-305">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="c9ea7-306">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="c9ea7-307">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="c9ea7-308">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c9ea7-309">若要在 PowerShell 中设置安全链接规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c9ea7-310">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-310">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="c9ea7-311">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-311">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="c9ea7-312">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-SafeLinksRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="c9ea7-313">有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="c9ea7-314">使用 PowerShell 删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="c9ea7-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="c9ea7-315">使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="c9ea7-316">若要在 PowerShell 中删除安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c9ea7-317">此示例删除名为 Marketing Department 的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c9ea7-318">有关语法和参数的详细信息，请参阅[Remove-SafeLinksPolicy。](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="c9ea7-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="c9ea7-319">使用 PowerShell 删除安全链接规则</span><span class="sxs-lookup"><span data-stu-id="c9ea7-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="c9ea7-320">使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="c9ea7-321">若要在 PowerShell 中删除安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="c9ea7-322">本示例删除名为"Marketing Department"的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c9ea7-323">有关语法和参数的详细信息，请参阅 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="c9ea7-324">若要验证安全链接是否正在扫描邮件，请检查可用的 Microsoft Defender for Office 365 报告。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="c9ea7-325">有关详细信息，请参阅[查看适用于 Office 365 的 Defender](view-reports-for-mdo.md)报告和使用安全与合规中心&[资源管理器。](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="c9ea7-325">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c9ea7-326">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="c9ea7-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="c9ea7-327">若要验证是否成功创建、修改或删除了安全链接策略，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="c9ea7-328">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全链接**。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="c9ea7-329">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="c9ea7-330">若要查看更多详细信息，请从列表中选择策略，然后查看飞出中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9ea7-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="c9ea7-331">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行 \<Name\> 以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="c9ea7-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```