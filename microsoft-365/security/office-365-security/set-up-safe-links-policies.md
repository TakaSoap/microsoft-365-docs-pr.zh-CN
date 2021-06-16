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
ms.openlocfilehash: fb157792f0f9e80e4a974b59aebaa2e1991c5d0b
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933115"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="31ec8-103">在 Microsoft Defender 保险箱设置链接策略Office 365</span><span class="sxs-lookup"><span data-stu-id="31ec8-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="31ec8-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="31ec8-104">**Applies to**</span></span>
- [<span data-ttu-id="31ec8-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="31ec8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="31ec8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31ec8-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="31ec8-107">本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="31ec8-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="31ec8-108">如果你是一位家庭用户，正在查找有关 Outlook 中的安全链接的信息，请参阅 Advanced [Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="31ec8-109">保险箱Microsoft [Defender for Office 365](defender-for-office-365.md)中的链接提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。</span><span class="sxs-lookup"><span data-stu-id="31ec8-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="31ec8-110">有关详细信息，请参阅 microsoft Defender 保险箱[中的链接Office 365。](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="31ec8-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="31ec8-111">链接策略没有内置或默认保险箱。</span><span class="sxs-lookup"><span data-stu-id="31ec8-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="31ec8-112">若要保险箱 URL 的链接扫描，需要创建一个或多个保险箱链接策略，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="31ec8-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="31ec8-113">在"链接"策略保险箱 **配置链接保护保险箱** 全局设置。</span><span class="sxs-lookup"><span data-stu-id="31ec8-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="31ec8-114">有关说明，请参阅[在 Microsoft Defender 中配置保险箱链接的全局Office 365。](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="31ec8-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="31ec8-115">管理员应考虑链接的不同配置保险箱设置。</span><span class="sxs-lookup"><span data-stu-id="31ec8-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="31ec8-116">可用选项之一是在"链接"中包括保险箱信息。</span><span class="sxs-lookup"><span data-stu-id="31ec8-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="31ec8-117">此功能使 *安全运营团队* 能够调查潜在用户泄露、采取纠正措施并限制代价高昂的泄露。</span><span class="sxs-lookup"><span data-stu-id="31ec8-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="31ec8-118">可以在 保险箱 Defender Microsoft 365或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置链接Exchange Online;独立 EOP PowerShell，适用于Exchange Online邮箱，但使用 Microsoft Defender for Office 365 加载项订阅的组织) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="31ec8-119">链接策略的基本保险箱包括：</span><span class="sxs-lookup"><span data-stu-id="31ec8-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="31ec8-120">安全链接策略：打开 保险箱 链接保护，启用实时 URL 扫描，指定是否在传递邮件之前等待实时扫描完成，启用内部邮件扫描，指定是否跟踪用户单击 URL，并指定是否允许用户单击原始 URL。</span><span class="sxs-lookup"><span data-stu-id="31ec8-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="31ec8-121">**安全链接规则**：指定策略应用于 (的优先级和收件人) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="31ec8-122">当你在 defender 门户中管理链接保险箱，这两个元素Microsoft 365并不明显：</span><span class="sxs-lookup"><span data-stu-id="31ec8-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="31ec8-123">创建链接保险箱策略时，实际上是同时对两者使用相同的名称创建安全链接规则和相关安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="31ec8-124">修改邮件保险箱策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="31ec8-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="31ec8-125">所有其他设置修改关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="31ec8-126">删除链接保险箱时，安全链接规则和相关的安全链接策略将被删除。</span><span class="sxs-lookup"><span data-stu-id="31ec8-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="31ec8-127">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="31ec8-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="31ec8-128">有关详细信息，请参阅本文稍后的使用[Exchange Online PowerShell 或独立 EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)配置 保险箱 链接策略部分。</span><span class="sxs-lookup"><span data-stu-id="31ec8-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="31ec8-129">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="31ec8-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="31ec8-130">访问 <https://security.microsoft.com/> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="31ec8-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="31ec8-131">若要直接转到"链接 **保险箱，** 请使用 <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="31ec8-132">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="31ec8-133">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="31ec8-134">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="31ec8-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="31ec8-135">若要创建、修改和删除 保险箱 链接策略，你需要是 Microsoft 365 Defender 门户中组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。  </span><span class="sxs-lookup"><span data-stu-id="31ec8-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="31ec8-136">若要对链接策略保险箱只读访问权限，您需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="31ec8-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="31ec8-137">有关详细信息，请参阅 Microsoft 365 Defender 门户[中的权限](permissions-in-the-security-and-compliance-center.md)和 Exchange Online 中[的权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="31ec8-138">将用户添加到 Microsoft 365 管理中心中的相应 Azure Active Directory 角色会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="31ec8-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="31ec8-139">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="31ec8-140">.</span><span class="sxs-lookup"><span data-stu-id="31ec8-140">.</span></span> <span data-ttu-id="31ec8-141">- **Exchange Online** 中的"仅查看组织管理"[](/Exchange/permissions-exo/permissions-exo#role-groups)角色组还授予对该功能的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="31ec8-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="31ec8-142">有关推荐的链接策略保险箱，请参阅保险箱[链接策略设置。](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="31ec8-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="31ec8-143">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="31ec8-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="31ec8-144">[新功能不断添加到 Microsoft Defender for Office 365。](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="31ec8-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="31ec8-145">添加新功能时，可能需要对现有"链接"策略保险箱调整。</span><span class="sxs-lookup"><span data-stu-id="31ec8-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="31ec8-146">使用 Microsoft 365 Defender 门户创建保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="31ec8-147">在 保险箱 Defender 门户中创建自定义Microsoft 365链接策略会同时创建安全链接规则和相关的安全链接策略，对二者使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="31ec8-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="31ec8-148">在 Microsoft 365 Defender 门户中，转到"策略&**规则**""威胁策略策略"部分 \>  \> 保险箱 \> **链接"。**</span><span class="sxs-lookup"><span data-stu-id="31ec8-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="31ec8-149">在 **"保险箱"** 页上，单击" ![ 创建"图标" ](../../media/m365-cc-sc-create-icon.png) **创建"。**</span><span class="sxs-lookup"><span data-stu-id="31ec8-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="31ec8-150">"**新建保险箱链接"策略** 向导将打开。</span><span class="sxs-lookup"><span data-stu-id="31ec8-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="31ec8-151">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="31ec8-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="31ec8-152">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="31ec8-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="31ec8-153">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="31ec8-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="31ec8-154">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="31ec8-155">在 **出现的"用户** 和域"页上，标识策略应用于以下收件人 (内部) ：</span><span class="sxs-lookup"><span data-stu-id="31ec8-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="31ec8-156">**用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="31ec8-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="31ec8-157">**组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="31ec8-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="31ec8-158">**域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="31ec8-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="31ec8-159">单击相应的框，开始键入值，然后从结果中选择所需的值。</span><span class="sxs-lookup"><span data-stu-id="31ec8-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="31ec8-160">根据需要多次重复此过程。</span><span class="sxs-lookup"><span data-stu-id="31ec8-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="31ec8-161">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="31ec8-161">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="31ec8-163">“删除”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-163">next to the value.</span></span>

   <span data-ttu-id="31ec8-164">对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="31ec8-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="31ec8-165">对于用户，请自行输入星号 (\*) 以查看所有可用值。</span><span class="sxs-lookup"><span data-stu-id="31ec8-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="31ec8-166">同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="31ec8-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="31ec8-167">不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="31ec8-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="31ec8-168">**排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。</span><span class="sxs-lookup"><span data-stu-id="31ec8-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="31ec8-169">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="31ec8-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="31ec8-170">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="31ec8-171">在出现的 **"** 保护设置"页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="31ec8-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="31ec8-172">**选择邮件中未知潜在** 恶意 URL 的操作：选择"打开"以保险箱电子邮件中的链接的链接保护。</span><span class="sxs-lookup"><span data-stu-id="31ec8-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="31ec8-173">如果启用此设置，则以下设置可用：</span><span class="sxs-lookup"><span data-stu-id="31ec8-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="31ec8-174">**对指向文件的可疑链接应用实时 URL** 扫描：选择此选项可启用电子邮件中链接的实时扫描。</span><span class="sxs-lookup"><span data-stu-id="31ec8-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="31ec8-175">如果打开此设置，则以下设置可用：</span><span class="sxs-lookup"><span data-stu-id="31ec8-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="31ec8-176">**等待 URL 扫描完成，然后再传递邮件**：选择此选项以等待实时 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="31ec8-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="31ec8-177">**Apply 保险箱 Links to email messages sent within the organization**： Select this option to apply the 保险箱 Links policy to messages between internal senders and internal recipients.</span><span class="sxs-lookup"><span data-stu-id="31ec8-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="31ec8-178">**Select the action for unknown or potentially malicious URLS within Microsoft Teams**： Select **On** to enable 保险箱 Links protection for links in Teams.</span><span class="sxs-lookup"><span data-stu-id="31ec8-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="31ec8-179">**Do not track user clicks**： Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span><span class="sxs-lookup"><span data-stu-id="31ec8-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="31ec8-180">**不允许用户单击到原始 URL：** 选择此选项可阻止用户单击到警告页面中 [的原始](safe-links.md#warning-pages-from-safe-links)URL。</span><span class="sxs-lookup"><span data-stu-id="31ec8-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="31ec8-181">**不要重写以下 URL：** 允许访问指定 URL，否则，链接保险箱阻止。</span><span class="sxs-lookup"><span data-stu-id="31ec8-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="31ec8-182">在框中，键入您需要的 URL 或值，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="31ec8-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="31ec8-183">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="31ec8-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="31ec8-184">若要删除现有条目，请单击</span><span class="sxs-lookup"><span data-stu-id="31ec8-184">To remove an existing entry, click</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="31ec8-186">项旁边。</span><span class="sxs-lookup"><span data-stu-id="31ec8-186">next to the entry.</span></span>

     <span data-ttu-id="31ec8-187">有关条目语法，请参阅 ["不重写以下 URL"列表的条目语法](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="31ec8-188">有关这些设置的详细信息，请参阅保险箱[电子邮件](safe-links.md#safe-links-settings-for-email-messages)的链接设置和保险箱[的链接Microsoft Teams。](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="31ec8-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="31ec8-189">有关"标准"和"严格"策略设置的建议值，请参阅保险箱[链接策略设置"](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="31ec8-190">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="31ec8-191">在 **出现的"** 通知"页上，为"如何通知用户？"选择下列值 **之一**：</span><span class="sxs-lookup"><span data-stu-id="31ec8-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="31ec8-192">**使用默认通知文本**</span><span class="sxs-lookup"><span data-stu-id="31ec8-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="31ec8-193">**使用自定义通知文本**：如果选择此值，将显示以下设置：</span><span class="sxs-lookup"><span data-stu-id="31ec8-193">**Use custom notification text**: If you select this value, the following settings appear:</span></span>
     - <span data-ttu-id="31ec8-194">**使用 Microsoft 翻译工具进行自动本地化**</span><span class="sxs-lookup"><span data-stu-id="31ec8-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="31ec8-195">**自定义通知文本**：在此框中输入自定义通知文本。</span><span class="sxs-lookup"><span data-stu-id="31ec8-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="31ec8-196">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="31ec8-197">在出现的“**审阅**”页面上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="31ec8-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="31ec8-198">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="31ec8-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="31ec8-199">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="31ec8-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="31ec8-200">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="31ec8-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="31ec8-201">在出现的确认页面上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="31ec8-202">使用 Microsoft 365 Defender 门户查看保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="31ec8-203">在 Microsoft 365 Defender 门户中，转到"策略&**规则**""威胁策略策略"部分 \>  \> 保险箱 \> **链接"。**</span><span class="sxs-lookup"><span data-stu-id="31ec8-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="31ec8-204">在保险箱 **链接"** 页上，以下属性显示在"链接保险箱列表中：</span><span class="sxs-lookup"><span data-stu-id="31ec8-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="31ec8-205">**名称**</span><span class="sxs-lookup"><span data-stu-id="31ec8-205">**Name**</span></span>
   - <span data-ttu-id="31ec8-206">**状态**</span><span class="sxs-lookup"><span data-stu-id="31ec8-206">**Status**</span></span>
   - <span data-ttu-id="31ec8-207">**优先级**</span><span class="sxs-lookup"><span data-stu-id="31ec8-207">**Priority**</span></span>

3. <span data-ttu-id="31ec8-208">当您通过单击该名称选择策略时，策略设置将显示在一个飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="31ec8-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="31ec8-209">使用 Microsoft 365 Defender 门户修改保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="31ec8-210">在 Microsoft 365 Defender 门户中，转到"策略&**规则**""威胁策略策略"部分 \>  \> 保险箱 \> **链接"。**</span><span class="sxs-lookup"><span data-stu-id="31ec8-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="31ec8-211">在 **"保险箱链接**"页上，单击该名称从列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="31ec8-212">在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="31ec8-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="31ec8-213">有关设置详细信息，请参阅本文前面的使用 Microsoft 365 Defender 门户[创建保险箱链接](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)策略部分。</span><span class="sxs-lookup"><span data-stu-id="31ec8-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="31ec8-214">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="31ec8-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="31ec8-215">启用或禁用保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="31ec8-216">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **Policies** section \> **保险箱 Links**.</span><span class="sxs-lookup"><span data-stu-id="31ec8-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="31ec8-217">在 **"保险箱链接**"页上，单击该名称从列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="31ec8-218">在出现的策略详细信息浮出控件顶部，你将看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="31ec8-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="31ec8-219">**策略关闭**：若要打开策略，请单击![“打开”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="31ec8-220">**策略打开**：若要关闭策略，请单击![“关闭”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="31ec8-221">在出现的确认对话框中，单击“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="31ec8-222">单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="31ec8-223">返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="31ec8-224">设置链接保险箱的优先级</span><span class="sxs-lookup"><span data-stu-id="31ec8-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="31ec8-225">默认情况下，保险箱链接的优先级基于它们在 (中的创建顺序，而新策略的优先级低于旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="31ec8-226">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="31ec8-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="31ec8-227">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="31ec8-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="31ec8-228">若要更改策略的优先级，请单击策略属性中的“**提高优先级**”或“**降低优先级**”（不能直接修改 Microsoft 365 Defender 门户中的“**优先级**”数字）。</span><span class="sxs-lookup"><span data-stu-id="31ec8-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="31ec8-229">只有当你有多个策略时，更改策略的优先级才有意义。</span><span class="sxs-lookup"><span data-stu-id="31ec8-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="31ec8-230">**注意**：</span><span class="sxs-lookup"><span data-stu-id="31ec8-230">**Note**:</span></span>

- <span data-ttu-id="31ec8-231">在 Microsoft 365 Defender 门户中，你只能在创建后更改保险箱链接策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="31ec8-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="31ec8-232">在 PowerShell 中，您可以在创建安全链接规则集时替代默认优先级 (这可能会影响现有规则或规则) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="31ec8-233">保险箱按照链接策略的显示顺序处理 (优先级值为 0 时) 。 </span><span class="sxs-lookup"><span data-stu-id="31ec8-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="31ec8-234">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="31ec8-235">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **Policies** section \> **保险箱 Links**.</span><span class="sxs-lookup"><span data-stu-id="31ec8-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="31ec8-236">在 **"保险箱链接**"页上，单击该名称从列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="31ec8-237">在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：</span><span class="sxs-lookup"><span data-stu-id="31ec8-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="31ec8-238">优先级值为 **0** **的策略** 只有"**减少优先级"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="31ec8-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="31ec8-239">优先级值最低的策略 (例如 **，3**) 只有"增加优先级 **"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="31ec8-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="31ec8-240">如果你有三个或多个策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 选项。</span><span class="sxs-lookup"><span data-stu-id="31ec8-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="31ec8-241">单击![“提高优先级”图标](../../media/m365-cc-sc-increase-icon.png)“**提高优先级**”或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png)“**降低优先级**”以更改“**优先级**”值。</span><span class="sxs-lookup"><span data-stu-id="31ec8-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="31ec8-242">完成后，单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="31ec8-243">使用 Microsoft 365 Defender 门户删除保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="31ec8-244">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** Threat \> **policies** \> **Policies** section \> **保险箱 Links**.</span><span class="sxs-lookup"><span data-stu-id="31ec8-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="31ec8-245">在 **"保险箱链接**"页上，单击该名称从列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="31ec8-246">在出现的策略详细信息浮出控件顶部，单击![“更多操作”图标](../../media/m365-cc-sc-more-actions-icon.png)“**更多操作**”\> ![“删除策略”图标](../../media/m365-cc-sc-delete-icon.png)“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="31ec8-247">在出现的确认对话框中，单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="31ec8-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="31ec8-248">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置保险箱链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="31ec8-249">如前所述，链接保险箱由安全链接策略和安全链接规则组成。</span><span class="sxs-lookup"><span data-stu-id="31ec8-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="31ec8-250">在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="31ec8-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="31ec8-251">您可以使用 **\* -SafeLinksPolicy** cmdlet 管理安全链接策略，使用 **\* -SafeLinksRule** cmdlet 管理安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="31ec8-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="31ec8-252">在 PowerShell 中，首先创建安全链接策略，然后创建安全链接规则，以标识该规则应用于的策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="31ec8-253">在 PowerShell 中，分别修改安全链接策略和安全链接规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="31ec8-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="31ec8-254">从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="31ec8-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="31ec8-255">使用 PowerShell 创建链接保险箱策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="31ec8-256">在 PowerShell 保险箱链接策略的过程包含两个步骤：</span><span class="sxs-lookup"><span data-stu-id="31ec8-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="31ec8-257">创建安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="31ec8-258">创建安全链接规则，该规则指定应用该规则的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="31ec8-259">你可以创建新的安全链接规则，并为其分配现有的未关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="31ec8-260">安全链接规则不能与多个安全链接策略关联。</span><span class="sxs-lookup"><span data-stu-id="31ec8-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="31ec8-261">可以在 PowerShell 中的新安全链接策略上配置以下设置，这些设置在 Microsoft 365 Defender 门户中不可用，除非创建策略：</span><span class="sxs-lookup"><span data-stu-id="31ec8-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="31ec8-262">在 `$false` **New-SafeLinksRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="31ec8-263">在 _\<Number\>_ **New-SafeLinksRule** cmdlet cmdlet (中) 策略的优先级) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="31ec8-264">在将策略分配给安全链接规则之前，在 PowerShell 中新建的安全链接策略Microsoft 365 Defender 门户中不可见。</span><span class="sxs-lookup"><span data-stu-id="31ec8-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="31ec8-265">步骤 1：使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="31ec8-266">若要创建安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="31ec8-267">有关要用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅"不要重写以下 [URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)列表的条目语法。</span><span class="sxs-lookup"><span data-stu-id="31ec8-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="31ec8-268">有关在使用 **Set-SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于 _DoNotRewriteUrls_ 参数的其他语法，请参阅本文稍后的使用 [PowerShell](#use-powershell-to-modify-safe-links-policies)修改安全链接策略一节。</span><span class="sxs-lookup"><span data-stu-id="31ec8-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="31ec8-269">此示例创建一个名为 Contoso All 的安全链接策略，并具有以下值：</span><span class="sxs-lookup"><span data-stu-id="31ec8-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="31ec8-270">在电子邮件中打开 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="31ec8-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="31ec8-271">在"点击点击预览Teams (启用 URL) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="31ec8-272">打开单击的 URL（包括指向文件的单击链接）实时扫描。</span><span class="sxs-lookup"><span data-stu-id="31ec8-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="31ec8-273">等待 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="31ec8-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="31ec8-274">打开内部邮件的 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="31ec8-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="31ec8-275">跟踪与 保险箱 链接保护相关的用户单击 (我们使用的不是 _DoNotTrackUserClicks_ 参数，默认值是 $false，这意味着用户单击会) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="31ec8-276">不允许用户单击访问原始 URL。</span><span class="sxs-lookup"><span data-stu-id="31ec8-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="31ec8-277">有关语法和参数的详细信息，请参阅[New-SafeLinksPolicy。](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="31ec8-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="31ec8-278">步骤 2：使用 PowerShell 创建安全链接规则</span><span class="sxs-lookup"><span data-stu-id="31ec8-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="31ec8-279">若要创建安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="31ec8-280">本示例创建一个名为"Contoso All"的安全链接规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="31ec8-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="31ec8-281">该规则与名为 Contoso All 的安全链接策略相关联。</span><span class="sxs-lookup"><span data-stu-id="31ec8-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="31ec8-282">该规则适用于域中的所有 contoso.com 收件人。</span><span class="sxs-lookup"><span data-stu-id="31ec8-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="31ec8-283">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="31ec8-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="31ec8-284">如果规则 (_Enabled_ 参数，则启用该规则，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="31ec8-285">有关语法和参数的详细信息，请参阅[New-SafeLinksRule。](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="31ec8-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="31ec8-286">使用 PowerShell 查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="31ec8-287">若要查看现有安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="31ec8-288">本示例返回所有安全链接策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="31ec8-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="31ec8-289">此示例返回名为 Contoso Executives 的安全链接策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="31ec8-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="31ec8-290">有关语法和参数的详细信息，请参阅 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="31ec8-291">使用 PowerShell 查看安全链接规则</span><span class="sxs-lookup"><span data-stu-id="31ec8-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="31ec8-292">若要查看现有安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="31ec8-293">本示例返回所有安全链接规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="31ec8-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="31ec8-294">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="31ec8-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="31ec8-295">本示例返回名为 Contoso Executives 的安全链接规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="31ec8-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="31ec8-296">有关语法和参数的详细信息，请参阅 [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="31ec8-297">使用 PowerShell 修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="31ec8-298">如果 **Set-SafeLinksPolicy** cmdlet 没有 Name 参数，则 (在 PowerShell 中重命名安全链接) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="31ec8-299">当你在 defender 保险箱中重命名Microsoft 365链接策略时，你仅重命名安全链接 _规则_。</span><span class="sxs-lookup"><span data-stu-id="31ec8-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="31ec8-300">在 PowerShell 中修改安全链接策略的唯一额外注意事项是 _DoNotRewriteUrls_ 参数的可用语法 ("不重写以下 [URL"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 列表) ：</span><span class="sxs-lookup"><span data-stu-id="31ec8-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="31ec8-301">若要添加将替换任何现有条目的值，请使用以下语法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="31ec8-302">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="31ec8-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="31ec8-303">否则，创建安全链接策略时可用的设置与本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) 创建安全链接策略部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="31ec8-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="31ec8-304">若要修改安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="31ec8-305">有关语法和参数的详细信息，请参阅 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="31ec8-306">使用 PowerShell 修改安全链接规则</span><span class="sxs-lookup"><span data-stu-id="31ec8-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="31ec8-307">在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="31ec8-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="31ec8-308">若要启用或禁用现有安全链接规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="31ec8-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="31ec8-309">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) 创建安全链接规则一节中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="31ec8-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="31ec8-310">若要修改安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="31ec8-311">有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="31ec8-312">使用 PowerShell 启用或禁用安全链接规则</span><span class="sxs-lookup"><span data-stu-id="31ec8-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="31ec8-313">在 PowerShell 中启用或禁用安全链接规则可启用或禁用整个 保险箱 链接策略 (安全链接规则以及分配的安全链接策略) 。</span><span class="sxs-lookup"><span data-stu-id="31ec8-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="31ec8-314">若要在 PowerShell 中启用或禁用安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="31ec8-315">本示例禁用名为"Marketing Department"的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="31ec8-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="31ec8-316">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="31ec8-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="31ec8-317">有关语法和参数的详细信息，请参阅[Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule)和[Disable-SafeLinksRule。](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="31ec8-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="31ec8-318">使用 PowerShell 设置安全链接规则的优先级</span><span class="sxs-lookup"><span data-stu-id="31ec8-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="31ec8-p131">可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。</span><span class="sxs-lookup"><span data-stu-id="31ec8-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="31ec8-324">若要在 PowerShell 中设置安全链接规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="31ec8-p132">此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。</span><span class="sxs-lookup"><span data-stu-id="31ec8-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="31ec8-327">若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-SafeLinksRule** cmdlet 上的 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="31ec8-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="31ec8-328">有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="31ec8-329">使用 PowerShell 删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="31ec8-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="31ec8-330">使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="31ec8-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="31ec8-331">若要在 PowerShell 中删除安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="31ec8-332">此示例删除名为 Marketing Department 的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="31ec8-333">有关语法和参数的详细信息，请参阅[Remove-SafeLinksPolicy。](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="31ec8-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="31ec8-334">使用 PowerShell 删除安全链接规则</span><span class="sxs-lookup"><span data-stu-id="31ec8-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="31ec8-335">使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="31ec8-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="31ec8-336">若要在 PowerShell 中删除安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="31ec8-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="31ec8-337">本示例删除名为"Marketing Department"的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="31ec8-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="31ec8-338">有关语法和参数的详细信息，请参阅 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="31ec8-339">若要验证保险箱是否正在扫描邮件，请查看可用的 Microsoft Defender Office 365报告。</span><span class="sxs-lookup"><span data-stu-id="31ec8-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="31ec8-340">有关详细信息，请参阅查看[Defender for Office 365](view-reports-for-mdo.md)报告和使用 Microsoft 365 [Defender 门户中的资源管理器](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="31ec8-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="31ec8-341">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="31ec8-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="31ec8-342">若要验证是否成功创建、修改或删除了链接保险箱，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="31ec8-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="31ec8-343">在 Microsoft 365 Defender 门户中，转到"策略 **"&"** 威胁策略保险箱 \>  \> **链接"。**</span><span class="sxs-lookup"><span data-stu-id="31ec8-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="31ec8-344">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="31ec8-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="31ec8-345">若要查看更多详细信息，请从列表中选择策略，然后查看飞出中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="31ec8-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="31ec8-346">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：</span><span class="sxs-lookup"><span data-stu-id="31ec8-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
